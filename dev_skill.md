# dev_skill.md — LLM-8850 / Raspberry Pi 5 开发调试经验沉淀

这份文档把一次在 `rpi5` 上从“装驱动 → 跑通 Whisper / CosyVoice2（OpenAI API）→ 音色克隆（clone）→ 磁盘清理”的实际踩坑过程整理成可复用的 checklist，方便以后复现与排障。

## 0. 环境假设（本次实测）

- Host：Raspberry Pi 5（Debian bookworm，aarch64）
- 加速卡：LLM-8850（PCIe）
- 连接方式：`ssh rpi5` 免登；`sudo` 不需要密码
- 代理策略：
  - GitHub 需要代理：`127.0.0.1:7890`
  - HuggingFace 下载用 `hf-mirror.com`，并尽量不走代理（节省代理带宽）

> 下文示例以 `PROXY=http://127.0.0.1:7890` 为例；如果你的代理不同，替换即可。

## 1. 网络/代理：两套“按命令生效”的环境变量

不要全局写 `~/.gitconfig` 的 `http.proxy`，否则很容易把本来不需要代理的下载也绕进代理里（尤其是大模型文件）。

### 1.1 GitHub（走代理）

```bash
PROXY=http://127.0.0.1:7890
env http_proxy="$PROXY" https_proxy="$PROXY" all_proxy="$PROXY" \
  git clone https://github.com/xxx/yyy.git
```

### 1.2 HuggingFace（不走代理，走 hf-mirror.com）

```bash
env no_proxy='*' http_proxy= https_proxy= all_proxy= HTTP_PROXY= HTTPS_PROXY= ALL_PROXY= \
  curl -L -o /tmp/file.bin 'https://hf-mirror.com/<org>/<repo>/resolve/main/<path>'
```

经验结论：

- `hf-mirror.com` 上用 `curl .../resolve/main/...` 直链下载，比 `git lfs` 稳定（见下文“LFS 坑”）。
- 明确清空 `http_proxy/https_proxy/all_proxy`，再加 `no_proxy='*'`，基本能确保“不走代理”。

## 2. 驱动/设备排障：`/dev/axcl_host` 不存在

典型报错（来自 `axcl-smi` 或服务日志）：

```text
axcl init fail, ret = 0x8030010b
open /dev/axcl_host fail, errno: 2 No such file or directory
```

优先按这个顺序排：

1) PCIe 是否识别到卡：

```bash
lspci | grep -Ei "Axera|0650" || true
```

2) 驱动（DKMS）是否给当前内核编出来了（尤其是你升级过内核后）：

```bash
uname -r
dkms status | grep -i axcl || true
```

3) 重新为当前内核编译并加载模块，然后确认节点创建：

```bash
sudo /usr/sbin/dkms autoinstall -k "$(uname -r)"
sudo modprobe axcl_host
ls -l /dev/axcl_host
axcl-smi
```

如果还是不行，再考虑断电重插、检查供电、或重装 `axclhost` 包。

## 3. APT 源与核心包（axclhost + llm8850）

经验结论：`axclhost` 源解决“驱动与基础工具”，`bookworm llm8850` 源解决“StackFlow 的模型/服务（llm-*)”。

```bash
sudo wget -qO /etc/apt/keyrings/StackFlow.gpg https://repo.llm.m5stack.com/m5stack-apt-repo/key/StackFlow.gpg

echo 'deb [signed-by=/etc/apt/keyrings/StackFlow.gpg] https://repo.llm.m5stack.com/m5stack-apt-repo axclhost main' \
  | sudo tee /etc/apt/sources.list.d/axclhost.list

echo 'deb [signed-by=/etc/apt/keyrings/StackFlow.gpg] https://repo.llm.m5stack.com/m5stack-apt-repo bookworm llm8850' \
  | sudo tee /etc/apt/sources.list.d/llm8850.list

sudo apt update
```

## 4. StackFlow 服务：快速自检与 500 排障

### 4.1 服务自检（最短路径）

```bash
systemctl is-active llm-sys llm-cosy-voice llm-openai-api
curl -s http://127.0.0.1:8000/v1/models
```

期望能看到类似：

```json
{"data":[{"id":"CosyVoice2-0.5B-axcl", ...}],"object":"list"}
```

### 4.2 CosyVoice2 TTS 请求要显式写 `voice`

一次实测中，没写 `voice` 会触发 500（服务端返回空 body，客户端解析 JSON 报 `Expecting value` 之类）。

推荐请求模板：

```bash
curl -X POST http://127.0.0.1:8000/v1/audio/speech \
  -H "Content-Type: application/json" \
  -d '{"model":"CosyVoice2-0.5B-axcl","voice":"prompt_data","response_format":"wav","input":"你好，这是一次 TTS 测试。"}' \
  -o /tmp/cosyvoice2_test.wav
```

### 4.3 一键“救火重启”

```bash
sudo systemctl restart llm-sys llm-cosy-voice llm-openai-api
```

配套看日志：

```bash
journalctl -u llm-openai-api -n 200 --no-pager
journalctl -u llm-cosy-voice -n 200 --no-pager
```

## 5. Whisper（`whisper.axcl`）：什么是“编译运行”

这里的“编译运行”指：

1) 拉源码（含子模块/依赖）  
2) 在本机（rpi5）编译生成可执行文件与依赖库  
3) 按项目约定把 `.axmodel` 等模型文件放到运行目录  
4) 在正确的工作目录（CWD）启动可执行文件

典型流程（示意）：

```bash
cd ~/rsp/whisper.axcl
./build.sh
cd install
./whisper -w ../demo.wav
```

### 5.1 `.axmodel` 从哪里来：HF 的 `M5Stack/whisper-small-axmodel`

离线文档里常见没写清“模型文件来源”，实测可直接从 HF（建议镜像）下载到 `install/models/`。

示例（用 `hf-mirror.com`，不走代理）：

```bash
cd ~/rsp/whisper.axcl/install/models
env no_proxy='*' http_proxy= https_proxy= all_proxy= \
  curl -L -O 'https://hf-mirror.com/M5Stack/whisper-small-axmodel/resolve/main/whisper-small.axmodel'
```

### 5.2 运行目录（CWD）很关键

实测 `whisper` 可执行文件会按“当前目录”找 `./models/...`，以及可能依赖一些同目录的配置/资源（例如 `t2s.json` 等）。

经验做法：始终从 `install/` 目录运行；缺什么就把资源补到 `install/`（或按项目说明放到相对路径）。

### 5.3 模型重复两份的问题（本次真的遇到过）

Whisper 项目里容易出现两份模型目录：

- `~/rsp/whisper.axcl/models`（源码目录下）
- `~/rsp/whisper.axcl/install/models`（运行目录下）

实际运行只需要 `install/models` 一份；另一份是“误下载/误拷贝”导致的浪费空间。

排查命令：

```bash
du -sh ~/rsp/whisper.axcl/models ~/rsp/whisper.axcl/install/models 2>/dev/null
```

## 6. CosyVoice2 音色克隆（`CosyVoice2-scripts`）的几个大坑

### 6.1 `git lfs` 在 hf-mirror 上可能失败：别用它拉大文件

现象：`git lfs pull` 会去访问类似 `cas-bridge.xethub.hf-mirror.org` 的域名，DNS/网络环境不一致时会失败。

更稳的做法：

- 仓库先跳过 LFS：

```bash
GIT_LFS_SKIP_SMUDGE=1 git clone https://hf-mirror.com/FunAudioLLM/CosyVoice2.git CosyVoice2-scripts
```

- 需要的 LFS 大文件用 `curl .../resolve/main/...` 精准补齐

### 6.2 不是只有 `asset/zh_woman1.wav`：还缺两个前端 ONNX（很大）

`scripts/process_prompt.py` 生成 prompt data 时，除了示例音频，还需要：

- `frontend-onnx/campplus.onnx`（~27MB）
- `frontend-onnx/speech_tokenizer_v2.onnx`（~500MB）

建议用镜像直链下载（不走代理）：

```bash
cd ~/rsp/CosyVoice2-scripts
env no_proxy='*' http_proxy= https_proxy= all_proxy= \
  curl -L -o asset/zh_woman1.wav \
  'https://hf-mirror.com/FunAudioLLM/CosyVoice2/resolve/main/asset/zh_woman1.wav'

env no_proxy='*' http_proxy= https_proxy= all_proxy= \
  curl -L -o frontend-onnx/campplus.onnx \
  'https://hf-mirror.com/FunAudioLLM/CosyVoice2/resolve/main/frontend-onnx/campplus.onnx'

env no_proxy='*' http_proxy= https_proxy= all_proxy= \
  curl -L -o frontend-onnx/speech_tokenizer_v2.onnx \
  'https://hf-mirror.com/FunAudioLLM/CosyVoice2/resolve/main/frontend-onnx/speech_tokenizer_v2.onnx'
```

### 6.3 submodule 必须初始化（`wetext`）

否则会报 `tagger.fst` 一类资源不存在。

```bash
cd ~/rsp/CosyVoice2-scripts
git submodule update --init --recursive
```

### 6.4 pip 被全局配置坑到：hash mismatch（piwheels）

如果系统/用户的 pip 配置混了 `piwheels`，近期实测装 `transformers`、`modelscope` 可能出现 hash mismatch。

最稳规避：对这次安装临时禁用全局 pip 配置，并指定一个镜像源：

```bash
cd ~/rsp/CosyVoice2-scripts
PIP_CONFIG_FILE=/dev/null pip install --no-cache-dir --index-url https://mirrors.cloud.tencent.com/pypi/simple -r requirements.txt
```

### 6.5 生成 voice 并接入 CosyVoice2-0.5B-axcl

生成 prompt data（示例）：

```bash
cd ~/rsp/CosyVoice2-scripts
python3 scripts/process_prompt.py \
  --input_wav asset/zh_woman1.wav \
  --input_text '欢迎使用 CosyVoice2。' \
  --output zh_woman1
```

接入 StackFlow 的 CosyVoice2 模型目录（约定在 `/opt/m5stack/data`）：

```bash
sudo cp -a zh_woman1 /opt/m5stack/data/CosyVoice2-0.5B-axcl/zh_woman1
sudo systemctl restart llm-sys llm-openai-api
```

然后用 OpenAI API 测试：

```bash
curl -X POST http://127.0.0.1:8000/v1/audio/speech \
  -H "Content-Type: application/json" \
  -d '{"model":"CosyVoice2-0.5B-axcl","voice":"zh_woman1","response_format":"wav","input":"这是克隆音色测试。"}' \
  -o /tmp/zh_woman1_test.wav
```

## 7. 磁盘与日志：能省多少、优先删什么（本次实测数据）

本次在 rpi5 上的关键目录体积（2026-03-01 实测）：

- `/opt/m5stack/data/CosyVoice2-0.5B-axcl`：约 **1.4G**（推理必需，不建议删）
- `~/rsp/whisper.axcl`：约 **747M**（含源码/产物/模型；可按需清理源码缓存，但不建议动 `install/` 里的运行必需文件）
- `~/rsp/CosyVoice2-scripts`：约 **2.1G**（主要是“克隆工具链 + ONNX + Python 依赖”，**clone 完就可以删**）
- `~/.cache/pip`：约 **191M**（可删）
- `journalctl`：约 **99M**（可控）

常用清理命令：

```bash
# 1) pip 缓存
rm -rf ~/.cache/pip

# 2) systemd journal
sudo journalctl --vacuum-size=100M

# 3) APT 缓存 + 无用依赖
sudo apt clean
sudo apt autoremove --purge -y

# 4) 可选：删除克隆工具链（如果你已经把 voice 拷贝进 /opt/m5stack/data 了）
rm -rf ~/rsp/CosyVoice2-scripts
```

## 8. 一页纸排障流程（建议收藏）

1) `lspci` 能看到 `Axera ... 0650`  
2) `ls -l /dev/axcl_host` 存在；`axcl-smi` 正常  
3) `systemctl is-active llm-sys llm-openai-api` 为 `active`  
4) `curl http://127.0.0.1:8000/v1/models` 有 `CosyVoice2-0.5B-axcl`  
5) TTS 请求必须带 `voice`；500 先重启三件套再看日志  
6) 大文件下载优先 `hf-mirror.com/resolve/main/...` 直链，避免 `git lfs` 不稳定  
7) 空间不够优先删 `~/rsp/CosyVoice2-scripts`、`~/.cache/pip`、压缩 `journalctl`

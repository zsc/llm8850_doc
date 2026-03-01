# LLM-8850 Card（M5Stack AI 加速卡）离线整理

本仓库保存了从 M5Stack Developer Center 抓取的 LLM-8850 Card 相关页面离线 Markdown（见 `offline/`）。原始抓取内容包含大量站点导航/重复行，不便阅读；本 `README.md` 将**系统级信息**（硬件安装、Raspberry Pi/Windows 环境与驱动、常用工具、模型/应用的典型运行方式、基准与 FAQ）重新整理，便于离线快速查阅。

> 原始来源：每个 `offline/*.md` 文件顶部均包含 `来源: ...`。

## 目录

- [你在用的是什么](#你在用的是什么)
- [目录结构](#目录结构)
- [Raspberry Pi 5：硬件安装](#raspberry-pi-5硬件安装)
- [Raspberry Pi 5：环境与驱动安装（AXCL Host）](#raspberry-pi-5环境与驱动安装axcl-host)
- [Windows：环境与驱动安装](#windows环境与驱动安装)
- [常用工具与命令](#常用工具与命令)
  - [axcl-smi（设备管理/诊断）](#axcl-smi设备管理诊断)
  - [AXCL FFmpeg（硬解码/转码）](#axcl-ffmpeg硬解码转码)
  - [Docker（可选）](#docker可选)
  - [Git LFS（可选）](#git-lfs可选)
- [常见运行模式（模型/应用）](#常见运行模式模型应用)
  - [视觉模型快速体验（axcl_demo.zip）](#视觉模型快速体验axcl_demozip)
  - [Whisper（whisper.axcl）离线语音转文字](#whisperwhisperaxcl离线语音转文字)
  - [OpenAI 兼容 API（文本对话）](#openai-兼容-api文本对话)
  - [OpenAI 兼容 API（CosyVoice2 文本转语音）](#openai-兼容-apicosyvoice2-文本转语音)
- [NPU 示例与工具链](#npu-示例与工具链)
- [NPU Benchmark（性能参考）](#npu-benchmark性能参考)
- [FAQ（常见问题）](#faq常见问题)
- [离线文档索引（按主题）](#离线文档索引按主题)

## 你在用的是什么

- **LLM-8850 Card**：通过 PCIe 连接到 Host（常见为 Raspberry Pi 5）的 AI 加速卡。
- **识别特征**：在 Raspberry Pi 5 上可通过 `lspci` 看到 `Axera Semiconductor Co., Ltd Device 0650`（示例见下文）。
- **驱动/运行时**：文档中以 `axclhost`（AXCL Host 侧驱动包）为核心，安装后可使用 `axcl-smi` 等工具查看设备信息与状态。

## 目录结构

- `README.md`：本整理文档（你正在读的这个）。
- `offline/`：从网页直接抓取的原始 Markdown（包含导航/重复，必要时可用于对照原文）。

## Raspberry Pi 5：硬件安装

> 安装前务必断电：**不可带电插拔**。

在树莓派 5 上安装 LLM-8850 加速卡时，官方文档给出了两种常见方案：

1) 使用 **M5Stack LLM-8850 PiHat** 扩展板  
   - 供电建议：通过转接板的 **PD 供电接口**为整机供电  
   - 供电能力：**> 9V@3A（27W）**

2) 使用树莓派官方 **M.2 HAT+** 扩展板  
   - 供电建议：推荐 **DC 5V@3A** 的开关电源（**非 PD 协议**）  
   - 说明：若使用 PD 电源，可能因协议协商导致无法输出最大功率，从而引发异常

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_hardware_install.md`

## Raspberry Pi 5：环境与驱动安装（AXCL Host）

### 1) 更新系统与 EEPROM（树莓派 5 推荐）

```bash
sudo apt update && sudo apt full-upgrade

sudo rpi-eeprom-update
```

如果你看到 EEPROM 日期**早于 2023-12-06**：

```bash
sudo raspi-config
# Advanced Options > Bootloader Version > Latest

sudo rpi-eeprom-update -a
sudo reboot
```

### 2) 检查 PCIe 设备是否识别

```bash
lspci
```

示例输出（关键行）：

```text
Multimedia video controller: Axera Semiconductor Co., Ltd Device 0650 (rev 01)
```

### 3) 安装驱动与运行库（axclhost）

> 提示：文档提示驱动安装可能依赖编译环境（如 `gcc`/`make`/`patch`/`linux-header-$(uname -r)` 等），请提前准备或确保安装时网络可用。

添加软件源并安装：

```bash
sudo wget -qO /etc/apt/keyrings/StackFlow.gpg https://repo.llm.m5stack.com/m5stack-apt-repo/key/StackFlow.gpg
echo 'deb [signed-by=/etc/apt/keyrings/StackFlow.gpg] https://repo.llm.m5stack.com/m5stack-apt-repo axclhost main' \
  | sudo tee /etc/apt/sources.list.d/axclhost.list

sudo apt update
sudo apt install -y dkms axclhost
```

安装完成后，为了让新安装的可执行程序立即可用，更新终端环境：

```bash
source /etc/profile
```

### 4) 用 axcl-smi 验证驱动与设备状态

```bash
axcl-smi
```

能看到设备列表/固件/驱动版本/CMM 使用情况即为正常（示例见 `AXCL-SMI` 小节）。

### 5) 驱动卸载

```bash
sudo apt remove axclhost
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_software_install.md`

## Windows：环境与驱动安装

### 1) 系统要求

- 仅支持 **Windows 10 64 位（22H2）**、**Windows 11 64 位（>= 23H2）**
- 建议关闭系统睡眠（睡眠改为“从不”）
- 建议关闭安全防护软件（避免误杀）
- 安装 **Visual Studio 2022 运行时库** `VC_redist.x64.exe`（需要管理员权限）

### 2) 识别设备

关机断电插卡后开机：

- `Win+R` → `devmgmt.msc`（设备管理器）
- “其他设备”里会出现未知“多媒体视频控制器”
- 属性中可确认 `VENDOR` 为 `1F4B`

### 3) 安装/卸载驱动

- 以管理员权限运行发布包：`axcl_win64_setup_Vx.x.x_yyyymmdd_NOxxxx.exe`
  - 会自动安装：驱动、DLL（含导入库）、可执行程序（如 `axcl-smi.exe`）、示例源码
  - 建议全选安装，注意安装路径（包含头文件、动态库、卸载程序等）
  - 安装完成后重启电脑
- 重启后设备管理器“系统设备”中应出现：`Axera NPU Accelerator Device`
- 卸载：进入安装路径 `AXCL`，运行 `uninst.exe`

### 4) 编译 SDK/示例（可选）

文档给出的依赖：

- Visual Studio Community 2026（组件：使用 C++ 的桌面开发）
- CMake（> 3.20）
- ninja（示例推荐 v1.31.1，加入系统 Path）
- Python3（可用 conda）

编译脚本与运行示例：

```bat
:: 在 AXCL\axcl\scripts
build_win64.cmd

:: 编译产物目录执行（模型路径请自行替换）
axcl_run_model.exe -m yolo11s.axmodel -r 10
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_windows_install.md`

## 常用工具与命令

### axcl-smi（设备管理/诊断）

用途（文档列举）：

- 设备型号/固件/驱动版本
- CPU/NPU 利用率
- 内存使用、CMM（媒体内存）使用
- SoC 结温
- 设备侧日志下载、执行设备侧 shell、重启设备等

常用示例：

```bash
# 设备总览（最常用）
axcl-smi

# 查询 CMM 使用
axcl-smi info --cmm -d 0

# 查询 VENC 模块 proc（其他模块同理：vdec/ivps/ive/...）
axcl-smi proc --venc -d 0

# 设置设备 CPU 频率（仅支持：1200000/1400000/1700000）
axcl-smi set -f 1200000 -d 0

# 下载日志（默认建议 -1：全部日志）
axcl-smi log -t -1 -d 0

# 执行设备侧命令（包含特殊字符时建议用引号包起来）
axcl-smi sh "ls -l" -d 0

# 重启设备（会提示确认）
axcl-smi reboot -d 0
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_axcl_smi.md`

### AXCL FFmpeg（硬解码/转码）

文档给出的路径约定：

- 动态库：`/usr/lib/axcl/ffmpeg`
- 可执行程序：`/usr/bin/axcl/ffmpeg`

运行前需设置动态库搜索路径：

```bash
export LD_LIBRARY_PATH="/usr/lib/axcl/ffmpeg:$LD_LIBRARY_PATH"
```

示例（h264 硬解码为 yuv）：

```bash
/usr/bin/axcl/ffmpeg/ffmpeg -c:v h264_axdec -i input.mp4 -f rawvideo -pix_fmt yuv420p output.yuv
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_ffmpeg.md`

### Docker（可选）

Raspberry Pi 上按文档安装 Docker（Debian 系）：

```bash
sudo apt update
sudo apt install -y ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings

sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian $(. /etc/os-release && echo \"$VERSION_CODENAME\") stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo usermod -aG docker $USER
newgrp docker
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_docker.md`

### Git LFS（可选）

大量模型仓库使用 Git LFS：

```bash
sudo apt update
sudo apt install -y git-lfs
git lfs install
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_git_lfs.md`

## 常见运行模式（模型/应用）

不同模型/应用的交付形式不完全一致，但文档中常见模式大致分为三类：

1) **单个整合包（zip）**：下载解压后直接运行二进制（常见于视觉 demo）。  
2) **Hugging Face 仓库（可能含 LFS）**：`git clone` 拉取后，运行脚本/启动 Python 服务/启动二进制。  
3) **StackFlow APT 包 + systemd 服务**：`apt install` 安装模型与服务，使用 OpenAI 兼容 API 调用。

### 视觉模型快速体验（axcl_demo.zip）

以 YOLO11 文档为例，先获取整合包：

```bash
wget https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/linux/ax8850_card/axcl_demo.zip
unzip axcl_demo.zip
```

随后在同一目录下运行不同 demo（不同模型对应不同可执行文件与 `.axmodel`）：

```bash
# 目标检测：YOLO11x
./axcl_demo/axcl_yolo11 -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x.axmodel

# 深度估计：Depth Anything V2（文档提示复用同一整合包）
./axcl_demo/axcl_depth_anything -m axcl_demo/depth_anything_v2_vits_ax650.axmodel -i axcl_demo/ssd_horse.jpg
```

视觉模型参考文档：

- `offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_yolo11.md`
- `offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_yolo_world_v2.md`
- `offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_yolov7_face.md`
- `offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_depth_anything_v2.md`
- `offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_mixformer_v2.md`
- `offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_real_esrgan.md`
- `offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_superresolution.md`
- `offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_rife.md`

### Whisper（whisper.axcl）离线语音转文字

官方 Whisper 小节给了“编译 + 运行”的命令，但没有把 `.axmodel` 的来源说清楚：`whisper.axcl` 只是示例代码与可执行程序，**真正跑推理还需要下载预编译好的模型文件（`.axmodel`）**。

以 `whisper-small` 为例，预编译模型在 Hugging Face：`M5Stack/whisper-small-axmodel`（AX650 版本在 `ax650/` 目录）。下面是在 Raspberry Pi 5 上按文档跑通示例的一套可复用流程（包含你当前的网络约束：GitHub 走 `7890` 代理，Hugging Face 走 `hf-mirror.com` 且不占代理带宽）。

1) 获取源码（GitHub 走代理）

```bash
mkdir -p ~/rsp && cd ~/rsp
env http_proxy=http://127.0.0.1:7890 https_proxy=http://127.0.0.1:7890 \
  git clone --depth 1 https://github.com/ml-inory/whisper.axcl.git
```

2) 编译安装（得到 `install/whisper`）

```bash
cd ~/rsp/whisper.axcl
./build.sh
```

3) 下载预编译模型（Hugging Face 用 `hf-mirror.com`，禁用代理）

> 说明：有些网络环境下 `git lfs pull` 可能会卡在 LFS 域名解析/鉴权；此时直接用 `resolve/main/...` 下载最稳（`curl -L` 会自动跟随重定向）。

```bash
cd ~/rsp/whisper.axcl/install
mkdir -p models

env no_proxy='*' http_proxy= https_proxy= \
  curl -fL -o models/small-encoder.axmodel \
  'https://hf-mirror.com/M5Stack/whisper-small-axmodel/resolve/main/ax650/small-encoder.axmodel'

env no_proxy='*' http_proxy= https_proxy= \
  curl -fL -o models/small-decoder-main.axmodel \
  'https://hf-mirror.com/M5Stack/whisper-small-axmodel/resolve/main/ax650/small-decoder-main.axmodel'

env no_proxy='*' http_proxy= https_proxy= \
  curl -fL -o models/small-decoder-loop.axmodel \
  'https://hf-mirror.com/M5Stack/whisper-small-axmodel/resolve/main/ax650/small-decoder-loop.axmodel'

env no_proxy='*' http_proxy= https_proxy= \
  curl -fL -o models/small-positional_embedding.bin \
  'https://hf-mirror.com/M5Stack/whisper-small-axmodel/resolve/main/small-positional_embedding.bin'

env no_proxy='*' http_proxy= https_proxy= \
  curl -fL -o models/small-tokens.txt \
  'https://hf-mirror.com/M5Stack/whisper-small-axmodel/resolve/main/small-tokens.txt'
```

4) 准备运行时配置文件（否则会提示找不到 `t2s.json`）

`whisper` 在运行时会加载 OpenCC 的 `t2s.json`（繁转简配置），并且它按 **当前工作目录（CWD）**找文件。文档示例是在 `install/` 目录运行，因此把这些文件拷进去：

```bash
cd ~/rsp/whisper.axcl/install
cp ../t2s.json ../TSCharacters.ocd2 ../TSPhrases.ocd2 .
```

5) 运行（与官方示例一致）

```bash
cd ~/rsp/whisper.axcl/install
./whisper -w ../demo.wav
```

正常会在末尾输出 `Result: ...` 的识别结果。

> 磁盘紧张提示：模型文件较大，只保留 `install/models/` 一份即可（不需要在 `~/rsp/whisper.axcl/models/` 再放一份重复文件）。

### OpenAI 兼容 API（文本对话）

文档提供了一套 **OpenAI API 兼容**的本地服务（默认本机 `8000` 端口），安装 StackFlow 包后即可使用：

```bash
sudo apt install lib-llm llm-sys llm-llm llm-openai-api
sudo apt install llm-model-qwen3-1.7b-int8-ctx-axcl

# 每次安装新模型后，需要重启服务以刷新模型列表
sudo systemctl restart llm-openai-api
```

调用示例：

```bash
curl http://127.0.0.1:8000/v1/models -H "Content-Type: application/json"

curl http://127.0.0.1:8000/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer sk-xxxxxxxx" \
  -d '{
    "model": "qwen3-1.7B-Int8-ctx-axcl",
    "messages": [
      {"role": "developer", "content": "You are a helpful home assistant."},
      {"role": "user", "content": "Turn on the light!"}
    ]
  }'
```

Python（OpenAI SDK）示例：

```python
from openai import OpenAI

client = OpenAI(api_key="sk-", base_url="http://127.0.0.1:8000/v1")
print(client.models.list())
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_openai.md`

> 注意：当你要运行某些“单模型 demo / 独立推理服务”时，文档提示可能需要先 `sudo systemctl stop llm-openai-api` 释放资源（示例见 `Qwen3-1.7B` 文档）。

### OpenAI 兼容 API（CosyVoice2 文本转语音）

安装包与模型（示例）：

```bash
sudo apt install lib-llm llm-sys llm-cosy-voice llm-openai-api
sudo apt install llm-model-cosyvoice2-0.5b-axcl
sudo systemctl restart llm-openai-api
```

文档说明：

- CosyVoice2 属于基于 LLM 的语音生成模型
- 当前版本单次生成音频最大长度约 **27s**
- 第一次加载模型可能较慢

Curl 示例（生成 `wav`）：

```bash
curl http://127.0.0.1:8000/v1/audio/speech \
  -H "Content-Type: application/json" \
  -d '{
    "model": "CosyVoice2-0.5B-axcl",
    "response_format": "wav",
    "input": "君不见黄河之水天上来，奔流到海不复回。"
  }' \
  -o output.wav
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_cosy_voice2_api.md`

## NPU 示例与工具链

文档中提到：

- **Pulsar2**：将模型部署到芯片 NPU 的工具链（含算子支持列表、大模型转换等）。
- **AXCL-Samples**：爱芯元智主导开发的示例工程，包含常见开源模型在基于其 SoC 的 PCIe 算力卡上的运行示例；并提供预编译 ModelZoo（文档给出百度网盘 / Hugging Face / OSS 等下载渠道入口）。

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_npu_samples.md`

## NPU Benchmark（性能参考）

文档说明（基于 Raspberry Pi 5 Host 测试，仅供参考）：

- 更新时间：**2024-11-22**
- 工具链版本：**Pulsar2 3.2-patch2**
- 测试工具：`axcl_run_model`
- Batch Size：1 或 8
- 单位：IPS（Image/Second）；音频为 RTF；LLM/VLM 为 TTFT 与 tokens/s
- `axcl_run_model` 仅统计 Device 侧推理耗时（不同 Host 的 memcopy/PCIe 性能会影响整体）

**Vision Model（IPS）**

| 模型 | 输入 | Batch1 | Batch8 |
|---|---:|---:|---:|
| Inceptionv1 | 224 | 1073 | 2494 |
| Inceptionv3 | 224 | 478 | 702 |
| MobileNetv1 | 224 | 1508 | 4854 |
| MobileNetv2 | 224 | 1366 | 5073 |
| ResNet18 | 224 | 1066 | 2254 |
| ResNet50 | 224 | 576 | 1045 |
| SqueezeNet11 | 224 | 1560 | 5961 |
| Swin-T | 224 | 342 | 507 |
| ViT-B/16 | 224 | 162 | 207 |
| YOLOv5s | 640 | 326 | 394 |
| YOLOv6s | 640 | 282 | 322 |
| YOLOv8s | 640 | 248 | 279 |
| YOLOv9s | 640 | 237 | — |
| YOLOv10s | 640 | 298 | — |
| YOLOv11n | 640 | 860 | — |
| YOLOv11s | 640 | 305 | — |
| YOLOv11m | 640 | 114 | — |
| YOLOv11l | 640 | 87 | — |
| YOLOv11x | 640 | 41 | — |

**Audio Model（RTF）**

| 模型 | RTF |
|---|---:|
| Whisper-Tiny | 0.03 |
| Whisper-Small | 0.18 |
| MeloTTS | 0.04 |

**LLM**

| 模型 | Prompt(tokens) | TTFT(ms) | 生成(tokens/s) |
|---|---:|---:|---:|
| Qwen2.5-0.5B | 128 | 188 | 28 |
| Qwen2.5-1.5B | 128 | 407.75 | 9.05 |
| Qwen2.5-1.5B-Int4 | 128 | 407.75 | 9.05 |

**VLM**

| 模型 | 图像输入 | Image Encoder(ms) | Prompt(tokens) | TTFT(ms) | 生成(tokens/s) |
|---|---|---:|---:|---:|---:|
| InternVL2-1B | 448×448 | 4200 | 320 | 425 | 29 |

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_npu_benchmark.md`

## FAQ（常见问题）

### axcl-smi 报错找不到设备（0x8030010b）

现象（示例）：

```text
axcl init fail, ret = 0x8030010b
open /dev/axcl_host fail, errno: 2 No such file or directory
```

排查方向（按文档）：

1) 用 `lspci` 检查是否识别到 `Axera Semiconductor Co., Ltd Device 0650`  
2) 检查加速卡是否插紧；断电后重启  
3) 卸载并重新安装驱动（`sudo apt remove axclhost` 后重新安装）

补充：如果你近期升级过内核（`uname -r` 变了），可能是 DKMS 没有为**当前内核**编译模块，导致节点未创建。可尝试：

```bash
sudo /usr/sbin/dkms autoinstall -k "$(uname -r)"
sudo modprobe axcl_host
ls -l /dev/axcl_host
axcl-smi
```

参考原文：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_faq.md`

## 离线文档索引（按主题）

> 下面的文件均位于 `offline/`。如果你要对照原文，请直接打开对应文件搜索关键字（如模型名、`wget`、`git clone`、`python -m venv`、`systemctl` 等）。

### 快速上手 / 安装

- 硬件安装：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_hardware_install.md`
- Raspberry Pi 环境与驱动：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_software_install.md`
- Windows 安装：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_windows_install.md`
- Docker：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_docker.md`
- Git LFS：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_git_lfs.md`

### 工具 / 进阶

- AXCL-SMI：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_axcl_smi.md`
- AXCL SDK API（原文很长）：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_axcl_api.md`
- AXCL Sample 使用说明：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_samples.md`
- FFmpeg：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_ffmpeg.md`
- NPU 示例：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_npu_samples.md`
- NPU 基准：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_npu_benchmark.md`

### 视觉模型

- YOLO11：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_yolo11.md`
- Yolo-World-V2：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_yolo_world_v2.md`
- Yolov7-face：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_yolov7_face.md`
- Depth-Anything-V2：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_depth_anything_v2.md`
- MixFormer-V2：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_mixformer_v2.md`
- Real-ESRGAN：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_real_esrgan.md`
- SuperResolution：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_superresolution.md`
- RIFE：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_rife.md`
- PPOCR v5：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_ppocr_v5.md`

### 大语言模型（LLM）

- Qwen3-0.6B：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_qwen3_0.6b.md`
- Qwen3-1.7B：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_qwen3_1.7b.md`
- Qwen2.5-0.5B-Instruct：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_qwen2.5_0.5b.md`
- Qwen2.5-1.5B-Instruct：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_qwen2.5_1.5b.md`
- DeepSeek-R1-Distill-Qwen-1.5B：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_deepseek.md`
- MiniCPM4-0.5B：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_minicpm4.md`

### 多模态（VLM/CLIP）

- InternVL3-1B：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_internvl3.md`
- Qwen2.5-VL：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_qwen2.5_vl.md`
- Qwen3-VL-2B：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_qwen3_vl_2b.md`
- Qwen3-VL-4B：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_qwen3_vl_4b.md`
- SmolVLM2：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_smolvlm2.md`
- LibCLIP：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_clip.md`
- Jina CLIP v2：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_jina_clip_v2.md`

### 音频模型

- Whisper：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_whisper.md`
- MeloTTS：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_melotts.md`
- SenseVoice：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_sensevoice.md`
- CosyVoice2：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_cosy_voice2.md`
- 3D-Speaker-MT：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_3d_speaker_mt.md`
- sherpa-onnx：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_sherpa-onnx.md`

### 生成/创作

- lcm-lora-sdv1-5：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_lcm_lora_sd.md`
- SD1.5-LLM8850：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_sd_demo.md`
- LivePortrait：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_liveportrait.md`
- Deimv2：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_deimv2.md`

### 应用

- Frigate NVR：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_frigate.md`
- Immich：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_immich.md`
- OpenAI API：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_openai.md`
- CosyVoice2 API：`offline/zh_CN_guide_ai_accelerator_llm-8850_m5_llm_8850_cosy_voice2_api.md`

# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_qwen3_1.7b

产品上手指引
目录索引
Linux PC
CM4Stack
RaspberryPi OS
UIFlow 本地部署
CoreMP135
镜像 & 软件更新
应用开发框架
Fdisk & 根文件系统扩容
网络配置
UiFlow2 快速上手
Buildroot
覆盖设备树(DTBO)
AI 加速卡
LLM-8850 Card
目录索引
快速上手
1. 硬件安装
2. 环境配置
3. 快速体验
4. 常见问题
视觉模型
YOLO11
Yolo-World-V2
Yolov7-face
Depth-Anything-V2
MixFormer-V2
Real-ESRGAN
SuperResolution
RIFE
大语言模型
Qwen3-0.6B
Qwen3-1.7B
Qwen2.5-0.5B-Instruct
Qwen2.5-1.5B-Instruct
DeepSeek-R1-Distill-Qwen-1.5B
MiniCPM4-0.5B
多模态模型
InternVL3-1B
Qwen2.5-VL-3B-Instruct
Qwen3-VL-2B-Instruct
Qwen3-VL-4B-Instruct-GPTQ-Int4
SmolVLM2-500M-Video-Instruct
LibCLIP
音频模型
Whisper
MeloTTS
SenseVoice
CosyVoice2
3D-Speaker-MT
生成模型
lcm-lora-sdv1-5
SD1.5-LLM8850
LivePortrait
应用列表
Frigate NVR
Immich
OpenAI API
CosyVoice2 API
sherpa-onnx
进阶使用
LLM-8850 AXCL-SMI
LLM-8850 NPU 使用示例
LLM-8850 NPU 基准
LLM-8850 AXCL-Sample 使用说明
LLM-8850 AXCL ffmpeg 使用示例
LLM-8850 AXCL SDK API
大语言模型
StackFlow AI
实时 AI 语音助手
OpenAI 语音助手
For Atomic Echo Base
For CoreS3 / CoreS3 SE
小智语音助手
Atom EchoS3R
小智墨伴语音助手
适配 AtomS3 / AtomS3R系列
适配 CoreS3 / CoreS3-SE
适配 StickS3
小聆语音助手
适配 AtomS3R
适配 CoreS3 / CoreS3-SE
火山引擎语音助手
For Atomic Echo Base
离线语音识别
Unit ASR
自定义固件生成
Arduino 快速上手
Module ASR
自定义固件生成
Arduino 快速上手
工业控制
StamPLC
用户手册
Arduino 快速上手
IoT 测量仪表
Air Quality
用户手册
PowerHub
用户手册
Module13.2 PPS
用户手册
VAMeter
用户手册
T-Lite
用户手册
输入设备
Chain DualKey
Ezdata
EzData2 快速上手
EzData2 设备接入 API
Ethernet 摄像头
PoECAM
PoECAM Web CAM
Wi-Fi 摄像头
TimerCAM
CameraTool
Timer Capture
SMB Folder Pusher
Amazon S3 Pusher
UIFlow1 Control
Unit CamS3/-5MP
WebCAM
AI 摄像头
UnitV2
Built-in Function
Jupyter notebook
UnitV2 V-Training
SSH & Wi-Fi
镜像 & 软件更新
StickV/UnitV
UnitV Maixpy
StickV Maixpy
V-Function
V-Training
LoRa & LoRaWAN
TTN (The Things Network)
TTN 平台连接与使用
LoRaWAN470 网关与节点
Meshtastic
Meshtastic 介绍
Unit C6L
电机驱动
Unit Roller485/CAN
Unit Roller485
Unit RollerCAN
电机校准
开发工具
M5 DAPLink
Easyloader 打包教程
vlw Font Creator
ToDo List
爱好套装
StampFly & Atom Joystick
RoverC & JoyC
Bala2
BalaC-Plus
Faces Kit Gameboy
Atom Printer
恢复出厂固件教程
Air Quality 恢复出厂固件
Basic/Fire/Gray 恢复出厂固件
Cardputer 恢复出厂固件
Cardputer-Adv 恢复出厂固件
Core2 恢复出厂固件
CoreS3 恢复出厂固件
CoreS3 Thread BR 恢复出厂固件
StamPLC 恢复出厂固件
StickC 恢复出厂固件
StickC-Plus 恢复出厂固件
StickC-Plus2 恢复出厂固件
Tab5 恢复出厂固件
Tab5 ESP-C6 Wi-Fi 恢复出厂固件
Unit PoE-P4 恢复出厂固件
VAMeter 恢复出厂固件
Xiaozhi Card Kit 恢复出厂固件
拨码开关&引脚切换
DIP Switch 引脚切换说明
Not Search Result
HOT SEARCHES
Camera
WiFi
RS485
RS232
Relay
LoRaWAN
GPS
NB-IoT
LTE
GSM
Zigbee
Servo
StepMotor
Ethernet
E-Paper
Product
Tutorial
Search
Qwen3-1.7B
手动下载模型
并上传到 raspberrypi5，或者通过以下命令拉取模型仓库。
提示
如果没有安装
git lfs
，先参考
git lfs 安装说明
进行安装。
git
clone
https://huggingface.co/AXERA-TECH/Qwen3-1.7B
git clone https://huggingface.co/AXERA-TECH/Qwen3-1.7B
文件说明
m5stack@raspberrypi:~/rsp/Qwen3-1.7B$ ls -lh
total 21M
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 09:07 config.json
-rw-rw-r-- 1 m5stack m5stack 1.1M Oct 13 09:46 main_api_ax650
-rw-r--r-- 1 m5stack m5stack  132 Oct 13 11:45 main_api_axcl_aarch64
-rw-rw-r-- 1 m5stack m5stack 8.5M Oct 13 09:46 main_api_axcl_x86
-rw-rw-r-- 1 m5stack m5stack 963K Oct 13 09:46 main_ax650
-rw-rw-r-- 1 m5stack m5stack 1.7M Oct 13 09:46 main_axcl_aarch64
-rw-rw-r-- 1 m5stack m5stack 8.1M Oct 13 09:46 main_axcl_x86
-rw-rw-r-- 1 m5stack m5stack  277 Aug 12 09:07 post_config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:07 qwen2.5_tokenizer
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 13 11:46 qwen3-1.7b-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:10 qwen3_tokenizer
-rw-rw-r-- 1 m5stack m5stack 7.6K Aug 12 09:07 qwen3_tokenizer_uid.py
-rw-rw-r-- 1 m5stack m5stack  12K Oct 13 09:43 README.md
-rw-rw-r-- 1 m5stack m5stack 2.5K Oct 13 09:43 run_qwen3_1.7b_int8_ctx_ax650.sh
-rw-rw-r-- 1 m5stack m5stack 2.5K Oct 13 09:43 run_qwen3_1.7b_int8_ctx_axcl_aarch64.sh
-rw-rw-r-- 1 m5stack m5stack 2.5K Oct 13 09:43 run_qwen3_1.7b_int8_ctx_axcl_x86_api.sh
-rw-rw-r-- 1 m5stack m5stack 2.5K Oct 13 09:43 run_qwen3_1.7b_int8_ctx_axcl_x86.sh
m5stack@raspberrypi:~/rsp/Qwen3-1.7B$ ls -lh
total 21M
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 09:07 config.json
-rw-rw-r-- 1 m5stack m5stack 1.1M Oct 13 09:46 main_api_ax650
-rw-r--r-- 1 m5stack m5stack  132 Oct 13 11:45 main_api_axcl_aarch64
-rw-rw-r-- 1 m5stack m5stack 8.5M Oct 13 09:46 main_api_axcl_x86
-rw-rw-r-- 1 m5stack m5stack 963K Oct 13 09:46 main_ax650
-rw-rw-r-- 1 m5stack m5stack 1.7M Oct 13 09:46 main_axcl_aarch64
-rw-rw-r-- 1 m5stack m5stack 8.1M Oct 13 09:46 main_axcl_x86
-rw-rw-r-- 1 m5stack m5stack  277 Aug 12 09:07 post_config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:07 qwen2.5_tokenizer
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 13 11:46 qwen3-1.7b-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:10 qwen3_tokenizer
-rw-rw-r-- 1 m5stack m5stack 7.6K Aug 12 09:07 qwen3_tokenizer_uid.py
-rw-rw-r-- 1 m5stack m5stack  12K Oct 13 09:43 README.md
-rw-rw-r-- 1 m5stack m5stack 2.5K Oct 13 09:43 run_qwen3_1.7b_int8_ctx_ax650.sh
-rw-rw-r-- 1 m5stack m5stack 2.5K Oct 13 09:43 run_qwen3_1.7b_int8_ctx_axcl_aarch64.sh
-rw-rw-r-- 1 m5stack m5stack 2.5K Oct 13 09:43 run_qwen3_1.7b_int8_ctx_axcl_x86_api.sh
-rw-rw-r-- 1 m5stack m5stack 2.5K Oct 13 09:43 run_qwen3_1.7b_int8_ctx_axcl_x86.sh
提示
如果之前已经创建了
qwen
的虚拟环境，不需要重新创建，只需要激活即可。
创建虚拟环境
python -m venv qwen
python -m venv qwen
激活虚拟环境
source
qwen/bin/activate
source qwen/bin/activate
安装依赖包
pip install transformers jinja2
pip install transformers jinja2
启动 tokenizer 解析器
python qwen3_tokenizer_uid.py --port 12345
python qwen3_tokenizer_uid.py --port 12345
运行 tokenizer 服务，Host ip 默认为 localhost，端口号设置为 12345，运行后信息如下：
(qwen) m5stack@raspberrypi:~/Qwen3-0.6B $ python qwen3_tokenizer_uid.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won
't be available and only tokenizers, configuration and file/data utilities can be used.
Server running at http://0.0.0.0:12345
(qwen) m5stack@raspberrypi:~/Qwen3-0.6B $ python qwen3_tokenizer_uid.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won't be available and only tokenizers, configuration and file/data utilities can be used.
Server running at http://0.0.0.0:12345
提示
以下操作需要新建一个 raspberrypi 的终端。
设置可执行权限
chmod +x main_axcl_aarch64 run_qwen3_1.7b_int8_ctx_axcl_aarch64.sh
chmod +x main_axcl_aarch64 run_qwen3_1.7b_int8_ctx_axcl_aarch64.sh
启动 Qwen3 模型推理服务
./run_qwen3_1.7b_int8_ctx_axcl_aarch64.sh
./run_qwen3_1.7b_int8_ctx_axcl_aarch64.sh
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/Qwen3-1.7B$ ./run_qwen3_1.7b_int8_ctx_axcl_aarch64.sh
[I][                            Init][ 136]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
[I][                            Init][  57]: uid: 95e7d5f3-fc8d-48ea-b489-1de9f37924d1
bos_id: -1, eos_id: 151645
  3% | ██                                |   1 /  31 [1.08s<33.54s, 0.92 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  6% | ███                               |   2 /  31 [1.08s<16.77s, 1.85 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
  100% | ████████████████████████████████ |  31 /  31 [64.75s<64.75s, 0.48 count/s] init post axmodel ok,remain_cmm(3788 MB)
[I][                            Init][ 237]: max_token_len : 2559
[I][                            Init][ 240]: kv_cache_size : 1024, kv_cache_num: 2559
[I][                            Init][ 248]: prefill_token_num : 128
[I][                            Init][ 252]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 252]: grp: 2, prefill_max_token_num : 512
[I][                            Init][ 252]: grp: 3, prefill_max_token_num : 1024
[I][                            Init][ 252]: grp: 4, prefill_max_token_num : 1536
[I][                            Init][ 252]: grp: 5, prefill_max_token_num : 2048
[I][                            Init][ 256]: prefill_max_token_num : 2048
________________________
|    ID| remain cmm(MB)|
========================
|     0|           3788|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config:
{
"enable_repetition_penalty"
:
false
,
"enable_temperature"
:
false
,
"enable_top_k_sampling"
:
true
,
"enable_top_p_sampling"
:
false
,
"penalty_window"
: 20,
"repetition_penalty"
: 1.2,
"temperature"
: 0.9,
"top_k"
: 1,
"top_p"
: 0.8
}

[I][                            Init][ 279]: LLM init ok
Type
"q"
to
exit
, Ctrl+c to stop current running
[I][          GenerateKVCachePrefill][ 335]: input token num : 21, prefill_split_num : 1 prefill_grpid : 2
[I][          GenerateKVCachePrefill][ 372]: input_num_token:21
[I][                            main][ 236]: precompute_len: 21
[I][                            main][ 237]: system_prompt: You are Qwen, created by Alibaba Cloud. You are a helpful assistant.
prompt >> hello
[I][                      SetKVCache][ 628]: prefill_grpid:2 kv_cache_num:512 precompute_len:21 input_num_token:12
[I][                      SetKVCache][ 631]: current prefill_max_token_num:1920
[I][                             Run][ 869]: input token num : 12, prefill_split_num : 1
[I][                             Run][ 901]: input_num_token:12
[I][                             Run][1030]: ttft: 796.38 ms
<think>

</think>

Hello! How can I assist you today?

[N][                             Run][1182]: hit eos,avg 7.38 token/s

[I][                      GetKVCache][ 597]: precompute_len:46, remaining:2002
prompt >>
m5stack@raspberrypi:~/rsp/Qwen3-1.7B$ ./run_qwen3_1.7b_int8_ctx_axcl_aarch64.sh
[I][                            Init][ 136]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
[I][                            Init][  57]: uid: 95e7d5f3-fc8d-48ea-b489-1de9f37924d1
bos_id: -1, eos_id: 151645
  3% | ██                                |   1 /  31 [1.08s<33.54s, 0.92 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  6% | ███                               |   2 /  31 [1.08s<16.77s, 1.85 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
  100% | ████████████████████████████████ |  31 /  31 [64.75s<64.75s, 0.48 count/s] init post axmodel ok,remain_cmm(3788 MB)
[I][                            Init][ 237]: max_token_len : 2559
[I][                            Init][ 240]: kv_cache_size : 1024, kv_cache_num: 2559
[I][                            Init][ 248]: prefill_token_num : 128
[I][                            Init][ 252]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 252]: grp: 2, prefill_max_token_num : 512
[I][                            Init][ 252]: grp: 3, prefill_max_token_num : 1024
[I][                            Init][ 252]: grp: 4, prefill_max_token_num : 1536
[I][                            Init][ 252]: grp: 5, prefill_max_token_num : 2048
[I][                            Init][ 256]: prefill_max_token_num : 2048
________________________
|    ID| remain cmm(MB)|
========================
|     0|           3788|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config:
{
    "enable_repetition_penalty": false,
    "enable_temperature": false,
    "enable_top_k_sampling": true,
    "enable_top_p_sampling": false,
    "penalty_window": 20,
    "repetition_penalty": 1.2,
    "temperature": 0.9,
    "top_k": 1,
    "top_p": 0.8
}

[I][                            Init][ 279]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
[I][          GenerateKVCachePrefill][ 335]: input token num : 21, prefill_split_num : 1 prefill_grpid : 2
[I][          GenerateKVCachePrefill][ 372]: input_num_token:21
[I][                            main][ 236]: precompute_len: 21
[I][                            main][ 237]: system_prompt: You are Qwen, created by Alibaba Cloud. You are a helpful assistant.
prompt >> hello
[I][                      SetKVCache][ 628]: prefill_grpid:2 kv_cache_num:512 precompute_len:21 input_num_token:12
[I][                      SetKVCache][ 631]: current prefill_max_token_num:1920
[I][                             Run][ 869]: input token num : 12, prefill_split_num : 1
[I][                             Run][ 901]: input_num_token:12
[I][                             Run][1030]: ttft: 796.38 ms
<think>

</think>

Hello! How can I assist you today?

[N][                             Run][1182]: hit eos,avg 7.38 token/s

[I][                      GetKVCache][ 597]: precompute_len:46, remaining:2002
prompt >>
API 使用
确保已运行 tokenizer 服务
(qwen) m5stack@raspberrypi:~/Qwen3-0.6B $ python qwen3_tokenizer_uid.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won
't be available and only tokenizers, configuration and file/data utilities can be used.
Server running at http://0.0.0.0:12345
(qwen) m5stack@raspberrypi:~/Qwen3-0.6B $ python qwen3_tokenizer_uid.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won't be available and only tokenizers, configuration and file/data utilities can be used.
Server running at http://0.0.0.0:12345
复制
run_qwen3_1.7b_int8_ctx_axcl_x86_api.sh
到
run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh
并设置可执行权限
cp run_qwen3_1.7b_int8_ctx_axcl_x86_api.sh run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh
chmod +x main_api_axcl_aarch64 run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh
cp run_qwen3_1.7b_int8_ctx_axcl_x86_api.sh run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh
chmod +x main_api_axcl_aarch64 run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh
修改
run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh
文件内容
./main_api_axcl_aarch64 \
--system_prompt "You are Qwen, created by Alibaba Cloud. You are a helpful assistant." \
--template_filename_axmodel "qwen3-1.7b-ax650/qwen3_p128_l%d_together.axmodel" \
--axmodel_num 28 \
--url_tokenizer_model "http://127.0.0.1:12345" \
--filename_post_axmodel qwen3-1.7b-ax650/qwen3_post.axmodel \
--filename_tokens_embed qwen3-1.7b-ax650/model.embed_tokens.weight.bfloat16.bin \
--tokens_embed_num 151936 \
--tokens_embed_size 2048 \
--use_mmap_load_embed 1 \
--devices 0
./main_api_axcl_aarch64 \
--system_prompt "You are Qwen, created by Alibaba Cloud. You are a helpful assistant." \
--template_filename_axmodel "qwen3-1.7b-ax650/qwen3_p128_l%d_together.axmodel" \
--axmodel_num 28 \
--url_tokenizer_model "http://127.0.0.1:12345" \
--filename_post_axmodel qwen3-1.7b-ax650/qwen3_post.axmodel \
--filename_tokens_embed qwen3-1.7b-ax650/model.embed_tokens.weight.bfloat16.bin \
--tokens_embed_num 151936 \
--tokens_embed_size 2048 \
--use_mmap_load_embed 1 \
--devices 0
注意
如果已安装 StackFlow 提供的 openai-api 服务，需要手动执行
sudo systemctl stop llm-openai-api
停止
启动 Qwen3 模型推理 API 服务
./run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh
./run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/Qwen3-1.7B $ ./run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh 
[I][                            Init][ 130]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
[I][                            Init][  57]: uid: 3f3c54ef-ddfa-4fbc-bd2f-74523109857e
bos_id: -1, eos_id: 151645
  3% | ██                                |   1 /  31 [0.95s<29.33s, 1.06 count/s] tokenizer init ok[I]
[I][                            Init][ 221]: max_token_len : 2047
[I][                            Init][ 224]: kv_cache_size : 1024, kv_cache_num: 2047
[I][                            Init][ 232]: prefill_token_num : 128
[I][                            Init][ 236]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 236]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 236]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 236]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 236]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 236]: grp: 6, prefill_max_token_num : 640
[I][                            Init][ 236]: grp: 7, prefill_max_token_num : 768
[I][                            Init][ 236]: grp: 8, prefill_max_token_num : 896
[I][                            Init][ 236]: grp: 9, prefill_max_token_num : 1024
[I][                            Init][ 240]: prefill_max_token_num : 1024
________________________
|    ID| remain cmm(MB)|
========================
|     0|           3665|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config: 
{
"enable_repetition_penalty"
:
false
,
"enable_temperature"
:
false
,
"enable_top_k_sampling"
:
true
,
"enable_top_p_sampling"
:
false
,
"penalty_window"
: 20,
"repetition_penalty"
: 1.2,
"temperature"
: 0.9,
"top_k"
: 1,
"top_p"
: 0.8
}

[I][                            Init][ 263]: LLM init ok
Server running on port 8000...
m5stack@raspberrypi:~/rsp/Qwen3-1.7B $ ./run_qwen3_1.7b_int8_ctx_axcl_aarch_api.sh 
[I][                            Init][ 130]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
[I][                            Init][  57]: uid: 3f3c54ef-ddfa-4fbc-bd2f-74523109857e
bos_id: -1, eos_id: 151645
  3% | ██                                |   1 /  31 [0.95s<29.33s, 1.06 count/s] tokenizer init ok[I]
[I][                            Init][ 221]: max_token_len : 2047
[I][                            Init][ 224]: kv_cache_size : 1024, kv_cache_num: 2047
[I][                            Init][ 232]: prefill_token_num : 128
[I][                            Init][ 236]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 236]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 236]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 236]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 236]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 236]: grp: 6, prefill_max_token_num : 640
[I][                            Init][ 236]: grp: 7, prefill_max_token_num : 768
[I][                            Init][ 236]: grp: 8, prefill_max_token_num : 896
[I][                            Init][ 236]: grp: 9, prefill_max_token_num : 1024
[I][                            Init][ 240]: prefill_max_token_num : 1024
________________________
|    ID| remain cmm(MB)|
========================
|     0|           3665|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config: 
{
    "enable_repetition_penalty": false,
    "enable_temperature": false,
    "enable_top_k_sampling": true,
    "enable_top_p_sampling": false,
    "penalty_window": 20,
    "repetition_penalty": 1.2,
    "temperature": 0.9,
    "top_k": 1,
    "top_p": 0.8
}

[I][                            Init][ 263]: LLM init ok
Server running on port 8000...
API 列表
方法
路径
功能
GET
/api/stop
停止当前推理任务
POST
/api/reset
重置上下文（可设置新的 system prompt）
POST
/api/generate
异步生成文本（流式输出通过 /api/generate_provider 获取）
GET
/api/generate_provider
获取当前生成的增量输出（轮询用）
POST
/api/chat
同步问答（单轮）
1. POST /api/generate
curl -X POST
"http://localhost:8000/api/generate"
\
    -H
"Content-Type: application/json"
\
    -d
'{
           "prompt": "Hello, please introduce yourself.",
           "temperature": 0.7,
           "top-k": 40
         }'
curl -X POST "http://localhost:8000/api/generate" \
    -H "Content-Type: application/json" \
    -d '{
           "prompt": "Hello, please introduce yourself.",
           "temperature": 0.7,
           "top-k": 40
         }'
返回：
{
"status"
:
"ok"
}
{"status": "ok"}
说明：
prompt 是必需的
temperature, top-k, top-p, repetition_penalty 等为可选采样参数
调用后立即返回 "status": "ok"，后台开始生成
2. GET /api/generate_provider
获取生成内容和进度（流式轮询）：
curl
"http://localhost:8000/api/generate_provider"
curl "http://localhost:8000/api/generate_provider"
返回：
{
"done"
:
false
,
"response"
:
"<think>\n\n</think>\n\nHello! I'm a large language model developed by Alibaba"
}
{"done":false,"response":"<think>\n\n</think>\n\nHello! I'm a large language model developed by Alibaba"}
当 "done": true 时表示生成结束。
你可以每隔 200~500ms 请求一次，实现客户端流式获取模型输出。
3. POST /api/reset
重置 LLM 上下文（清空历史对话），可选传入新的 system prompt：
curl -X POST
"http://localhost:8000/api/reset"
\
    -H
"Content-Type: application/json"
\
    -d
'{"system_prompt": "You are a helpful assistant."}'
curl -X POST "http://localhost:8000/api/reset" \
    -H "Content-Type: application/json" \
    -d '{"system_prompt": "You are a helpful assistant."}'
返回：
{
"status"
:
"ok"
}
{"status": "ok"}
用于清理 KV cache 或切换对话场景。
4. GET /api/stop
立即中断当前生成任务：
curl
"http://localhost:8000/api/stop"
curl "http://localhost:8000/api/stop"
返回：
{
"status"
:
"ok"
}
{"status": "ok"}
5. POST /api/chat
一次性输入消息并直接同步返回结果（非 streaming）
curl -X POST
"http://localhost:8000/api/chat"
\
    -H
"Content-Type: application/json"
\
    -d
'{
          "messages": [
            {"role": "user", "content": "Hello, please introduce yourself in one sentence."}
          ],
          "temperature": 0.7
        }'
curl -X POST "http://localhost:8000/api/chat" \
    -H "Content-Type: application/json" \
    -d '{
          "messages": [
            {"role": "user", "content": "Hello, please introduce yourself in one sentence."}
          ],
          "temperature": 0.7
        }'
返回：
{
"done"
:
true
,
"message"
:
"<think>\n\n</think>\n\nHi there! I'm a large language model developed by Alibaba Cloud, designed to assist with a wide range of tasks and answer questions."
}
{"done":true,"message":"<think>\n\n</think>\n\nHi there! I'm a large language model developed by Alibaba Cloud, designed to assist with a wide range of tasks and answer questions."}
注意
/api/generate
+
/api/generate_provider
是 异步/流式模式（适合 UI 场景）
/api/chat
是 同步阻塞模式（适合一次性获取完整答案）
如果模型正在运行，请求会返回：
{
"error"
:
"llm is running"
}
{"error": "llm is running"}
如果模型未初始化，会返回：
{
"error"
:
"Model not init"
}
{"error": "Model not init"}
典型调用流程（异步）
POST /api/generate 发送 prompt
客户端每隔几百毫秒 GET /api/generate_provider
当 done:true 出现 → 停止轮询
Next
目录索引
On This Page
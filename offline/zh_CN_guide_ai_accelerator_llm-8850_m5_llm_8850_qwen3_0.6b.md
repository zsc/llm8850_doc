# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_qwen3_0.6b

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
Qwen3-0.6B
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
https://huggingface.co/AXERA-TECH/Qwen3-0.6B
git clone https://huggingface.co/AXERA-TECH/Qwen3-0.6B
文件说明
m5stack@raspberrypi:~/Qwen3-0.6B $ ls -lh
total 4.4M
-rw-r--r-- 1 m5stack m5stack    0 Jul 25 15:48 config.json
-rw-r--r-- 1 m5stack m5stack 959K Jul 25 15:54 main_ax650
-rw-r--r-- 1 m5stack m5stack 1.7M Jul 25 15:54 main_axcl_aarch64
-rw-r--r-- 1 m5stack m5stack 1.8M Jul 25 15:54 main_axcl_x86
-rw-r--r-- 1 m5stack m5stack  277 Jul 25 15:47 post_config.json
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 15:47 qwen2.5_tokenizer
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 15:47 qwen3-0.6b-ax630c
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 15:47 qwen3-0.6b-ax650
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 15:47 qwen3_tokenizer
-rw-r--r-- 1 m5stack m5stack 7.6K Jul 25 15:47 qwen3_tokenizer_uid.py
-rw-r--r-- 1 m5stack m5stack  11K Jul 25 15:47 README.md
-rw-r--r-- 1 m5stack m5stack  577 Jul 25 15:47 run_qwen3_0.6b_int8_ctx_ax630c.sh
-rw-r--r-- 1 m5stack m5stack  574 Jul 25 15:47 run_qwen3_0.6b_int8_ctx_ax650.sh
-rw-r--r-- 1 m5stack m5stack  594 Jul 25 15:47 run_qwen3_0.6b_int8_ctx_axcl_aarch64.sh
-rw-r--r-- 1 m5stack m5stack  590 Jul 25 15:47 run_qwen3_0.6b_int8_ctx_axcl_x86.sh
m5stack@raspberrypi:~/Qwen3-0.6B $ ls -lh
total 4.4M
-rw-r--r-- 1 m5stack m5stack    0 Jul 25 15:48 config.json
-rw-r--r-- 1 m5stack m5stack 959K Jul 25 15:54 main_ax650
-rw-r--r-- 1 m5stack m5stack 1.7M Jul 25 15:54 main_axcl_aarch64
-rw-r--r-- 1 m5stack m5stack 1.8M Jul 25 15:54 main_axcl_x86
-rw-r--r-- 1 m5stack m5stack  277 Jul 25 15:47 post_config.json
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 15:47 qwen2.5_tokenizer
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 15:47 qwen3-0.6b-ax630c
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 15:47 qwen3-0.6b-ax650
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 15:47 qwen3_tokenizer
-rw-r--r-- 1 m5stack m5stack 7.6K Jul 25 15:47 qwen3_tokenizer_uid.py
-rw-r--r-- 1 m5stack m5stack  11K Jul 25 15:47 README.md
-rw-r--r-- 1 m5stack m5stack  577 Jul 25 15:47 run_qwen3_0.6b_int8_ctx_ax630c.sh
-rw-r--r-- 1 m5stack m5stack  574 Jul 25 15:47 run_qwen3_0.6b_int8_ctx_ax650.sh
-rw-r--r-- 1 m5stack m5stack  594 Jul 25 15:47 run_qwen3_0.6b_int8_ctx_axcl_aarch64.sh
-rw-r--r-- 1 m5stack m5stack  590 Jul 25 15:47 run_qwen3_0.6b_int8_ctx_axcl_x86.sh
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
chmod +x main_axcl_aarch64 run_qwen3_0.6b_int8_ctx_axcl_aarch64.sh
chmod +x main_axcl_aarch64 run_qwen3_0.6b_int8_ctx_axcl_aarch64.sh
启动 Qwen3 模型推理服务
./run_qwen3_0.6b_int8_ctx_axcl_aarch64.sh
./run_qwen3_0.6b_int8_ctx_axcl_aarch64.sh
成功启动后信息如下
m5stack@raspberrypi:~/rsp/Qwen3-0.6B$ ./run_qwen3_0.6b_int8_ctx_axcl_aarch64.sh
[I][                            Init][ 136]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
[I][                            Init][  57]: uid: abf93a3d-2d6a-4ddb-8c9b-42a208a012f7
bos_id: -1, eos_id: 151645
  3% | ██                                |   1 /  31 [1.11s<34.47s, 0.90 count/s] tokenizer init ok[I][Init][  45]: LLaMaEmbedSelector use mmap
  6% | ███                               |   2 /  31 [1.11s<17.25s, 1.80 count/s] embed_selector init ok
  96% | ███████████████████████████████   |  30 /  31 [31.91s<32.98s, 0.94 count/s] init 27 axmodel
  100% | ████████████████████████████████ |  31 /  31 [36.09s<36.09s, 0.86 count/s] init post axmodel ok,remain_cmm(5068 MB)
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
|     0|           5068|
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
[I][                             Run][1030]: ttft: 670.51 ms
<think>

</think>

Hello! How can I assist you today?

[N][                             Run][1182]: hit eos,avg 12.88 token/s

[I][                      GetKVCache][ 597]: precompute_len:46, remaining:2002
prompt >>
m5stack@raspberrypi:~/rsp/Qwen3-0.6B$ ./run_qwen3_0.6b_int8_ctx_axcl_aarch64.sh
[I][                            Init][ 136]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
[I][                            Init][  57]: uid: abf93a3d-2d6a-4ddb-8c9b-42a208a012f7
bos_id: -1, eos_id: 151645
  3% | ██                                |   1 /  31 [1.11s<34.47s, 0.90 count/s] tokenizer init ok[I][Init][  45]: LLaMaEmbedSelector use mmap
  6% | ███                               |   2 /  31 [1.11s<17.25s, 1.80 count/s] embed_selector init ok
  96% | ███████████████████████████████   |  30 /  31 [31.91s<32.98s, 0.94 count/s] init 27 axmodel
  100% | ████████████████████████████████ |  31 /  31 [36.09s<36.09s, 0.86 count/s] init post axmodel ok,remain_cmm(5068 MB)
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
|     0|           5068|
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
[I][                             Run][1030]: ttft: 670.51 ms
<think>

</think>

Hello! How can I assist you today?

[N][                             Run][1182]: hit eos,avg 12.88 token/s

[I][                      GetKVCache][ 597]: precompute_len:46, remaining:2002
prompt >>
模型
量化方式
tftt (ms)
token/s
Qwen3-0.6B
w8a16
670.51
12.88
Qwen3-1.7B
w8a16
796.38
7.38
Qwen2.5-0.5B
w4a16
-
27.05
Qwen2.5-1.5B
w4a16
-
15.06
Next
目录索引
On This Page
# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_internvl3

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
InternVL3-1B
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
https://huggingface.co/AXERA-TECH/InternVL3-1B
git clone https://huggingface.co/AXERA-TECH/InternVL3-1B
文件说明
(axcl) m5stack@raspberrypi5:~/InternVL3-1B $ ls -lh
total 17M
-rw-r--r-- 1 m5stack m5stack 3.8K Jul 25 16:04 config.json
-rw-r--r-- 1 m5stack m5stack 3.9K Jul 25 16:04 gradio_demo.py
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 16:06 internvl3_1b_ax650
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 16:04 internvl3_tokenizer
-rw-r--r-- 1 m5stack m5stack 6.6K Jul 25 16:04 internvl3_tokenizer.py
-rw-r--r-- 1 m5stack m5stack 6.4M Jul 25 16:05 main_api_ax650
-rw-r--r-- 1 m5stack m5stack 1.9M Jul 25 16:05 main_api_axcl_x86
-rw-r--r-- 1 m5stack m5stack 6.3M Jul 25 16:05 main_ax650
-rw-r--r-- 1 m5stack m5stack 1.8M Jul 25 16:05 main_axcl_x86
-rw-r--r-- 1 m5stack m5stack  277 Jul 25 16:04 post_config.json
-rw-r--r-- 1 m5stack m5stack 6.0K Jul 25 16:04 README.md
-rw-r--r-- 1 m5stack m5stack  495 Jul 25 16:04 run_internvl_3_1b_448_api_ax650.sh
-rw-r--r-- 1 m5stack m5stack  516 Jul 25 16:04 run_internvl_3_1b_448_api_axcl_x86.sh
-rw-r--r-- 1 m5stack m5stack  506 Jul 25 16:04 run_internvl_3_1b_448_ax650.sh
-rw-r--r-- 1 m5stack m5stack  527 Jul 25 16:04 run_internvl_3_1b_448_axcl_x86.sh
-rw-r--r-- 1 m5stack m5stack  50K Jul 25 16:04 ssd_car.jpg
(axcl) m5stack@raspberrypi5:~/InternVL3-1B $ ls -lh
total 17M
-rw-r--r-- 1 m5stack m5stack 3.8K Jul 25 16:04 config.json
-rw-r--r-- 1 m5stack m5stack 3.9K Jul 25 16:04 gradio_demo.py
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 16:06 internvl3_1b_ax650
drwxr-xr-x 2 m5stack m5stack 4.0K Jul 25 16:04 internvl3_tokenizer
-rw-r--r-- 1 m5stack m5stack 6.6K Jul 25 16:04 internvl3_tokenizer.py
-rw-r--r-- 1 m5stack m5stack 6.4M Jul 25 16:05 main_api_ax650
-rw-r--r-- 1 m5stack m5stack 1.9M Jul 25 16:05 main_api_axcl_x86
-rw-r--r-- 1 m5stack m5stack 6.3M Jul 25 16:05 main_ax650
-rw-r--r-- 1 m5stack m5stack 1.8M Jul 25 16:05 main_axcl_x86
-rw-r--r-- 1 m5stack m5stack  277 Jul 25 16:04 post_config.json
-rw-r--r-- 1 m5stack m5stack 6.0K Jul 25 16:04 README.md
-rw-r--r-- 1 m5stack m5stack  495 Jul 25 16:04 run_internvl_3_1b_448_api_ax650.sh
-rw-r--r-- 1 m5stack m5stack  516 Jul 25 16:04 run_internvl_3_1b_448_api_axcl_x86.sh
-rw-r--r-- 1 m5stack m5stack  506 Jul 25 16:04 run_internvl_3_1b_448_ax650.sh
-rw-r--r-- 1 m5stack m5stack  527 Jul 25 16:04 run_internvl_3_1b_448_axcl_x86.sh
-rw-r--r-- 1 m5stack m5stack  50K Jul 25 16:04 ssd_car.jpg
启动 tokenizer 解析器
python internvl3_tokenizer.py --port 12345
python internvl3_tokenizer.py --port 12345
运行 tokenizer 服务，Host ip 默认为 localhost，端口号设置为 12345，正在运行后信息如下：
(axcl) m5stack@raspberrypi5:~/InternVL3-1B $ python internvl3_tokenizer.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won
't be available and only tokenizers, configuration and file/data utilities can be used.
None None 151645 <|im_end|> 151665 151667
context_len is  256
prompt is <|im_start|>system
你是书生·万象, 英文名是InternVL, 是由上海人工智能实验室、清华大学及多家合作单位联合开发的多模态大语言模型.<|im_end|>
<|im_start|>user
你好
<img></img>
<|im_end|>
<|im_start|>assistant
47
http://0.0.0.0:12345
(axcl) m5stack@raspberrypi5:~/InternVL3-1B $ python internvl3_tokenizer.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won't be available and only tokenizers, configuration and file/data utilities can be used.
None None 151645 <|im_end|> 151665 151667
context_len is  256
prompt is <|im_start|>system
你是书生·万象, 英文名是InternVL, 是由上海人工智能实验室、清华大学及多家合作单位联合开发的多模态大语言模型.<|im_end|>
<|im_start|>user
你好
<img></img>
<|im_end|>
<|im_start|>assistant
47
http://0.0.0.0:12345
运行 InternVL3-1B
m5stack@raspberrypi5:~/InternVL3-1B $ chmod +x main_axcl_aarch64 run_internvl_3_1b_448_axcl_aarch64.sh
m5stack@raspberrypi5:~/InternVL3-1B $ chmod +x main_axcl_aarch64 run_internvl_3_1b_448_axcl_aarch64.sh
测试图片
输出信息
m5stack@raspberrypi5:~/InternVL3-1B $ ./run_internvl_3_1b_448_axcl_aarch64.sh
[I][                            Init][ 160]: LLM init start
[I][                            Init][  34]: connect http://0.0.0.0:12345 ok
bos_id: -1, eos_id: 151645
img_start_token: 151665
img_context_token: 151667
input size: 1
    name:    image [unknown] [unknown]
        1 x 3 x 448 x 448 size:2408448

output size: 1
    name:   output
        1 x 256 x 896 size:917504

[I][                            Init][ 265]: IMAGE_CONTEXT_TOKEN: 151667, IMAGE_START_TOKEN: 151665
[I][                            Init][ 290]: image encoder input nchw@float32
[I][                            Init][ 320]: image encoder output float32

[I][                            Init][ 330]: image_encoder_height : 448, image_encoder_width: 448
[I][                            Init][ 332]: max_token_len : 2047
[I][                            Init][ 335]: kv_cache_size : 128, kv_cache_num: 2047
[I][                            Init][ 343]: prefill_token_num : 128
[I][                            Init][ 347]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 347]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 347]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 347]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 347]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 347]: grp: 6, prefill_max_token_num : 640
[I][                            Init][ 347]: grp: 7, prefill_max_token_num : 768
[I][                            Init][ 347]: grp: 8, prefill_max_token_num : 896
[I][                            Init][ 347]: grp: 9, prefill_max_token_num : 1024
[I][                            Init][ 351]: prefill_max_token_num : 1024
________________________
|    ID| remain cmm(MB)|
========================
|     0|           5764|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config:
{
"enable_repetition_penalty"
:
false
,
"enable_temperature"
:
true
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
: 10,
"top_p"
: 0.8
}

[I][                            Init][ 448]: LLM init ok
Type
"q"
to
exit
, Ctrl+c to stop current running
prompt >> Please describe this image
m5stack@raspberrypi5:~/InternVL3-1B $ ./run_internvl_3_1b_448_axcl_aarch64.sh
[I][                            Init][ 160]: LLM init start
[I][                            Init][  34]: connect http://0.0.0.0:12345 ok
bos_id: -1, eos_id: 151645
img_start_token: 151665
img_context_token: 151667
input size: 1
    name:    image [unknown] [unknown]
        1 x 3 x 448 x 448 size:2408448

output size: 1
    name:   output
        1 x 256 x 896 size:917504

[I][                            Init][ 265]: IMAGE_CONTEXT_TOKEN: 151667, IMAGE_START_TOKEN: 151665
[I][                            Init][ 290]: image encoder input nchw@float32
[I][                            Init][ 320]: image encoder output float32

[I][                            Init][ 330]: image_encoder_height : 448, image_encoder_width: 448
[I][                            Init][ 332]: max_token_len : 2047
[I][                            Init][ 335]: kv_cache_size : 128, kv_cache_num: 2047
[I][                            Init][ 343]: prefill_token_num : 128
[I][                            Init][ 347]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 347]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 347]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 347]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 347]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 347]: grp: 6, prefill_max_token_num : 640
[I][                            Init][ 347]: grp: 7, prefill_max_token_num : 768
[I][                            Init][ 347]: grp: 8, prefill_max_token_num : 896
[I][                            Init][ 347]: grp: 9, prefill_max_token_num : 1024
[I][                            Init][ 351]: prefill_max_token_num : 1024
________________________
|    ID| remain cmm(MB)|
========================
|     0|           5764|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config:
{
    "enable_repetition_penalty": false,
    "enable_temperature": true,
    "enable_top_k_sampling": true,
    "enable_top_p_sampling": false,
    "penalty_window": 20,
    "repetition_penalty": 1.2,
    "temperature": 0.9,
    "top_k": 10,
    "top_p": 0.8
}

[I][                            Init][ 448]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
prompt >> Please describe this image
Next
目录索引
On This Page
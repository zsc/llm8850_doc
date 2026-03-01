# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_qwen2.5_vl

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
Qwen2.5-VL-3B-Instruct
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
https://huggingface.co/AXERA-TECH/Qwen2.5-VL-3B-Instruct
git clone https://huggingface.co/AXERA-TECH/Qwen2.5-VL-3B-Instruct
文件说明
m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ ls -lh
total 10M
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 16:37 config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:52 image
-rw-rw-r-- 1 m5stack m5stack 6.3M Aug 12 16:52 main
-rwxrwxr-x 1 m5stack m5stack  132 Aug 12 16:37 main_ax650
-rwxrwxr-x 1 m5stack m5stack 1.8M Aug 12 16:52 main_axcl_aarch64
-rwxrwxr-x 1 m5stack m5stack 1.8M Aug 12 16:52 main_axcl_x86
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:37 python
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:52 qwen2_5-vl-3b-image-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:47 Qwen2.5-VL-3B-Instruct-AX650-chunk_prefill_512
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:55 qwen2_5-vl-3b-video-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:37 qwen2_5-vl-tokenizer
-rw-rw-r-- 1 m5stack m5stack 9.0K Aug 12 16:37 qwen2_tokenizer_images.py
-rw-rw-r-- 1 m5stack m5stack  16K Aug 12 16:37 qwen2_tokenizer_video_308.py
-rw-rw-r-- 1 m5stack m5stack  14K Aug 12 16:37 README.md
-rwxrwxr-x 1 m5stack m5stack  708 Aug 12 16:37 run_qwen2_5_vl_image_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  704 Aug 12 16:37 run_qwen2_5_vl_image_axcl_x86.sh
-rwxrwxr-x 1 m5stack m5stack  780 Aug 12 16:37 run_qwen2_5_vl_image.sh
-rwxrwxr-x 1 m5stack m5stack  705 Aug 12 16:37 run_qwen2_5_vl_video_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  701 Aug 12 16:37 run_qwen2_5_vl_video_axcl_x86.sh
-rwxrwxr-x 1 m5stack m5stack  777 Aug 12 16:37 run_qwen2_5_vl_video.sh
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:37 video
m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ ls -lh
total 10M
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 16:37 config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:52 image
-rw-rw-r-- 1 m5stack m5stack 6.3M Aug 12 16:52 main
-rwxrwxr-x 1 m5stack m5stack  132 Aug 12 16:37 main_ax650
-rwxrwxr-x 1 m5stack m5stack 1.8M Aug 12 16:52 main_axcl_aarch64
-rwxrwxr-x 1 m5stack m5stack 1.8M Aug 12 16:52 main_axcl_x86
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:37 python
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:52 qwen2_5-vl-3b-image-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:47 Qwen2.5-VL-3B-Instruct-AX650-chunk_prefill_512
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:55 qwen2_5-vl-3b-video-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:37 qwen2_5-vl-tokenizer
-rw-rw-r-- 1 m5stack m5stack 9.0K Aug 12 16:37 qwen2_tokenizer_images.py
-rw-rw-r-- 1 m5stack m5stack  16K Aug 12 16:37 qwen2_tokenizer_video_308.py
-rw-rw-r-- 1 m5stack m5stack  14K Aug 12 16:37 README.md
-rwxrwxr-x 1 m5stack m5stack  708 Aug 12 16:37 run_qwen2_5_vl_image_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  704 Aug 12 16:37 run_qwen2_5_vl_image_axcl_x86.sh
-rwxrwxr-x 1 m5stack m5stack  780 Aug 12 16:37 run_qwen2_5_vl_image.sh
-rwxrwxr-x 1 m5stack m5stack  705 Aug 12 16:37 run_qwen2_5_vl_video_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  701 Aug 12 16:37 run_qwen2_5_vl_video_axcl_x86.sh
-rwxrwxr-x 1 m5stack m5stack  777 Aug 12 16:37 run_qwen2_5_vl_video.sh
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 16:37 video
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
启动图片 tokenizer 解析器
python qwen2_tokenizer_images.py --port 12345
python qwen2_tokenizer_images.py --port 12345
运行 tokenizer 服务，Host ip 默认为 localhost，端口号设置为 12345，正在运行后信息如下
(qwen) m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ python qwen2_tokenizer_images.py --port 12345
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151653, 74785, 419, 2168, 13, 151645, 198, 151644, 77091, 198]
281
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:12345
(qwen) m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ python qwen2_tokenizer_images.py --port 12345
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151653, 74785, 419, 2168, 13, 151645, 198, 151644, 77091, 198]
281
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:12345
提示
以下操作需要新建一个 raspberrypi 的终端。
设置可执行权限
chmod +x main_axcl_aarch64 run_qwen2_5_vl_image_axcl_aarch64.sh
chmod +x main_axcl_aarch64 run_qwen2_5_vl_image_axcl_aarch64.sh
启动 Qwen2.5-VL 模型 图片推理服务
./run_qwen2_5_vl_image_axcl_aarch64.sh
./run_qwen2_5_vl_image_axcl_aarch64.sh
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ ./run_qwen2_5_vl_image_axcl_aarch64.sh
[I][                            Init][ 162]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151655
  2% | █                                 |   1 /  39 [0.01s<0.20s, 200.00 count/s] tokenizer init ok
  [I][Init][  45]: LLaMaEmbedSelector use mmap
100% | ████████████████████████████████ |  39 /  39 [72.58s<78.62s, 0.50 count/s] init post axmodel ok,remain_cmm(-1 MB)
input size: 1
    name: hidden_states [unknown] [unknown]
        1 x 1024 x 392 x 3 size:1204224

output size: 1
    name: hidden_states_out
        256 x 2048 size:2097152

[I][                            Init][ 267]: IMAGE_CONTEXT_TOKEN: 151655, IMAGE_START_TOKEN: 151652
[I][                            Init][ 328]: image encoder output float32

[I][                            Init][ 340]: max_token_len : 1023
[I][                            Init][ 343]: kv_cache_size : 256, kv_cache_num: 1023
[I][                            Init][ 351]: prefill_token_num : 128
[I][                            Init][ 355]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 355]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 355]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 355]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 355]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 359]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|             -1|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[E][                     load_config][ 278]: config file(post_config.json) open failed
[W][                            Init][ 452]: load postprocess config(post_config.json) failed
[I][                            Init][ 456]: LLM init ok
Type
"q"
to
exit
, Ctrl+c to stop current running
prompt >> who are you?
image >>
[I][                             Run][ 625]: input token num : 23, prefill_split_num : 1
[I][                             Run][ 659]: input_num_token:23
[I][                             Run][ 796]: ttft: 558.68 ms
I am a large language model created by Alibaba Cloud. I am called Qwen.

[N][                             Run][ 949]: hit eos,avg 4.81 token/s

prompt >>
m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ ./run_qwen2_5_vl_image_axcl_aarch64.sh
[I][                            Init][ 162]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151655
  2% | █                                 |   1 /  39 [0.01s<0.20s, 200.00 count/s] tokenizer init ok
  [I][Init][  45]: LLaMaEmbedSelector use mmap
100% | ████████████████████████████████ |  39 /  39 [72.58s<78.62s, 0.50 count/s] init post axmodel ok,remain_cmm(-1 MB)
input size: 1
    name: hidden_states [unknown] [unknown]
        1 x 1024 x 392 x 3 size:1204224

output size: 1
    name: hidden_states_out
        256 x 2048 size:2097152

[I][                            Init][ 267]: IMAGE_CONTEXT_TOKEN: 151655, IMAGE_START_TOKEN: 151652
[I][                            Init][ 328]: image encoder output float32

[I][                            Init][ 340]: max_token_len : 1023
[I][                            Init][ 343]: kv_cache_size : 256, kv_cache_num: 1023
[I][                            Init][ 351]: prefill_token_num : 128
[I][                            Init][ 355]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 355]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 355]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 355]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 355]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 359]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|             -1|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[E][                     load_config][ 278]: config file(post_config.json) open failed
[W][                            Init][ 452]: load postprocess config(post_config.json) failed
[I][                            Init][ 456]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
prompt >> who are you?
image >>
[I][                             Run][ 625]: input token num : 23, prefill_split_num : 1
[I][                             Run][ 659]: input_num_token:23
[I][                             Run][ 796]: ttft: 558.68 ms
I am a large language model created by Alibaba Cloud. I am called Qwen.

[N][                             Run][ 949]: hit eos,avg 4.81 token/s

prompt >>
分析图片
prompt >> describe this picture
image >> image/ssd_car.jpg
[I][                          Encode][ 539]: image encode time : 773.948975 ms, size : 524288
[I][                             Run][ 625]: input token num : 280, prefill_split_num : 3
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:24
[I][                             Run][ 796]: ttft: 2076.95 ms
The picture shows a busy urban street scene
in
what appears to be a city center. A red double-decker bus is prominently featured
in
the foreground, with a large advertisement on its side that reads,
"THINGS GET MORE EXITING WHEN YOU SAY 'YES' VirginMoney.co.uk."
The bus is driving on the right side of the road,
which
is typical
in
the UK.

In the background, there are several pedestrians walking on the sidewalk, and a few cars are visible on the road. The buildings lining the street are modern and have large windows, suggesting a commercial or business district. The street is well-maintained, with clear pedestrian crossings and a clear separation between the road and the sidewalk.

The overall atmosphere of the image is bustling and typical of a busy city environment.

[N][                             Run][ 949]: hit eos,avg 4.83 token/s
prompt >> describe this picture
image >> image/ssd_car.jpg
[I][                          Encode][ 539]: image encode time : 773.948975 ms, size : 524288
[I][                             Run][ 625]: input token num : 280, prefill_split_num : 3
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:24
[I][                             Run][ 796]: ttft: 2076.95 ms
The picture shows a busy urban street scene in what appears to be a city center. A red double-decker bus is prominently featured in the foreground, with a large advertisement on its side that reads, "THINGS GET MORE EXITING WHEN YOU SAY 'YES' VirginMoney.co.uk." The bus is driving on the right side of the road, which is typical in the UK.

In the background, there are several pedestrians walking on the sidewalk, and a few cars are visible on the road. The buildings lining the street are modern and have large windows, suggesting a commercial or business district. The street is well-maintained, with clear pedestrian crossings and a clear separation between the road and the sidewalk.

The overall atmosphere of the image is bustling and typical of a busy city environment.

[N][                             Run][ 949]: hit eos,avg 4.83 token/s
提示
以下操作需要停止上一个 tokenizer 服务，使用
CTRL + C
结束运行。
启动视频 tokenizer 解析器
python qwen2_tokenizer_video_308.py --port 12345
python qwen2_tokenizer_video_308.py --port 12345
运行 tokenizer 服务，Host ip 默认为 localhost，端口号设置为 12345，运行后信息如下：
(qwen) m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ python qwen2_tokenizer_video_308.py --port 12345
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151653, 53481, 100158, 99487, 87140, 104597, 151645, 198, 151644, 77091, 198]
510
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:12345
(qwen) m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ python qwen2_tokenizer_video_308.py --port 12345
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151653, 53481, 100158, 99487, 87140, 104597, 151645, 198, 151644, 77091, 198]
510
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:12345
提示
以下操作需要新建一个 raspberrypi 的终端。
设置可执行权限
chmod +x main_axcl_aarch64 run_qwen2_5_vl_video_axcl_aarch64.sh
chmod +x main_axcl_aarch64 run_qwen2_5_vl_video_axcl_aarch64.sh
启动 Qwen2.5-VL 模型 视频推理服务
./run_qwen2_5_vl_video_axcl_aarch64.sh
./run_qwen2_5_vl_video_axcl_aarch64.sh
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ ./run_qwen2_5_vl_video_axcl_aarch64.sh
[I][                            Init][ 162]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151656
  2% | █                                 |   1 /  39 [0.00s<0.12s, 333.33 count/s] tokenizer init ok
100% | ████████████████████████████████ |  39 /  39 [75.71s<77.70s, 0.50 count/s] init post axmodel ok,remain_cmm(3220 MB)
input size: 1
    name: hidden_states [unknown] [unknown]
        1 x 484 x 392 x 3 size:569184

output size: 1
    name: hidden_states_out
        121 x 2048 size:991232

[I][                            Init][ 267]: IMAGE_CONTEXT_TOKEN: 151656, IMAGE_START_TOKEN: 151652
[I][                            Init][ 328]: image encoder output float32

[I][                            Init][ 340]: max_token_len : 1023
[I][                            Init][ 343]: kv_cache_size : 256, kv_cache_num: 1023
[I][                            Init][ 351]: prefill_token_num : 128
[I][                            Init][ 355]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 355]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 355]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 355]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 355]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 359]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|             -1|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[E][                     load_config][ 278]: config file(post_config.json) open failed
[W][                            Init][ 452]: load postprocess config(post_config.json) failed
[I][                            Init][ 456]: LLM init ok
Type
"q"
to
exit
, Ctrl+c to stop current running
prompt >> Describe the content of this video
image >> video
video/frame_0000.jpg
video/frame_0008.jpg
video/frame_0016.jpg
video/frame_0024.jpg
video/frame_0032.jpg
video/frame_0040.jpg
video/frame_0048.jpg
video/frame_0056.jpg
[I][                          Encode][ 539]: image encode time : 1480.802002 ms, size : 991232
[I][                             Run][ 625]: input token num : 511, prefill_split_num : 4
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:127
[I][                             Run][ 796]: ttft: 3032.74 ms
The video depicts two ground squirrels engaging
in
a playful interaction on a rocky path. The squirrels are facing each other, and their front paws are raised, as
if
they are playfully bumping or scratching each other. The background features a scenic mountain landscape with green hills and a clear blue sky, suggesting a sunny day. The squirrels
' fur is a mix of brown, black, and white, and their tails are bushy and fluffy. The overall atmosphere of the video is light-hearted and playful, capturing a moment of natural behavior in a beautiful outdoor setting.

[N][                             Run][ 949]: hit eos,avg 4.86 token/s

prompt >>
m5stack@raspberrypi:~/rsp/Qwen2.5-VL-3B-Instruct $ ./run_qwen2_5_vl_video_axcl_aarch64.sh
[I][                            Init][ 162]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151656
  2% | █                                 |   1 /  39 [0.00s<0.12s, 333.33 count/s] tokenizer init ok
100% | ████████████████████████████████ |  39 /  39 [75.71s<77.70s, 0.50 count/s] init post axmodel ok,remain_cmm(3220 MB)
input size: 1
    name: hidden_states [unknown] [unknown]
        1 x 484 x 392 x 3 size:569184

output size: 1
    name: hidden_states_out
        121 x 2048 size:991232

[I][                            Init][ 267]: IMAGE_CONTEXT_TOKEN: 151656, IMAGE_START_TOKEN: 151652
[I][                            Init][ 328]: image encoder output float32

[I][                            Init][ 340]: max_token_len : 1023
[I][                            Init][ 343]: kv_cache_size : 256, kv_cache_num: 1023
[I][                            Init][ 351]: prefill_token_num : 128
[I][                            Init][ 355]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 355]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 355]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 355]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 355]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 359]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|             -1|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[E][                     load_config][ 278]: config file(post_config.json) open failed
[W][                            Init][ 452]: load postprocess config(post_config.json) failed
[I][                            Init][ 456]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
prompt >> Describe the content of this video
image >> video
video/frame_0000.jpg
video/frame_0008.jpg
video/frame_0016.jpg
video/frame_0024.jpg
video/frame_0032.jpg
video/frame_0040.jpg
video/frame_0048.jpg
video/frame_0056.jpg
[I][                          Encode][ 539]: image encode time : 1480.802002 ms, size : 991232
[I][                             Run][ 625]: input token num : 511, prefill_split_num : 4
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:128
[I][                             Run][ 659]: input_num_token:127
[I][                             Run][ 796]: ttft: 3032.74 ms
The video depicts two ground squirrels engaging in a playful interaction on a rocky path. The squirrels are facing each other, and their front paws are raised, as if they are playfully bumping or scratching each other. The background features a scenic mountain landscape with green hills and a clear blue sky, suggesting a sunny day. The squirrels' fur is a mix of brown, black, and white, and their tails are bushy and fluffy. The overall atmosphere of the video is light-hearted and playful, capturing a moment of natural behavior in a beautiful outdoor setting.

[N][                             Run][ 949]: hit eos,avg 4.86 token/s

prompt >>
模型
量化方式
image encode (ms)
tftt (ms)
token/s
Qwen2.5-3B-VL
w8a16
773.95
558.68
4.81
Next
目录索引
On This Page
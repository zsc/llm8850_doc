# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_ffmpeg

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
FFmpeg
环境准备
AXCL_FFMPEG 动态库存放在
/usr/lib/axcl/ffmpeg
，AXCL_FFMPEG 可执行程序存放在
/usr/bin/axcl/ffmpeg
。
执行 ffmpeg 需要首先设置动态库查找路径，环境变量设置：
export
LD_LIBRARY_PATH=
"/usr/lib/axcl/ffmpeg:
$LD_LIBRARY_PATH
"
;
export LD_LIBRARY_PATH="/usr/lib/axcl/ffmpeg:$LD_LIBRARY_PATH";
如何使用
m5stack@raspberrypi5:~ $ /usr/bin/axcl/ffmpeg/ffmpeg -c:v h264_axdec -i input.mp4 -f rawvideo -pix_fmt yuv420p  output.yuv
m5stack@raspberrypi5:~ $ /usr/bin/axcl/ffmpeg/ffmpeg -c:v h264_axdec -i input.mp4 -f rawvideo -pix_fmt yuv420p  output.yuv
如何重新编译 FFmpeg
SDK FFmpeg 基于 7.1 版本开发，并提供了编译后的 so 和 ffmpeg bin 文件可直接链接和运行。
如果需要重新编译 FFmpeg，按照如下步骤：
从
github
下载 FFmpeg-n7.1.tar.gz，将 FFmpeg-n7.1.tar.gz 拷贝到
axcl/3rdparty/ffmpeg
目录。
解压
tar -zxvf FFmpeg-n7.1.tar.gz
tar -zxvf FFmpeg-n7.1.tar.gz
patch
patch -p3 < FFmpeg-n7.1.patch
patch -p3 < FFmpeg-n7.1.patch
编译
arm64
cd
axcl/3rdparty/ffmpeg
make host=arm64 clean all install
cd axcl/3rdparty/ffmpeg
make host=arm64 clean all install
目标文件路径：
lib: axcl/out/axcl_linux_arm64/lib/ffmpeg
bin: axcl/out/axcl_linux_arm64/bin/ffmpeg
lib: axcl/out/axcl_linux_arm64/lib/ffmpeg
bin: axcl/out/axcl_linux_arm64/bin/ffmpeg
x86
cd
axcl/3rdparty/ffmpeg
make host=x86 clean all install
cd axcl/3rdparty/ffmpeg
make host=x86 clean all install
目标文件路径：
lib: axcl/out/axcl_linux_x86/lib/ffmpeg
bin: axcl/out/axcl_linux_x86/bin/ffmpeg
lib: axcl/out/axcl_linux_x86/lib/ffmpeg
bin: axcl/out/axcl_linux_x86/bin/ffmpeg
Next
目录索引
On This Page
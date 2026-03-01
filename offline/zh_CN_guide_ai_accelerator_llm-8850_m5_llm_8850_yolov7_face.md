# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_yolov7_face

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
YOLOv7-Face
提示
参考
YOLO11章节
获取获取并解压整合包。
运行：
./axcl_demo/axcl_yolov7_face -m axcl_demo/yolov7-face.axmodel -i axcl_demo/selfie.jpg
./axcl_demo/axcl_yolov7_face -m axcl_demo/yolov7-face.axmodel -i axcl_demo/selfie.jpg
运行结果如下：
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolov7_face -m axcl_demo/yolov7-face.axmodel -i axcl_demo/selfie.jpg
--------------------------------------
model file : axcl_demo/yolov7-face.axmodel
image file : axcl_demo/selfie.jpg
img_h, img_w : 640 640
--------------------------------------
axclrtEngineCreateContextt is
done
.
axclrtEngineGetIOInfo is
done
.

grpid: 0

input size: 1
    name:   images
        1 x 640 x 640 x 3

output size: 3
    name:      511
        1 x 80 x 80 x 63

    name:      520
        1 x 40 x 40 x 63

    name:      529
        1 x 20 x 20 x 63

==================================================

Engine push input is
done
.
--------------------------------------
post process cost time:7.76 ms
--------------------------------------
Repeat 1
times
, avg time 12.23 ms, max_time 12.23 ms, min_time 12.23 ms
--------------------------------------
detection num: 277
 0:  91%, [1137,  869, 1283, 1065], face
 0:  91%, [1424,  753, 1570,  949], face
 0:  89%, [1305,  764, 1403,  900], face
 0:  87%, [1738,  786, 1796,  860], face
 0:  86%, [1914,  785, 1981,  865], face
 0:  86%, [ 860,  795,  967,  906], face
 0:  85%, [ 362,  891,  429,  978], face
 0:  85%, [ 280,  790,  335,  852], face
 0:  83%, [1666,  889, 1738,  969], face
 0:  83%, [  53,  869,  131,  955], face
 0:  83%, [ 447,  828,  505,  895], face
 0:  82%, [1586,  735, 1640,  801], face
 0:  82%, [ 455,  941,  528, 1037], face
 0:  81%, [1767,  905, 1834,  978], face
 0:  81%, [ 666,  798,  721,  856], face
 0:  81%, [ 203,  739,  261,  801], face
 0:  81%, [ 274,  874,  335,  953], face
 0:  81%, [  76,  721,  129,  779], face
 0:  81%, [ 462,  729,  512,  787], face
 0:  60%, [ 309,  457,  332,  487], face
 ...
 0:  20%, [1543,  563, 1574,  604], face
--------------------------------------
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolov7_face -m axcl_demo/yolov7-face.axmodel -i axcl_demo/selfie.jpg
--------------------------------------
model file : axcl_demo/yolov7-face.axmodel
image file : axcl_demo/selfie.jpg
img_h, img_w : 640 640
--------------------------------------
axclrtEngineCreateContextt is done.
axclrtEngineGetIOInfo is done.

grpid: 0

input size: 1
    name:   images
        1 x 640 x 640 x 3

output size: 3
    name:      511
        1 x 80 x 80 x 63

    name:      520
        1 x 40 x 40 x 63

    name:      529
        1 x 20 x 20 x 63

==================================================

Engine push input is done.
--------------------------------------
post process cost time:7.76 ms
--------------------------------------
Repeat 1 times, avg time 12.23 ms, max_time 12.23 ms, min_time 12.23 ms
--------------------------------------
detection num: 277
 0:  91%, [1137,  869, 1283, 1065], face
 0:  91%, [1424,  753, 1570,  949], face
 0:  89%, [1305,  764, 1403,  900], face
 0:  87%, [1738,  786, 1796,  860], face
 0:  86%, [1914,  785, 1981,  865], face
 0:  86%, [ 860,  795,  967,  906], face
 0:  85%, [ 362,  891,  429,  978], face
 0:  85%, [ 280,  790,  335,  852], face
 0:  83%, [1666,  889, 1738,  969], face
 0:  83%, [  53,  869,  131,  955], face
 0:  83%, [ 447,  828,  505,  895], face
 0:  82%, [1586,  735, 1640,  801], face
 0:  82%, [ 455,  941,  528, 1037], face
 0:  81%, [1767,  905, 1834,  978], face
 0:  81%, [ 666,  798,  721,  856], face
 0:  81%, [ 203,  739,  261,  801], face
 0:  81%, [ 274,  874,  335,  953], face
 0:  81%, [  76,  721,  129,  779], face
 0:  81%, [ 462,  729,  512,  787], face
 0:  60%, [ 309,  457,  332,  487], face
 ...
 0:  20%, [1543,  563, 1574,  604], face
--------------------------------------
Next
目录索引
On This Page
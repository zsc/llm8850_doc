# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_yolo11

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
YOLO11
基于 Ultralytics YOLO11 系列模型详细的模型导出、量化、编译的流程请参考
《基于 AX650N 部署 YOLO11》
。
获取整合包
并上传树莓派，或在树莓派终端执行以下命令。
下载
wget https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/linux/ax8850_card/axcl_demo.zip
wget https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/linux/ax8850_card/axcl_demo.zip
解压
unzip axcl_demo.zip
unzip axcl_demo.zip
YOLO11x
运行：
./axcl_demo/axcl_yolo11 -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x.axmodel
./axcl_demo/axcl_yolo11 -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x.axmodel
运行结果如下：
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolo11 -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x.axmodel
--------------------------------------
model file : axcl_demo/yolo11x.axmodel
image file : axcl_demo/ssd_horse.jpg
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
    name: /model.23/Concat_output_0
        1 x 80 x 80 x 144

    name: /model.23/Concat_1_output_0
        1 x 40 x 40 x 144

    name: /model.23/Concat_2_output_0
        1 x 20 x 20 x 144

==================================================

Engine push input is
done
.
--------------------------------------
post process cost time:0.88 ms
--------------------------------------
Repeat 1
times
, avg time 24.69 ms, max_time 24.69 ms, min_time 24.69 ms
--------------------------------------
detection num: 6
17:  96%, [ 216,   71,  423,  370], horse
16:  93%, [ 144,  203,  196,  345], dog
 0:  89%, [ 273,   14,  349,  231], person
 2:  88%, [   1,  105,  132,  197], car
 0:  82%, [ 431,  124,  451,  178], person
19:  46%, [ 171,  137,  202,  169], cow
--------------------------------------
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolo11 -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x.axmodel
--------------------------------------
model file : axcl_demo/yolo11x.axmodel
image file : axcl_demo/ssd_horse.jpg
img_h, img_w : 640 640
--------------------------------------
axclrtEngineCreateContextt is done.
axclrtEngineGetIOInfo is done.

grpid: 0

input size: 1
    name:   images
        1 x 640 x 640 x 3

output size: 3
    name: /model.23/Concat_output_0
        1 x 80 x 80 x 144

    name: /model.23/Concat_1_output_0
        1 x 40 x 40 x 144

    name: /model.23/Concat_2_output_0
        1 x 20 x 20 x 144

==================================================

Engine push input is done.
--------------------------------------
post process cost time:0.88 ms
--------------------------------------
Repeat 1 times, avg time 24.69 ms, max_time 24.69 ms, min_time 24.69 ms
--------------------------------------
detection num: 6
17:  96%, [ 216,   71,  423,  370], horse
16:  93%, [ 144,  203,  196,  345], dog
 0:  89%, [ 273,   14,  349,  231], person
 2:  88%, [   1,  105,  132,  197], car
 0:  82%, [ 431,  124,  451,  178], person
19:  46%, [ 171,  137,  202,  169], cow
--------------------------------------
YOLO11x-Seg
运行：
./axcl_demo/axcl_yolo11_seg -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x-seg.axmodel
./axcl_demo/axcl_yolo11_seg -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x-seg.axmodel
运行结果如下：
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolo11_seg -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x-seg.axmodel
--------------------------------------
model file : axcl_demo/yolo11x-seg.axmodel
image file : axcl_demo/ssd_horse.jpg
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

output size: 7
    name: /model.23/Concat_1_output_0
        1 x 80 x 80 x 144

    name: /model.23/Concat_2_output_0
        1 x 40 x 40 x 144

    name: /model.23/Concat_3_output_0
        1 x 20 x 20 x 144

    name: /model.23/cv4.0/cv4.0.2/Conv_output_0
        1 x 80 x 80 x 32

    name: /model.23/cv4.1/cv4.1.2/Conv_output_0
        1 x 40 x 40 x 32

    name: /model.23/cv4.2/cv4.2.2/Conv_output_0
        1 x 20 x 20 x 32

    name:  output1
        1 x 32 x 160 x 160

==================================================

Engine push input is
done
.
--------------------------------------
post process cost time:5.62 ms
--------------------------------------
Repeat 1
times
, avg time 34.72 ms, max_time 34.72 ms, min_time 34.72 ms
--------------------------------------
detection num: 6
17:  96%, [ 216,   71,  423,  370], horse
16:  93%, [ 144,  203,  196,  345], dog
 0:  89%, [ 273,   14,  349,  231], person
 2:  88%, [   1,  105,  132,  197], car
 0:  82%, [ 431,  124,  451,  178], person
19:  46%, [ 171,  137,  202,  169], cow
--------------------------------------
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolo11_seg -i axcl_demo/ssd_horse.jpg -m axcl_demo/yolo11x-seg.axmodel
--------------------------------------
model file : axcl_demo/yolo11x-seg.axmodel
image file : axcl_demo/ssd_horse.jpg
img_h, img_w : 640 640
--------------------------------------
axclrtEngineCreateContextt is done.
axclrtEngineGetIOInfo is done.

grpid: 0

input size: 1
    name:   images
        1 x 640 x 640 x 3

output size: 7
    name: /model.23/Concat_1_output_0
        1 x 80 x 80 x 144

    name: /model.23/Concat_2_output_0
        1 x 40 x 40 x 144

    name: /model.23/Concat_3_output_0
        1 x 20 x 20 x 144

    name: /model.23/cv4.0/cv4.0.2/Conv_output_0
        1 x 80 x 80 x 32

    name: /model.23/cv4.1/cv4.1.2/Conv_output_0
        1 x 40 x 40 x 32

    name: /model.23/cv4.2/cv4.2.2/Conv_output_0
        1 x 20 x 20 x 32

    name:  output1
        1 x 32 x 160 x 160

==================================================

Engine push input is done.
--------------------------------------
post process cost time:5.62 ms
--------------------------------------
Repeat 1 times, avg time 34.72 ms, max_time 34.72 ms, min_time 34.72 ms
--------------------------------------
detection num: 6
17:  96%, [ 216,   71,  423,  370], horse
16:  93%, [ 144,  203,  196,  345], dog
 0:  89%, [ 273,   14,  349,  231], person
 2:  88%, [   1,  105,  132,  197], car
 0:  82%, [ 431,  124,  451,  178], person
19:  46%, [ 171,  137,  202,  169], cow
--------------------------------------
YOLO11x-Pose
运行：
./axcl_demo/axcl_yolo11_pose -i axcl_demo/football.jpg -m axcl_demo/yolo11x-pose.axmodel
./axcl_demo/axcl_yolo11_pose -i axcl_demo/football.jpg -m axcl_demo/yolo11x-pose.axmodel
运行结果如下：
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolo11_pose -i axcl_demo/football.jpg -m axcl_demo/yolo11x-pose.axmodel
--------------------------------------
model file : axcl_demo/yolo11x-pose.axmodel
image file : axcl_demo/football.jpg
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

output size: 6
    name: /model.23/Concat_1_output_0
        1 x 80 x 80 x 65

    name: /model.23/Concat_2_output_0
        1 x 40 x 40 x 65

    name: /model.23/Concat_3_output_0
        1 x 20 x 20 x 65

    name: /model.23/cv4.0/cv4.0.2/Conv_output_0
        1 x 80 x 80 x 51

    name: /model.23/cv4.1/cv4.1.2/Conv_output_0
        1 x 40 x 40 x 51

    name: /model.23/cv4.2/cv4.2.2/Conv_output_0
        1 x 20 x 20 x 51

==================================================

Engine push input is
done
.
--------------------------------------
post process cost time:0.36 ms
--------------------------------------
Repeat 1
times
, avg time 25.09 ms, max_time 25.09 ms, min_time 25.09 ms
--------------------------------------
detection num: 6
 0:  94%, [1350,  337, 1632, 1036], person
 0:  93%, [ 492,  477,  658, 1000], person
 0:  92%, [ 756,  219, 1126, 1154], person
 0:  91%, [   0,  354,  314, 1108], person
 0:  73%, [   0,  530,   81, 1017], person
 0:  54%, [ 142,  589,  239, 1013], person
--------------------------------------
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolo11_pose -i axcl_demo/football.jpg -m axcl_demo/yolo11x-pose.axmodel
--------------------------------------
model file : axcl_demo/yolo11x-pose.axmodel
image file : axcl_demo/football.jpg
img_h, img_w : 640 640
--------------------------------------
axclrtEngineCreateContextt is done.
axclrtEngineGetIOInfo is done.

grpid: 0

input size: 1
    name:   images
        1 x 640 x 640 x 3

output size: 6
    name: /model.23/Concat_1_output_0
        1 x 80 x 80 x 65

    name: /model.23/Concat_2_output_0
        1 x 40 x 40 x 65

    name: /model.23/Concat_3_output_0
        1 x 20 x 20 x 65

    name: /model.23/cv4.0/cv4.0.2/Conv_output_0
        1 x 80 x 80 x 51

    name: /model.23/cv4.1/cv4.1.2/Conv_output_0
        1 x 40 x 40 x 51

    name: /model.23/cv4.2/cv4.2.2/Conv_output_0
        1 x 20 x 20 x 51

==================================================

Engine push input is done.
--------------------------------------
post process cost time:0.36 ms
--------------------------------------
Repeat 1 times, avg time 25.09 ms, max_time 25.09 ms, min_time 25.09 ms
--------------------------------------
detection num: 6
 0:  94%, [1350,  337, 1632, 1036], person
 0:  93%, [ 492,  477,  658, 1000], person
 0:  92%, [ 756,  219, 1126, 1154], person
 0:  91%, [   0,  354,  314, 1108], person
 0:  73%, [   0,  530,   81, 1017], person
 0:  54%, [ 142,  589,  239, 1013], person
--------------------------------------
Next
目录索引
On This Page
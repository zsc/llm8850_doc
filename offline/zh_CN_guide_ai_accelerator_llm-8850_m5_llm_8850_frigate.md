# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_frigate

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
Frigate
Frigate 是一个开源的 NVR，基于实时 AI 物体检测构建。所有处理均在您自己的硬件上本地执行，您的摄像头视频流从不会离开您的家。
手动下载程序
并上传到 raspberrypi5，或者通过以下命令拉取模型仓库。
提示
如果没有安装
git lfs
，先参考
git lfs 安装说明
进行安装。
git
clone
-b rpi-axcl https://huggingface.co/AXERA-TECH/frigate-resource
git clone -b rpi-axcl https://huggingface.co/AXERA-TECH/frigate-resource
文件说明：
m5stack@raspberrypi:~/rsp/frigate-resource $ ls -lh
total 2.8G
-rw-rw-r-- 1 m5stack m5stack  48M Oct  9 16:46 axcl_host_aarch64_V3.6.5_20250908154509_NO4973.deb
-rw-rw-r-- 1 m5stack m5stack  648 Oct  9 16:41 docker-compose.yml
-rw-rw-r-- 1 m5stack m5stack 2.8G Oct  9 16:46 frigate-rpi-axcl-f8f387a.tar
-rw-rw-r-- 1 m5stack m5stack 3.7K Oct  9 16:41 README.md
m5stack@raspberrypi:~/rsp/frigate-resource $ ls -lh
total 2.8G
-rw-rw-r-- 1 m5stack m5stack  48M Oct  9 16:46 axcl_host_aarch64_V3.6.5_20250908154509_NO4973.deb
-rw-rw-r-- 1 m5stack m5stack  648 Oct  9 16:41 docker-compose.yml
-rw-rw-r-- 1 m5stack m5stack 2.8G Oct  9 16:46 frigate-rpi-axcl-f8f387a.tar
-rw-rw-r-- 1 m5stack m5stack 3.7K Oct  9 16:41 README.md
导入 docker 镜像
提示
如果没有安装
docker
，先参考
RaspberryPi docker 安装说明
进行安装。
docker load -i frigate-resource/frigate-rpi-axcl-f8f387a.tar
# 镜像文件可能升级，以实际文件名为准。
docker load -i frigate-resource/frigate-rpi-axcl-f8f387a.tar # 镜像文件可能升级，以实际文件名为准。
准备工作目录
mkdir -p ~/frigate-runtime/{config,storage}
cp frigate-resource/docker-compose.yml ~/frigate-runtime/
mkdir -p ~/frigate-runtime/{config,storage}
cp frigate-resource/docker-compose.yml ~/frigate-runtime/
启动容器
cd
~/frigate-runtime/
docker compose up -d
cd ~/frigate-runtime/
docker compose up -d
通过
https://server_ip:8971
访问 Frigate 管理 Web
提示
默认用户名
admin
默认密码
axera123456
点击设置，配置参数，填入以下内容。go2rtc:部分修改为自己的 IP Camera 地址，保存并重启。
配置示例
#ffmpeg全局变量，必须
ffmpeg:
global_args:
[
"-hide_banner"
,
"-loglevel"
,
"warning"
,
"-threads"
,
"1"
]
output_args:
detect:
[
"-threads"
,
"1"
,
"-f"
,
"rawvideo"
,
"-pix_fmt"
,
"yuv420p"
]
mqtt:
enabled:
false
go2rtc:
streams:
#主码流
road1:
-
rtsp://192.168.20.57:8554/road1.264
#子码流
road1_sub:
-
rtsp://192.168.20.57:8554/road1_sub.264
cameras:
road1:
enabled:
true
ffmpeg:
inputs:
#录制流的路径，这里使用go2rtc中设置的主码流
#调试阶段这里可以使用本地码流文件
-
path:
rtsp://127.0.0.1:8554/road1
roles:
-
record
#检测流的路径，这里使用go2rtc中设置的辅码流
#调试阶段这里可以使用本地码流文件
-
path:
rtsp://127.0.0.1:8554/road1_sub
roles:
-
detect
#preset-rpi-64-h264用于解码h264码流
#preset-rpi-64-h265用于解码h265码流
hwaccel_args:
preset-rpi-64-h264
record:
enabled:
true
#打开检测功能
#若不设置检测宽高，则默认使用检测码流的原生分辨率
detect:
enabled:
true
width:
1280
height:
720
fps:
5
#配置检测引擎使用axengine
detectors:
axengine:
type:
axengine
#配置axengine的目标检测模型
model:
path:
yolov5s_320
width:
320
height:
320
input_pixel_format:
bgr
labelmap_path:
/labelmap/coco-80.txt
#要跟踪的目标类型
objects:
track:
-
person
-
car
-
bicycle
-
motorcycle
version:
0.16
-0
#ffmpeg全局变量，必须
ffmpeg:
  global_args: ["-hide_banner", "-loglevel", "warning", "-threads", "1"]
  output_args:
    detect: ["-threads", "1", "-f", "rawvideo",  "-pix_fmt", "yuv420p"]

mqtt:
  enabled: false

go2rtc:
  streams:
    #主码流
    road1:
      - rtsp://192.168.20.57:8554/road1.264
    #子码流
    road1_sub:
      - rtsp://192.168.20.57:8554/road1_sub.264
cameras:
  road1:
    enabled: true
    ffmpeg:
      inputs:
        #录制流的路径，这里使用go2rtc中设置的主码流
        #调试阶段这里可以使用本地码流文件
        - path: rtsp://127.0.0.1:8554/road1
          roles:
            - record
        #检测流的路径，这里使用go2rtc中设置的辅码流
        #调试阶段这里可以使用本地码流文件
        - path: rtsp://127.0.0.1:8554/road1_sub
          roles:
            - detect
      #preset-rpi-64-h264用于解码h264码流
      #preset-rpi-64-h265用于解码h265码流
      hwaccel_args: preset-rpi-64-h264

record:
  enabled: true
 
#打开检测功能
#若不设置检测宽高，则默认使用检测码流的原生分辨率
detect:
  enabled: true
  width: 1280
  height: 720
  fps: 5
 
#配置检测引擎使用axengine
detectors:
  axengine:
    type: axengine
 
#配置axengine的目标检测模型
model:
  path: yolov5s_320
  width: 320
  height: 320
  input_pixel_format: bgr
  labelmap_path: /labelmap/coco-80.txt
 
#要跟踪的目标类型
objects:
  track:
    - person
    - car
    - bicycle
    - motorcycle
 
version: 0.16-0
可以在设置中预览配置
Next
目录索引
On This Page
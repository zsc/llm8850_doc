# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_sd_demo

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
SD1.5-LLM8850
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
https://huggingface.co/M5Stack/SD1.5-LLM8850
git clone https://huggingface.co/M5Stack/SD1.5-LLM8850
文件说明：
m5stack@raspberrypi5:~/rsp/SD1.5-LLM8850 $ ls -lh
total 92K
-rw-rw-r-- 1 m5stack m5stack  12K Sep 26 11:07 api_10steps.py
-rw-rw-r-- 1 m5stack m5stack  12K Sep 26 11:07 api_server.py
-rw-rw-r-- 1 m5stack m5stack  19K Sep 26 11:07 axengine-0.1.3-py3-none-any.whl
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 26 11:11 client
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 26 11:11 client_jp
-rw-rw-r-- 1 m5stack m5stack  13K Sep 26 11:07 dpm20_infer.py
-rw-rw-r-- 1 m5stack m5stack 1.3K Sep 26 11:07 gen_img.py
drwxrwxr-x 4 m5stack m5stack 4.0K Sep 26 11:08 models
-rw-rw-r-- 1 m5stack m5stack 2.5K Sep 26 11:10 README.md
-rw-rw-r-- 1 m5stack m5stack  112 Sep 26 11:07 requirements.txt
-rw-rw-r-- 1 m5stack m5stack  165 Sep 26 11:07 sd-launch.desktop
-rw-rw-r-- 1 m5stack m5stack 2.4K Sep 26 11:07 sd-launch.sh
m5stack@raspberrypi5:~/rsp/SD1.5-LLM8850 $ ls -lh
total 92K
-rw-rw-r-- 1 m5stack m5stack  12K Sep 26 11:07 api_10steps.py
-rw-rw-r-- 1 m5stack m5stack  12K Sep 26 11:07 api_server.py
-rw-rw-r-- 1 m5stack m5stack  19K Sep 26 11:07 axengine-0.1.3-py3-none-any.whl
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 26 11:11 client
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 26 11:11 client_jp
-rw-rw-r-- 1 m5stack m5stack  13K Sep 26 11:07 dpm20_infer.py
-rw-rw-r-- 1 m5stack m5stack 1.3K Sep 26 11:07 gen_img.py
drwxrwxr-x 4 m5stack m5stack 4.0K Sep 26 11:08 models
-rw-rw-r-- 1 m5stack m5stack 2.5K Sep 26 11:10 README.md
-rw-rw-r-- 1 m5stack m5stack  112 Sep 26 11:07 requirements.txt
-rw-rw-r-- 1 m5stack m5stack  165 Sep 26 11:07 sd-launch.desktop
-rw-rw-r-- 1 m5stack m5stack 2.4K Sep 26 11:07 sd-launch.sh
创建虚拟环境
python -m venv sd
python -m venv sd
激活虚拟环境
source
sd/bin/activate
source sd/bin/activate
安装依赖包
sudo apt install cmake -y
pip install -r requirements.txt
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
sudo apt install cmake -y
pip install -r requirements.txt
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
启动后端
uvicorn api_10steps:app --host 0.0.0.0 --port 7888
uvicorn api_10steps:app --host 0.0.0.0 --port 7888
新建一个终端，启动 Web 界面
source
sd/bin/activate
cd
client && python app.py
source sd/bin/activate
cd client && python app.py
浏览器访问
http://127.0.0.1:5000
选择想要生成的参数或选择随机描述，点击立即生成
Next
目录索引
On This Page
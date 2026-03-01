# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_immich

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
Immich
Immich 是一个开源的自托管照片和视频管理平台，支持自动备份、智能搜索和跨设备访问。
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
https://huggingface.co/AXERA-TECH/immich
git clone https://huggingface.co/AXERA-TECH/immich
文件说明：
m5stack@raspberrypi:~/rsp/immich $ ls -lh
total 421M
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 10 09:12 asset
-rw-rw-r-- 1 m5stack m5stack 421M Oct 10 09:20 ax-immich-server-aarch64.tar.gz
-rw-rw-r-- 1 m5stack m5stack    0 Oct 10 09:12 config.json
-rw-rw-r-- 1 m5stack m5stack 7.6K Oct 10 09:12 docker-deploy.zip
-rw-rw-r-- 1 m5stack m5stack 104K Oct 10 09:12 immich_ml-1.129.0-py3-none-any.whl
-rw-rw-r-- 1 m5stack m5stack 9.4K Oct 10 09:12 README.md
-rw-rw-r-- 1 m5stack m5stack  177 Oct 10 09:12 requirements.txt
m5stack@raspberrypi:~/rsp/immich $ ls -lh
total 421M
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 10 09:12 asset
-rw-rw-r-- 1 m5stack m5stack 421M Oct 10 09:20 ax-immich-server-aarch64.tar.gz
-rw-rw-r-- 1 m5stack m5stack    0 Oct 10 09:12 config.json
-rw-rw-r-- 1 m5stack m5stack 7.6K Oct 10 09:12 docker-deploy.zip
-rw-rw-r-- 1 m5stack m5stack 104K Oct 10 09:12 immich_ml-1.129.0-py3-none-any.whl
-rw-rw-r-- 1 m5stack m5stack 9.4K Oct 10 09:12 README.md
-rw-rw-r-- 1 m5stack m5stack  177 Oct 10 09:12 requirements.txt
导入 docker 镜像
提示
如果没有安装
docker
，先参考
RaspberryPi docker 安装说明
进行安装。
cd
immich
docker load -i ax-immich-server-aarch64.tar.gz
cd immich
docker load -i ax-immich-server-aarch64.tar.gz
准备工作目录
unzip docker-deploy.zip
cp example.env .env
unzip docker-deploy.zip
cp example.env .env
启动容器
docker compose -f docker-compose.yml -f docker-compose.override.yml up -d
docker compose -f docker-compose.yml -f docker-compose.override.yml up -d
启动成功后信息如下：
m5stack@raspberrypi:~/rsp/immich $ docker compose -f docker-compose.yml -f docker-compose.override.yml up -d
WARN[0000] /home/m5stack/rsp/immich/docker-compose.override.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion 
[+] Running 3/3
 ✔ Container immich_postgres  Started                                      1.0s 
 ✔ Container immich_redis     Started                                      0.9s 
 ✔ Container immich_server    Started                                      0.9s
m5stack@raspberrypi:~/rsp/immich $ docker compose -f docker-compose.yml -f docker-compose.override.yml up -d
WARN[0000] /home/m5stack/rsp/immich/docker-compose.override.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion 
[+] Running 3/3
 ✔ Container immich_postgres  Started                                      1.0s 
 ✔ Container immich_redis     Started                                      0.9s 
 ✔ Container immich_server    Started                                      0.9s
创建虚拟环境
python -m venv mich
python -m venv mich
激活虚拟环境
source
mich/bin/activate
source mich/bin/activate
安装依赖包
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
pip install -r requirements.txt
pip install immich_ml-1.129.0-py3-none-any.whl
# 预编译包可能升级，以实际文件名为准。
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
pip install -r requirements.txt
pip install immich_ml-1.129.0-py3-none-any.whl # 预编译包可能升级，以实际文件名为准。
启动 immich_ml 服务
python -m immich_ml
python -m immich_ml
运行后信息如下：
(mich) m5stack@raspberrypi:~/rsp/immich $ python -m immich_ml
[10/10/25 09:50:12] INFO     Starting gunicorn 23.0.0                           
[10/10/25 09:50:12] INFO     Listening at: http://[::]:3003 (8698)              
[10/10/25 09:50:12] INFO     Using worker: immich_ml.config.CustomUvicornWorker 
[10/10/25 09:50:12] INFO     Booting worker with pid: 8699                      
2025-10-10 09:50:13.589360675 [W:onnxruntime:Default, device_discovery.cc:164 DiscoverDevicesForPlatform] GPU device discovery failed: device_discovery.cc:89 ReadFileContents Failed to open file:
"/sys/class/drm/card1/device/vendor"
[INFO] Available providers:  [
'AXCLRTExecutionProvider'
]
/home/m5stack/rsp/immich/mich/lib/python3.11/site-packages/immich_ml/models/clip/cn_vocab.txt
[10/10/25 09:50:16] INFO     Started server process [8699]                      
[10/10/25 09:50:16] INFO     Waiting
for
application startup.                   
[10/10/25 09:50:16] INFO     Created in-memory cache with unloading after 300s  
                             of inactivity.                                     
[10/10/25 09:50:16] INFO     Initialized request thread pool with 4 threads.    
[10/10/25 09:50:16] INFO     Application startup complete.
(mich) m5stack@raspberrypi:~/rsp/immich $ python -m immich_ml
[10/10/25 09:50:12] INFO     Starting gunicorn 23.0.0                           
[10/10/25 09:50:12] INFO     Listening at: http://[::]:3003 (8698)              
[10/10/25 09:50:12] INFO     Using worker: immich_ml.config.CustomUvicornWorker 
[10/10/25 09:50:12] INFO     Booting worker with pid: 8699                      
2025-10-10 09:50:13.589360675 [W:onnxruntime:Default, device_discovery.cc:164 DiscoverDevicesForPlatform] GPU device discovery failed: device_discovery.cc:89 ReadFileContents Failed to open file: "/sys/class/drm/card1/device/vendor"
[INFO] Available providers:  ['AXCLRTExecutionProvider']
/home/m5stack/rsp/immich/mich/lib/python3.11/site-packages/immich_ml/models/clip/cn_vocab.txt
[10/10/25 09:50:16] INFO     Started server process [8699]                      
[10/10/25 09:50:16] INFO     Waiting for application startup.                   
[10/10/25 09:50:16] INFO     Created in-memory cache with unloading after 300s  
                             of inactivity.                                     
[10/10/25 09:50:16] INFO     Initialized request thread pool with 4 threads.    
[10/10/25 09:50:16] INFO     Application startup complete.
在浏览器中输入 Raspberry Pi 的 IP地址和 3003 端口，例如 192.168.20.27:3003
注意，第一次访问需要注册管理员账户，帐号密码保存在本地
配置完成，即可上传图片
第一次需要配置机器学习服务器，参考下图进入配置
URL 填写为 Raspberry Pi 的 IP地址和 3003 端口，例如 192.168.20.27:3003
CLIP 模型如果使用中文搜索，填写为
ViT-L-14-336-CN__axera
如果使用英文搜索填写为
ViT-L-14-336__axera
设置完成后，保存
第一次需要手动进入 Jobs 选项，在 SMART SEARCH 中手动触发
在搜索栏输入图片的描述，即可检索相关的图片
Next
目录索引
On This Page
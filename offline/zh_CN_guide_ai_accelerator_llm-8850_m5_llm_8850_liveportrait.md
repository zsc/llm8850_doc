# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_liveportrait

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
LivePortrait
LivePortrait 是一种基于深度学习的人像驱动生成模型，可将静态人像转换为具有真实表情与动作的动态视频效果。
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
https://huggingface.co/AXERA-TECH/LivePortrait
git clone https://huggingface.co/AXERA-TECH/LivePortrait
文件说明：
m5stack@raspberrypi:~/rsp/LivePortrait $ ls -lh
total 16K
drwxrwxr-x 3 m5stack m5stack 4.0K Aug 13 09:41 assets
-rw-rw-r-- 1 m5stack m5stack    0 Aug 13 09:41 config.json
drwxrwxr-x 5 m5stack m5stack 4.0K Aug 13 09:41 python
-rw-rw-r-- 1 m5stack m5stack 5.7K Aug 13 09:41 README.md
m5stack@raspberrypi:~/rsp/LivePortrait $ ls -lh
total 16K
drwxrwxr-x 3 m5stack m5stack 4.0K Aug 13 09:41 assets
-rw-rw-r-- 1 m5stack m5stack    0 Aug 13 09:41 config.json
drwxrwxr-x 5 m5stack m5stack 4.0K Aug 13 09:41 python
-rw-rw-r-- 1 m5stack m5stack 5.7K Aug 13 09:41 README.md
创建虚拟环境
python -m venv lvpr
python -m venv lvpr
激活虚拟环境
source
lvpr/bin/activate
source lvpr/bin/activate
安装依赖包
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
pip install -r python/requirements.txt
pip install requests tqdm
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
pip install -r python/requirements.txt
pip install requests tqdm
Image
运行：
python ./python/infer.py --
source
./assets/examples/
source
/s0.jpg --driving ./assets/examples/driving/d8.jpg --models ./python/axmodels/ --output-dir ./axmodel_infer
python ./python/infer.py --source ./assets/examples/source/s0.jpg --driving ./assets/examples/driving/d8.jpg --models ./python/axmodels/ --output-dir ./axmodel_infer
运行结果：
(lvpr) m5stack@raspberrypi:~/rsp/LivePortrait $ python ./python/infer.py --
source
./assets/examples/
source
/s0.jpg --driving ./assets/examples/driving/d8.jpg --models ./python/axmodels/ --output-dir ./axmodel_infer
[INFO] Available providers:  [
'AXCLRTExecutionProvider'
]
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 3.3 0f7260e8
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
FaceAnalysisDIY warmup time: 0.237s
LandmarkRunner warmup time: 0.183s
2025-08-13 10:04:42.914 | INFO     | __main__:main:727 - Start making driving motion template...
2025-08-13 10:04:43.782 | INFO     | __main__:main:747 - Prepared pasteback mask
done
.
2025-08-13 10:04:44.565 | INFO     | __main__:main:787 - The output of image-driven portrait animation is an image.
2025-08-13 10:04:50.566 | DEBUG    | __main__:warp_decode:647 - warp time: 5.997s
2025-08-13 10:04:50.902 | INFO     | __main__:main:881 - Animated image: ./axmodel_infer/s0--d8.jpg
2025-08-13 10:04:50.902 | INFO     | __main__:main:882 - Animated image with concat: ./axmodel_infer/s0--d8_concat.jpg
2025-08-13 10:04:50.920 | DEBUG    | __main__:<module>:894 - LivePortrait axmodel infer time: 18.068s
(lvpr) m5stack@raspberrypi:~/rsp/LivePortrait $ python ./python/infer.py --source ./assets/examples/source/s0.jpg --driving ./assets/examples/driving/d8.jpg --models ./python/axmodels/ --output-dir ./axmodel_infer
[INFO] Available providers:  ['AXCLRTExecutionProvider']
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 3.3 0f7260e8
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
FaceAnalysisDIY warmup time: 0.237s
LandmarkRunner warmup time: 0.183s
2025-08-13 10:04:42.914 | INFO     | __main__:main:727 - Start making driving motion template...
2025-08-13 10:04:43.782 | INFO     | __main__:main:747 - Prepared pasteback mask done.
2025-08-13 10:04:44.565 | INFO     | __main__:main:787 - The output of image-driven portrait animation is an image.
2025-08-13 10:04:50.566 | DEBUG    | __main__:warp_decode:647 - warp time: 5.997s
2025-08-13 10:04:50.902 | INFO     | __main__:main:881 - Animated image: ./axmodel_infer/s0--d8.jpg
2025-08-13 10:04:50.902 | INFO     | __main__:main:882 - Animated image with concat: ./axmodel_infer/s0--d8_concat.jpg
2025-08-13 10:04:50.920 | DEBUG    | __main__:<module>:894 - LivePortrait axmodel infer time: 18.068s
原图：
输出：
Video
运行：
python ./python/infer.py --
source
./assets/examples/
source
/s0.jpg --driving ./assets/examples/driving/d0.mp4 --models ./python/axmodels/ --output-dir ./axmodel_infer
python ./python/infer.py --source ./assets/examples/source/s0.jpg --driving ./assets/examples/driving/d0.mp4 --models ./python/axmodels/ --output-dir ./axmodel_infer
运行结果：
(lvpr) m5stack@raspberrypi:~/rsp/LivePortrait $ python ./python/infer.py --
source
./assets/examples/
source
/s0.jpg --driving ./assets/examples/driving/d0.mp4 --models ./python/axmodels/ --output-dir ./axmodel_infer

[INFO] Available providers:  [
'AXCLRTExecutionProvider'
]
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 3.3 0f7260e8
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
FaceAnalysisDIY warmup time: 0.213s
LandmarkRunner warmup time: 0.180s
2025-08-13 10:14:47.779 | INFO     | __main__:main:727 - Start making driving motion template...
2025-08-13 10:15:04.110 | INFO     | __main__:main:747 - Prepared pasteback mask
done
.
2025-08-13 10:15:04.903 | INFO     | __main__:main:785 - The animated video consists of 78 frames.
2025-08-13 10:15:11.468 | DEBUG    | __main__:warp_decode:647 - warp time: 6.561s
2025-08-13 10:25:50.630 | DEBUG    | __main__:warp_decode:647 - warp time: 8.343s
2025-08-13 10:25:51.493 | INFO     | __main__:has_audio_stream:114 - Error occurred
while
probing video: ./assets/examples/driving/d0.mp4, you may need to install ffprobe! (https://ffmpeg.org/download.html) Now
set
audio to
false
!
2025-08-13 10:25:54.608 | INFO     | __main__:main:870 - Animated video: ./axmodel_infer/s0--d0.mp4
2025-08-13 10:25:54.609 | INFO     | __main__:main:871 - Animated video with concat: ./axmodel_infer/s0--d0_concat.mp4
2025-08-13 10:25:54.644 | DEBUG    | __main__:<module>:894 - LivePortrait axmodel infer time: 670.930s
(lvpr) m5stack@raspberrypi:~/rsp/LivePortrait $ python ./python/infer.py --source ./assets/examples/source/s0.jpg --driving ./assets/examples/driving/d0.mp4 --models ./python/axmodels/ --output-dir ./axmodel_infer

[INFO] Available providers:  ['AXCLRTExecutionProvider']
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 3.3 0f7260e8
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 3.3 144960ad
FaceAnalysisDIY warmup time: 0.213s
LandmarkRunner warmup time: 0.180s
2025-08-13 10:14:47.779 | INFO     | __main__:main:727 - Start making driving motion template...
2025-08-13 10:15:04.110 | INFO     | __main__:main:747 - Prepared pasteback mask done.
2025-08-13 10:15:04.903 | INFO     | __main__:main:785 - The animated video consists of 78 frames.
2025-08-13 10:15:11.468 | DEBUG    | __main__:warp_decode:647 - warp time: 6.561s
2025-08-13 10:25:50.630 | DEBUG    | __main__:warp_decode:647 - warp time: 8.343s
2025-08-13 10:25:51.493 | INFO     | __main__:has_audio_stream:114 - Error occurred while probing video: ./assets/examples/driving/d0.mp4, you may need to install ffprobe! (https://ffmpeg.org/download.html) Now set audio to false!
2025-08-13 10:25:54.608 | INFO     | __main__:main:870 - Animated video: ./axmodel_infer/s0--d0.mp4
2025-08-13 10:25:54.609 | INFO     | __main__:main:871 - Animated video with concat: ./axmodel_infer/s0--d0_concat.mp4
2025-08-13 10:25:54.644 | DEBUG    | __main__:<module>:894 - LivePortrait axmodel infer time: 670.930s
原视频：
输出：
Next
目录索引
On This Page
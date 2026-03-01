# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_melotts

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
MeloTTS
本小节只指导如何在 Raspberry Pi 5 上运行预编译好的 MeloTTS 文字转语音示例；
模型转换、示例源码编译请参考
melotts.axcl
。
下载
git
clone
https://github.com/ml-inory/melotts.axcl.git
chmod +x build_aarch64.sh
./build_aarch64.sh
git clone https://github.com/ml-inory/melotts.axcl.git
chmod +x build_aarch64.sh
./build_aarch64.sh
预编译模型
cd
melotts.axcl
./download_models.sh
cd melotts.axcl
./download_models.sh
预编译模型下载：
Hugging Face MeloTTS-Chinese
Hugging Face MeloTTS-English
Hugging Face MeloTTS-Japanese
Hugging Face MeloTTS-Spanish
编译
aarch64 平台
./build_aarch64.sh
./build_aarch64.sh
运行 MeloTTS
在 melotts.axcl 项目根目录下运行：
./install/melotts -s 句子
./install/melotts -s 句子
./install/melotts -e ../MeloTTS-English-ax650/encoder-en.onnx -d ../MeloTTS-English-ax650/decoder-en-au.axmodel -l ../MeloTTS-English-ax650/lexicon-en.txt -t ../MeloTTS-English-ax650/tokens-en.txt --g ../MeloTTS-English-ax650/g-en-au.bin -s
"M5Stack is a leading provider of IoT solutions, committed to providing developers worldwide with convenient and flexible development components and tools. "
./install/melotts -e ../MeloTTS-English-ax650/encoder-en.onnx -d ../MeloTTS-English-ax650/decoder-en-au.axmodel -l ../MeloTTS-English-ax650/lexicon-en.txt -t ../MeloTTS-English-ax650/tokens-en.txt --g ../MeloTTS-English-ax650/g-en-au.bin -s "M5Stack is a leading provider of IoT solutions, committed to providing developers worldwide with convenient and flexible development components and tools. "
运行结果：
m5stack@raspberrypi5:~/melotts.axcl $ ./install/melotts -e ../MeloTTS-English-ax650/encoder-en.onnx -d ../MeloTTS-English-ax650/decoder-en-au.axmodel -l ../MeloTTS-English-ax650/lexicon-en.txt -t ../MeloTTS-English-ax650/tokens-en.txt --g ../MeloTTS-English-ax650/g-en-au.bin -s
"M5Stack is a leading provider of IoT solutions, committed to providing developers worldwide with convenient and flexible development components and tools. "
encoder: ../MeloTTS-English-ax650/encoder-en.onnx
decoder: ../MeloTTS-English-ax650/decoder-en-au.axmodel
lexicon: ../MeloTTS-English-ax650/lexicon-en.txt
token: ../MeloTTS-English-ax650/tokens-en.txt
sentence: M5Stack is a leading provider of IoT solutions, committed to providing developers worldwide with convenient and flexible development components and tools.
wav: output.wav
speed: 0.800000
sample_rate: 44100
Load encoder
Load decoder model
Encoder run take 535.47ms
decoder slice num: 9
Decode slice(1/9) take 40.15ms
Decode slice(2/9) take 39.87ms
Decode slice(3/9) take 39.86ms
Decode slice(4/9) take 39.75ms
Decode slice(5/9) take 40.19ms
Decode slice(6/9) take 39.79ms
Decode slice(7/9) take 39.77ms
Decode slice(8/9) take 39.82ms
Decode slice(9/9) take 40.34ms
Saved audio to output.wav
m5stack@raspberrypi5:~/melotts.axcl $ ./install/melotts -e ../MeloTTS-English-ax650/encoder-en.onnx -d ../MeloTTS-English-ax650/decoder-en-au.axmodel -l ../MeloTTS-English-ax650/lexicon-en.txt -t ../MeloTTS-English-ax650/tokens-en.txt --g ../MeloTTS-English-ax650/g-en-au.bin -s "M5Stack is a leading provider of IoT solutions, committed to providing developers worldwide with convenient and flexible development components and tools. "
encoder: ../MeloTTS-English-ax650/encoder-en.onnx
decoder: ../MeloTTS-English-ax650/decoder-en-au.axmodel
lexicon: ../MeloTTS-English-ax650/lexicon-en.txt
token: ../MeloTTS-English-ax650/tokens-en.txt
sentence: M5Stack is a leading provider of IoT solutions, committed to providing developers worldwide with convenient and flexible development components and tools.
wav: output.wav
speed: 0.800000
sample_rate: 44100
Load encoder
Load decoder model
Encoder run take 535.47ms
decoder slice num: 9
Decode slice(1/9) take 40.15ms
Decode slice(2/9) take 39.87ms
Decode slice(3/9) take 39.86ms
Decode slice(4/9) take 39.75ms
Decode slice(5/9) take 40.19ms
Decode slice(6/9) take 39.79ms
Decode slice(7/9) take 39.77ms
Decode slice(8/9) take 39.82ms
Decode slice(9/9) take 40.34ms
Saved audio to output.wav
Next
目录索引
On This Page
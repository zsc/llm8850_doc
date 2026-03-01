# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_cosy_voice2_api

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
CosyVoice2-API
我们提供一套兼容 OpenAI API 的使用方式，只需要安装 StackFlow 包即可。
准备工作
参考
RaspberryPi & LLM8850 软件包获取教程
，完成以下模型包和软件包的安装。
sudo apt install lib-llm llm-sys llm-cosy-voice llm-openai-api
sudo apt install lib-llm llm-sys llm-cosy-voice llm-openai-api
sudo apt install llm-model-cosyvoice2-0.5b-axcl
sudo apt install llm-model-cosyvoice2-0.5b-axcl
注意
每次安装新模型后，需要手动执行
sudo systemctl restart llm-openai-api
更新模型列表。
注意
CosyVoice2 是一个基于 LLM 的语音生成模型，能够合成自然流畅的语音，但由于资源或设计限制，每次生成的音频长度有限。当前版本生成的音频最大长度为 27s，第一次加载模型较慢，请耐心等待。
Curl 调用
curl http://127.0.0.1:8000/v1/audio/speech \
  -H
"Content-Type: application/json"
\
  -d
'{
    "model": "CosyVoice2-0.5B-axcl",
    "response_format": "wav",
    "input": "君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。人生得意须尽欢，莫使金樽空对月。天生我材必有用，千金散尽还复来。"
  }'
\
  -o output.wav
curl http://127.0.0.1:8000/v1/audio/speech \
  -H "Content-Type: application/json" \
  -d '{
    "model": "CosyVoice2-0.5B-axcl",
    "response_format": "wav",
    "input": "君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。人生得意须尽欢，莫使金樽空对月。天生我材必有用，千金散尽还复来。"
  }' \
  -o output.wav
Python 调用
from
pathlib
import
Path
from
openai
import
OpenAI

client = OpenAI(
    api_key=
"sk-"
,
    base_url=
"http://127.0.0.1:8000/v1"
)

speech_file_path = Path(__file__).parent /
"output.wav"
with
client.audio.speech.with_streaming_response.create(
  model=
"CosyVoice2-0.5B-axcl"
,
  voice=
"prompt_data"
,
  response_format=
"wav"
,
input
=
'君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。人生得意须尽欢，莫使金樽空对月。天生我材必有用，千金散尽还复来。'
,
)
as
response:
  response.stream_to_file(speech_file_path)
from pathlib import Path
from openai import OpenAI

client = OpenAI(
    api_key="sk-",
    base_url="http://127.0.0.1:8000/v1"
)

speech_file_path = Path(__file__).parent / "output.wav"
with client.audio.speech.with_streaming_response.create(
  model="CosyVoice2-0.5B-axcl",
  voice="prompt_data",
  response_format="wav",
  input='君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。人生得意须尽欢，莫使金樽空对月。天生我材必有用，千金散尽还复来。',
) as response:
  response.stream_to_file(speech_file_path)
音色克隆
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
--recurse-submodules https://huggingface.co/M5Stack/CosyVoice2-scripts
git clone --recurse-submodules https://huggingface.co/M5Stack/CosyVoice2-scripts
文件说明
m5stack@raspberrypi:~/rsp/CosyVoice2-scripts $ ls -lh
total 28K
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  6 15:18 asset
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  6 15:18 CosyVoice-BlankEN
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  6 15:19 frontend-onnx
drwxrwxr-x 3 m5stack m5stack 4.0K Nov  6 15:18 pengzhendong
-rw-rw-r-- 1 m5stack m5stack   24 Nov  6 15:18 README.md
-rw-rw-r-- 1 m5stack m5stack  103 Nov  6 15:18 requirements.txt
drwxrwxr-x 3 m5stack m5stack 4.0K Nov  6 15:18 scripts
m5stack@raspberrypi:~/rsp/CosyVoice2-scripts $ ls -lh
total 28K
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  6 15:18 asset
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  6 15:18 CosyVoice-BlankEN
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  6 15:19 frontend-onnx
drwxrwxr-x 3 m5stack m5stack 4.0K Nov  6 15:18 pengzhendong
-rw-rw-r-- 1 m5stack m5stack   24 Nov  6 15:18 README.md
-rw-rw-r-- 1 m5stack m5stack  103 Nov  6 15:18 requirements.txt
drwxrwxr-x 3 m5stack m5stack 4.0K Nov  6 15:18 scripts
创建虚拟环境
python -m venv cosyvoice
python -m venv cosyvoice
激活虚拟环境
source
cosyvoice/bin/activate
source cosyvoice/bin/activate
安装依赖包
pip install -r requirements.txt
pip install -r requirements.txt
运行 process_prompt 脚本
python3 scripts/process_prompt.py --prompt_text  asset/zh_woman1.txt --prompt_speech asset/zh_woman1.wav --output zh_woman1
python3 scripts/process_prompt.py --prompt_text  asset/zh_woman1.txt --prompt_speech asset/zh_woman1.wav --output zh_woman1
成功生成音频特征文件
(cosyvoice) m5stack@raspberrypi:~/rsp/CosyVoice2-scripts $ python3 scripts/process_prompt.py --prompt_text  asset/zh_woman1.txt --prompt_speech asset/zh_woman1.wav --output zh_woman1
2025-11-06 15:54:43.619688866 [W:onnxruntime:Default, device_discovery.cc:164 DiscoverDevicesForPlatform] GPU device discovery failed: device_discovery.cc:89 ReadFileContents Failed to open file:
"/sys/class/drm/card1/device/vendor"
prompt_text 希望你以后能够做的比我还好呦。
fmax 8000
prompt speech token size: torch.Size([1, 87])
(cosyvoice) m5stack@raspberrypi:~/rsp/CosyVoice2-scripts $ python3 scripts/process_prompt.py --prompt_text  asset/zh_woman1.txt --prompt_speech asset/zh_woman1.wav --output zh_woman1
2025-11-06 15:54:43.619688866 [W:onnxruntime:Default, device_discovery.cc:164 DiscoverDevicesForPlatform] GPU device discovery failed: device_discovery.cc:89 ReadFileContents Failed to open file: "/sys/class/drm/card1/device/vendor"
prompt_text 希望你以后能够做的比我还好呦。
fmax 8000
prompt speech token size: torch.Size([1, 87])
复制 'zh_woman1' 文件到模型目录，并重新初始化模型。
cp -r zh_woman1 /opt/m5stack/data/CosyVoice2-0.5B-axcl/
cp -r zh_woman1 /opt/m5stack/data/CosyVoice2-0.5B-axcl/
sudo systemctl restart llm-sys
# 重置模型配置
sudo systemctl restart llm-sys # 重置模型配置
提示
如果想替换默认克隆音色，修改
/opt/m5stack/data/models/mode_CosyVoice2-0.5B-axcl.json
文件中的
prompt_dir
字段为替换的目录即可。每次替换音色需要重新初始化模型。
Curl 调用
curl http://127.0.0.1:8000/v1/audio/speech \
  -H
"Content-Type: application/json"
\
  -d
'{
    "model": "CosyVoice2-0.5B-axcl",
    "voice": "zh_woman1",
    "response_format": "wav",
    "input": "君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。人生得意须尽欢，莫使金樽空对月。天生我材必有用，千金散尽还复来。"
  }'
\
  -o output.wav
curl http://127.0.0.1:8000/v1/audio/speech \
  -H "Content-Type: application/json" \
  -d '{
    "model": "CosyVoice2-0.5B-axcl",
    "voice": "zh_woman1",
    "response_format": "wav",
    "input": "君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。人生得意须尽欢，莫使金樽空对月。天生我材必有用，千金散尽还复来。"
  }' \
  -o output.wav
Python 调用
from
pathlib
import
Path
from
openai
import
OpenAI

client = OpenAI(
    api_key=
"sk-"
,
    base_url=
"http://127.0.0.1:8000/v1"
)

speech_file_path = Path(__file__).parent /
"output.wav"
with
client.audio.speech.with_streaming_response.create(
  model=
"CosyVoice2-0.5B-axcl"
,
  voice=
"zh_woman1"
,
  response_format=
"wav"
,
input
=
'君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。人生得意须尽欢，莫使金樽空对月。天生我材必有用，千金散尽还复来。'
,
)
as
response:
  response.stream_to_file(speech_file_path)
from pathlib import Path
from openai import OpenAI

client = OpenAI(
    api_key="sk-",
    base_url="http://127.0.0.1:8000/v1"
)

speech_file_path = Path(__file__).parent / "output.wav"
with client.audio.speech.with_streaming_response.create(
  model="CosyVoice2-0.5B-axcl",
  voice="zh_woman1",
  response_format="wav",
  input='君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。人生得意须尽欢，莫使金樽空对月。天生我材必有用，千金散尽还复来。',
) as response:
  response.stream_to_file(speech_file_path)
Next
目录索引
On This Page
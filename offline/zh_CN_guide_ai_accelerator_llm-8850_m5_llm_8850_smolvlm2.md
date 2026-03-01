# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_smolvlm2

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
SmolVLM2-500M-Video-Instruct
SmolVLM2-500M-Video-Instruct 是一款轻量级多模态视频语言模型，能够理解和生成基于视频内容的文本，并支持指令式交互。
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
https://huggingface.co/AXERA-TECH/SmolVLM2-500M-Video-Instruct
git clone https://huggingface.co/AXERA-TECH/SmolVLM2-500M-Video-Instruct
文件说明：
m5stack@raspberrypi:~/rsp/SmolVLM2-500M-Video-Instruct $ ls -lh
total 40K
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 assets
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 09:12 config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 embeds
-rw-rw-r-- 1 m5stack m5stack  10K Aug 12 09:12 infer_axmodel.py
-rw-rw-r-- 1 m5stack m5stack 2.5K Aug 12 09:12 README.md
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 smolvlm2_axmodel
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 smolvlm2_tokenizer
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 utils
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:13 vit_model
m5stack@raspberrypi:~/rsp/SmolVLM2-500M-Video-Instruct $ ls -lh
total 40K
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 assets
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 09:12 config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 embeds
-rw-rw-r-- 1 m5stack m5stack  10K Aug 12 09:12 infer_axmodel.py
-rw-rw-r-- 1 m5stack m5stack 2.5K Aug 12 09:12 README.md
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 smolvlm2_axmodel
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 smolvlm2_tokenizer
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:12 utils
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 09:13 vit_model
创建虚拟环境
python -m venv smolvlm
python -m venv smolvlm
激活虚拟环境
source
smolvlm/bin/activate
source smolvlm/bin/activate
安装依赖包
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
pip install transformers torch torchvision tqdm pillow num2words onnx onnxruntime
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
pip install transformers torch torchvision tqdm pillow num2words onnx onnxruntime
运行
python infer_axmodel.py --axmodel_path smolvlm2_axmodel/ --vit_model vit_model/vision_model.axmodel --hf_model smolvlm2_tokenizer/ -i assets/bee.jpg
python infer_axmodel.py --axmodel_path smolvlm2_axmodel/ --vit_model vit_model/vision_model.axmodel --hf_model smolvlm2_tokenizer/ -i assets/bee.jpg
测试图片：
运行结果：
(smolvlm) m5stack@raspberrypi:~/rsp/SmolVLM2-500M-Video-Instruct $ python infer_axmodel.py --axmodel_path smolvlm2_axmodel/ --vit_model vit_model/vision_model.axmodel --hf_model smolvlm2_tokenizer/ -i assets/bee.jpg
[INFO] Available providers:  [
'AXCLRTExecutionProvider'
]
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 4.1-patch1-dirty 59be8f11-dirty
You have video processor config saved
in
`preprocessor.json` file
which
is deprecated. Video processor configs should be saved
in
their own `video_preprocessor.json` file. You can rename the file or load and save the processor back
which
renames it automatically. Loading from `preprocessor.json` will be removed
in
v5.0.
Init InferenceSession:   0%|                                                                                       | 0/32 [00:00<?, ?it/s][INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 4.1-patch1-dirty 59be8f11-dirty
Init InferenceSession: 100%|██████████████████████████████████████████████████████████████████████████████| 32/32 [00:10<00:00,  2.98it/s]
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 4.1-patch1-dirty 59be8f11-dirty
Model loaded successfully!
slice_indices: [0, 1, 2, 3, 4, 5, 6, 7, 8]
Slice prefill
done
: 0
Slice prefill
done
: 1
Slice prefill
done
: 2
Slice prefill
done
: 3
Slice prefill
done
: 4
Slice prefill
done
: 5
Slice prefill
done
: 6
Slice prefill
done
: 7
Slice prefill
done
: 8
answer >>  The image depicts a close-up view of a pink flower with a bee on it. The bee,
which
appears to be a bumblebee, is perched on the flower
's center, which is surrounded by a cluster of other flowers. The bee is in the process of collecting nectar from the flower, which is a common behavior for bees. The flower itself has a yellow center with a cluster of yellow stamens surrounding it. The petals of the flower are a vibrant shade of pink, and the bee is positioned very close to the camera, making it the focal point of the image. The background is slightly blurred, but it appears to be a garden or a field with other flowers and plants, contributing to the overall natural setting of the image.
(smolvlm) m5stack@raspberrypi:~/rsp/SmolVLM2-500M-Video-Instruct $ python infer_axmodel.py --axmodel_path smolvlm2_axmodel/ --vit_model vit_model/vision_model.axmodel --hf_model smolvlm2_tokenizer/ -i assets/bee.jpg
[INFO] Available providers:  ['AXCLRTExecutionProvider']
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 4.1-patch1-dirty 59be8f11-dirty
You have video processor config saved in `preprocessor.json` file which is deprecated. Video processor configs should be saved in their own `video_preprocessor.json` file. You can rename the file or load and save the processor back which renames it automatically. Loading from `preprocessor.json` will be removed in v5.0.
Init InferenceSession:   0%|                                                                                       | 0/32 [00:00<?, ?it/s][INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 4.1-patch1-dirty 59be8f11-dirty
Init InferenceSession: 100%|██████████████████████████████████████████████████████████████████████████████| 32/32 [00:10<00:00,  2.98it/s]
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 4.1-patch1-dirty 59be8f11-dirty
Model loaded successfully!
slice_indices: [0, 1, 2, 3, 4, 5, 6, 7, 8]
Slice prefill done: 0
Slice prefill done: 1
Slice prefill done: 2
Slice prefill done: 3
Slice prefill done: 4
Slice prefill done: 5
Slice prefill done: 6
Slice prefill done: 7
Slice prefill done: 8
answer >>  The image depicts a close-up view of a pink flower with a bee on it. The bee, which appears to be a bumblebee, is perched on the flower's center, which is surrounded by a cluster of other flowers. The bee is in the process of collecting nectar from the flower, which is a common behavior for bees. The flower itself has a yellow center with a cluster of yellow stamens surrounding it. The petals of the flower are a vibrant shade of pink, and the bee is positioned very close to the camera, making it the focal point of the image. The background is slightly blurred, but it appears to be a garden or a field with other flowers and plants, contributing to the overall natural setting of the image.
Next
目录索引
On This Page
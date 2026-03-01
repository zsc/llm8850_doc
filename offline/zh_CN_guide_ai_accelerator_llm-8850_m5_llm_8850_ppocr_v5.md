# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_ppocr_v5

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
PP-OCRv5
PP-OCRv5 是PP-OCR新一代文字识别解决方案，该方案聚焦于多场景、多文字类型的文字识别。在文字类型方面，PP-OCRv5支持简体中文、中文拼音、繁体中文、英文、日文5大主流文字类型，在场景方面，PP-OCRv5升级了中英复杂手写体、竖排文本、生僻字等多种挑战性场景的识别能力。
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
https://huggingface.co/AXERA-TECH/PPOCR_v5
git clone https://huggingface.co/AXERA-TECH/PPOCR_v5
文件说明：
m5stack@raspberrypi:~/rsp/PPOCR_v5 $ ls -lh
total 32M
-rw-rw-r-- 1 m5stack m5stack  48K Oct 20 10:40 11.jpg
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 20 10:40 ax620e
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 20 10:40 ax650
-rw-rw-r-- 1 m5stack m5stack 1.3K Oct 20 10:35 cls.json
-rw-rw-r-- 1 m5stack m5stack 958K Oct 20 10:38 cls_mobile_sim_static.onnx
-rw-rw-r-- 1 m5stack m5stack    0 Oct 20 10:35 config.json
-rw-rw-r-- 1 m5stack m5stack 1.2K Oct 20 10:35 det.json
-rw-rw-r-- 1 m5stack m5stack 4.6M Oct 20 10:38 det_mobile_sim_static.onnx
-rw-rw-r-- 1 m5stack m5stack  21K Oct 20 10:35 infer_axmodel.py
-rw-rw-r-- 1 m5stack m5stack  21K Oct 20 10:35 infer_onnx.py
-rw-rw-r-- 1 m5stack m5stack  73K Oct 20 10:35 ppocrv5_dict.txt
-rw-rw-r-- 1 m5stack m5stack 4.4K Oct 20 10:35 README.md
-rw-rw-r-- 1 m5stack m5stack 1.3K Oct 20 10:35 rec.json
-rw-rw-r-- 1 m5stack m5stack  16M Oct 20 10:38 rec_mobile_sim_static.onnx
-rw-rw-r-- 1 m5stack m5stack 121K Oct 20 10:40 res_ax.jpg
-rw-rw-r-- 1 m5stack m5stack 121K Oct 20 10:40 res_onnx.jpg
-rw-rw-r-- 1 m5stack m5stack  11M Oct 20 10:36 simfang.ttf
m5stack@raspberrypi:~/rsp/PPOCR_v5 $ ls -lh
total 32M
-rw-rw-r-- 1 m5stack m5stack  48K Oct 20 10:40 11.jpg
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 20 10:40 ax620e
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 20 10:40 ax650
-rw-rw-r-- 1 m5stack m5stack 1.3K Oct 20 10:35 cls.json
-rw-rw-r-- 1 m5stack m5stack 958K Oct 20 10:38 cls_mobile_sim_static.onnx
-rw-rw-r-- 1 m5stack m5stack    0 Oct 20 10:35 config.json
-rw-rw-r-- 1 m5stack m5stack 1.2K Oct 20 10:35 det.json
-rw-rw-r-- 1 m5stack m5stack 4.6M Oct 20 10:38 det_mobile_sim_static.onnx
-rw-rw-r-- 1 m5stack m5stack  21K Oct 20 10:35 infer_axmodel.py
-rw-rw-r-- 1 m5stack m5stack  21K Oct 20 10:35 infer_onnx.py
-rw-rw-r-- 1 m5stack m5stack  73K Oct 20 10:35 ppocrv5_dict.txt
-rw-rw-r-- 1 m5stack m5stack 4.4K Oct 20 10:35 README.md
-rw-rw-r-- 1 m5stack m5stack 1.3K Oct 20 10:35 rec.json
-rw-rw-r-- 1 m5stack m5stack  16M Oct 20 10:38 rec_mobile_sim_static.onnx
-rw-rw-r-- 1 m5stack m5stack 121K Oct 20 10:40 res_ax.jpg
-rw-rw-r-- 1 m5stack m5stack 121K Oct 20 10:40 res_onnx.jpg
-rw-rw-r-- 1 m5stack m5stack  11M Oct 20 10:36 simfang.ttf
创建虚拟环境
python -m venv ppocr
python -m venv ppocr
激活虚拟环境
source
ppocr/bin/activate
source ppocr/bin/activate
安装依赖包
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
pip install -r requirements.txt
pip install https://github.com/AXERA-TECH/pyaxengine/releases/download/0.1.3.rc2/axengine-0.1.3-py3-none-any.whl
pip install -r requirements.txt
运行：
python infer_axmodel.py --det_model_dir ./ax650/det_npu3.axmodel --rec_model_dir ./ax650/rec_npu3.axmodel --cls_model_dir ./ax650/cls_npu3.axmodel
python infer_axmodel.py --det_model_dir ./ax650/det_npu3.axmodel --rec_model_dir ./ax650/rec_npu3.axmodel --cls_model_dir ./ax650/cls_npu3.axmodel
运行结果：
(ppocr) m5stack@raspberrypi:~/rsp/PPOCR_v5 $ python infer_axmodel.py \
  --det_model_dir ./ax650/det_npu3.axmodel \
  --rec_model_dir ./ax650/rec_npu3.axmodel \
  --cls_model_dir ./ax650/cls_npu3.axmodel
[INFO] Available providers:  [
'AXCLRTExecutionProvider'
]
[INFO] Available providers: [
'AXCLRTExecutionProvider'
]
[INFO] 使用 provider: AXCLRTExecutionProvider
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 4.2 b98901c3
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 4.2 b98901c3
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU
type
: VNPUType.DISABLED
[INFO] Compiler version: 4.2 b98901c3
[[[22.0, 32.0], [307.0, 32.0], [307.0, 77.0], [22.0, 77.0]], (
'纯臻营养护发素'
, 0.9881175756454468)]
[[[24.0, 80.0], [174.0, 80.0], [174.0, 105.0], [24.0, 105.0]], (
'产品信息/参数'
, 0.9941993951797485)]
[[[25.0, 110.0], [333.0, 110.0], [333.0, 135.0], [25.0, 135.0]], (
'(45元/每公斤，100公斤起订）'
, 0.9549185633659363)]
[[[24.0, 140.0], [283.0, 142.0], [283.0, 167.0], [24.0, 165.0]], (
'每瓶22元，1000瓶起订）'
, 0.9522098898887634)]
[[[23.0, 175.0], [302.0, 174.0], [302.0, 197.0], [23.0, 198.0]], (
'【品牌】：代加工方式/OEMODM'
, 0.98729008436203)]
[[[24.0, 206.0], [235.0, 208.0], [235.0, 229.0], [24.0, 228.0]], (
'【品名】：纯臻营养护发素'
, 0.9895920753479004)]
[[[26.0, 238.0], [242.0, 238.0], [242.0, 259.0], [26.0, 259.0]], (
'【产品编号】：YM-X-3011'
, 0.9853904843330383)]
[[[412.0, 233.0], [430.0, 233.0], [430.0, 303.0], [412.0, 303.0]], (
'ODMOEM'
, 0.8154547810554504)]
[[[24.0, 269.0], [181.0, 268.0], [181.0, 289.0], [25.0, 290.0]], (
'【净含量】：220ml'
, 0.9779437780380249)]
[[[24.0, 300.0], [253.0, 301.0], [253.0, 322.0], [24.0, 321.0]], (
'【适用人群】：适合所有肤质'
, 0.9893492460250854)]
[[[24.0, 331.0], [345.0, 332.0], [345.0, 354.0], [24.0, 352.0]], (
'【主要成分】：鲸蜡硬脂醇、燕麦β-葡聚'
, 0.9715114235877991)]
[[[26.0, 364.0], [283.0, 364.0], [283.0, 384.0], [26.0, 384.0]], (
'糖、椰油酰胺丙基甜菜碱、泛醌'
, 0.9863923192024231)]
[[[367.0, 366.0], [476.0, 366.0], [476.0, 388.0], [367.0, 388.0]], (
'(成品包材)'
, 0.8738409876823425)]
[[[25.0, 394.0], [362.0, 394.0], [362.0, 416.0], [25.0, 416.0]], (
'【主要功能】：可紧致头发磷层，从而达到'
, 0.9911136627197266)]
[[[27.0, 426.0], [373.0, 426.0], [373.0, 447.0], [27.0, 447.0]], (
'即时持久改善头发光泽的效果，给干燥的头'
, 0.9935663342475891)]
[[[26.0, 457.0], [137.0, 457.0], [137.0, 478.0], [26.0, 478.0]], (
'发足够的滋养'
, 0.9879047274589539)]
(ppocr) m5stack@raspberrypi:~/rsp/PPOCR_v5 $ python infer_axmodel.py \
  --det_model_dir ./ax650/det_npu3.axmodel \
  --rec_model_dir ./ax650/rec_npu3.axmodel \
  --cls_model_dir ./ax650/cls_npu3.axmodel
[INFO] Available providers:  ['AXCLRTExecutionProvider']
[INFO] Available providers: ['AXCLRTExecutionProvider']
[INFO] 使用 provider: AXCLRTExecutionProvider
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 4.2 b98901c3
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 4.2 b98901c3
[INFO] Using provider: AXCLRTExecutionProvider
[INFO] SOC Name: AX650N
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Compiler version: 4.2 b98901c3
[[[22.0, 32.0], [307.0, 32.0], [307.0, 77.0], [22.0, 77.0]], ('纯臻营养护发素', 0.9881175756454468)]
[[[24.0, 80.0], [174.0, 80.0], [174.0, 105.0], [24.0, 105.0]], ('产品信息/参数', 0.9941993951797485)]
[[[25.0, 110.0], [333.0, 110.0], [333.0, 135.0], [25.0, 135.0]], ('(45元/每公斤，100公斤起订）', 0.9549185633659363)]
[[[24.0, 140.0], [283.0, 142.0], [283.0, 167.0], [24.0, 165.0]], ('每瓶22元，1000瓶起订）', 0.9522098898887634)]
[[[23.0, 175.0], [302.0, 174.0], [302.0, 197.0], [23.0, 198.0]], ('【品牌】：代加工方式/OEMODM', 0.98729008436203)]
[[[24.0, 206.0], [235.0, 208.0], [235.0, 229.0], [24.0, 228.0]], ('【品名】：纯臻营养护发素', 0.9895920753479004)]
[[[26.0, 238.0], [242.0, 238.0], [242.0, 259.0], [26.0, 259.0]], ('【产品编号】：YM-X-3011', 0.9853904843330383)]
[[[412.0, 233.0], [430.0, 233.0], [430.0, 303.0], [412.0, 303.0]], ('ODMOEM', 0.8154547810554504)]
[[[24.0, 269.0], [181.0, 268.0], [181.0, 289.0], [25.0, 290.0]], ('【净含量】：220ml', 0.9779437780380249)]
[[[24.0, 300.0], [253.0, 301.0], [253.0, 322.0], [24.0, 321.0]], ('【适用人群】：适合所有肤质', 0.9893492460250854)]
[[[24.0, 331.0], [345.0, 332.0], [345.0, 354.0], [24.0, 352.0]], ('【主要成分】：鲸蜡硬脂醇、燕麦β-葡聚', 0.9715114235877991)]
[[[26.0, 364.0], [283.0, 364.0], [283.0, 384.0], [26.0, 384.0]], ('糖、椰油酰胺丙基甜菜碱、泛醌', 0.9863923192024231)]
[[[367.0, 366.0], [476.0, 366.0], [476.0, 388.0], [367.0, 388.0]], ('(成品包材)', 0.8738409876823425)]
[[[25.0, 394.0], [362.0, 394.0], [362.0, 416.0], [25.0, 416.0]], ('【主要功能】：可紧致头发磷层，从而达到', 0.9911136627197266)]
[[[27.0, 426.0], [373.0, 426.0], [373.0, 447.0], [27.0, 447.0]], ('即时持久改善头发光泽的效果，给干燥的头', 0.9935663342475891)]
[[[26.0, 457.0], [137.0, 457.0], [137.0, 478.0], [26.0, 478.0]], ('发足够的滋养', 0.9879047274589539)]
Next
目录索引
On This Page
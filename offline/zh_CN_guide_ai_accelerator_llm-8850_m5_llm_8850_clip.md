# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_clip

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
CLIP
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
https://huggingface.co/AXERA-TECH/LibCLIP
git clone https://huggingface.co/AXERA-TECH/LibCLIP
文件说明
m5stack@raspberrypi:~/rsp/LibCLIP $ ls -lh
total 157M
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 11 09:09 cnclip
-rw-rw-r-- 1 m5stack m5stack 156M Aug 11 09:08 coco_1000.tar
-rw-rw-r-- 1 m5stack m5stack 3.8K Aug 11 09:08 config.json
-rw-rw-r-- 1 m5stack m5stack 779K Aug 11 09:08 gradio_01.png
drwxrwxr-x 5 m5stack m5stack 4.0K Aug 11 09:08 install
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 11 09:08 pyclip
-rw-rw-r-- 1 m5stack m5stack 6.0K Aug 11 09:08 README.md
m5stack@raspberrypi:~/rsp/LibCLIP $ ls -lh
total 157M
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 11 09:09 cnclip
-rw-rw-r-- 1 m5stack m5stack 156M Aug 11 09:08 coco_1000.tar
-rw-rw-r-- 1 m5stack m5stack 3.8K Aug 11 09:08 config.json
-rw-rw-r-- 1 m5stack m5stack 779K Aug 11 09:08 gradio_01.png
drwxrwxr-x 5 m5stack m5stack 4.0K Aug 11 09:08 install
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 11 09:08 pyclip
-rw-rw-r-- 1 m5stack m5stack 6.0K Aug 11 09:08 README.md
创建虚拟环境
python -m venv clip
python -m venv clip
激活虚拟环境
source
clip/bin/activate
source clip/bin/activate
安装依赖包
pip install -r pyclip/requirements.txt
pip install -r pyclip/requirements.txt
设置环境变量
export
LD_PRELOAD=/usr/lib/
export LD_PRELOAD=/usr/lib/
复制动态库
cp install/lib/aarch64/libclip.so pyclip/
cp install/lib/aarch64/libclip.so pyclip/
解压测试图片
tar xf coco_1000.tar
tar xf coco_1000.tar
启动 Web 服务
python pyclip/gradio_example.py --ienc cnclip/cnclip_vit_l14_336px_vision_u16u8.axmodel --tenc cnclip/cnclip_vit_l14_336px_text_u16.axmodel --vocab cnclip/cn_vocab.txt --isCN 1 --db_path clip_feat_db_coco --image_folder coco_1000/
python pyclip/gradio_example.py --ienc cnclip/cnclip_vit_l14_336px_vision_u16u8.axmodel --tenc cnclip/cnclip_vit_l14_336px_text_u16.axmodel --vocab cnclip/cn_vocab.txt --isCN 1 --db_path clip_feat_db_coco --image_folder coco_1000/
成功启动后信息如下
(clip) m5stack@raspberrypi:~/rsp/LibCLIP $ python pyclip/gradio_example.py --ienc cnclip/cnclip_vit_l14_336px_vision_u16u8.axmodel --tenc cnclip/cnclip_vit_l14_336px_text_u16.axmodel --vocab cnclip/cn_vocab.txt --isCN 1 --db_path clip_feat_db_coco --image_folder coco_1000/
Trying to load: /home/m5stack/rsp/LibCLIP/pyclip/aarch64/libclip.so

❌ Failed to load: /home/m5stack/rsp/LibCLIP/pyclip/aarch64/libclip.so
   /home/m5stack/rsp/LibCLIP/pyclip/aarch64/libclip.so: cannot open shared object file: No such file or directory
🔍 File not found. Please verify that libclip.so exists and the path is correct.

Trying to load: /home/m5stack/rsp/LibCLIP/pyclip/libclip.so
open libax_sys.so failed
open libax_engine.so failed
✅ Successfully loaded: /home/m5stack/rsp/LibCLIP/pyclip/libclip.so
可用设备: {
'host'
: {
'available'
: True,
'version'
:
''
,
'mem_info'
: {
'remain'
: 0,
'total'
: 0}},
'devices'
: {
'host_version'
:
'V3.6.3_20250722020142'
,
'dev_version'
:
'V3.6.3_20250722020142'
,
'count'
: 1,
'devices_info'
: [{
'temp'
: 62,
'cpu_usage'
: 1,
'npu_usage'
: 0,
'mem_info'
: {
'remain'
: 7022,
'total'
: 7040}}]}}
[I][                             run][  31]: AXCLWorker start with devid 0

input size: 1
    name:    image [unknown] [unknown]
        1 x 3 x 336 x 336

output size: 1
    name: unnorm_image_features
        1 x 768

[I][              load_image_encoder][  50]: nchw 336 336
[I][              load_image_encoder][  60]: image feature len 768

input size: 1
    name:     text [unknown] [unknown]
        1 x 52

output size: 1
    name: unnorm_text_features
        1 x 768

[I][               load_text_encoder][  44]: text feature len 768
[I][                  load_tokenizer][  60]: text token len 52
100%|███████████████████████████████████| 1000/1000 [00:00<00:00, 163246.95it/s]
* Running on
local
URL:  http://0.0.0.0:7860
* To create a public link,
set
`share=True`
in
`launch()`.
(clip) m5stack@raspberrypi:~/rsp/LibCLIP $ python pyclip/gradio_example.py --ienc cnclip/cnclip_vit_l14_336px_vision_u16u8.axmodel --tenc cnclip/cnclip_vit_l14_336px_text_u16.axmodel --vocab cnclip/cn_vocab.txt --isCN 1 --db_path clip_feat_db_coco --image_folder coco_1000/
Trying to load: /home/m5stack/rsp/LibCLIP/pyclip/aarch64/libclip.so

❌ Failed to load: /home/m5stack/rsp/LibCLIP/pyclip/aarch64/libclip.so
   /home/m5stack/rsp/LibCLIP/pyclip/aarch64/libclip.so: cannot open shared object file: No such file or directory
🔍 File not found. Please verify that libclip.so exists and the path is correct.

Trying to load: /home/m5stack/rsp/LibCLIP/pyclip/libclip.so
open libax_sys.so failed
open libax_engine.so failed
✅ Successfully loaded: /home/m5stack/rsp/LibCLIP/pyclip/libclip.so
可用设备: {'host': {'available': True, 'version': '', 'mem_info': {'remain': 0, 'total': 0}}, 'devices': {'host_version': 'V3.6.3_20250722020142', 'dev_version': 'V3.6.3_20250722020142', 'count': 1, 'devices_info': [{'temp': 62, 'cpu_usage': 1, 'npu_usage': 0, 'mem_info': {'remain': 7022, 'total': 7040}}]}}
[I][                             run][  31]: AXCLWorker start with devid 0

input size: 1
    name:    image [unknown] [unknown]
        1 x 3 x 336 x 336

output size: 1
    name: unnorm_image_features
        1 x 768

[I][              load_image_encoder][  50]: nchw 336 336
[I][              load_image_encoder][  60]: image feature len 768

input size: 1
    name:     text [unknown] [unknown]
        1 x 52

output size: 1
    name: unnorm_text_features
        1 x 768

[I][               load_text_encoder][  44]: text feature len 768
[I][                  load_tokenizer][  60]: text token len 52
100%|███████████████████████████████████| 1000/1000 [00:00<00:00, 163246.95it/s]
* Running on local URL:  http://0.0.0.0:7860
* To create a public link, set `share=True` in `launch()`.
在浏览器中打开
http://127.0.0.1:7860
，在文本框输出需要检索的内容，点击搜图。
Next
目录索引
On This Page
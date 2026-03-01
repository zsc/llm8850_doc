# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_yolo_world_v2

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
YOLO World
YOLO World v2
YOLO-Worldv2 该模型的详细模型导出、量化、编译的流程请参考
《再谈 YOLO World 部署》
。
模型：yoloworldv2_4cls_50_npu3.axmodel
输入图片：ssd_horse.jpg
输入文本：dog.bin, 对应的 4 分类 'dog' 'horse' 'sheep' 'cow'
提示
参考
YOLO11章节
获取获取并解压整合包。
运行
./axcl_demo/axcl_yolo_world_open_vocabulary -m axcl_demo/yoloworldv2_4cls_50_npu3.axmodel -t axcl_demo/dog.bin -i axcl_demo/ssd_horse.jpg
./axcl_demo/axcl_yolo_world_open_vocabulary -m axcl_demo/yoloworldv2_4cls_50_npu3.axmodel -t axcl_demo/dog.bin -i axcl_demo/ssd_horse.jpg
运行结果如下：
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolo_world_open_vocabulary -m axcl_demo/yoloworldv2_4cls_50_npu3.axmodel -t axcl_demo/dog.bin -i axcl_demo/ssd_horse.jpg
--------------------------------------
model file : axcl_demo/yoloworldv2_4cls_50_npu3.axmodel
image file : axcl_demo/ssd_horse.jpg
text_feature file : axcl_demo/dog.bin
img_h, img_w : 640 640
--------------------------------------
axclrtEngineCreateContextt is
done
.
axclrtEngineGetIOInfo is
done
.

grpid: 0

input size: 2
    name:   images
        1 x 640 x 640 x 3

    name: txt_feats
        1 x 4 x 512

output size: 3
    name:  stride8
        1 x 80 x 80 x 68

    name: stride16
        1 x 40 x 40 x 68

    name: stride32
        1 x 20 x 20 x 68

==================================================

Engine push input is
done
.
--------------------------------------
post process cost time:0.25 ms
--------------------------------------
Repeat 1
times
, avg time 4.52 ms, max_time 4.52 ms, min_time 4.52 ms
--------------------------------------
detection num: 2
 1:  91%, [ 215,   71,  421,  374], class2
 0:  67%, [ 144,  204,  197,  346], class1
--------------------------------------
m5stack@raspberrypi:~/rsp $ ./axcl_demo/axcl_yolo_world_open_vocabulary -m axcl_demo/yoloworldv2_4cls_50_npu3.axmodel -t axcl_demo/dog.bin -i axcl_demo/ssd_horse.jpg
--------------------------------------
model file : axcl_demo/yoloworldv2_4cls_50_npu3.axmodel
image file : axcl_demo/ssd_horse.jpg
text_feature file : axcl_demo/dog.bin
img_h, img_w : 640 640
--------------------------------------
axclrtEngineCreateContextt is done.
axclrtEngineGetIOInfo is done.

grpid: 0

input size: 2
    name:   images
        1 x 640 x 640 x 3

    name: txt_feats
        1 x 4 x 512

output size: 3
    name:  stride8
        1 x 80 x 80 x 68

    name: stride16
        1 x 40 x 40 x 68

    name: stride32
        1 x 20 x 20 x 68

==================================================

Engine push input is done.
--------------------------------------
post process cost time:0.25 ms
--------------------------------------
Repeat 1 times, avg time 4.52 ms, max_time 4.52 ms, min_time 4.52 ms
--------------------------------------
detection num: 2
 1:  91%, [ 215,   71,  421,  374], class2
 0:  67%, [ 144,  204,  197,  346], class1
--------------------------------------
YOLO World v2 CLI
获取源码
并上传到 raspberrypi5 或使用 git 命令拉取。
拉取代码
git
clone
https://github.com/AXERA-TECH/yoloworld.axera.git
git clone https://github.com/AXERA-TECH/yoloworld.axera.git
进入项目目录
cd
yoloworld.axera
cd yoloworld.axera
提示
后续操作在此目录执行。
文件说明：
m5stack@raspberrypi:~/rsp/yoloworld.axera $ ls -lh
total 36K
-rwxrwxr-x 1 m5stack m5stack 2.1K Aug 12 11:26 build_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  775 Aug 12 11:26 build.sh
-rw-rw-r-- 1 m5stack m5stack 1.5K Aug 12 11:26 CMakeLists.txt
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:26 include
drwxrwxr-x 3 m5stack m5stack 4.0K Aug 12 14:46 pyyoloworld
-rw-rw-r-- 1 m5stack m5stack 1.9K Aug 12 11:26 README.md
drwxrwxr-x 4 m5stack m5stack 4.0K Aug 12 11:26 src
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:26 tests
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:26 toolchains
m5stack@raspberrypi:~/rsp/yoloworld.axera $ ls -lh
total 36K
-rwxrwxr-x 1 m5stack m5stack 2.1K Aug 12 11:26 build_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  775 Aug 12 11:26 build.sh
-rw-rw-r-- 1 m5stack m5stack 1.5K Aug 12 11:26 CMakeLists.txt
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:26 include
drwxrwxr-x 3 m5stack m5stack 4.0K Aug 12 14:46 pyyoloworld
-rw-rw-r-- 1 m5stack m5stack 1.9K Aug 12 11:26 README.md
drwxrwxr-x 4 m5stack m5stack 4.0K Aug 12 11:26 src
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:26 tests
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:26 toolchains
安装依赖
sudo apt update
sudo apt install cmake libopencv-dev -y
sudo apt update
sudo apt install cmake libopencv-dev -y
编译代码
mkdir build &&
cd
build
cmake .. && make -j4 install
cd
..
mkdir build && cd build
cmake .. && make -j4 install
cd ..
获取模型和词表
wget https://github.com/AXERA-TECH/yoloworld.axera/releases/download/v0.1/clip_b1_u16_ax650.axmodel
wget https://github.com/AXERA-TECH/yoloworld.axera/releases/download/v0.1/yolo_u16_ax650.axmodel
wget https://github.com/AXERA-TECH/yoloworld.axera/releases/download/v0.1/vocab.txt
wget https://github.com/AXERA-TECH/yoloworld.axera/releases/download/v0.1/clip_b1_u16_ax650.axmodel
wget https://github.com/AXERA-TECH/yoloworld.axera/releases/download/v0.1/yolo_u16_ax650.axmodel
wget https://github.com/AXERA-TECH/yoloworld.axera/releases/download/v0.1/vocab.txt
运行
./build/test_detect_by_text --yoloworld yolo_u16_ax650.axmodel --tenc clip_b1_u16_ax650.axmodel -v vocab.txt -i ssd_horse.jpg --classes person,car,dog,horse
./build/test_detect_by_text --yoloworld yolo_u16_ax650.axmodel --tenc clip_b1_u16_ax650.axmodel -v vocab.txt -i ssd_horse.jpg --classes person,car,dog,horse
运行结果如下：
m5stack@raspberrypi:~/rsp/yoloworld.axera $ ./build/test_detect_by_text --yoloworld yolo_u16_ax650.axmodel --tenc clip_b1_u16_ax650.axmodel -v vocab.txt -i ssd_horse.jpg --classes person,car,dog,horse
open libax_sys.so failed
open libax_engine.so failed
[I][                             run][  31]: AXCLWorker start with devid 0
label-0 class_names: person
label-1 class_names: car
label-2 class_names: dog
label-3 class_names: horse
yoloworld_path: yolo_u16_ax650.axmodel
text_encoder_path: clip_b1_u16_ax650.axmodel
tokenizer_path: vocab.txt

input size: 2
    name:   images [unknown] [unknown]
        1 x 640 x 640 x 3   size: 1228800

    name: txt_feats [unknown] [unknown]
        1 x 4 x 512   size: 8192

output size: 3
    name:  stride8
        1 x 80 x 80 x 68   size: 1740800

    name: stride16
        1 x 40 x 40 x 68   size: 435200

    name: stride32
        1 x 20 x 20 x 68   size: 108800

[I][                       yw_create][ 408]: num_classes: 4, num_features: 512, input w: 640, h: 640
is_output_nhwc: 1

input size: 1
    name: text_token [unknown] [unknown]
        1 x 77   size: 308

output size: 1
    name:     2202
        1 x 1 x 512   size: 2048

[I][               load_text_encoder][  44]: text feature len 512
[I][                  load_tokenizer][  60]: text token len 77
[I][                  yw_set_classes][ 463]: label-0 class_names: person
[I][                  yw_set_classes][ 463]: label-1 class_names: car
[I][                  yw_set_classes][ 463]: label-2 class_names: dog
[I][                  yw_set_classes][ 463]: label-3 class_names: horse
yw_set_classes time: 12.76 ms
preprocess 1.04
inference 19.06
postprocess 0.27
yw_detect time: 20.45 ms
object-0 class_id: 3 score: 0.88 box: 215 69 206 304
object-1 class_id: 0 score: 0.88 box: 271 13 76 220
object-2 class_id: 0 score: 0.77 box: 430 123 20 54
object-3 class_id: 2 score: 0.75 box: 144 203 52 143
object-4 class_id: 1 score: 0.65 box: 0 105 131 91
object-5 class_id: 0 score: 0.37 box: 402 130 7 16
object-6 class_id: 0 score: 0.16 box: 413 134 13 16
[I][                             run][  81]: AXCLWorker
exit
with devid 0
[2025-08-12 16:00:53.491][55020][C][device][
print
][18]: allocated device memories: 7
[2025-08-12 16:00:53.491][55020][C][device][
print
][20]: [0x1497ae000] : 0x134 bytes
[2025-08-12 16:00:53.491][55020][C][device][
print
][20]: [0x1495de000] : 0x1a900 bytes
[2025-08-12 16:00:53.491][55020][C][device][
print
][20]: [0x1497af000] : 0x800 bytes
[2025-08-12 16:00:53.491][55020][C][device][
print
][20]: [0x149573000] : 0x6a400 bytes
[2025-08-12 16:00:53.491][55020][C][device][
print
][20]: [0x1493ca000] : 0x1a9000 bytes
[2025-08-12 16:00:53.491][55020][C][device][
print
][20]: [0x1493c8000] : 0x2000 bytes
[2025-08-12 16:00:53.491][55020][C][device][
print
][20]: [0x14929c000] : 0x12c000 bytes
m5stack@raspberrypi:~/rsp/yoloworld.axera $ ./build/test_detect_by_text --yoloworld yolo_u16_ax650.axmodel --tenc clip_b1_u16_ax650.axmodel -v vocab.txt -i ssd_horse.jpg --classes person,car,dog,horse
open libax_sys.so failed
open libax_engine.so failed
[I][                             run][  31]: AXCLWorker start with devid 0
label-0 class_names: person
label-1 class_names: car
label-2 class_names: dog
label-3 class_names: horse
yoloworld_path: yolo_u16_ax650.axmodel
text_encoder_path: clip_b1_u16_ax650.axmodel
tokenizer_path: vocab.txt

input size: 2
    name:   images [unknown] [unknown]
        1 x 640 x 640 x 3   size: 1228800

    name: txt_feats [unknown] [unknown]
        1 x 4 x 512   size: 8192

output size: 3
    name:  stride8
        1 x 80 x 80 x 68   size: 1740800

    name: stride16
        1 x 40 x 40 x 68   size: 435200

    name: stride32
        1 x 20 x 20 x 68   size: 108800

[I][                       yw_create][ 408]: num_classes: 4, num_features: 512, input w: 640, h: 640
is_output_nhwc: 1

input size: 1
    name: text_token [unknown] [unknown]
        1 x 77   size: 308

output size: 1
    name:     2202
        1 x 1 x 512   size: 2048

[I][               load_text_encoder][  44]: text feature len 512
[I][                  load_tokenizer][  60]: text token len 77
[I][                  yw_set_classes][ 463]: label-0 class_names: person
[I][                  yw_set_classes][ 463]: label-1 class_names: car
[I][                  yw_set_classes][ 463]: label-2 class_names: dog
[I][                  yw_set_classes][ 463]: label-3 class_names: horse
yw_set_classes time: 12.76 ms
preprocess 1.04
inference 19.06
postprocess 0.27
yw_detect time: 20.45 ms
object-0 class_id: 3 score: 0.88 box: 215 69 206 304
object-1 class_id: 0 score: 0.88 box: 271 13 76 220
object-2 class_id: 0 score: 0.77 box: 430 123 20 54
object-3 class_id: 2 score: 0.75 box: 144 203 52 143
object-4 class_id: 1 score: 0.65 box: 0 105 131 91
object-5 class_id: 0 score: 0.37 box: 402 130 7 16
object-6 class_id: 0 score: 0.16 box: 413 134 13 16
[I][                             run][  81]: AXCLWorker exit with devid 0
[2025-08-12 16:00:53.491][55020][C][device][print][18]: allocated device memories: 7
[2025-08-12 16:00:53.491][55020][C][device][print][20]: [0x1497ae000] : 0x134 bytes
[2025-08-12 16:00:53.491][55020][C][device][print][20]: [0x1495de000] : 0x1a900 bytes
[2025-08-12 16:00:53.491][55020][C][device][print][20]: [0x1497af000] : 0x800 bytes
[2025-08-12 16:00:53.491][55020][C][device][print][20]: [0x149573000] : 0x6a400 bytes
[2025-08-12 16:00:53.491][55020][C][device][print][20]: [0x1493ca000] : 0x1a9000 bytes
[2025-08-12 16:00:53.491][55020][C][device][print][20]: [0x1493c8000] : 0x2000 bytes
[2025-08-12 16:00:53.491][55020][C][device][print][20]: [0x14929c000] : 0x12c000 bytes
YOLO World v2 Web
创建虚拟环境
python -m venv yolo
python -m venv yolo
激活虚拟环境
source
yolo/bin/activate
source yolo/bin/activate
安装依赖包
pip install -r pyyoloworld/requirements.txt
pip install -r pyyoloworld/requirements.txt
复制动态库
cp build/libyoloworld.so pyyoloworld/
cp build/libyoloworld.so pyyoloworld/
启动服务
python pyyoloworld/gradio_example.py --yoloworld yolo_u16_ax650.axmodel --tenc clip_b1_u16_ax650.axmodel --vocab vocab.txt
python pyyoloworld/gradio_example.py --yoloworld yolo_u16_ax650.axmodel --tenc clip_b1_u16_ax650.axmodel --vocab vocab.txt
正在运行后信息如下：
(yolo) m5stack@raspberrypi:~/rsp/yoloworld.axera $ python pyyoloworld/gradio_example.py --yoloworld yolo_u16_ax650.axmodel --tenc clip_b1_u16_ax650.axmodel --vocab vocab.txt
Trying to load: /home/m5stack/rsp/yoloworld.axera/pyyoloworld/aarch64/libyoloworld.so

❌ Failed to load: /home/m5stack/rsp/yoloworld.axera/pyyoloworld/aarch64/libyoloworld.so
   /home/m5stack/rsp/yoloworld.axera/pyyoloworld/aarch64/libyoloworld.so: cannot open shared object file: No such file or directory
🔍 File not found. Please verify that libclip.so exists and the path is correct.

Trying to load: /home/m5stack/rsp/yoloworld.axera/pyyoloworld/libyoloworld.so
open libax_sys.so failed
open libax_engine.so failed
✅ Successfully loaded: /home/m5stack/rsp/yoloworld.axera/pyyoloworld/libyoloworld.so
[I][                             run][  31]: AXCLWorker start with devid 0

input size: 2
    name:   images [unknown] [unknown]
        1 x 640 x 640 x 3   size: 1228800

    name: txt_feats [unknown] [unknown]
        1 x 4 x 512   size: 8192

output size: 3
    name:  stride8
        1 x 80 x 80 x 68   size: 1740800

    name: stride16
        1 x 40 x 40 x 68   size: 435200

    name: stride32
        1 x 20 x 20 x 68   size: 108800

[I][                       yw_create][ 408]: num_classes: 4, num_features: 512, input w: 640, h: 640
is_output_nhwc: 1

input size: 1
    name: text_token [unknown] [unknown]
        1 x 77   size: 308

output size: 1
    name:     2202
        1 x 1 x 512   size: 2048

[I][               load_text_encoder][  44]: text feature len 512
[I][                  load_tokenizer][  60]: text token len 77
* Running on
local
URL:  http://0.0.0.0:7860
* To create a public link,
set
`share=True`
in
`launch()`.
(yolo) m5stack@raspberrypi:~/rsp/yoloworld.axera $ python pyyoloworld/gradio_example.py --yoloworld yolo_u16_ax650.axmodel --tenc clip_b1_u16_ax650.axmodel --vocab vocab.txt
Trying to load: /home/m5stack/rsp/yoloworld.axera/pyyoloworld/aarch64/libyoloworld.so

❌ Failed to load: /home/m5stack/rsp/yoloworld.axera/pyyoloworld/aarch64/libyoloworld.so
   /home/m5stack/rsp/yoloworld.axera/pyyoloworld/aarch64/libyoloworld.so: cannot open shared object file: No such file or directory
🔍 File not found. Please verify that libclip.so exists and the path is correct.

Trying to load: /home/m5stack/rsp/yoloworld.axera/pyyoloworld/libyoloworld.so
open libax_sys.so failed
open libax_engine.so failed
✅ Successfully loaded: /home/m5stack/rsp/yoloworld.axera/pyyoloworld/libyoloworld.so
[I][                             run][  31]: AXCLWorker start with devid 0

input size: 2
    name:   images [unknown] [unknown]
        1 x 640 x 640 x 3   size: 1228800

    name: txt_feats [unknown] [unknown]
        1 x 4 x 512   size: 8192

output size: 3
    name:  stride8
        1 x 80 x 80 x 68   size: 1740800

    name: stride16
        1 x 40 x 40 x 68   size: 435200

    name: stride32
        1 x 20 x 20 x 68   size: 108800

[I][                       yw_create][ 408]: num_classes: 4, num_features: 512, input w: 640, h: 640
is_output_nhwc: 1

input size: 1
    name: text_token [unknown] [unknown]
        1 x 77   size: 308

output size: 1
    name:     2202
        1 x 1 x 512   size: 2048

[I][               load_text_encoder][  44]: text feature len 512
[I][                  load_tokenizer][  60]: text token len 77
* Running on local URL:  http://0.0.0.0:7860
* To create a public link, set `share=True` in `launch()`.
在浏览器中打开 127.0.0.1:7860，添加图片，输入要检测的类别，点击
检测
Next
目录索引
On This Page
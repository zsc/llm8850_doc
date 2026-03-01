# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_qwen3_vl_4b

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
Qwen3-VL-4B-Instruct-GPTQ-Int4
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
https://huggingface.co/M5Stack/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel
git clone https://huggingface.co/M5Stack/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel
文件说明
m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ ls -lh
total 7.4M
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  7 11:48 images
-rwxrwxr-x 1 m5stack m5stack 7.3M Nov  7 15:55 main_axcl_aarch64
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  7 11:49 Qwen3-VL-4B-Instruct-ax8850
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  7 11:42 qwen3-vl-tokenizer
-rw-rw-r-- 1 m5stack m5stack   24 Nov  7 16:02 README.md
-rwxrwxr-x 1 m5stack m5stack  715 Nov  7 16:19 run_image_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  715 Nov  7 16:20 run_video_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack 9.4K Nov  7 14:42 tokenizer_images.py
-rwxrwxr-x 1 m5stack m5stack 9.3K Nov  7 14:41 tokenizer_video.py
drwxr-xr-x 2 m5stack m5stack 4.0K Nov  7 12:04 video
m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ ls -lh
total 7.4M
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  7 11:48 images
-rwxrwxr-x 1 m5stack m5stack 7.3M Nov  7 15:55 main_axcl_aarch64
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  7 11:49 Qwen3-VL-4B-Instruct-ax8850
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  7 11:42 qwen3-vl-tokenizer
-rw-rw-r-- 1 m5stack m5stack   24 Nov  7 16:02 README.md
-rwxrwxr-x 1 m5stack m5stack  715 Nov  7 16:19 run_image_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  715 Nov  7 16:20 run_video_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack 9.4K Nov  7 14:42 tokenizer_images.py
-rwxrwxr-x 1 m5stack m5stack 9.3K Nov  7 14:41 tokenizer_video.py
drwxr-xr-x 2 m5stack m5stack 4.0K Nov  7 12:04 video
提示
如果之前已经创建了
qwen
的虚拟环境，不需要重新创建，只需要激活即可。
创建虚拟环境
python -m venv qwen
python -m venv qwen
激活虚拟环境
source
qwen/bin/activate
source qwen/bin/activate
安装依赖包
pip install transformers jinja2
pip install transformers jinja2
启动 images tokenizer 解析器
python tokenizer_images.py
python tokenizer_images.py
运行 images tokenizer 服务，Host ip 默认为 localhost，端口号设置为 8080，运行后信息如下：
(qwen) m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ python tokenizer_images.py 
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151653, 74785, 419, 2168, 13, 151645, 198, 151644, 77091, 198]
281
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:8080
(qwen) m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ python tokenizer_images.py 
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151653, 74785, 419, 2168, 13, 151645, 198, 151644, 77091, 198]
281
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:8080
提示
以下操作需要新建一个 raspberrypi 的终端。
设置可执行权限
chmod +x main_axcl_aarch64 run_image_axcl_aarch64.sh
chmod +x main_axcl_aarch64 run_image_axcl_aarch64.sh
启动 Qwen3 模型图片推理服务
./run_image_axcl_aarch64.sh
./run_image_axcl_aarch64.sh
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ ./run_image_axcl_aarch64.sh
[I][                            Init][ 163]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:8080 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151655
  2% | █                                 |   1 /  39 [0.01s<0.20s, 200.00 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  5% | ██                                |   2 /  39 [0.01s<0.10s, 400.00 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
 10% |  █      ███                                                     |   3 /  39 [8.26s<80.56s, 0.48 count/s] init 18 axmodel ok,devid(0) re 94% | █████████████████████████████████████████████████████ █ ██ |  37 /  39 [73.09s<79.18s, 0.49 count/s] init 8 axmodel ok,devid(0) remain_100% | ████████████████████████████████ |  39 /  39 [81.89s<84.05s, 0.46 count/s] init post axmodel ok,remain_cmm(1894 MB)2299 MB)
input size: 1
    name: hidden_states [unknown] [unknown] 
        1 x 576 x 512 x 3 size:884736

output size: 4
    name: hidden_states_out 
        144 x 2560 size:1474560

    name: deepstack_feature_0 
        144 x 2560 size:1474560

    name: deepstack_feature_1 
        144 x 2560 size:1474560

    name: deepstack_feature_2 
        144 x 2560 size:1474560

[I][                            Init][ 268]: IMAGE_CONTEXT_TOKEN: 151655, IMAGE_START_TOKEN: 151652
[I][                            Init][ 329]: image encoder output float32

[I][                            Init][ 341]: max_token_len : 2047
[I][                            Init][ 344]: kv_cache_size : 1024, kv_cache_num: 2047
[I][                            Init][ 352]: prefill_token_num : 128
[I][                            Init][ 356]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 356]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 356]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 356]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 356]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 356]: grp: 6, prefill_max_token_num : 640
[I][                            Init][ 356]: grp: 7, prefill_max_token_num : 768
[I][                            Init][ 356]: grp: 8, prefill_max_token_num : 896
[I][                            Init][ 356]: grp: 9, prefill_max_token_num : 1024
[I][                            Init][ 356]: grp: 10, prefill_max_token_num : 1152
[I][                            Init][ 360]: prefill_max_token_num : 1152
________________________
|    ID| remain cmm(MB)|
========================
|     0|           1443|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[E][                     load_config][ 278]: config file(post_config.json) open failed
[W][                            Init][ 453]: load postprocess config(post_config.json) failed
[I][                            Init][ 457]: LLM init ok
Type
"q"
to
exit
, Ctrl+c to stop current running
prompt >> Describe the content of the image
image >> images/recoAll_attractions_1.jpg
[I][                     EncodeImage][ 531]: pixel_values size 1
[I][                     EncodeImage][ 532]: grid_h 24 grid_w 24
[I][                     EncodeImage][ 580]: image encode time : 196.322998 ms, size : 1
[I][                          Encode][ 622]: input_ids size:171
[I][                          Encode][ 630]: offset 15
[I][                          Encode][ 659]: img_embed.size:1, 368640
[I][                          Encode][ 673]: out_embed size:437760
[I][                          Encode][ 674]: input_ids size 171
[I][                          Encode][ 676]: position_ids size:171
[I][                             Run][ 698]: input token num : 171, prefill_split_num : 2
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:43
[I][                             Run][ 909]: ttft: 984.20 ms
This image captures a classic view of the Giza Pyramids
in
Egypt,
set
against a vast, clear blue sky.

In the foreground, the desert sands stretch out, with a few small figures of people visible, providing a sense of scale. The most prominent structure is the Great Pyramid of Giza, its massive stone blocks forming a steep, triangular silhouette. To its left, the smaller Pyramid of Khafre is visible, and to its right, the Pyramid of Menkaure can be seen, though less distinct.

The pyramids are bathed
in
bright sunlight, casting long, dark shadows that emphasize their monumental scale and the precision of their construction. The clear, cloudless sky creates a dramatic contrast with the ancient, enduring stone, evoking a sense of timeless grandeur and mystery.

This scene is one of the most iconic and recognizable
in
the world, symbolizing the enduring legacy of ancient Egypt and the awe-inspiring achievements of its civilization.

[N][                             Run][1062]: hit eos,avg 5.92 token/s

prompt >>
m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ ./run_image_axcl_aarch64.sh
[I][                            Init][ 163]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:8080 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151655
  2% | █                                 |   1 /  39 [0.01s<0.20s, 200.00 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  5% | ██                                |   2 /  39 [0.01s<0.10s, 400.00 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
 10% |  █      ███                                                     |   3 /  39 [8.26s<80.56s, 0.48 count/s] init 18 axmodel ok,devid(0) re 94% | █████████████████████████████████████████████████████ █ ██ |  37 /  39 [73.09s<79.18s, 0.49 count/s] init 8 axmodel ok,devid(0) remain_100% | ████████████████████████████████ |  39 /  39 [81.89s<84.05s, 0.46 count/s] init post axmodel ok,remain_cmm(1894 MB)2299 MB)
input size: 1
    name: hidden_states [unknown] [unknown] 
        1 x 576 x 512 x 3 size:884736

output size: 4
    name: hidden_states_out 
        144 x 2560 size:1474560

    name: deepstack_feature_0 
        144 x 2560 size:1474560

    name: deepstack_feature_1 
        144 x 2560 size:1474560

    name: deepstack_feature_2 
        144 x 2560 size:1474560

[I][                            Init][ 268]: IMAGE_CONTEXT_TOKEN: 151655, IMAGE_START_TOKEN: 151652
[I][                            Init][ 329]: image encoder output float32

[I][                            Init][ 341]: max_token_len : 2047
[I][                            Init][ 344]: kv_cache_size : 1024, kv_cache_num: 2047
[I][                            Init][ 352]: prefill_token_num : 128
[I][                            Init][ 356]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 356]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 356]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 356]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 356]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 356]: grp: 6, prefill_max_token_num : 640
[I][                            Init][ 356]: grp: 7, prefill_max_token_num : 768
[I][                            Init][ 356]: grp: 8, prefill_max_token_num : 896
[I][                            Init][ 356]: grp: 9, prefill_max_token_num : 1024
[I][                            Init][ 356]: grp: 10, prefill_max_token_num : 1152
[I][                            Init][ 360]: prefill_max_token_num : 1152
________________________
|    ID| remain cmm(MB)|
========================
|     0|           1443|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[E][                     load_config][ 278]: config file(post_config.json) open failed
[W][                            Init][ 453]: load postprocess config(post_config.json) failed
[I][                            Init][ 457]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
prompt >> Describe the content of the image
image >> images/recoAll_attractions_1.jpg
[I][                     EncodeImage][ 531]: pixel_values size 1
[I][                     EncodeImage][ 532]: grid_h 24 grid_w 24
[I][                     EncodeImage][ 580]: image encode time : 196.322998 ms, size : 1
[I][                          Encode][ 622]: input_ids size:171
[I][                          Encode][ 630]: offset 15
[I][                          Encode][ 659]: img_embed.size:1, 368640
[I][                          Encode][ 673]: out_embed size:437760
[I][                          Encode][ 674]: input_ids size 171
[I][                          Encode][ 676]: position_ids size:171
[I][                             Run][ 698]: input token num : 171, prefill_split_num : 2
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:43
[I][                             Run][ 909]: ttft: 984.20 ms
This image captures a classic view of the Giza Pyramids in Egypt, set against a vast, clear blue sky.

In the foreground, the desert sands stretch out, with a few small figures of people visible, providing a sense of scale. The most prominent structure is the Great Pyramid of Giza, its massive stone blocks forming a steep, triangular silhouette. To its left, the smaller Pyramid of Khafre is visible, and to its right, the Pyramid of Menkaure can be seen, though less distinct.

The pyramids are bathed in bright sunlight, casting long, dark shadows that emphasize their monumental scale and the precision of their construction. The clear, cloudless sky creates a dramatic contrast with the ancient, enduring stone, evoking a sense of timeless grandeur and mystery.

This scene is one of the most iconic and recognizable in the world, symbolizing the enduring legacy of ancient Egypt and the awe-inspiring achievements of its civilization.

[N][                             Run][1062]: hit eos,avg 5.92 token/s

prompt >>
停止 images tokenizer 解析器，并启动 video tokenizer 解析器
python tokenizer_video.py
python tokenizer_video.py
运行 video tokenizer 服务，Host ip 默认为 localhost，端口号设置为 8080，运行后信息如下：
(qwen) m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ python tokenizer_video.py
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151653, 74785, 419, 2168, 13, 151645, 198, 151644, 77091, 198]
281
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:8080
(qwen) m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ python tokenizer_video.py
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151653, 74785, 419, 2168, 13, 151645, 198, 151644, 77091, 198]
281
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:8080
启动 Qwen3 模型视频推理服务
./run_video_axcl_aarch64.sh
./run_video_axcl_aarch64.sh
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ ./run_video_axcl_aarch64.sh
[I][                            Init][ 163]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:8080 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151656
  2% | █                                 |   1 /  39 [0.00s<0.12s, 333.33 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  5% | ██                                |   2 /  39 [0.00s<0.08s, 500.00 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
100% | ████████████████████████████████ |  39 /  39 [67.42s<67.42s, 0.58 count/s] init post axmodel ok,remain_cmm(1894 MB)299 MB))
input size: 1
    name: hidden_states [unknown] [unknown] 
        1 x 576 x 512 x 3 size:884736

output size: 4
    name: hidden_states_out 
        144 x 2560 size:1474560

    name: deepstack_feature_0 
        144 x 2560 size:1474560

    name: deepstack_feature_1 
        144 x 2560 size:1474560

    name: deepstack_feature_2 
        144 x 2560 size:1474560

[I][                            Init][ 268]: IMAGE_CONTEXT_TOKEN: 151656, IMAGE_START_TOKEN: 151652
[I][                            Init][ 329]: image encoder output float32

[I][                            Init][ 341]: max_token_len : 2047
[I][                            Init][ 344]: kv_cache_size : 1024, kv_cache_num: 2047
[I][                            Init][ 352]: prefill_token_num : 128
[I][                            Init][ 356]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 356]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 356]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 356]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 356]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 356]: grp: 6, prefill_max_token_num : 640
[I][                            Init][ 356]: grp: 7, prefill_max_token_num : 768
[I][                            Init][ 356]: grp: 8, prefill_max_token_num : 896
[I][                            Init][ 356]: grp: 9, prefill_max_token_num : 1024
[I][                            Init][ 356]: grp: 10, prefill_max_token_num : 1152
[I][                            Init][ 360]: prefill_max_token_num : 1152
________________________
|    ID| remain cmm(MB)|
========================
|     0|           1443|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[E][                     load_config][ 278]: config file(post_config.json) open failed
[W][                            Init][ 453]: load postprocess config(post_config.json) failed
[I][                            Init][ 457]: LLM init ok
Type
"q"
to
exit
, Ctrl+c to stop current running
prompt >> Describe the content of the video
video >> video
video/out_0001.jpg
video/out_0002.jpg
video/out_0003.jpg
video/out_0004.jpg
video/out_0005.jpg
video/out_0006.jpg
video/out_0007.jpg
video/out_0008.jpg
video/out_0009.jpg
[I][                     EncodeImage][ 531]: pixel_values size 5
[I][                     EncodeImage][ 532]: grid_h 24 grid_w 24
[I][                     EncodeImage][ 580]: image encode time : 938.083008 ms, size : 5
[I][                          Encode][ 622]: input_ids size:747
[I][                          Encode][ 630]: offset 15
[I][                          Encode][ 659]: img_embed.size:5, 368640
[I][                          Encode][ 664]: offset:159
[I][                          Encode][ 664]: offset:303
[I][                          Encode][ 664]: offset:447
[I][                          Encode][ 664]: offset:591
[I][                          Encode][ 673]: out_embed size:1912320
[I][                          Encode][ 674]: input_ids size 747
[I][                          Encode][ 676]: position_ids size:747
[I][                             Run][ 698]: input token num : 747, prefill_split_num : 6
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:107
[I][                             Run][ 909]: ttft: 3385.97 ms
This video appears to be a static, low-angle shot of an indoor hallway or corridor, likely
in
a modern building or office. The scene is composed of several key elements:

- **The Setting**: The hallway is lined with dark, polished, reflective tiles that create a sleek, contemporary look. The reflections on the floor and walls add depth to the scene. On the right wall, there are two small, green-lit
exit
signs, indicating a fire safety feature. Below them, a red fire extinguisher is mounted on the wall, and a small, white control panel or thermostat is also visible.

- **The People**: Two individuals are present
in
the frame. One, wearing a white t-shirt with a blue graphic and dark pants, is walking away from the camera, moving toward the elevator or stairwell. The second person, dressed
in
a dark shirt and shorts, is also walking away, slightly to the right of the first person. Their movement is captured
in
motion, suggesting the video was taken
in
a moment of activity.

- **The Technology**: In the foreground, there are three laptops, each displaying a blue screen with a glowing, abstract image that resembles a jellyfish or a similar organic form. The laptops are placed on a gray, curved stand or cart,
which
is positioned near the wall. The laptops are connected to a network of cables, suggesting they are part of a monitoring or surveillance system. The laptops are not
in
use, as they are displaying a static image,
which
may indicate they are
in
standby mode or are being used
for
a specific purpose, such as monitoring or recording.

- **The Overall Atmosphere**: The scene is calm and uncluttered, with a focus on the technology and the movement of the people. The lighting is soft and ambient, and the overall mood is one of quiet observation, as
if
the viewer is being invited to watch the scene unfold.

The video seems to be a snapshot of a moment
in
time, capturing the interplay between human activity and technology
in
a modern, well-maintained environment. The presence of the laptops and the fire safety equipment suggests that this is a space that is monitored and maintained
for
safety and efficiency.

[N][                             Run][1062]: hit eos,avg 5.94 token/s

prompt >>
m5stack@raspberrypi:~/rsp/Qwen3-VL-4B-Instruct-GPTQ-Int4-axmodel $ ./run_video_axcl_aarch64.sh
[I][                            Init][ 163]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:8080 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151656
  2% | █                                 |   1 /  39 [0.00s<0.12s, 333.33 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  5% | ██                                |   2 /  39 [0.00s<0.08s, 500.00 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
100% | ████████████████████████████████ |  39 /  39 [67.42s<67.42s, 0.58 count/s] init post axmodel ok,remain_cmm(1894 MB)299 MB))
input size: 1
    name: hidden_states [unknown] [unknown] 
        1 x 576 x 512 x 3 size:884736

output size: 4
    name: hidden_states_out 
        144 x 2560 size:1474560

    name: deepstack_feature_0 
        144 x 2560 size:1474560

    name: deepstack_feature_1 
        144 x 2560 size:1474560

    name: deepstack_feature_2 
        144 x 2560 size:1474560

[I][                            Init][ 268]: IMAGE_CONTEXT_TOKEN: 151656, IMAGE_START_TOKEN: 151652
[I][                            Init][ 329]: image encoder output float32

[I][                            Init][ 341]: max_token_len : 2047
[I][                            Init][ 344]: kv_cache_size : 1024, kv_cache_num: 2047
[I][                            Init][ 352]: prefill_token_num : 128
[I][                            Init][ 356]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 356]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 356]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 356]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 356]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 356]: grp: 6, prefill_max_token_num : 640
[I][                            Init][ 356]: grp: 7, prefill_max_token_num : 768
[I][                            Init][ 356]: grp: 8, prefill_max_token_num : 896
[I][                            Init][ 356]: grp: 9, prefill_max_token_num : 1024
[I][                            Init][ 356]: grp: 10, prefill_max_token_num : 1152
[I][                            Init][ 360]: prefill_max_token_num : 1152
________________________
|    ID| remain cmm(MB)|
========================
|     0|           1443|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[E][                     load_config][ 278]: config file(post_config.json) open failed
[W][                            Init][ 453]: load postprocess config(post_config.json) failed
[I][                            Init][ 457]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
prompt >> Describe the content of the video
video >> video
video/out_0001.jpg
video/out_0002.jpg
video/out_0003.jpg
video/out_0004.jpg
video/out_0005.jpg
video/out_0006.jpg
video/out_0007.jpg
video/out_0008.jpg
video/out_0009.jpg
[I][                     EncodeImage][ 531]: pixel_values size 5
[I][                     EncodeImage][ 532]: grid_h 24 grid_w 24
[I][                     EncodeImage][ 580]: image encode time : 938.083008 ms, size : 5
[I][                          Encode][ 622]: input_ids size:747
[I][                          Encode][ 630]: offset 15
[I][                          Encode][ 659]: img_embed.size:5, 368640
[I][                          Encode][ 664]: offset:159
[I][                          Encode][ 664]: offset:303
[I][                          Encode][ 664]: offset:447
[I][                          Encode][ 664]: offset:591
[I][                          Encode][ 673]: out_embed size:1912320
[I][                          Encode][ 674]: input_ids size 747
[I][                          Encode][ 676]: position_ids size:747
[I][                             Run][ 698]: input token num : 747, prefill_split_num : 6
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:107
[I][                             Run][ 909]: ttft: 3385.97 ms
This video appears to be a static, low-angle shot of an indoor hallway or corridor, likely in a modern building or office. The scene is composed of several key elements:

- **The Setting**: The hallway is lined with dark, polished, reflective tiles that create a sleek, contemporary look. The reflections on the floor and walls add depth to the scene. On the right wall, there are two small, green-lit exit signs, indicating a fire safety feature. Below them, a red fire extinguisher is mounted on the wall, and a small, white control panel or thermostat is also visible.

- **The People**: Two individuals are present in the frame. One, wearing a white t-shirt with a blue graphic and dark pants, is walking away from the camera, moving toward the elevator or stairwell. The second person, dressed in a dark shirt and shorts, is also walking away, slightly to the right of the first person. Their movement is captured in motion, suggesting the video was taken in a moment of activity.

- **The Technology**: In the foreground, there are three laptops, each displaying a blue screen with a glowing, abstract image that resembles a jellyfish or a similar organic form. The laptops are placed on a gray, curved stand or cart, which is positioned near the wall. The laptops are connected to a network of cables, suggesting they are part of a monitoring or surveillance system. The laptops are not in use, as they are displaying a static image, which may indicate they are in standby mode or are being used for a specific purpose, such as monitoring or recording.

- **The Overall Atmosphere**: The scene is calm and uncluttered, with a focus on the technology and the movement of the people. The lighting is soft and ambient, and the overall mood is one of quiet observation, as if the viewer is being invited to watch the scene unfold.

The video seems to be a snapshot of a moment in time, capturing the interplay between human activity and technology in a modern, well-maintained environment. The presence of the laptops and the fire safety equipment suggests that this is a space that is monitored and maintained for safety and efficiency.

[N][                             Run][1062]: hit eos,avg 5.94 token/s

prompt >>
Next
目录索引
On This Page
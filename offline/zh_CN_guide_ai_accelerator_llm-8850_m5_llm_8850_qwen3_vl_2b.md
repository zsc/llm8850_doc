# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_qwen3_vl_2b

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
Qwen3-VL-2B-Instruct
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
https://huggingface.co/M5Stack/Qwen3-VL-2B-Instruct-axmodel
git clone https://huggingface.co/M5Stack/Qwen3-VL-2B-Instruct-axmodel
文件说明
m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ ls -lh
total 7.4M
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 28 09:37 images
-rwxrwxr-x 1 m5stack m5stack 7.3M Nov  7 15:55 main_axcl_aarch64
-rwxrwxr-x 1 m5stack m5stack  276 Nov  7 11:58 post_config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 28 09:38 Qwen3-VL-2B-Instruct-ax8850
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 28 09:31 qwen3-vl-tokenizer
-rw-rw-r-- 1 m5stack m5stack   24 Nov  7 14:12 README.md
-rwxrwxr-x 1 m5stack m5stack  715 Nov  7 14:17 run_image_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  715 Nov  7 14:17 run_video_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack 9.4K Nov  7 14:42 tokenizer_images.py
-rwxrwxr-x 1 m5stack m5stack 9.3K Nov  7 14:41 tokenizer_video.py
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  7 11:26 video
m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ ls -lh
total 7.4M
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 28 09:37 images
-rwxrwxr-x 1 m5stack m5stack 7.3M Nov  7 15:55 main_axcl_aarch64
-rwxrwxr-x 1 m5stack m5stack  276 Nov  7 11:58 post_config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 28 09:38 Qwen3-VL-2B-Instruct-ax8850
drwxrwxr-x 2 m5stack m5stack 4.0K Oct 28 09:31 qwen3-vl-tokenizer
-rw-rw-r-- 1 m5stack m5stack   24 Nov  7 14:12 README.md
-rwxrwxr-x 1 m5stack m5stack  715 Nov  7 14:17 run_image_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  715 Nov  7 14:17 run_video_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack 9.4K Nov  7 14:42 tokenizer_images.py
-rwxrwxr-x 1 m5stack m5stack 9.3K Nov  7 14:41 tokenizer_video.py
drwxrwxr-x 2 m5stack m5stack 4.0K Nov  7 11:26 video
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
(qwen) m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ python tokenizer_images.py 
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151655, 151653, 74785, 419, 2168, 13, 151645, 198, 151644, 77091, 198]
281
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:8080
(qwen) m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ python tokenizer_images.py 
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
m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ ./run_image_axcl_aarch64.sh 
[I][                            Init][ 163]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:8080 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151655
  3% | ██                                |   1 /  31 [0.01s<0.19s, 166.67 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  6% | ███                               |   2 /  31 [0.01s<0.09s, 333.33 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
 80% | ███████████████████████████████████████████████ █ █           |  24 /  31 [45.28s<56.14s, 0.55 count/s] init 26 axmodel ok,devid(0) rem100% | ████████████████████████████████ |  31 /  31 [61.71s<61.71s, 0.50 count/s] init post axmodel ok,remain_cmm(3341 MB)3665 MB)
input size: 1
    name: hidden_states [unknown] [unknown] 
        1 x 576 x 512 x 3 size:884736

output size: 4
    name: hidden_states_out 
        144 x 2048 size:1179648

    name: deepstack_feature_0 
        144 x 2048 size:1179648

    name: deepstack_feature_1 
        144 x 2048 size:1179648

    name: deepstack_feature_2 
        144 x 2048 size:1179648

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
|     0|           2899|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config: 
{
"enable_repetition_penalty"
:
false
,
"enable_temperature"
:
true
,
"enable_top_k_sampling"
:
true
,
"enable_top_p_sampling"
:
false
,
"penalty_window"
: 30,
"repetition_penalty"
: 1,
"temperature"
: 0.2,
"top_k"
: 10,
"top_p"
: 0.8
}

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
[I][                     EncodeImage][ 580]: image encode time : 191.645004 ms, size : 1
[I][                          Encode][ 622]: input_ids size:171
[I][                          Encode][ 630]: offset 15
[I][                          Encode][ 659]: img_embed.size:1, 294912
[I][                          Encode][ 673]: out_embed size:350208
[I][                          Encode][ 674]: input_ids size 171
[I][                          Encode][ 676]: position_ids size:171
[I][                             Run][ 698]: input token num : 171, prefill_split_num : 2
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:43
[I][                             Run][ 909]: ttft: 596.82 ms
This is a photograph of the Great Pyramids of Giza, the three largest and most famous pyramids
in
the world, located
in
the Giza Plateau
in
Egypt. The image captures the pyramids under a clear blue sky, with the vast, sandy desert landscape surrounding them. The pyramids are constructed from large stone blocks, and their massive, stepped structures are clearly visible. In the foreground, a few small figures can be seen, providing a sense of scale to the immense structures. The image is a clear and detailed depiction of the iconic ancient monuments.

[N][                             Run][1062]: hit eos,avg 7.80 token/s

prompt >>
m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ ./run_image_axcl_aarch64.sh 
[I][                            Init][ 163]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:8080 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151655
  3% | ██                                |   1 /  31 [0.01s<0.19s, 166.67 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  6% | ███                               |   2 /  31 [0.01s<0.09s, 333.33 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
 80% | ███████████████████████████████████████████████ █ █           |  24 /  31 [45.28s<56.14s, 0.55 count/s] init 26 axmodel ok,devid(0) rem100% | ████████████████████████████████ |  31 /  31 [61.71s<61.71s, 0.50 count/s] init post axmodel ok,remain_cmm(3341 MB)3665 MB)
input size: 1
    name: hidden_states [unknown] [unknown] 
        1 x 576 x 512 x 3 size:884736

output size: 4
    name: hidden_states_out 
        144 x 2048 size:1179648

    name: deepstack_feature_0 
        144 x 2048 size:1179648

    name: deepstack_feature_1 
        144 x 2048 size:1179648

    name: deepstack_feature_2 
        144 x 2048 size:1179648

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
|     0|           2899|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config: 
{
    "enable_repetition_penalty": false,
    "enable_temperature": true,
    "enable_top_k_sampling": true,
    "enable_top_p_sampling": false,
    "penalty_window": 30,
    "repetition_penalty": 1,
    "temperature": 0.2,
    "top_k": 10,
    "top_p": 0.8
}

[I][                            Init][ 457]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
prompt >> Describe the content of the image
image >> images/recoAll_attractions_1.jpg
[I][                     EncodeImage][ 531]: pixel_values size 1
[I][                     EncodeImage][ 532]: grid_h 24 grid_w 24
[I][                     EncodeImage][ 580]: image encode time : 191.645004 ms, size : 1
[I][                          Encode][ 622]: input_ids size:171
[I][                          Encode][ 630]: offset 15
[I][                          Encode][ 659]: img_embed.size:1, 294912
[I][                          Encode][ 673]: out_embed size:350208
[I][                          Encode][ 674]: input_ids size 171
[I][                          Encode][ 676]: position_ids size:171
[I][                             Run][ 698]: input token num : 171, prefill_split_num : 2
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:43
[I][                             Run][ 909]: ttft: 596.82 ms
This is a photograph of the Great Pyramids of Giza, the three largest and most famous pyramids in the world, located in the Giza Plateau in Egypt. The image captures the pyramids under a clear blue sky, with the vast, sandy desert landscape surrounding them. The pyramids are constructed from large stone blocks, and their massive, stepped structures are clearly visible. In the foreground, a few small figures can be seen, providing a sense of scale to the immense structures. The image is a clear and detailed depiction of the iconic ancient monuments.

[N][                             Run][1062]: hit eos,avg 7.80 token/s

prompt >>
停止 images tokenizer 解析器，并启动 video tokenizer 解析器
python tokenizer_video.py
python tokenizer_video.py
运行 video tokenizer 服务，Host ip 默认为 localhost，端口号设置为 8080，运行后信息如下：
(qwen) m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ python tokenizer_video.py 
None None 151645 <|im_end|>
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 151652, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151656, 151653, 74785, 419, 2168, 13, 151645, 198, 151644, 77091, 198]
281
[151644, 8948, 198, 2610, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
21
http://localhost:8080
(qwen) m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ python tokenizer_video.py 
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
m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ ./run_video_axcl_aarch64.sh 
[I][                            Init][ 163]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:8080 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151656
  3% | ██                                |   1 /  31 [0.00s<0.09s, 333.33 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  6% | ███                               |   2 /  31 [0.00s<0.06s, 500.00 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
 16% | █████████ ██                                       |   4 /  31 [6.09s<47.22s, 0.66 count/s] init 7 axmodel ok,devid(0) remain_cmm(-1 MB 93% | ███████████████████████████████████████████████████████████     |  29 /  31 [39.21s<43.41s, 0.71 count/s] init 13 axmodel ok,devid(0) r100% | ████████████████████████████████ |  31 /  31 [45.05s<46.55s, 0.67 count/s] init post axmodel ok,remain_cmm(3341 MB)3665 MB)
input size: 1
    name: hidden_states [unknown] [unknown] 
        1 x 576 x 512 x 3 size:884736

output size: 4
    name: hidden_states_out 
        144 x 2048 size:1179648

    name: deepstack_feature_0 
        144 x 2048 size:1179648

    name: deepstack_feature_1 
        144 x 2048 size:1179648

    name: deepstack_feature_2 
        144 x 2048 size:1179648

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
|     0|           2899|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config: 
{
"enable_repetition_penalty"
:
false
,
"enable_temperature"
:
true
,
"enable_top_k_sampling"
:
true
,
"enable_top_p_sampling"
:
false
,
"penalty_window"
: 30,
"repetition_penalty"
: 1,
"temperature"
: 0.2,
"top_k"
: 10,
"top_p"
: 0.8
}

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
[I][                     EncodeImage][ 580]: image encode time : 915.744019 ms, size : 5
[I][                          Encode][ 622]: input_ids size:747
[I][                          Encode][ 630]: offset 15
[I][                          Encode][ 659]: img_embed.size:5, 294912
[I][                          Encode][ 664]: offset:159
[I][                          Encode][ 664]: offset:303
[I][                          Encode][ 664]: offset:447
[I][                          Encode][ 664]: offset:591
[I][                          Encode][ 673]: out_embed size:1529856
[I][                          Encode][ 674]: input_ids size 747
[I][                          Encode][ 676]: position_ids size:747
[I][                             Run][ 698]: input token num : 747, prefill_split_num : 6
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:107
[I][                             Run][ 909]: ttft: 2033.21 ms
The video captures a person walking through a modern, well-lit hallway. The individual, seen from behind, is wearing a white t-shirt with a blue graphic on the back and dark pants. They are moving towards a glass door,
which
is part of a larger
set
of doors, possibly
in
a building
's entrance or a corridor.

The hallway features dark, polished tiles with a subtle, elegant pattern. A green emergency exit sign is visible on the wall, indicating the direction to the exit. To the right of the person, a laptop is placed on a stand, its screen displaying a blue image, possibly a video or a live feed. The laptop is connected to a cable, suggesting it might be used for monitoring or communication purposes.

The overall atmosphere of the scene is clean, professional, and modern, with a focus on safety and technology. The person'
s movement and the surrounding environment suggest a routine activity, such as entering a building or checking on a system.

[N][                             Run][1062]: hit eos,avg 7.77 token/s

prompt >>
m5stack@raspberrypi:~/rsp/Qwen3-VL-2B-Instruct-axmodel $ ./run_video_axcl_aarch64.sh 
[I][                            Init][ 163]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:8080 ok
bos_id: -1, eos_id: 151645
img_start_token: 151652
img_context_token: 151656
  3% | ██                                |   1 /  31 [0.00s<0.09s, 333.33 count/s] tokenizer init ok[I][                            Init][  45]: LLaMaEmbedSelector use mmap
  6% | ███                               |   2 /  31 [0.00s<0.06s, 500.00 count/s] embed_selector init ok
[I][                             run][  30]: AXCLWorker start with devid 0
 16% | █████████ ██                                       |   4 /  31 [6.09s<47.22s, 0.66 count/s] init 7 axmodel ok,devid(0) remain_cmm(-1 MB 93% | ███████████████████████████████████████████████████████████     |  29 /  31 [39.21s<43.41s, 0.71 count/s] init 13 axmodel ok,devid(0) r100% | ████████████████████████████████ |  31 /  31 [45.05s<46.55s, 0.67 count/s] init post axmodel ok,remain_cmm(3341 MB)3665 MB)
input size: 1
    name: hidden_states [unknown] [unknown] 
        1 x 576 x 512 x 3 size:884736

output size: 4
    name: hidden_states_out 
        144 x 2048 size:1179648

    name: deepstack_feature_0 
        144 x 2048 size:1179648

    name: deepstack_feature_1 
        144 x 2048 size:1179648

    name: deepstack_feature_2 
        144 x 2048 size:1179648

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
|     0|           2899|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config: 
{
    "enable_repetition_penalty": false,
    "enable_temperature": true,
    "enable_top_k_sampling": true,
    "enable_top_p_sampling": false,
    "penalty_window": 30,
    "repetition_penalty": 1,
    "temperature": 0.2,
    "top_k": 10,
    "top_p": 0.8
}

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
[I][                     EncodeImage][ 580]: image encode time : 915.744019 ms, size : 5
[I][                          Encode][ 622]: input_ids size:747
[I][                          Encode][ 630]: offset 15
[I][                          Encode][ 659]: img_embed.size:5, 294912
[I][                          Encode][ 664]: offset:159
[I][                          Encode][ 664]: offset:303
[I][                          Encode][ 664]: offset:447
[I][                          Encode][ 664]: offset:591
[I][                          Encode][ 673]: out_embed size:1529856
[I][                          Encode][ 674]: input_ids size 747
[I][                          Encode][ 676]: position_ids size:747
[I][                             Run][ 698]: input token num : 747, prefill_split_num : 6
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:128
[I][                             Run][ 732]: input_num_token:107
[I][                             Run][ 909]: ttft: 2033.21 ms
The video captures a person walking through a modern, well-lit hallway. The individual, seen from behind, is wearing a white t-shirt with a blue graphic on the back and dark pants. They are moving towards a glass door, which is part of a larger set of doors, possibly in a building's entrance or a corridor.

The hallway features dark, polished tiles with a subtle, elegant pattern. A green emergency exit sign is visible on the wall, indicating the direction to the exit. To the right of the person, a laptop is placed on a stand, its screen displaying a blue image, possibly a video or a live feed. The laptop is connected to a cable, suggesting it might be used for monitoring or communication purposes.

The overall atmosphere of the scene is clean, professional, and modern, with a focus on safety and technology. The person's movement and the surrounding environment suggest a routine activity, such as entering a building or checking on a system.

[N][                             Run][1062]: hit eos,avg 7.77 token/s

prompt >>
Next
目录索引
On This Page
# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_qwen2.5_1.5b

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
Qwen2.5-1.5B
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
https://huggingface.co/AXERA-TECH/Qwen2.5-1.5B-Instruct-GPTQ-Int4
git clone https://huggingface.co/AXERA-TECH/Qwen2.5-1.5B-Instruct-GPTQ-Int4
文件说明
m5stack@raspberrypi:~/rsp/Qwen2.5-1.5B-Instruct-GPTQ-Int4$ ls -lh
total 2.9M
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 10:48 config.json
-rw-rw-r-- 1 m5stack m5stack 976K Aug 12 10:48 main_axcl_aarch64
-rw-rw-r-- 1 m5stack m5stack 999K Aug 12 10:48 main_axcl_x86
-rw-rw-r-- 1 m5stack m5stack 932K Aug 12 10:48 main_prefill
-rw-rw-r-- 1 m5stack m5stack  277 Aug 12 10:48 post_config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 10:49 qwen2.5-1.5b-gptq-int4-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 10:48 qwen2.5_tokenizer
-rw-rw-r-- 1 m5stack m5stack 4.2K Aug 12 10:48 qwen2.5_tokenizer.py
-rw-rw-r-- 1 m5stack m5stack 6.8K Aug 12 10:48 README.md
-rw-rw-r-- 1 m5stack m5stack  521 Aug 12 10:48 run_qwen2.5_1.5b_gptq_int4_ax650.sh
-rw-rw-r-- 1 m5stack m5stack  526 Aug 12 10:48 run_qwen2.5_1.5b_gptq_int4_axcl_aarch64.sh
-rw-rw-r-- 1 m5stack m5stack  522 Aug 12 10:48 run_qwen2.5_1.5b_gptq_int4_axcl_x86.sh
m5stack@raspberrypi:~/rsp/Qwen2.5-1.5B-Instruct-GPTQ-Int4$ ls -lh
total 2.9M
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 10:48 config.json
-rw-rw-r-- 1 m5stack m5stack 976K Aug 12 10:48 main_axcl_aarch64
-rw-rw-r-- 1 m5stack m5stack 999K Aug 12 10:48 main_axcl_x86
-rw-rw-r-- 1 m5stack m5stack 932K Aug 12 10:48 main_prefill
-rw-rw-r-- 1 m5stack m5stack  277 Aug 12 10:48 post_config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 10:49 qwen2.5-1.5b-gptq-int4-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 10:48 qwen2.5_tokenizer
-rw-rw-r-- 1 m5stack m5stack 4.2K Aug 12 10:48 qwen2.5_tokenizer.py
-rw-rw-r-- 1 m5stack m5stack 6.8K Aug 12 10:48 README.md
-rw-rw-r-- 1 m5stack m5stack  521 Aug 12 10:48 run_qwen2.5_1.5b_gptq_int4_ax650.sh
-rw-rw-r-- 1 m5stack m5stack  526 Aug 12 10:48 run_qwen2.5_1.5b_gptq_int4_axcl_aarch64.sh
-rw-rw-r-- 1 m5stack m5stack  522 Aug 12 10:48 run_qwen2.5_1.5b_gptq_int4_axcl_x86.sh
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
启动 tokenizer 解析器
python qwen2.5_tokenizer.py --port 12345
python qwen2.5_tokenizer.py --port 12345
运行 tokenizer 服务，Host ip 默认为 localhost，端口号设置为 12345，运行后信息如下：
(qwen) m5stack@raspberrypi:~/rsp/Qwen2.5-1.5B-Instruct-GPTQ-Int4 $ python qwen2.5_tokenizer.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won
't be available and only tokenizers, configuration and file/data utilities can be used.
None None 151645 <|im_end|>
<|im_start|>system
You are Qwen, created by Alibaba Cloud. You are a helpful assistant.<|im_end|>
<|im_start|>user
hello world<|im_end|>
<|im_start|>assistant

[151644, 8948, 198, 2610, 525, 1207, 16948, 11, 3465, 553, 54364, 14817, 13, 1446, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
http://localhost:12345
(qwen) m5stack@raspberrypi:~/rsp/Qwen2.5-1.5B-Instruct-GPTQ-Int4 $ python qwen2.5_tokenizer.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won't be available and only tokenizers, configuration and file/data utilities can be used.
None None 151645 <|im_end|>
<|im_start|>system
You are Qwen, created by Alibaba Cloud. You are a helpful assistant.<|im_end|>
<|im_start|>user
hello world<|im_end|>
<|im_start|>assistant

[151644, 8948, 198, 2610, 525, 1207, 16948, 11, 3465, 553, 54364, 14817, 13, 1446, 525, 264, 10950, 17847, 13, 151645, 198, 151644, 872, 198, 14990, 1879, 151645, 198, 151644, 77091, 198]
http://localhost:12345
提示
以下操作需要新建一个 raspberrypi 的终端。
设置可执行权限
chmod +x main_axcl_aarch64 run_qwen2.5_1.5b_gptq_int4_axcl_aarch64.sh
chmod +x main_axcl_aarch64 run_qwen2.5_1.5b_gptq_int4_axcl_aarch64.sh
启动 Qwen2.5 模型推理服务
./run_qwen2.5_1.5b_gptq_int4_axcl_aarch64.sh
./run_qwen2.5_1.5b_gptq_int4_axcl_aarch64.sh
成功启动后信息如下
m5stack@raspberrypi:~/rsp/Qwen2.5-1.5B-Instruct-GPTQ-Int4$ ./run_qwen2.5_1.5b_gptq_int4_axcl_aarch64.sh
build time: Feb 13 2025 15:44:57
[I][                            Init][ 111]: LLM init start
bos_id: -1, eos_id: 151645
  3% | ██                                |   1 /  31 [0.00s<0.09s, 333.33 count/s] tokenizer init
  100% | ████████████████████████████████ |  31 /  31 [28.75s<28.75s, 1.08 count/s] init post axmodel ok
[I][                            Init][ 226]: max_token_len : 1024
[I][                            Init][ 231]: kv_cache_size : 256, kv_cache_num: 1024
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
: 20,
"repetition_penalty"
: 1.2,
"temperature"
: 0.9,
"top_k"
: 10,
"top_p"
: 0.8
}

[I][                            Init][ 288]: LLM init ok
Type
"q"
to
exit
, Ctrl+c to stop current running
>> hello
Hello! How can I assist you today?

[N][                             Run][ 610]: hit eos,avg 15.03 token/s

>>
m5stack@raspberrypi:~/rsp/Qwen2.5-1.5B-Instruct-GPTQ-Int4$ ./run_qwen2.5_1.5b_gptq_int4_axcl_aarch64.sh
build time: Feb 13 2025 15:44:57
[I][                            Init][ 111]: LLM init start
bos_id: -1, eos_id: 151645
  3% | ██                                |   1 /  31 [0.00s<0.09s, 333.33 count/s] tokenizer init
  100% | ████████████████████████████████ |  31 /  31 [28.75s<28.75s, 1.08 count/s] init post axmodel ok
[I][                            Init][ 226]: max_token_len : 1024
[I][                            Init][ 231]: kv_cache_size : 256, kv_cache_num: 1024
[I][                     load_config][ 282]: load config:
{
    "enable_repetition_penalty": false,
    "enable_temperature": true,
    "enable_top_k_sampling": true,
    "enable_top_p_sampling": false,
    "penalty_window": 20,
    "repetition_penalty": 1.2,
    "temperature": 0.9,
    "top_k": 10,
    "top_p": 0.8
}

[I][                            Init][ 288]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
>> hello
Hello! How can I assist you today?

[N][                             Run][ 610]: hit eos,avg 15.03 token/s

>>
Next
目录索引
On This Page
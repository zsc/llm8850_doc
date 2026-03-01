# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_minicpm4

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
MiniCPM4-0.5B
MiniCPM4-0.5B 是一款轻量级、约 5 亿参数的高效多语言对话模型，具备良好的理解与生成能力，适用于资源受限环境。
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
https://huggingface.co/AXERA-TECH/MiniCPM4-0.5B
git clone https://huggingface.co/AXERA-TECH/MiniCPM4-0.5B
文件说明：
m5stack@raspberrypi:~/rsp/MiniCPM4-0.5B $ ls -lh
total 4.4M
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 10:58 config.json
-rw-rw-r-- 1 m5stack m5stack 967K Aug 12 11:00 main_ax650
-rw-rw-r-- 1 m5stack m5stack 1.7M Aug 12 11:00 main_axcl_aarch64
-rw-rw-r-- 1 m5stack m5stack 1.8M Aug 12 11:00 main_axcl_x86
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:00 minicpm4-0.5b-int8-ctx-ax630c
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:00 minicpm4-0.5b-int8-ctx-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:00 minicpm4_tokenizer
-rw-rw-r-- 1 m5stack m5stack 7.1K Aug 12 10:58 minicpm4_tokenizer_uid.py
-rw-rw-r-- 1 m5stack m5stack  277 Aug 12 10:58 post_config.json
-rw-rw-r-- 1 m5stack m5stack 5.2K Aug 12 10:58 README.md
-rw-rw-r-- 1 m5stack m5stack  642 Aug 12 10:58 run_minicpm4_0.5b_int8_ctx_ax630c.sh
-rw-rw-r-- 1 m5stack m5stack  639 Aug 12 10:58 run_minicpm4_0.5b_int8_ctx_ax650.sh
m5stack@raspberrypi:~/rsp/MiniCPM4-0.5B $ ls -lh
total 4.4M
-rw-rw-r-- 1 m5stack m5stack    0 Aug 12 10:58 config.json
-rw-rw-r-- 1 m5stack m5stack 967K Aug 12 11:00 main_ax650
-rw-rw-r-- 1 m5stack m5stack 1.7M Aug 12 11:00 main_axcl_aarch64
-rw-rw-r-- 1 m5stack m5stack 1.8M Aug 12 11:00 main_axcl_x86
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:00 minicpm4-0.5b-int8-ctx-ax630c
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:00 minicpm4-0.5b-int8-ctx-ax650
drwxrwxr-x 2 m5stack m5stack 4.0K Aug 12 11:00 minicpm4_tokenizer
-rw-rw-r-- 1 m5stack m5stack 7.1K Aug 12 10:58 minicpm4_tokenizer_uid.py
-rw-rw-r-- 1 m5stack m5stack  277 Aug 12 10:58 post_config.json
-rw-rw-r-- 1 m5stack m5stack 5.2K Aug 12 10:58 README.md
-rw-rw-r-- 1 m5stack m5stack  642 Aug 12 10:58 run_minicpm4_0.5b_int8_ctx_ax630c.sh
-rw-rw-r-- 1 m5stack m5stack  639 Aug 12 10:58 run_minicpm4_0.5b_int8_ctx_ax650.sh
创建虚拟环境
python -m venv minicpm
python -m venv minicpm
激活虚拟环境
source
minicpm/bin/activate
source minicpm/bin/activate
安装依赖包
pip install transformers jinja2
pip install transformers jinja2
启动 tokenizer 解析器
python minicpm4_tokenizer_uid.py --port 12345
python minicpm4_tokenizer_uid.py --port 12345
运行 tokenizer 服务，Host ip 默认为 localhost，端口号设置为 12345，正在运行后信息如下：
(minicpm) m5stack@raspberrypi:~/rsp/MiniCPM4-0.5B $ python minicpm4_tokenizer_uid.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won
't be available and only tokenizers, configuration and file/data utilities can be used.
Server running at http://0.0.0.0:12345
(minicpm) m5stack@raspberrypi:~/rsp/MiniCPM4-0.5B $ python minicpm4_tokenizer_uid.py --port 12345
None of PyTorch, TensorFlow >= 2.0, or Flax have been found. Models won't be available and only tokenizers, configuration and file/data utilities can be used.
Server running at http://0.0.0.0:12345
提示
以下操作需要新建一个 raspberrypi 的终端
设置可执行权限
chmod +x main_axcl_aarch64
chmod +x main_axcl_aarch64
启动 MiniCPM4-0.5B 模型推理服务
./main_axcl_aarch64 --system_prompt
"You are MiniCPM4, created by ModelBest. You are a helpful assistant."
--kvcache_path
"./kvcache"
--template_filename_axmodel
"minicpm4-0.5b-int8-ctx-ax650/MiniCPMForCausalLM_p128_l%d_together.axmodel"
--axmodel_num 24 --tokenizer_type 2 --url_tokenizer_model
"http://127.0.0.1:12345"
--filename_post_axmodel
"minicpm4-0.5b-int8-ctx-ax650/MiniCPMForCausalLM_post.axmodel"
--filename_tokens_embed
"minicpm4-0.5b-int8-ctx-ax650/model.embed_tokens.weight.bfloat16.bin"
--tokens_embed_num 73448 --tokens_embed_size 1024 --use_mmap_load_embed 0 --live_print 1 --devices 0
./main_axcl_aarch64 --system_prompt "You are MiniCPM4, created by ModelBest. You are a helpful assistant." --kvcache_path "./kvcache" --template_filename_axmodel "minicpm4-0.5b-int8-ctx-ax650/MiniCPMForCausalLM_p128_l%d_together.axmodel" --axmodel_num 24 --tokenizer_type 2 --url_tokenizer_model "http://127.0.0.1:12345" --filename_post_axmodel "minicpm4-0.5b-int8-ctx-ax650/MiniCPMForCausalLM_post.axmodel" --filename_tokens_embed "minicpm4-0.5b-int8-ctx-ax650/model.embed_tokens.weight.bfloat16.bin" --tokens_embed_num 73448 --tokens_embed_size 1024 --use_mmap_load_embed 0 --live_print 1 --devices 0
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/MiniCPM4-0.5B$ ./main_axcl_aarch64 --system_prompt
"You are MiniCPM4, created by ModelBest. You are a helpful assistant."
--kvcache_path
"./kvcache"
--template_filename_axmodel
"minicpm4-0.5b-int8-ctx-ax650/MiniCPMForCausalLM_p128_l%d_together.axmodel"
--axmodel_num 24 --tokenizer_type 2 --url_tokenizer_model
"http://127.0.0.1:12345"
--filename_post_axmodel
"minicpm4-0.5b-int8-ctx-ax650/MiniCPMForCausalLM_post.axmodel"
--filename_tokens_embed
"minicpm4-0.5b-int8-ctx-ax650/model.embed_tokens.weight.bfloat16.bin"
--tokens_embed_num 73448 --tokens_embed_size 1024 --use_mmap_load_embed 0 --live_print 1 --devices 0
[I][                            Init][ 136]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
[I][                            Init][  57]: uid: 9f086096-ff95-40cd-91f0-7551875c5e61
bos_id: 1, eos_id: 73440
  3% | ██                                |   1 /  27 [0.51s<13.72s, 1.97 count/s] tokenizer init ok
  100% | ████████████████████████████████ |  27 /  27 [22.21s<22.21s, 1.22 count/s] init post axmodel ok,remain_cmm(6450 MB)
[I][                            Init][ 237]: max_token_len : 1023
[I][                            Init][ 240]: kv_cache_size : 128, kv_cache_num: 1023
[I][                            Init][ 248]: prefill_token_num : 128
[I][                            Init][ 252]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 252]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 252]: grp: 3, prefill_max_token_num : 512
[I][                            Init][ 256]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|           6450|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config:
{
"enable_repetition_penalty"
:
false
,
"enable_temperature"
:
false
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
: 1,
"top_p"
: 0.8
}

[I][                            Init][ 279]: LLM init ok
Type
"q"
to
exit
, Ctrl+c to stop current running
[E][                    load_kvcache][ 100]: k_cache ./kvcache/k_cache_0.bin or v_cache ./kvcache/v_cache_0.bin not exist
[W][                            main][ 223]: load kvcache from path: ./kvcache failed,generate kvcache
[I][          GenerateKVCachePrefill][ 336]: input token num : 25, prefill_split_num : 1 prefill_grpid : 2
[I][          GenerateKVCachePrefill][ 373]: input_num_token:25
[E][                    save_kvcache][  49]: save kvcache failed
[E][                            main][ 227]: save kvcache failed
[I][                            main][ 229]: generate kvcache to path: ./kvcache
[I][                            main][ 236]: precompute_len: 25
[I][                            main][ 237]: system_prompt: You are MiniCPM4, created by ModelBest. You are a helpful assistant.
prompt >> hello
[I][                      SetKVCache][ 629]: prefill_grpid:2 kv_cache_num:128 precompute_len:25 input_num_token:10
[I][                      SetKVCache][ 632]: current prefill_max_token_num:384
[I][                             Run][ 870]: input token num : 10, prefill_split_num : 1
[I][                             Run][ 902]: input_num_token:10
[I][                             Run][1031]: ttft: 212.91 ms
Hi, Iam a MiniCPM seriesmodel, developedby Modelbestand OpenBMB. Formore information,please visit https://github.com/OpenBMB/

[N][                             Run][1183]: hit eos,avg 21.05 token/s

[I][                      GetKVCache][ 598]: precompute_len:71, remaining:441
prompt >>
m5stack@raspberrypi:~/rsp/MiniCPM4-0.5B$ ./main_axcl_aarch64 --system_prompt "You are MiniCPM4, created by ModelBest. You are a helpful assistant." --kvcache_path "./kvcache" --template_filename_axmodel "minicpm4-0.5b-int8-ctx-ax650/MiniCPMForCausalLM_p128_l%d_together.axmodel" --axmodel_num 24 --tokenizer_type 2 --url_tokenizer_model "http://127.0.0.1:12345" --filename_post_axmodel "minicpm4-0.5b-int8-ctx-ax650/MiniCPMForCausalLM_post.axmodel" --filename_tokens_embed "minicpm4-0.5b-int8-ctx-ax650/model.embed_tokens.weight.bfloat16.bin" --tokens_embed_num 73448 --tokens_embed_size 1024 --use_mmap_load_embed 0 --live_print 1 --devices 0
[I][                            Init][ 136]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
[I][                            Init][  57]: uid: 9f086096-ff95-40cd-91f0-7551875c5e61
bos_id: 1, eos_id: 73440
  3% | ██                                |   1 /  27 [0.51s<13.72s, 1.97 count/s] tokenizer init ok
  100% | ████████████████████████████████ |  27 /  27 [22.21s<22.21s, 1.22 count/s] init post axmodel ok,remain_cmm(6450 MB)
[I][                            Init][ 237]: max_token_len : 1023
[I][                            Init][ 240]: kv_cache_size : 128, kv_cache_num: 1023
[I][                            Init][ 248]: prefill_token_num : 128
[I][                            Init][ 252]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 252]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 252]: grp: 3, prefill_max_token_num : 512
[I][                            Init][ 256]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|           6450|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                     load_config][ 282]: load config:
{
    "enable_repetition_penalty": false,
    "enable_temperature": false,
    "enable_top_k_sampling": true,
    "enable_top_p_sampling": false,
    "penalty_window": 20,
    "repetition_penalty": 1.2,
    "temperature": 0.9,
    "top_k": 1,
    "top_p": 0.8
}

[I][                            Init][ 279]: LLM init ok
Type "q" to exit, Ctrl+c to stop current running
[E][                    load_kvcache][ 100]: k_cache ./kvcache/k_cache_0.bin or v_cache ./kvcache/v_cache_0.bin not exist
[W][                            main][ 223]: load kvcache from path: ./kvcache failed,generate kvcache
[I][          GenerateKVCachePrefill][ 336]: input token num : 25, prefill_split_num : 1 prefill_grpid : 2
[I][          GenerateKVCachePrefill][ 373]: input_num_token:25
[E][                    save_kvcache][  49]: save kvcache failed
[E][                            main][ 227]: save kvcache failed
[I][                            main][ 229]: generate kvcache to path: ./kvcache
[I][                            main][ 236]: precompute_len: 25
[I][                            main][ 237]: system_prompt: You are MiniCPM4, created by ModelBest. You are a helpful assistant.
prompt >> hello
[I][                      SetKVCache][ 629]: prefill_grpid:2 kv_cache_num:128 precompute_len:25 input_num_token:10
[I][                      SetKVCache][ 632]: current prefill_max_token_num:384
[I][                             Run][ 870]: input token num : 10, prefill_split_num : 1
[I][                             Run][ 902]: input_num_token:10
[I][                             Run][1031]: ttft: 212.91 ms
Hi, Iam a MiniCPM seriesmodel, developedby Modelbestand OpenBMB. Formore information,please visit https://github.com/OpenBMB/

[N][                             Run][1183]: hit eos,avg 21.05 token/s

[I][                      GetKVCache][ 598]: precompute_len:71, remaining:441
prompt >>
模型
量化方式
tftt (ms)
token/s
MiniCPM4-0.5B
w8a16
212.91
21.05
Next
目录索引
On This Page
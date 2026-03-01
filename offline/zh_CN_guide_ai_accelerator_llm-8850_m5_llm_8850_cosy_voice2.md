# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_cosy_voice2

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
CosyVoice2
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
https://huggingface.co/AXERA-TECH/CosyVoice2
git clone https://huggingface.co/AXERA-TECH/CosyVoice2
文件说明：
m5stack@raspberrypi:~/rsp/CosyVoice2 $ ls -lh
total 26M
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 27 15:54 asset
-rwxrwxr-x 1 m5stack m5stack    0 Sep 18 14:32 config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Sep  5 19:12 CosyVoice-BlankEN-Ax650-prefill_512
drwxrwxr-x 2 m5stack m5stack 4.0K Sep  5 19:11 frontend-onnx
-rwxrwxr-x 1 m5stack m5stack 9.3M Sep 27 15:33 main_api_ax650
-rwxrwxr-x 1 m5stack m5stack 1.9M Sep 27 15:33 main_api_axcl_aarch64
-rwxrwxr-x 1 m5stack m5stack 2.0M Sep 27 15:33 main_api_axcl_x86
-rwxrwxr-x 1 m5stack m5stack 9.2M Sep 18 09:35 main_ax650
-rwxrwxr-x 1 m5stack m5stack 1.8M Sep 27 15:33 main_axcl_aarch64
-rwxrwxr-x 1 m5stack m5stack 1.9M Sep 27 15:33 main_axcl_x86
drwxrwxr-x 3 m5stack m5stack 4.0K Sep 27 15:33 onnxruntime-linux-aarch64-1.23.0
drwxrwxr-x 3 m5stack m5stack 4.0K Sep 27 15:33 onnxruntime-linux-x64-1.23.0
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 15 10:07 prompt_files
-rwxrwxr-x 1 m5stack m5stack 7.9K Sep 27 15:33 README.md
-rwxrwxr-x 1 m5stack m5stack  895 Sep 27 15:33 run_api_ax650.sh
-rwxrwxr-x 1 m5stack m5stack  997 Sep 27 15:33 run_api_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  989 Sep 27 15:33 run_api_axcl_x86.sh
-rwxrwxr-x 1 m5stack m5stack  865 Sep 27 15:33 run_ax650.sh
-rwxrwxr-x 1 m5stack m5stack  967 Sep 27 15:33 run_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  959 Sep 27 15:33 run_axcl_x86.sh
drwxrwxr-x 5 m5stack m5stack 4.0K Sep 27 15:33 scripts
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 27 15:33 token2wav-axmodels
m5stack@raspberrypi:~/rsp/CosyVoice2 $ ls -lh
total 26M
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 27 15:54 asset
-rwxrwxr-x 1 m5stack m5stack    0 Sep 18 14:32 config.json
drwxrwxr-x 2 m5stack m5stack 4.0K Sep  5 19:12 CosyVoice-BlankEN-Ax650-prefill_512
drwxrwxr-x 2 m5stack m5stack 4.0K Sep  5 19:11 frontend-onnx
-rwxrwxr-x 1 m5stack m5stack 9.3M Sep 27 15:33 main_api_ax650
-rwxrwxr-x 1 m5stack m5stack 1.9M Sep 27 15:33 main_api_axcl_aarch64
-rwxrwxr-x 1 m5stack m5stack 2.0M Sep 27 15:33 main_api_axcl_x86
-rwxrwxr-x 1 m5stack m5stack 9.2M Sep 18 09:35 main_ax650
-rwxrwxr-x 1 m5stack m5stack 1.8M Sep 27 15:33 main_axcl_aarch64
-rwxrwxr-x 1 m5stack m5stack 1.9M Sep 27 15:33 main_axcl_x86
drwxrwxr-x 3 m5stack m5stack 4.0K Sep 27 15:33 onnxruntime-linux-aarch64-1.23.0
drwxrwxr-x 3 m5stack m5stack 4.0K Sep 27 15:33 onnxruntime-linux-x64-1.23.0
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 15 10:07 prompt_files
-rwxrwxr-x 1 m5stack m5stack 7.9K Sep 27 15:33 README.md
-rwxrwxr-x 1 m5stack m5stack  895 Sep 27 15:33 run_api_ax650.sh
-rwxrwxr-x 1 m5stack m5stack  997 Sep 27 15:33 run_api_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  989 Sep 27 15:33 run_api_axcl_x86.sh
-rwxrwxr-x 1 m5stack m5stack  865 Sep 27 15:33 run_ax650.sh
-rwxrwxr-x 1 m5stack m5stack  967 Sep 27 15:33 run_axcl_aarch64.sh
-rwxrwxr-x 1 m5stack m5stack  959 Sep 27 15:33 run_axcl_x86.sh
drwxrwxr-x 5 m5stack m5stack 4.0K Sep 27 15:33 scripts
drwxrwxr-x 2 m5stack m5stack 4.0K Sep 27 15:33 token2wav-axmodels
创建虚拟环境
python -m venv cosyvoice
python -m venv cosyvoice
激活虚拟环境
source
cosyvoice/bin/activate
source cosyvoice/bin/activate
安装依赖包
pip install -r scripts/requirements.txt
pip install -r scripts/requirements.txt
启动 tokenizer 解析器
cd
scripts
python cosyvoice2_tokenizer.py
cd scripts
python cosyvoice2_tokenizer.py
运行 tokenizer 服务，Host ip 默认为 localhost，端口号设置为 12345，运行后信息如下：
(cosyvoice) m5stack@raspberrypi:~/rsp/CosyVoice2/scripts $ python cosyvoice2_tokenizer.py 
[14990, 1879]
http://localhost:12345
(cosyvoice) m5stack@raspberrypi:~/rsp/CosyVoice2/scripts $ python cosyvoice2_tokenizer.py 
[14990, 1879]
http://localhost:12345
提示
以下操作需要新建一个 raspberrypi 的终端。
使用 CosyVoice2 模型单次推理，输出音频文件为
output.wav
./run_axcl_aarch64.sh
./run_axcl_aarch64.sh
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/CosyVoice2 $ ./run_axcl_aarch64.sh 
rm: cannot remove
'output*.wav'
: No such file or directory
[I][                            main][ 291]: device: 0
[I][                             run][  30]: AXCLWorker start with devid 0
[I][                            Init][ 135]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
bos_id: 0, eos_id: 1773
  3% | ██                                |   1 /  27 [0.00s<0.03s, 1000.00 count  7% | ███                               |   2 /  27 [0.13s<1.81s, 14.93 count/s] embed_selector init ok[I][                            Init][ 174]: attr.axmodel_num:24
 11% | ████                              |   3 /  27 [1.35s<12.13s, 2.23 count/s 14% | ███████████████████████████████   |  26 /  27 [7.92s<8.22s, 3.28 count/s]100% | ████████████████████████████████ |  27 /  27 [10.59s<10.59s, 2.55 count/s] init post axmodel ok,remain_cmm(6323 MB)
[I][                            Init][ 225]: max_token_len : 1023
[I][                            Init][ 230]: kv_cache_size : 128, kv_cache_num: 1023
[I][                            Init][ 238]: prefill_token_num : 128
[I][                            Init][ 242]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 242]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 242]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 242]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 242]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 246]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|           6323|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                            Init][ 308]: LLM init ok
2025-09-29 11:09:20.814330123 [W:onnxruntime:, device_discovery.cc:164 DiscoverDevicesForPlatform] GPU device discovery failed: device_discovery.cc:89 ReadFileContents Failed to open file:
"/sys/class/drm/card1/device/vendor"
inputs: 
                 mel: 1 x 80 x 50
output: 
                   s: 1 x 1 x 24000

inputs: 
                 mel: 1 x 80 x 58
output: 
                   s: 1 x 1 x 27840
[I][                            Init][ 213]: Token2Wav init ok, remain_cmm(5863 MB)
[I][                             Run][ 449]: input token num : 142, prefill_split_num : 2
[I][                             Run][ 483]: input_num_token:128
[I][                             Run][ 483]: input_num_token:14
[I][                             Run][ 642]: ttft: 339.72 ms
[Main/Token2Wav Thread] Processing batch of 28 tokens...
Successfully saved audio to output_0.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 53 tokens...
Successfully saved audio to output_1.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_2.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_3.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_4.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_5.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_6.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_7.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_8.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_9.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_10.wav (32-bit Float PCM).
[I][                             Run][ 765]: hit eos, llm finished
[I][                             Run][ 795]: llm finished
[Main/Token2Wav Thread] Buffer is empty and LLM finished. Exiting.

[I][                             Run][ 800]: total decode tokens:300
[N][                             Run][ 801]: hit eos, decode avg 14.54 token/s

Successfully saved audio to output_11.wav (32-bit Float PCM).
Successfully saved audio to output.wav (32-bit Float PCM).
[I][                             tts][ 225]: tts total use time: 21.555 s

Voice generation pipeline completed.
[I][                             run][  80]: AXCLWorker
exit
with devid 0
m5stack@raspberrypi:~/rsp/CosyVoice2 $ ./run_axcl_aarch64.sh 
rm: cannot remove 'output*.wav': No such file or directory
[I][                            main][ 291]: device: 0
[I][                             run][  30]: AXCLWorker start with devid 0
[I][                            Init][ 135]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
bos_id: 0, eos_id: 1773
  3% | ██                                |   1 /  27 [0.00s<0.03s, 1000.00 count  7% | ███                               |   2 /  27 [0.13s<1.81s, 14.93 count/s] embed_selector init ok[I][                            Init][ 174]: attr.axmodel_num:24
 11% | ████                              |   3 /  27 [1.35s<12.13s, 2.23 count/s 14% | ███████████████████████████████   |  26 /  27 [7.92s<8.22s, 3.28 count/s]100% | ████████████████████████████████ |  27 /  27 [10.59s<10.59s, 2.55 count/s] init post axmodel ok,remain_cmm(6323 MB)
[I][                            Init][ 225]: max_token_len : 1023
[I][                            Init][ 230]: kv_cache_size : 128, kv_cache_num: 1023
[I][                            Init][ 238]: prefill_token_num : 128
[I][                            Init][ 242]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 242]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 242]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 242]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 242]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 246]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|           6323|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                            Init][ 308]: LLM init ok
2025-09-29 11:09:20.814330123 [W:onnxruntime:, device_discovery.cc:164 DiscoverDevicesForPlatform] GPU device discovery failed: device_discovery.cc:89 ReadFileContents Failed to open file: "/sys/class/drm/card1/device/vendor"

inputs: 
                 mel: 1 x 80 x 50
output: 
                   s: 1 x 1 x 24000

inputs: 
                 mel: 1 x 80 x 58
output: 
                   s: 1 x 1 x 27840
[I][                            Init][ 213]: Token2Wav init ok, remain_cmm(5863 MB)
[I][                             Run][ 449]: input token num : 142, prefill_split_num : 2
[I][                             Run][ 483]: input_num_token:128
[I][                             Run][ 483]: input_num_token:14
[I][                             Run][ 642]: ttft: 339.72 ms
[Main/Token2Wav Thread] Processing batch of 28 tokens...
Successfully saved audio to output_0.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 53 tokens...
Successfully saved audio to output_1.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_2.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_3.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_4.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_5.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_6.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_7.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_8.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_9.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_10.wav (32-bit Float PCM).
[I][                             Run][ 765]: hit eos, llm finished
[I][                             Run][ 795]: llm finished
[Main/Token2Wav Thread] Buffer is empty and LLM finished. Exiting.

[I][                             Run][ 800]: total decode tokens:300
[N][                             Run][ 801]: hit eos, decode avg 14.54 token/s

Successfully saved audio to output_11.wav (32-bit Float PCM).
Successfully saved audio to output.wav (32-bit Float PCM).
[I][                             tts][ 225]: tts total use time: 21.555 s

Voice generation pipeline completed.
[I][                             run][  80]: AXCLWorker exit with devid 0
修改 ‘run_axcl_aarch64.sh’ 中
continue
为
1
，再次执行，进入 CosyVoice2 交互推理模式，输出音频文件为
output.wav
m5stack@raspberrypi:~/rsp/CosyVoice2 $ cat ./run_axcl_aarch64.sh 
export LD_LIBRARY_PATH=onnxruntime-linux-aarch64-1.23.0/lib:$LD_LIBRARY_PATH

LLM_DIR=CosyVoice-BlankEN-Ax650-prefill_512/
TOKEN2WAV_DIR=token2wav-axmodels/

rm output*.wav
./main_axcl_aarch64 \
--template_filename_axmodel "${LLM_DIR}/qwen2_p128_l%d_together.axmodel" \
--token2wav_axmodel_dir $TOKEN2WAV_DIR \
--n_timesteps 10 \
--axmodel_num 24 \
--bos 0 --eos 0 \
--filename_tokenizer_model "http://127.0.0.1:12345" \
--filename_post_axmodel "${LLM_DIR}/qwen2_post.axmodel" \
--filename_decoder_axmodel "${LLM_DIR}/llm_decoder.axmodel" \
--filename_tokens_embed "${LLM_DIR}/model.embed_tokens.weight.bfloat16.bin" \
--filename_llm_embed "${LLM_DIR}/llm.llm_embedding.float16.bin" \
--filename_speech_embed "${LLM_DIR}/llm.speech_embedding.float16.bin" \
--continue 1 \
--devices "0," \
--prompt_files prompt_files \
--text "君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。"

chmod 777 output*.wav
m5stack@raspberrypi:~/rsp/CosyVoice2 $ cat ./run_axcl_aarch64.sh 
export LD_LIBRARY_PATH=onnxruntime-linux-aarch64-1.23.0/lib:$LD_LIBRARY_PATH

LLM_DIR=CosyVoice-BlankEN-Ax650-prefill_512/
TOKEN2WAV_DIR=token2wav-axmodels/

rm output*.wav
./main_axcl_aarch64 \
--template_filename_axmodel "${LLM_DIR}/qwen2_p128_l%d_together.axmodel" \
--token2wav_axmodel_dir $TOKEN2WAV_DIR \
--n_timesteps 10 \
--axmodel_num 24 \
--bos 0 --eos 0 \
--filename_tokenizer_model "http://127.0.0.1:12345" \
--filename_post_axmodel "${LLM_DIR}/qwen2_post.axmodel" \
--filename_decoder_axmodel "${LLM_DIR}/llm_decoder.axmodel" \
--filename_tokens_embed "${LLM_DIR}/model.embed_tokens.weight.bfloat16.bin" \
--filename_llm_embed "${LLM_DIR}/llm.llm_embedding.float16.bin" \
--filename_speech_embed "${LLM_DIR}/llm.speech_embedding.float16.bin" \
--continue 1 \
--devices "0," \
--prompt_files prompt_files \
--text "君不见黄河之水天上来，奔流到海不复回。君不见高堂明镜悲白发，朝如青丝暮成雪。"

chmod 777 output*.wav
成功启动后信息如下：
m5stack@raspberrypi:~/rsp/CosyVoice2 $ ./run_axcl_aarch64.sh 
[I][                            main][ 291]: device: 0
[I][                             run][  30]: AXCLWorker start with devid 0
[I][                            Init][ 135]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
bos_id: 0, eos_id: 1773
  3% | ██                                |   1 /  27 [0.00s<0.03s, 1000.00 count  7% | ████████████████████████████████ |  27 /  27 [10.57s<10.57s, 2.55 count/s] init post axmodel ok,remain_cmm(6323 MB)
[I][                            Init][ 225]: max_token_len : 1023
[I][                            Init][ 230]: kv_cache_size : 128, kv_cache_num: 1023
[I][                            Init][ 238]: prefill_token_num : 128
[I][                            Init][ 242]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 242]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 242]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 242]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 242]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 246]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|           6323|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                            Init][ 308]: LLM init ok
2025-09-29 11:22:34.715409537 [W:onnxruntime:, device_discovery.cc:164 DiscoverDevicesForPlatform] GPU device discovery failed: device_discovery.cc:89 ReadFileContents Failed to open file:
"/sys/class/drm/card1/device/vendor"
inputs: 
                 mel: 1 x 80 x 50
output: 
                   s: 1 x 1 x 24000

inputs: 
                 mel: 1 x 80 x 58
output: 
                   s: 1 x 1 x 27840
[I][                            Init][ 213]: Token2Wav init ok, remain_cmm(5863 MB)
[I][                             Run][ 449]: input token num : 142, prefill_split_num : 2
[I][                             Run][ 483]: input_num_token:128
[I][                             Run][ 483]: input_num_token:14
[I][                             Run][ 642]: ttft: 342.93 ms
[Main/Token2Wav Thread] Processing batch of 28 tokens...
Successfully saved audio to output_0.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 53 tokens...
Successfully saved audio to output_1.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_2.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_3.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_4.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_5.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_6.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_7.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_8.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_9.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
[I][                             Run][ 765]: hit eos, llm finished
[I][                             Run][ 795]: llm finished

[I][                             Run][ 800]: total decode tokens:278
[N][                             Run][ 801]: hit eos, decode avg 14.37 token/s

Successfully saved audio to output_10.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Buffer is empty and LLM finished. Exiting.
Successfully saved audio to output_11.wav (32-bit Float PCM).
Successfully saved audio to output.wav (32-bit Float PCM).
[I][                             tts][ 225]: tts total use time: 20.305 s

Voice generation pipeline completed.
Type
"q"
to
exit
, Ctrl+c to stop current running
text >> 很高兴认识你，Nice to meet you
[I][                             Run][ 449]: input token num : 115, prefill_split_num : 1
[I][                             Run][ 483]: input_num_token:115
[I][                             Run][ 642]: ttft: 153.41 ms
[Main/Token2Wav Thread] Processing batch of 28 tokens...
Successfully saved audio to output_0.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 53 tokens...
Successfully saved audio to output_1.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_2.wav (32-bit Float PCM).
[I][                             Run][ 765]: hit eos, llm finished
[I][                             Run][ 795]: llm finished

[I][                             Run][ 800]: total decode tokens:93
[N][                             Run][ 801]: hit eos, decode avg 15.73 token/s

[Main/Token2Wav Thread] Buffer is empty and LLM finished. Exiting.
Successfully saved audio to output_3.wav (32-bit Float PCM).
Successfully saved audio to output.wav (32-bit Float PCM).
[I][                             tts][ 225]: tts total use time: 6.617 s

Voice generation pipeline completed.
text >>
m5stack@raspberrypi:~/rsp/CosyVoice2 $ ./run_axcl_aarch64.sh 
[I][                            main][ 291]: device: 0
[I][                             run][  30]: AXCLWorker start with devid 0
[I][                            Init][ 135]: LLM init start
[I][                            Init][  34]: connect http://127.0.0.1:12345 ok
bos_id: 0, eos_id: 1773
  3% | ██                                |   1 /  27 [0.00s<0.03s, 1000.00 count  7% | ████████████████████████████████ |  27 /  27 [10.57s<10.57s, 2.55 count/s] init post axmodel ok,remain_cmm(6323 MB)
[I][                            Init][ 225]: max_token_len : 1023
[I][                            Init][ 230]: kv_cache_size : 128, kv_cache_num: 1023
[I][                            Init][ 238]: prefill_token_num : 128
[I][                            Init][ 242]: grp: 1, prefill_max_token_num : 1
[I][                            Init][ 242]: grp: 2, prefill_max_token_num : 128
[I][                            Init][ 242]: grp: 3, prefill_max_token_num : 256
[I][                            Init][ 242]: grp: 4, prefill_max_token_num : 384
[I][                            Init][ 242]: grp: 5, prefill_max_token_num : 512
[I][                            Init][ 246]: prefill_max_token_num : 512
________________________
|    ID| remain cmm(MB)|
========================
|     0|           6323|
¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
[I][                            Init][ 308]: LLM init ok
2025-09-29 11:22:34.715409537 [W:onnxruntime:, device_discovery.cc:164 DiscoverDevicesForPlatform] GPU device discovery failed: device_discovery.cc:89 ReadFileContents Failed to open file: "/sys/class/drm/card1/device/vendor"

inputs: 
                 mel: 1 x 80 x 50
output: 
                   s: 1 x 1 x 24000

inputs: 
                 mel: 1 x 80 x 58
output: 
                   s: 1 x 1 x 27840
[I][                            Init][ 213]: Token2Wav init ok, remain_cmm(5863 MB)
[I][                             Run][ 449]: input token num : 142, prefill_split_num : 2
[I][                             Run][ 483]: input_num_token:128
[I][                             Run][ 483]: input_num_token:14
[I][                             Run][ 642]: ttft: 342.93 ms
[Main/Token2Wav Thread] Processing batch of 28 tokens...
Successfully saved audio to output_0.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 53 tokens...
Successfully saved audio to output_1.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_2.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_3.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_4.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_5.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_6.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_7.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_8.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_9.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
[I][                             Run][ 765]: hit eos, llm finished
[I][                             Run][ 795]: llm finished

[I][                             Run][ 800]: total decode tokens:278
[N][                             Run][ 801]: hit eos, decode avg 14.37 token/s

Successfully saved audio to output_10.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Buffer is empty and LLM finished. Exiting.
Successfully saved audio to output_11.wav (32-bit Float PCM).
Successfully saved audio to output.wav (32-bit Float PCM).
[I][                             tts][ 225]: tts total use time: 20.305 s

Voice generation pipeline completed.
Type "q" to exit, Ctrl+c to stop current running
text >> 很高兴认识你，Nice to meet you
[I][                             Run][ 449]: input token num : 115, prefill_split_num : 1
[I][                             Run][ 483]: input_num_token:115
[I][                             Run][ 642]: ttft: 153.41 ms
[Main/Token2Wav Thread] Processing batch of 28 tokens...
Successfully saved audio to output_0.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 53 tokens...
Successfully saved audio to output_1.wav (32-bit Float PCM).
[Main/Token2Wav Thread] Processing batch of 78 tokens...
Successfully saved audio to output_2.wav (32-bit Float PCM).
[I][                             Run][ 765]: hit eos, llm finished
[I][                             Run][ 795]: llm finished

[I][                             Run][ 800]: total decode tokens:93
[N][                             Run][ 801]: hit eos, decode avg 15.73 token/s

[Main/Token2Wav Thread] Buffer is empty and LLM finished. Exiting.
Successfully saved audio to output_3.wav (32-bit Float PCM).
Successfully saved audio to output.wav (32-bit Float PCM).
[I][                             tts][ 225]: tts total use time: 6.617 s

Voice generation pipeline completed.
text >>
Next
目录索引
On This Page
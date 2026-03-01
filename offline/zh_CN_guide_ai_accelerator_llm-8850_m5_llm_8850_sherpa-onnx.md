# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_sherpa-onnx

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
sherpa-onnx
sherpa-onnx
是一个基于 ONNX Runtime 的轻量级语音识别/语音处理工具箱，专注于在本地设备上实现高性能、低延迟的流式与离线识别。目前已经支持 LLM8850 作为推理后端。且支持 NPU 加速。
官方文档
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
https://huggingface.co/M5Stack/SenseVoiceSmall-axmodel
git clone https://huggingface.co/M5Stack/SenseVoiceSmall-axmodel
文件说明：
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ls -lh
total 328K
drwxrwxr-x 2 m5stack m5stack 4.0K Dec  9 11:55 ax630c
drwxrwxr-x 2 m5stack m5stack 4.0K Dec  9 11:55 ax650
-rw-rw-r-- 1 m5stack m5stack   24 Dec  9 11:54 README.md
drwxrwxr-x 2 m5stack m5stack 4.0K Dec  9 11:54 test_wavs
-rw-rw-r-- 1 m5stack m5stack 309K Dec  9 11:54 tokens.txt
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ls -lh
total 328K
drwxrwxr-x 2 m5stack m5stack 4.0K Dec  9 11:55 ax630c
drwxrwxr-x 2 m5stack m5stack 4.0K Dec  9 11:55 ax650
-rw-rw-r-- 1 m5stack m5stack   24 Dec  9 11:54 README.md
drwxrwxr-x 2 m5stack m5stack 4.0K Dec  9 11:54 test_wavs
-rw-rw-r-- 1 m5stack m5stack 309K Dec  9 11:54 tokens.txt
获取预编译程序
手动下载链接
wget https://github.com/k2-fsa/sherpa-onnx/releases/download/v1.12.19/sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared.tar.bz2
wget https://github.com/k2-fsa/sherpa-onnx/releases/download/v1.12.19/sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared.tar.bz2
tar xvf sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared.tar.bz2
rm sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared.tar.bz2
tar xvf sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared.tar.bz2
rm sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared.tar.bz2
文件说明：
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ls -lh sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/
total 47M
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-alsa
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-alsa-offline
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-alsa-offline-audio-tagging
-rwxr-xr-x 1 m5stack m5stack 453K Dec  8 12:04 sherpa-onnx-alsa-offline-speaker-identification
-rwxr-xr-x 1 m5stack m5stack 710K Dec  8 12:04 sherpa-onnx-keyword-spotter
-rwxr-xr-x 1 m5stack m5stack 710K Dec  8 12:04 sherpa-onnx-keyword-spotter-alsa
-rwxr-xr-x 1 m5stack m5stack 903K Dec  8 12:04 sherpa-onnx-keyword-spotter-microphone
-rwxr-xr-x 1 m5stack m5stack 2.1M Dec  8 12:04 sherpa-onnx-microphone
-rwxr-xr-x 1 m5stack m5stack 2.1M Dec  8 12:04 sherpa-onnx-microphone-offline
-rwxr-xr-x 1 m5stack m5stack 582K Dec  8 12:04 sherpa-onnx-microphone-offline-audio-tagging
-rwxr-xr-x 1 m5stack m5stack 582K Dec  8 12:04 sherpa-onnx-microphone-offline-speaker-identification
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-offline
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-offline-audio-tagging
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-offline-denoiser
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-offline-language-identification
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-offline-parallel
-rwxr-xr-x 1 m5stack m5stack 325K Dec  8 12:04 sherpa-onnx-offline-punctuation
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-offline-source-separation
-rwxr-xr-x 1 m5stack m5stack 517K Dec  8 12:04 sherpa-onnx-offline-speaker-diarization
-rwxr-xr-x 1 m5stack m5stack 2.4M Dec  8 12:04 sherpa-onnx-offline-tts
-rwxr-xr-x 1 m5stack m5stack 2.6M Dec  8 12:04 sherpa-onnx-offline-tts-play
-rwxr-xr-x 1 m5stack m5stack 2.4M Dec  8 12:04 sherpa-onnx-offline-tts-play-alsa
-rwxr-xr-x 1 m5stack m5stack 2.2M Dec  8 12:04 sherpa-onnx-offline-websocket-server
-rwxr-xr-x 1 m5stack m5stack 2.4M Dec  8 12:04 sherpa-onnx-offline-zeroshot-tts
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-online-punctuation
-rwxr-xr-x 1 m5stack m5stack 645K Dec  8 12:04 sherpa-onnx-online-websocket-client
-rwxr-xr-x 1 m5stack m5stack 2.2M Dec  8 12:04 sherpa-onnx-online-websocket-server
-rwxr-xr-x 1 m5stack m5stack 261K Dec  8 12:04 sherpa-onnx-pa-devs
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-vad
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-vad-alsa
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-vad-alsa-offline-asr
-rwxr-xr-x 1 m5stack m5stack 582K Dec  8 12:04 sherpa-onnx-vad-microphone
-rwxr-xr-x 1 m5stack m5stack 2.1M Dec  8 12:04 sherpa-onnx-vad-microphone-offline-asr
-rwxr-xr-x 1 m5stack m5stack 2.1M Dec  8 12:04 sherpa-onnx-vad-microphone-simulated-streaming-asr
-rwxr-xr-x 1 m5stack m5stack 2.0M Dec  8 12:04 sherpa-onnx-vad-with-offline-asr
-rwxr-xr-x 1 m5stack m5stack 2.0M Dec  8 12:04 sherpa-onnx-vad-with-online-asr
-rwxr-xr-x 1 m5stack m5stack 195K Dec  8 12:04 sherpa-onnx-version
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ls -lh sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/
total 47M
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-alsa
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-alsa-offline
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-alsa-offline-audio-tagging
-rwxr-xr-x 1 m5stack m5stack 453K Dec  8 12:04 sherpa-onnx-alsa-offline-speaker-identification
-rwxr-xr-x 1 m5stack m5stack 710K Dec  8 12:04 sherpa-onnx-keyword-spotter
-rwxr-xr-x 1 m5stack m5stack 710K Dec  8 12:04 sherpa-onnx-keyword-spotter-alsa
-rwxr-xr-x 1 m5stack m5stack 903K Dec  8 12:04 sherpa-onnx-keyword-spotter-microphone
-rwxr-xr-x 1 m5stack m5stack 2.1M Dec  8 12:04 sherpa-onnx-microphone
-rwxr-xr-x 1 m5stack m5stack 2.1M Dec  8 12:04 sherpa-onnx-microphone-offline
-rwxr-xr-x 1 m5stack m5stack 582K Dec  8 12:04 sherpa-onnx-microphone-offline-audio-tagging
-rwxr-xr-x 1 m5stack m5stack 582K Dec  8 12:04 sherpa-onnx-microphone-offline-speaker-identification
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-offline
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-offline-audio-tagging
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-offline-denoiser
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-offline-language-identification
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-offline-parallel
-rwxr-xr-x 1 m5stack m5stack 325K Dec  8 12:04 sherpa-onnx-offline-punctuation
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-offline-source-separation
-rwxr-xr-x 1 m5stack m5stack 517K Dec  8 12:04 sherpa-onnx-offline-speaker-diarization
-rwxr-xr-x 1 m5stack m5stack 2.4M Dec  8 12:04 sherpa-onnx-offline-tts
-rwxr-xr-x 1 m5stack m5stack 2.6M Dec  8 12:04 sherpa-onnx-offline-tts-play
-rwxr-xr-x 1 m5stack m5stack 2.4M Dec  8 12:04 sherpa-onnx-offline-tts-play-alsa
-rwxr-xr-x 1 m5stack m5stack 2.2M Dec  8 12:04 sherpa-onnx-offline-websocket-server
-rwxr-xr-x 1 m5stack m5stack 2.4M Dec  8 12:04 sherpa-onnx-offline-zeroshot-tts
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-online-punctuation
-rwxr-xr-x 1 m5stack m5stack 645K Dec  8 12:04 sherpa-onnx-online-websocket-client
-rwxr-xr-x 1 m5stack m5stack 2.2M Dec  8 12:04 sherpa-onnx-online-websocket-server
-rwxr-xr-x 1 m5stack m5stack 261K Dec  8 12:04 sherpa-onnx-pa-devs
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-vad
-rwxr-xr-x 1 m5stack m5stack 389K Dec  8 12:04 sherpa-onnx-vad-alsa
-rwxr-xr-x 1 m5stack m5stack 1.9M Dec  8 12:04 sherpa-onnx-vad-alsa-offline-asr
-rwxr-xr-x 1 m5stack m5stack 582K Dec  8 12:04 sherpa-onnx-vad-microphone
-rwxr-xr-x 1 m5stack m5stack 2.1M Dec  8 12:04 sherpa-onnx-vad-microphone-offline-asr
-rwxr-xr-x 1 m5stack m5stack 2.1M Dec  8 12:04 sherpa-onnx-vad-microphone-simulated-streaming-asr
-rwxr-xr-x 1 m5stack m5stack 2.0M Dec  8 12:04 sherpa-onnx-vad-with-offline-asr
-rwxr-xr-x 1 m5stack m5stack 2.0M Dec  8 12:04 sherpa-onnx-vad-with-online-asr
-rwxr-xr-x 1 m5stack m5stack 195K Dec  8 12:04 sherpa-onnx-version
语音文件识别。
./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-offline --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl test_wavs/en.wav
./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-offline --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl test_wavs/en.wav
识别结果如下：
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-offline --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl test_wavs/en.wav 
/k2-fsa/sherpa-onnx/sherpa-onnx/csrc/parse-options.cc:Read:373 ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-offline --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl test_wavs/en.wav 

OfflineRecognizerConfig(feat_config=FeatureExtractorConfig(sampling_rate=16000, feature_dim=80, low_freq=20, high_freq=-400, dither=0, normalize_samples=True, snip_edges=False), model_config=OfflineModelConfig(transducer=OfflineTransducerModelConfig(encoder_filename=
""
, decoder_filename=
""
, joiner_filename=
""
), paraformer=OfflineParaformerModelConfig(model=
""
), nemo_ctc=OfflineNemoEncDecCtcModelConfig(model=
""
), whisper=OfflineWhisperModelConfig(encoder=
""
, decoder=
""
, language=
""
, task=
"transcribe"
, tail_paddings=-1), fire_red_asr=OfflineFireRedAsrModelConfig(encoder=
""
, decoder=
""
), tdnn=OfflineTdnnModelConfig(model=
""
), zipformer_ctc=OfflineZipformerCtcModelConfig(model=
""
), wenet_ctc=OfflineWenetCtcModelConfig(model=
""
), sense_voice=OfflineSenseVoiceModelConfig(model=
"ax650/model-10-seconds.axmodel"
, language=
"auto"
, use_itn=False), moonshine=OfflineMoonshineModelConfig(preprocessor=
""
, encoder=
""
, uncached_decoder=
""
, cached_decoder=
""
), dolphin=OfflineDolphinModelConfig(model=
""
), canary=OfflineCanaryModelConfig(encoder=
""
, decoder=
""
, src_lang=
""
, tgt_lang=
""
, use_pnc=True), omnilingual=OfflineOmnilingualAsrCtcModelConfig(model=
""
), telespeech_ctc=
""
, tokens=
"tokens.txt"
, num_threads=2, debug=False, provider=
"axcl"
, model_type=
""
, modeling_unit=
"cjkchar"
, bpe_vocab=
""
), lm_config=OfflineLMConfig(model=
""
, scale=0.5, lodr_scale=0.01, lodr_fst=
""
, lodr_backoff_id=-1), ctc_fst_decoder_config=OfflineCtcFstDecoderConfig(graph=
""
, max_active=3000), decoding_method=
"greedy_search"
, max_active_paths=4, hotwords_file=
""
, hotwords_score=1.5, blank_penalty=0, rule_fsts=
""
, rule_fars=
""
, hr=HomophoneReplacerConfig(lexicon=
""
, rule_fsts=
""
))
Creating recognizer ...
recognizer created
in
4.263 s
Started
Done!

test_wavs/en.wav
{
"lang"
:
"<|en|>"
,
"emotion"
:
"<|EMO_UNKNOWN|>"
,
"event"
:
"<|Speech|>"
,
"text"
:
"the tribal chieftain called for the boy and presented him with fifty pieces of gold"
,
"timestamps"
: [0.90, 1.26, 1.56, 1.80, 2.16, 2.46, 2.76, 2.94, 3.12, 3.60, 3.96, 4.50, 4.74, 5.10, 5.52, 5.88, 6.24],
"durations"
: [],
"tokens"
:[
"the"
,
" tri"
,
"bal"
,
" chief"
,
"tain"
,
" called"
,
" for"
,
" the"
,
" boy"
,
" and"
,
" presented"
,
" him"
,
" with"
,
" fifty"
,
" pieces"
,
" of"
,
" gold"
],
"ys_log_probs"
: [],
"words"
: []}
----
num threads: 2
decoding method: greedy_search
Elapsed seconds: 0.105 s
Real time factor (RTF): 0.105 / 7.152 = 0.015
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-offline --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl test_wavs/en.wav 
/k2-fsa/sherpa-onnx/sherpa-onnx/csrc/parse-options.cc:Read:373 ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-offline --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl test_wavs/en.wav 

OfflineRecognizerConfig(feat_config=FeatureExtractorConfig(sampling_rate=16000, feature_dim=80, low_freq=20, high_freq=-400, dither=0, normalize_samples=True, snip_edges=False), model_config=OfflineModelConfig(transducer=OfflineTransducerModelConfig(encoder_filename="", decoder_filename="", joiner_filename=""), paraformer=OfflineParaformerModelConfig(model=""), nemo_ctc=OfflineNemoEncDecCtcModelConfig(model=""), whisper=OfflineWhisperModelConfig(encoder="", decoder="", language="", task="transcribe", tail_paddings=-1), fire_red_asr=OfflineFireRedAsrModelConfig(encoder="", decoder=""), tdnn=OfflineTdnnModelConfig(model=""), zipformer_ctc=OfflineZipformerCtcModelConfig(model=""), wenet_ctc=OfflineWenetCtcModelConfig(model=""), sense_voice=OfflineSenseVoiceModelConfig(model="ax650/model-10-seconds.axmodel", language="auto", use_itn=False), moonshine=OfflineMoonshineModelConfig(preprocessor="", encoder="", uncached_decoder="", cached_decoder=""), dolphin=OfflineDolphinModelConfig(model=""), canary=OfflineCanaryModelConfig(encoder="", decoder="", src_lang="", tgt_lang="", use_pnc=True), omnilingual=OfflineOmnilingualAsrCtcModelConfig(model=""), telespeech_ctc="", tokens="tokens.txt", num_threads=2, debug=False, provider="axcl", model_type="", modeling_unit="cjkchar", bpe_vocab=""), lm_config=OfflineLMConfig(model="", scale=0.5, lodr_scale=0.01, lodr_fst="", lodr_backoff_id=-1), ctc_fst_decoder_config=OfflineCtcFstDecoderConfig(graph="", max_active=3000), decoding_method="greedy_search", max_active_paths=4, hotwords_file="", hotwords_score=1.5, blank_penalty=0, rule_fsts="", rule_fars="", hr=HomophoneReplacerConfig(lexicon="", rule_fsts=""))
Creating recognizer ...
recognizer created in 4.263 s
Started
Done!

test_wavs/en.wav
{"lang": "<|en|>", "emotion": "<|EMO_UNKNOWN|>", "event": "<|Speech|>", "text": "the tribal chieftain called for the boy and presented him with fifty pieces of gold", "timestamps": [0.90, 1.26, 1.56, 1.80, 2.16, 2.46, 2.76, 2.94, 3.12, 3.60, 3.96, 4.50, 4.74, 5.10, 5.52, 5.88, 6.24], "durations": [], "tokens":["the", " tri", "bal", " chief", "tain", " called", " for", " the", " boy", " and", " presented", " him", " with", " fifty", " pieces", " of", " gold"], "ys_log_probs": [], "words": []}
----
num threads: 2
decoding method: greedy_search
Elapsed seconds: 0.105 s
Real time factor (RTF): 0.105 / 7.152 = 0.015
带 VAD 分段语音文件识别。
获取 VAD 模型
wget https://github.com/k2-fsa/sherpa-onnx/releases/download/asr-models/silero_vad.onnx
wget https://github.com/k2-fsa/sherpa-onnx/releases/download/asr-models/silero_vad.onnx
获取长语音文件或自备
wget https://github.com/k2-fsa/sherpa-onnx/releases/download/asr-models/Obama.wav
wget https://github.com/k2-fsa/sherpa-onnx/releases/download/asr-models/Obama.wav
开始识别
./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-with-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl Obama.wav
./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-with-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl Obama.wav
识别结果如下：
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-with-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl Obama.wav 
/k2-fsa/sherpa-onnx/sherpa-onnx/csrc/parse-options.cc:Read:373 ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-with-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl Obama.wav 

VadModelConfig(silero_vad=SileroVadModelConfig(model=
"silero_vad.onnx"
, threshold=0.5, min_silence_duration=0.5, min_speech_duration=0.25, max_speech_duration=20, window_size=512, neg_threshold=-1), ten_vad=TenVadModelConfig(model=
""
, threshold=0.5, min_silence_duration=0.5, min_speech_duration=0.25, max_speech_duration=20, window_size=256), sample_rate=16000, num_threads=1, provider=
"cpu"
, debug=False)
OfflineRecognizerConfig(feat_config=FeatureExtractorConfig(sampling_rate=16000, feature_dim=80, low_freq=20, high_freq=-400, dither=0, normalize_samples=True, snip_edges=False), model_config=OfflineModelConfig(transducer=OfflineTransducerModelConfig(encoder_filename=
""
, decoder_filename=
""
, joiner_filename=
""
), paraformer=OfflineParaformerModelConfig(model=
""
), nemo_ctc=OfflineNemoEncDecCtcModelConfig(model=
""
), whisper=OfflineWhisperModelConfig(encoder=
""
, decoder=
""
, language=
""
, task=
"transcribe"
, tail_paddings=-1), fire_red_asr=OfflineFireRedAsrModelConfig(encoder=
""
, decoder=
""
), tdnn=OfflineTdnnModelConfig(model=
""
), zipformer_ctc=OfflineZipformerCtcModelConfig(model=
""
), wenet_ctc=OfflineWenetCtcModelConfig(model=
""
), sense_voice=OfflineSenseVoiceModelConfig(model=
"ax650/model-10-seconds.axmodel"
, language=
"auto"
, use_itn=False), moonshine=OfflineMoonshineModelConfig(preprocessor=
""
, encoder=
""
, uncached_decoder=
""
, cached_decoder=
""
), dolphin=OfflineDolphinModelConfig(model=
""
), canary=OfflineCanaryModelConfig(encoder=
""
, decoder=
""
, src_lang=
""
, tgt_lang=
""
, use_pnc=True), omnilingual=OfflineOmnilingualAsrCtcModelConfig(model=
""
), telespeech_ctc=
""
, tokens=
"tokens.txt"
, num_threads=2, debug=False, provider=
"axcl"
, model_type=
""
, modeling_unit=
"cjkchar"
, bpe_vocab=
""
), lm_config=OfflineLMConfig(model=
""
, scale=0.5, lodr_scale=0.01, lodr_fst=
""
, lodr_backoff_id=-1), ctc_fst_decoder_config=OfflineCtcFstDecoderConfig(graph=
""
, max_active=3000), decoding_method=
"greedy_search"
, max_active_paths=4, hotwords_file=
""
, hotwords_score=1.5, blank_penalty=0, rule_fsts=
""
, rule_fars=
""
, hr=HomophoneReplacerConfig(lexicon=
""
, rule_fsts=
""
))
Creating recognizer ...
Recognizer created!
Started
Reading: Obama.wav
Started!
9.286 -- 12.428: everybody all right everybody go ahead and have a seat
13.094 -- 14.988: how
's everybody doing today
18.694 -- 20.748: how about tim spicer
25.894 -- 31.948: i am here with students at wakefield high school in arlington virginia
...
297.318 -- 314.284: you want to be a doctor or a teacher or a police officer you want to be a nurse or an architect a lawyer or a member of our military you'
re going to need a good education
315.174 -- 319.852: you
've got to train for it and work for it and learn for it
320.518 -- 323.660: and this isn'
t just important
for
your own life and your own future
324.678 -- 333.004: what you make of your education will decide nothing less than the future of this country the future of america depends on you
num threads: 2
decoding method: greedy_search
Elapsed seconds: 6.061 s
Real time factor (RTF): 6.061 / 334.234 = 0.018
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-with-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl Obama.wav 
/k2-fsa/sherpa-onnx/sherpa-onnx/csrc/parse-options.cc:Read:373 ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-with-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl Obama.wav 

VadModelConfig(silero_vad=SileroVadModelConfig(model="silero_vad.onnx", threshold=0.5, min_silence_duration=0.5, min_speech_duration=0.25, max_speech_duration=20, window_size=512, neg_threshold=-1), ten_vad=TenVadModelConfig(model="", threshold=0.5, min_silence_duration=0.5, min_speech_duration=0.25, max_speech_duration=20, window_size=256), sample_rate=16000, num_threads=1, provider="cpu", debug=False)
OfflineRecognizerConfig(feat_config=FeatureExtractorConfig(sampling_rate=16000, feature_dim=80, low_freq=20, high_freq=-400, dither=0, normalize_samples=True, snip_edges=False), model_config=OfflineModelConfig(transducer=OfflineTransducerModelConfig(encoder_filename="", decoder_filename="", joiner_filename=""), paraformer=OfflineParaformerModelConfig(model=""), nemo_ctc=OfflineNemoEncDecCtcModelConfig(model=""), whisper=OfflineWhisperModelConfig(encoder="", decoder="", language="", task="transcribe", tail_paddings=-1), fire_red_asr=OfflineFireRedAsrModelConfig(encoder="", decoder=""), tdnn=OfflineTdnnModelConfig(model=""), zipformer_ctc=OfflineZipformerCtcModelConfig(model=""), wenet_ctc=OfflineWenetCtcModelConfig(model=""), sense_voice=OfflineSenseVoiceModelConfig(model="ax650/model-10-seconds.axmodel", language="auto", use_itn=False), moonshine=OfflineMoonshineModelConfig(preprocessor="", encoder="", uncached_decoder="", cached_decoder=""), dolphin=OfflineDolphinModelConfig(model=""), canary=OfflineCanaryModelConfig(encoder="", decoder="", src_lang="", tgt_lang="", use_pnc=True), omnilingual=OfflineOmnilingualAsrCtcModelConfig(model=""), telespeech_ctc="", tokens="tokens.txt", num_threads=2, debug=False, provider="axcl", model_type="", modeling_unit="cjkchar", bpe_vocab=""), lm_config=OfflineLMConfig(model="", scale=0.5, lodr_scale=0.01, lodr_fst="", lodr_backoff_id=-1), ctc_fst_decoder_config=OfflineCtcFstDecoderConfig(graph="", max_active=3000), decoding_method="greedy_search", max_active_paths=4, hotwords_file="", hotwords_score=1.5, blank_penalty=0, rule_fsts="", rule_fars="", hr=HomophoneReplacerConfig(lexicon="", rule_fsts=""))
Creating recognizer ...
Recognizer created!
Started
Reading: Obama.wav
Started!
9.286 -- 12.428: everybody all right everybody go ahead and have a seat
13.094 -- 14.988: how's everybody doing today
18.694 -- 20.748: how about tim spicer
25.894 -- 31.948: i am here with students at wakefield high school in arlington virginia
...
297.318 -- 314.284: you want to be a doctor or a teacher or a police officer you want to be a nurse or an architect a lawyer or a member of our military you're going to need a good education
315.174 -- 319.852: you've got to train for it and work for it and learn for it
320.518 -- 323.660: and this isn't just important for your own life and your own future
324.678 -- 333.004: what you make of your education will decide nothing less than the future of this country the future of america depends on you
num threads: 2
decoding method: greedy_search
Elapsed seconds: 6.061 s
Real time factor (RTF): 6.061 / 334.234 = 0.018
麦克风实时非流式识别。
获取麦克风设备列表
aplay -l
aplay -l
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ aplay -l
**** List of PLAYBACK Hardware Devices ****
card 0: vc4hdmi0 [vc4-hdmi-0], device 0: MAI PCM i2s-hifi-0 [MAI PCM i2s-hifi-0]
  Subdevices: 1/1
  Subdevice
#0: subdevice #0
card 1: vc4hdmi1 [vc4-hdmi-1], device 0: MAI PCM i2s-hifi-0 [MAI PCM i2s-hifi-0]
  Subdevices: 1/1
  Subdevice
#0: subdevice #0
card 2: Audio [AB13X USB Audio], device 0: USB Audio [USB Audio]
  Subdevices: 1/1
  Subdevice
#0: subdevice #0
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ aplay -l
**** List of PLAYBACK Hardware Devices ****
card 0: vc4hdmi0 [vc4-hdmi-0], device 0: MAI PCM i2s-hifi-0 [MAI PCM i2s-hifi-0]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: vc4hdmi1 [vc4-hdmi-1], device 0: MAI PCM i2s-hifi-0 [MAI PCM i2s-hifi-0]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 2: Audio [AB13X USB Audio], device 0: USB Audio [USB Audio]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
开启实时非流式识别
./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-alsa-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl plughw:2,0
# 注意要替换成实际的麦克风设备名
./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-alsa-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl plughw:2,0 # 注意要替换成实际的麦克风设备名
识别结果如下：
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-alsa-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl plughw:2,0
/k2-fsa/sherpa-onnx/sherpa-onnx/csrc/parse-options.cc:Read:373 ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-alsa-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl plughw:2,0 

VadModelConfig(silero_vad=SileroVadModelConfig(model=
"silero_vad.onnx"
, threshold=0.5, min_silence_duration=0.5, min_speech_duration=0.25, max_speech_duration=20, window_size=512, neg_threshold=-1), ten_vad=TenVadModelConfig(model=
""
, threshold=0.5, min_silence_duration=0.5, min_speech_duration=0.25, max_speech_duration=20, window_size=256), sample_rate=16000, num_threads=1, provider=
"cpu"
, debug=False)
OfflineRecognizerConfig(feat_config=FeatureExtractorConfig(sampling_rate=16000, feature_dim=80, low_freq=20, high_freq=-400, dither=0, normalize_samples=True, snip_edges=False), model_config=OfflineModelConfig(transducer=OfflineTransducerModelConfig(encoder_filename=
""
, decoder_filename=
""
, joiner_filename=
""
), paraformer=OfflineParaformerModelConfig(model=
""
), nemo_ctc=OfflineNemoEncDecCtcModelConfig(model=
""
), whisper=OfflineWhisperModelConfig(encoder=
""
, decoder=
""
, language=
""
, task=
"transcribe"
, tail_paddings=-1), fire_red_asr=OfflineFireRedAsrModelConfig(encoder=
""
, decoder=
""
), tdnn=OfflineTdnnModelConfig(model=
""
), zipformer_ctc=OfflineZipformerCtcModelConfig(model=
""
), wenet_ctc=OfflineWenetCtcModelConfig(model=
""
), sense_voice=OfflineSenseVoiceModelConfig(model=
"ax650/model-10-seconds.axmodel"
, language=
"auto"
, use_itn=False), moonshine=OfflineMoonshineModelConfig(preprocessor=
""
, encoder=
""
, uncached_decoder=
""
, cached_decoder=
""
), dolphin=OfflineDolphinModelConfig(model=
""
), canary=OfflineCanaryModelConfig(encoder=
""
, decoder=
""
, src_lang=
""
, tgt_lang=
""
, use_pnc=True), omnilingual=OfflineOmnilingualAsrCtcModelConfig(model=
""
), telespeech_ctc=
""
, tokens=
"tokens.txt"
, num_threads=2, debug=False, provider=
"axcl"
, model_type=
""
, modeling_unit=
"cjkchar"
, bpe_vocab=
""
), lm_config=OfflineLMConfig(model=
""
, scale=0.5, lodr_scale=0.01, lodr_fst=
""
, lodr_backoff_id=-1), ctc_fst_decoder_config=OfflineCtcFstDecoderConfig(graph=
""
, max_active=3000), decoding_method=
"greedy_search"
, max_active_paths=4, hotwords_file=
""
, hotwords_score=1.5, blank_penalty=0, rule_fsts=
""
, rule_fars=
""
, hr=HomophoneReplacerConfig(lexicon=
""
, rule_fsts=
""
))
Creating recognizer ...
Recognizer created!
Current sample rate: 16000
Recording started!
Use recording device: plughw:2,0
Started. Please speak
 0: hello
 1: how are you
^C
Caught Ctrl + C. Exiting...
m5stack@raspberrypi:~/rsp/SenseVoiceSmall-axmodel $ ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-alsa-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl plughw:2,0
/k2-fsa/sherpa-onnx/sherpa-onnx/csrc/parse-options.cc:Read:373 ./sherpa-onnx-v1.12.19-axcl-linux-aarch64-shared/bin/sherpa-onnx-vad-alsa-offline-asr --silero-vad-model=silero_vad.onnx --sense-voice-model=ax650/model-10-seconds.axmodel --tokens=tokens.txt --provider=axcl plughw:2,0 

VadModelConfig(silero_vad=SileroVadModelConfig(model="silero_vad.onnx", threshold=0.5, min_silence_duration=0.5, min_speech_duration=0.25, max_speech_duration=20, window_size=512, neg_threshold=-1), ten_vad=TenVadModelConfig(model="", threshold=0.5, min_silence_duration=0.5, min_speech_duration=0.25, max_speech_duration=20, window_size=256), sample_rate=16000, num_threads=1, provider="cpu", debug=False)
OfflineRecognizerConfig(feat_config=FeatureExtractorConfig(sampling_rate=16000, feature_dim=80, low_freq=20, high_freq=-400, dither=0, normalize_samples=True, snip_edges=False), model_config=OfflineModelConfig(transducer=OfflineTransducerModelConfig(encoder_filename="", decoder_filename="", joiner_filename=""), paraformer=OfflineParaformerModelConfig(model=""), nemo_ctc=OfflineNemoEncDecCtcModelConfig(model=""), whisper=OfflineWhisperModelConfig(encoder="", decoder="", language="", task="transcribe", tail_paddings=-1), fire_red_asr=OfflineFireRedAsrModelConfig(encoder="", decoder=""), tdnn=OfflineTdnnModelConfig(model=""), zipformer_ctc=OfflineZipformerCtcModelConfig(model=""), wenet_ctc=OfflineWenetCtcModelConfig(model=""), sense_voice=OfflineSenseVoiceModelConfig(model="ax650/model-10-seconds.axmodel", language="auto", use_itn=False), moonshine=OfflineMoonshineModelConfig(preprocessor="", encoder="", uncached_decoder="", cached_decoder=""), dolphin=OfflineDolphinModelConfig(model=""), canary=OfflineCanaryModelConfig(encoder="", decoder="", src_lang="", tgt_lang="", use_pnc=True), omnilingual=OfflineOmnilingualAsrCtcModelConfig(model=""), telespeech_ctc="", tokens="tokens.txt", num_threads=2, debug=False, provider="axcl", model_type="", modeling_unit="cjkchar", bpe_vocab=""), lm_config=OfflineLMConfig(model="", scale=0.5, lodr_scale=0.01, lodr_fst="", lodr_backoff_id=-1), ctc_fst_decoder_config=OfflineCtcFstDecoderConfig(graph="", max_active=3000), decoding_method="greedy_search", max_active_paths=4, hotwords_file="", hotwords_score=1.5, blank_penalty=0, rule_fsts="", rule_fars="", hr=HomophoneReplacerConfig(lexicon="", rule_fsts=""))
Creating recognizer ...
Recognizer created!
Current sample rate: 16000
Recording started!
Use recording device: plughw:2,0
Started. Please speak
 0: hello
 1: how are you
^C
Caught Ctrl + C. Exiting...
Next
目录索引
On This Page
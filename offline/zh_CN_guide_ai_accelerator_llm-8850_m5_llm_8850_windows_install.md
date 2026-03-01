# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_windows_install

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
LLM-8850 Card Windows 环境配置
Windows 版本要求
Windows
版本
10
22H2
11
>= 23H2
按下
Win+R
，输入
winver
，可以查询当前的 Windows 版本信息。
仅支持 Windows 10 64 位及 Windows 11 64 位操作系统。
按下
Win+I
打开设置 > 更新和安全 > Windows 更新，自动更新 Windows 版本，Windows 10 推荐用
微软更新助手
更新到 22H2 版本。
关闭系统睡眠功能：按下
Win+I
打开设置 > 系统 > 电源和睡眠，将睡眠更改为
从不
。
环境准备
建议关闭安全防护软件，避免被误杀。
下载 Visual Studio 2022 运行时库 VC_redist.x64.exe，（
微软下载链接
），并以管理员权限安装 VC_redist.x64.exe。
关机断电后将设备接入主板，严禁带电操作。
开机后按下
Win+R
, 输入
devmgmt.msc
，打开设备管理器，在其他设备中会出现未知的多媒体视频控制器，在属性中可确认设备
VENDOR
是
1F4B
。
驱动安装
注意
安装和卸载均需要管理员权限，需关闭系统睡眠功能。如果系统已经安装旧版本的 AXCL，请先卸载！
Windows 发布包
axcl_win64_setup_Vx.x.x_yyyymmdd_NOxxxx.exe
会自动安装驱动、动态链接库（含导入库）、可执行程序 (比如 axcl-smi.exe 等) 和 示例源码，使用管理员权限运行发布包，按向导提示完成安装。
点击下载
点击安装。
建议全选安装。
注意选择安装路径，此目录包含可执行程序，卸载程序，头文件及动态库。
等待安装完成，并重启计算机。
重启后，按下
Win+R
，输入
devmgmt.msc
，打开设备管理器，在系统设备中可发现 Axera NPU Accelerator Device 设备，如下图所示。
进入安装路径
AXCL\axcl\out\axcl_win_x64\bin
目录，在
Windows Terminal
中执行
axcl-smi.exe
，显示如下：
驱动卸载
进入安装路径 AXCL，运行 uninst.exe 执行卸载。
编译程序
注意
AXCL Windows SDK 可以使用 Visual Studio 2022/Visual Studio 2026 工具链进行编译，所需的环境依赖如下：
-
Visual Studio Community 2026
，参考
官方文档
，必选的组件：使用 C++ 的桌面开发。
- CMake ，版本高于 3.20
- ninja，推荐 v1.31.1。将 ninja.exe 的路径配置到系统环境变量 Path。
- Python3 可以通过 conda 安装。
环境安装好如下：
进入安装路径 AXCL\axcl\scripts，执行
build_win64.cmd
编译。
编译成功如下：
进入编译输出目录，执行
axcl_run_model.exe -m yolo11s.axmodel -r 10
，请替换为实际的模型文件路径。
预编译程序与模型下载
该目录包含第三方库。
该目录包含 axcl 相关的头文件和动态库。
以下为
axcl-sample
演示，
预编译程序及模型下载
提示
编译 Demo 可参考
仓库 Windows 分支
，建议使用
vcpkg
安装
opencv4:x64-windows
并在项目中配置。
Next
目录索引
On This Page
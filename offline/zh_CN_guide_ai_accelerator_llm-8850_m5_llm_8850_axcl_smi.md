# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_axcl_smi

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
AXCL-SMI
概述
AXCL-SMI (System Management Interface) 工具用于设备信息收集，对设备进行配置等功能，支持收集如下设备信息：
硬件设备型号
固件版本号
驱动版本号
设备利用率
内存使用情况
设备芯片结温
其他信息
使用说明
快速使用
在正确安装AXCL驱动包后，AXCL-SMI即安装成功，直接执行
axcl-smi
显示内容如下：
+------------------------------------------------------------------------------------------------+
| AXCL-SMI  V3.6.4_20250805020145                                  Driver  V3.6.4_20250805020145 |
+-----------------------------------------+--------------+---------------------------------------+
| Card  Name                     Firmware | Bus-Id       |                          Memory-Usage |
| Fan   Temp                Pwr:Usage/Cap | CPU      NPU |                             CMM-Usage |
|=========================================+==============+=======================================|
|    0  AX650N                     V3.6.4 | 0001:01:00.0 |                149 MiB /      945 MiB |
|   --   41C                      -- / -- | 1%        0% |                 18 MiB /     7040 MiB |
+-----------------------------------------+--------------+---------------------------------------+

+------------------------------------------------------------------------------------------------+
| Processes:                                                                                     |
| Card      PID  Process Name                                                   NPU Memory Usage |
|================================================================================================|
+------------------------------------------------------------------------------------------------+
| AXCL-SMI  V3.6.4_20250805020145                                  Driver  V3.6.4_20250805020145 |
+-----------------------------------------+--------------+---------------------------------------+
| Card  Name                     Firmware | Bus-Id       |                          Memory-Usage |
| Fan   Temp                Pwr:Usage/Cap | CPU      NPU |                             CMM-Usage |
|=========================================+==============+=======================================|
|    0  AX650N                     V3.6.4 | 0001:01:00.0 |                149 MiB /      945 MiB |
|   --   41C                      -- / -- | 1%        0% |                 18 MiB /     7040 MiB |
+-----------------------------------------+--------------+---------------------------------------+

+------------------------------------------------------------------------------------------------+
| Processes:                                                                                     |
| Card      PID  Process Name                                                   NPU Memory Usage |
|================================================================================================|
字段说明
字段
说明
字段
说明
Card
设备索引编号，注意不是PCIe的设备号
Bus-Id
设备Bus ID
Name
设备名称
CPU
CPU平均利用率
Fan
风扇转速比（未支持）
NPU
NPU平均利用率
Temp
设备芯片结温Tj
Memory-Usage
系统内存： 使用/总量
Firmware
设备固件版本号
CMM-Usage
媒体内存： 使用/总量
Pwr: Usage/Cap
功耗（未支持）
PID
主控进程PID
Process Name
主控进程名称
NPU Memory Usage
设备NPU已使用的CMM内存
备注
参阅FAQ
DDR带宽
和
NPU利用率
章节了解获取详细的DDR和NPU利用率。
帮助 (-h) 和版本 (-v)
axcl-smi -h
查询帮助信息
m5stack@raspberrypi5:~ $ axcl-smi -h
usage: axcl-smi [<
command
> [<args>]] [--device] [--version] [--
help
]

axcl-smi System Management Interface V3.6.3_20250722020142

Commands
    info                                    Show device information
        --temp                                  Show SoC temperature
        --mem                                   Show memory usage
        --cmm                                   Show CMM usage
        --cpu                                   Show CPU usage
        --npu                                   Show NPU usage
    proc                                    cat device proc
        --vdec                                  cat /proc/ax_proc/vdec
        --venc                                  cat /proc/ax_proc/venc
        --jenc                                  cat /proc/ax_proc/jenc
        --ivps                                  cat /proc/ax_proc/ivps
        --rgn                                   cat /proc/ax_proc/rgn
        --ive                                   cat /proc/ax_proc/ive
        --pool                                  cat /proc/ax_proc/pool
        --link                                  cat /proc/ax_proc/link_table
        --cmm                                   cat /proc/ax_proc/mem_cmm_info
set
Set
        -f[MHz], --freq=[MHz]                   Set CPU frequency
in
MHz. One of: 1200000, 1400000, 1700000
log
Dump logs from device
        -t[mask], --
type
=[mask]                 Specifies
which
logs to dump by a combination (bitwise OR) value of blow:
                                                  -1: all (default) 0x01: daemon 0x02: worker 0x10: syslog 0x20: kernel
        -o[path], --output=[path]               Specifies the path to save dump logs (default: ./)
    sh                                      Execute a shell
command
cmd                                     Shell
command
args...                                 Shell
command
arguments
    reboot                                  reboot device
-d, --device                            Card index [0, connected cards number - 1]
-v, --version                           Show axcl-smi version
-h, --
help
Show this
help
menu
m5stack@raspberrypi5:~ $ axcl-smi -h
usage: axcl-smi [<command> [<args>]] [--device] [--version] [--help]

axcl-smi System Management Interface V3.6.3_20250722020142

Commands
    info                                    Show device information
        --temp                                  Show SoC temperature
        --mem                                   Show memory usage
        --cmm                                   Show CMM usage
        --cpu                                   Show CPU usage
        --npu                                   Show NPU usage
    proc                                    cat device proc
        --vdec                                  cat /proc/ax_proc/vdec
        --venc                                  cat /proc/ax_proc/venc
        --jenc                                  cat /proc/ax_proc/jenc
        --ivps                                  cat /proc/ax_proc/ivps
        --rgn                                   cat /proc/ax_proc/rgn
        --ive                                   cat /proc/ax_proc/ive
        --pool                                  cat /proc/ax_proc/pool
        --link                                  cat /proc/ax_proc/link_table
        --cmm                                   cat /proc/ax_proc/mem_cmm_info
    set                                     Set
        -f[MHz], --freq=[MHz]                   Set CPU frequency in MHz. One of: 1200000, 1400000, 1700000
    log                                     Dump logs from device
        -t[mask], --type=[mask]                 Specifies which logs to dump by a combination (bitwise OR) value of blow:
                                                  -1: all (default) 0x01: daemon 0x02: worker 0x10: syslog 0x20: kernel
        -o[path], --output=[path]               Specifies the path to save dump logs (default: ./)
    sh                                      Execute a shell command
        cmd                                     Shell command
        args...                                 Shell command arguments
    reboot                                  reboot device
-d, --device                            Card index [0, connected cards number - 1]
-v, --version                           Show axcl-smi version
-h, --help                              Show this help menu
axcl-smi -v
查询AXCL-SMI工具的版本
m5stack@raspberrypi5:~ $ axcl-smi -v
AXCL-SMI V3.6.3_20250722020142 BUILD: Jul 22 2025 02:30:24
m5stack@raspberrypi5:~ $ axcl-smi -v
AXCL-SMI V3.6.3_20250722020142 BUILD: Jul 22 2025 02:30:24
选项
设备号 (-d, --device)
-d, --device                             Card index [0, connected cards number - 1]
-d, --device                             Card index [0, connected cards number - 1]
[-d, --device]
指定设备号索引，范围：[0, 连接设备数量 - 1]，
默认为0号设备
。
信息查询（info）
axcl-smi info
用于显示设备的详细信息，支持子命令如下：
子命令
说明
--temp
显示设备芯片结温，单位是摄氏度x1000。
--mem
显示设备系统详细内存使用情况。
--cmm
显示设备媒体内存使用情况。如果需要更详细的媒体内存，执行
axcl-smi sh cat /proc/ax_proc/mem_cmm_info -d xx
(xx是PCIe设备号)。
--cpu
显示设备CPU利用率。
--npu
显示设备NPU利用率。
示例
：查询索引号为0号的设备的媒体内存使用情况：
m5stack@raspberrypi5:~ $ axcl-smi info --cmm -d 0
Device ID           : 1 (0x1)
CMM Total           :  7208960 KiB
CMM Used            :    18876 KiB
CMM Remain          :  7190084 kiB
m5stack@raspberrypi5:~ $ axcl-smi info --cmm -d 0
Device ID           : 1 (0x1)
CMM Total           :  7208960 KiB
CMM Used            :    18876 KiB
CMM Remain          :  7190084 kiB
PROC查询（proc）
axcl-smi proc
用于查询设备模块的proc信息，支持子命令如下：
子命令
说明
--vdec
查询VDEC模块proc (
cat /proc/ax_proc/vdec
)
--venc
查询VENC模块proc (
cat /proc/ax_proc/venc
)
--jenc
查询JENC模块proc (
cat /proc/ax_proc/jenc
)
--ivps
查询IVPS模块proc (
cat /proc/ax_proc/ivps
)
--rgn
查询RGN模块proc (
cat /proc/ax_proc/rgn
)
--ive
查询IVE模块proc (
cat /proc/ax_proc/ive
)
--pool
查询POOL模块proc (
cat /proc/ax_proc/pool
)
--link
查询LINK模块proc (
cat /proc/ax_proc/link_table
)
--cmm
查询CMM模块proc (
cat /proc/ax_proc/mem_cmm_info
)
示例
：查询0号设备的VENC proc信息
m5stack@raspberrypi5:~ $ axcl-smi proc --venc -d 0
-------- VENC VERSION ------------------------
[Axera version]: ax_venc V3.6.3_20250722020142 Jul 22 2025 02:22:04 JK

-------- MODULE PARAM ------------------------
MaxChnNum   MaxRoiNum   MaxProcNum  
64          8           32
m5stack@raspberrypi5:~ $ axcl-smi proc --venc -d 0
-------- VENC VERSION ------------------------
[Axera version]: ax_venc V3.6.3_20250722020142 Jul 22 2025 02:22:04 JK

-------- MODULE PARAM ------------------------
MaxChnNum   MaxRoiNum   MaxProcNum  
64          8           32
参数设置（set）
axcl-smi set
用户配置设备信息，支持的子命令如下：
子命令
说明
-f[MHz], --freq=[MHz]
设置设备的CPU频率，只支持 1200000, 1400000, 1700000 三种频率
示例
：设置索引号为0号的设备CPU主频为1200MHz
m5stack@raspberrypi5:~ $ axcl-smi
set
-f 1200000 -d 0
set
cpu frequency 1200000 to device 1 succeed.
m5stack@raspberrypi5:~ $ axcl-smi set -f 1200000 -d 0
set cpu frequency 1200000 to device 1 succeed.
下载日志（log）
axcl-smi log
用于下载设备的日志文件到主控侧，支持的参数如下：
参数
说明
-t[mask], --type=[mask]
指定下载的日志类别。设备侧日志类别如下：
-1： 全部日志
0x01：守护进程
0x02:  业务进程
0x10：syslog
0x20：内核日志
推荐使用
-1
下载全部日志
-o[path], --output=[path]
指定日志保存路径，支持绝对和相对路径，默认是当前目录。注意目录需要有写权限。
示例
：下载索引为0号的设备的全部日志，并保存到当前目录
m5stack@raspberrypi5:~ $ axcl-smi
log
-d 0
[2025-07-25 10:04:30.332][1802][C][
log
][dump][73]:
log
dump finished: ./dev1_log_20250724210251.tar.gz
m5stack@raspberrypi5:~ $ axcl-smi log -d 0
[2025-07-25 10:04:30.332][1802][C][log][dump][73]: log dump finished: ./dev1_log_20250724210251.tar.gz
shell命令（sh）
axcl-smi sh
支持shell命令查询设备信息，通常用于查询设备侧模块的运行proc信息。
示例
：查询索引号为0号的设备CMM信息
m5stack@raspberrypi5:~ $ axcl-smi sh cat /proc/ax_proc/mem_cmm_info -d 0
--------------------SDK VERSION-------------------
[Axera version]: ax_cmm V3.6.3_20250722020142 Jul 22 2025 02:21:25 JK
+---PARTITION: Phys(0x148000000, 0x2FFFFFFFF), Size=7208960KB(7040MB),    NAME=
"anonymous"
nBlock(Max=0, Cur=23, New=0, Free=0)  nbytes(Max=0B(0KB,0MB), Cur=19329024B(18876KB,18MB), New=0B(0KB,0MB), Free=0B(0KB,0MB))  Block(Max=0B(0KB,0MB), Min=0B(0KB,0MB), Avg=0B(0KB,0MB)) 
   |-Block: phys(0x148000000, 0x148013FFF), cache =non-cacheable, length=80KB(0MB),    name=
"TDP_DEV"
|-Block: phys(0x148014000, 0x148014FFF), cache =non-cacheable, length=4KB(0MB),    name=
"TDP_CMODE3"
|-Block: phys(0x148015000, 0x148015FFF), cache =non-cacheable, length=4KB(0MB),    name=
"TDP_CMODE3_CPU"
|-Block: phys(0x148016000, 0x148029FFF), cache =non-cacheable, length=80KB(0MB),    name=
"TDP_DEV"
|-Block: phys(0x14802A000, 0x14802AFFF), cache =non-cacheable, length=4KB(0MB),    name=
"TDP_CMODE3"
|-Block: phys(0x14802B000, 0x14802BFFF), cache =non-cacheable, length=4KB(0MB),    name=
"TDP_CMODE3_CPU"
|-Block: phys(0x14802C000, 0x14862BFFF), cache =non-cacheable, length=6144KB(6MB),    name=
"vdec_ko"
|-Block: phys(0x14862C000, 0x148647FFF), cache =non-cacheable, length=112KB(0MB),    name=
"VGP_DEV"
|-Block: phys(0x148648000, 0x148648FFF), cache =non-cacheable, length=4KB(0MB),    name=
"VGP_CMODE3"
|-Block: phys(0x148649000, 0x148649FFF), cache =non-cacheable, length=4KB(0MB),    name=
"VGP_CMODE3_CPU"
|-Block: phys(0x14864A000, 0x148665FFF), cache =non-cacheable, length=112KB(0MB),    name=
"VPP_DEV"
|-Block: phys(0x148666000, 0x148666FFF), cache =non-cacheable, length=4KB(0MB),    name=
"VPP_CMODE3"
|-Block: phys(0x148667000, 0x148667FFF), cache =non-cacheable, length=4KB(0MB),    name=
"VPP_CMODE3_CPU"
|-Block: phys(0x148668000, 0x1487E7FFF), cache =non-cacheable, length=1536KB(1MB),    name=
"h26x_ko"
|-Block: phys(0x1487E8000, 0x148967FFF), cache =non-cacheable, length=1536KB(1MB),    name=
"h26x_ko"
|-Block: phys(0x148968000, 0x148968FFF), cache =non-cacheable, length=4KB(0MB),    name=
"h26x_ko"
|-Block: phys(0x148969000, 0x148969FFF), cache =non-cacheable, length=4KB(0MB),    name=
"GDC_CMDA3"
|-Block: phys(0x14896A000, 0x14896AFFF), cache =non-cacheable, length=4KB(0MB),    name=
"GDC_CMDA3_CPU"
|-Block: phys(0x14896B000, 0x14896DFFF), cache =non-cacheable, length=12KB(0MB),    name=
"GDC_CMD"
|-Block: phys(0x14896E000, 0x148AEDFFF), cache =non-cacheable, length=1536KB(1MB),    name=
"jenc_ko"
|-Block: phys(0x148AEE000, 0x148C6DFFF), cache =non-cacheable, length=1536KB(1MB),    name=
"jenc_ko"
|-Block: phys(0x148C6E000, 0x148C6EFFF), cache =non-cacheable, length=4KB(0MB),    name=
"jenc_ko"
|-Block: phys(0x148C6F000, 0x14926EFFF), cache =non-cacheable, length=6144KB(6MB),    name=
"vdec_ko"
---CMM_USE_INFO:
 total size=7208960KB(7040MB),used=18876KB(18MB + 444KB),remain=7190084KB(7021MB + 580KB),partition_number=1,block_number=23
m5stack@raspberrypi5:~ $ axcl-smi sh cat /proc/ax_proc/mem_cmm_info -d 0
--------------------SDK VERSION-------------------
[Axera version]: ax_cmm V3.6.3_20250722020142 Jul 22 2025 02:21:25 JK
+---PARTITION: Phys(0x148000000, 0x2FFFFFFFF), Size=7208960KB(7040MB),    NAME="anonymous"
 nBlock(Max=0, Cur=23, New=0, Free=0)  nbytes(Max=0B(0KB,0MB), Cur=19329024B(18876KB,18MB), New=0B(0KB,0MB), Free=0B(0KB,0MB))  Block(Max=0B(0KB,0MB), Min=0B(0KB,0MB), Avg=0B(0KB,0MB)) 
   |-Block: phys(0x148000000, 0x148013FFF), cache =non-cacheable, length=80KB(0MB),    name="TDP_DEV"
   |-Block: phys(0x148014000, 0x148014FFF), cache =non-cacheable, length=4KB(0MB),    name="TDP_CMODE3"
   |-Block: phys(0x148015000, 0x148015FFF), cache =non-cacheable, length=4KB(0MB),    name="TDP_CMODE3_CPU"
   |-Block: phys(0x148016000, 0x148029FFF), cache =non-cacheable, length=80KB(0MB),    name="TDP_DEV"
   |-Block: phys(0x14802A000, 0x14802AFFF), cache =non-cacheable, length=4KB(0MB),    name="TDP_CMODE3"
   |-Block: phys(0x14802B000, 0x14802BFFF), cache =non-cacheable, length=4KB(0MB),    name="TDP_CMODE3_CPU"
   |-Block: phys(0x14802C000, 0x14862BFFF), cache =non-cacheable, length=6144KB(6MB),    name="vdec_ko"
   |-Block: phys(0x14862C000, 0x148647FFF), cache =non-cacheable, length=112KB(0MB),    name="VGP_DEV"
   |-Block: phys(0x148648000, 0x148648FFF), cache =non-cacheable, length=4KB(0MB),    name="VGP_CMODE3"
   |-Block: phys(0x148649000, 0x148649FFF), cache =non-cacheable, length=4KB(0MB),    name="VGP_CMODE3_CPU"
   |-Block: phys(0x14864A000, 0x148665FFF), cache =non-cacheable, length=112KB(0MB),    name="VPP_DEV"
   |-Block: phys(0x148666000, 0x148666FFF), cache =non-cacheable, length=4KB(0MB),    name="VPP_CMODE3"
   |-Block: phys(0x148667000, 0x148667FFF), cache =non-cacheable, length=4KB(0MB),    name="VPP_CMODE3_CPU"
   |-Block: phys(0x148668000, 0x1487E7FFF), cache =non-cacheable, length=1536KB(1MB),    name="h26x_ko"
   |-Block: phys(0x1487E8000, 0x148967FFF), cache =non-cacheable, length=1536KB(1MB),    name="h26x_ko"
   |-Block: phys(0x148968000, 0x148968FFF), cache =non-cacheable, length=4KB(0MB),    name="h26x_ko"
   |-Block: phys(0x148969000, 0x148969FFF), cache =non-cacheable, length=4KB(0MB),    name="GDC_CMDA3"
   |-Block: phys(0x14896A000, 0x14896AFFF), cache =non-cacheable, length=4KB(0MB),    name="GDC_CMDA3_CPU"
   |-Block: phys(0x14896B000, 0x14896DFFF), cache =non-cacheable, length=12KB(0MB),    name="GDC_CMD"
   |-Block: phys(0x14896E000, 0x148AEDFFF), cache =non-cacheable, length=1536KB(1MB),    name="jenc_ko"
   |-Block: phys(0x148AEE000, 0x148C6DFFF), cache =non-cacheable, length=1536KB(1MB),    name="jenc_ko"
   |-Block: phys(0x148C6E000, 0x148C6EFFF), cache =non-cacheable, length=4KB(0MB),    name="jenc_ko"
   |-Block: phys(0x148C6F000, 0x14926EFFF), cache =non-cacheable, length=6144KB(6MB),    name="vdec_ko"

---CMM_USE_INFO:
 total size=7208960KB(7040MB),used=18876KB(18MB + 444KB),remain=7190084KB(7021MB + 580KB),partition_number=1,block_number=23
重要
shell命令参数如果包含
-
,
--
,
>
等字段，可以用双引号
"-l"
将命令和参数包含在一个字符串中，比如
axcl-smi >sh "ls -l" -d 0
。谨慎使用shell命令对设备进行配置。
重启（reboot）
axcl-smi reboot
命令首先复位指定设备，随后将自动加载固件，示例如下：
m5stack@raspberrypi5:~ $ axcl-smi reboot
Do you want to reboot device 0 ? (y/n): y
m5stack@raspberrypi5:~ $ axcl-smi reboot
Do you want to reboot device 0 ? (y/n): y
Next
目录索引
On This Page
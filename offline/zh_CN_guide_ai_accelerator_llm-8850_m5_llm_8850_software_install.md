# m5-docs

来源: https://docs.m5stack.com/zh_CN/guide/ai_accelerator/llm-8850/m5_llm_8850_software_install

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
LLM-8850 Card 环境配置
树莓派环境配置
参考以下文档或
官方链接
完成树莓派环境配置，注意：以下命令在树莓派的终端执行。
如同 PC 中的 BIOS，EEPROM 设置独立于烧录 OS 的 TF 卡，烧录最新的树莓派镜像或者切换镜像版本并不会主动更新 EEPROM 的设置。
首先执行 update：
sudo apt update && sudo apt full-upgrade
sudo apt update && sudo apt full-upgrade
然后检查一下 EEPROM 中的版本：
sudo rpi-eeprom-update
sudo rpi-eeprom-update
如果看到的日期早于
2023 年 12 月 6 日
，运行以下命令以打开 Raspberry Pi 配置 CLI：
sudo raspi-config
sudo raspi-config
在 Advanced Options > Bootloader Version （引导加载程序版本） 下，选择 Latest （最新）。然后，使用 Finish 或 ESC 键退出 raspi-config。
执行以下命令，将固件更新到最新版本。
sudo rpi-eeprom-update -a
sudo rpi-eeprom-update -a
最后使用
sudo reboot
重新启动。重启后就完成了 EEPROM 中 firmware 的更新。
sudo reboot
sudo reboot
完成修改并重启后，可以使用
lspci
命令检查加速卡是否正确被识别：
lspci
lspci
命令执行结果如下：
m5stack@raspberrypi5:~ $ lspci
0001:00:00.0 PCI bridge: Broadcom Inc. and subsidiaries BCM2712 PCIe Bridge (rev 30)
0001:01:00.0 Multimedia video controller: Axera Semiconductor Co., Ltd Device 0650 (rev 01)
0002:00:00.0 PCI bridge: Broadcom Inc. and subsidiaries BCM2712 PCIe Bridge (rev 30)
0002:01:00.0 Ethernet controller: Raspberry Pi Ltd RP1 PCIe 2.0 South Bridge
m5stack@raspberrypi5:~ $ lspci
0001:00:00.0 PCI bridge: Broadcom Inc. and subsidiaries BCM2712 PCIe Bridge (rev 30)
0001:01:00.0 Multimedia video controller: Axera Semiconductor Co., Ltd Device 0650 (rev 01)
0002:00:00.0 PCI bridge: Broadcom Inc. and subsidiaries BCM2712 PCIe Bridge (rev 30)
0002:01:00.0 Ethernet controller: Raspberry Pi Ltd RP1 PCIe 2.0 South Bridge
其中
Multimedia video controller: Axera Semiconductor Co., Ltd Device 0650 (rev 01)
就是 LLM-8850 加速卡。
LLM-8850 Card 驱动安装
提示
开发板需要编译支持，依赖 gcc, make, patch, linux-header-$(uname -r) 这几个包。需要提前安装好，或者保证安装时网络可用。
更新软件源
通过以下命令获取 aarch64/x86 deb 包：
sudo wget -qO /etc/apt/keyrings/StackFlow.gpg https://repo.llm.m5stack.com/m5stack-apt-repo/key/StackFlow.gpg
echo
'deb [signed-by=/etc/apt/keyrings/StackFlow.gpg] https://repo.llm.m5stack.com/m5stack-apt-repo axclhost main'
| sudo tee /etc/apt/sources.list.d/axclhost.list
sudo wget -qO /etc/apt/keyrings/StackFlow.gpg https://repo.llm.m5stack.com/m5stack-apt-repo/key/StackFlow.gpg
echo 'deb [signed-by=/etc/apt/keyrings/StackFlow.gpg] https://repo.llm.m5stack.com/m5stack-apt-repo axclhost main' | sudo tee /etc/apt/sources.list.d/axclhost.list
使用以下命令安装
sudo apt update
sudo apt update
sudo apt install dkms
sudo apt install dkms
sudo apt install axclhost
sudo apt install axclhost
安装将很快完成。安装时会自动增加环境变量，使得安装的 .so 和可执行程序可用。需要注意的是，如果需要可执行程序立即可用，还需要更新 bash 终端的环境：
source
/etc/profile
source /etc/profile
如果是 ssh 的方式远程连接的板卡，还可以选择重连 ssh 进行自动更新 (本机终端登录还可以重开一个终端进行自动更新)。
输入以下命令，即可查看设备的信息：
axcl-smi
axcl-smi
输出如下：
+------------------------------------------------------------------------------------------------+
| AXCL-SMI  V3.6.4_20250805020145                                  Driver  V3.6.4_20250805020145 |
+-----------------------------------------+--------------+---------------------------------------+
| Card  Name                     Firmware                                                          | Bus-Id       | Memory-Usage           |
| Fan   Temp                Pwr:Usage/Cap                                                          | CPU      NPU | CMM-Usage              |
| =========================================+==============+======================================= |
| 0  AX650N                     V3.6.4                                                             | 0001:01:00.0 | 148 MiB /      945 MiB |
| --   41C                      -- / --                                                            | 2%        0% | 18 MiB /     7040 MiB  |
+-----------------------------------------+--------------+---------------------------------------+

+------------------------------------------------------------------------------------------------+
| Processes:                                                                                       |
| Card      PID  Process Name                                                   NPU Memory Usage   |
| ================================================================================================ |
+------------------------------------------------------------------------------------------------+
| AXCL-SMI  V3.6.4_20250805020145                                  Driver  V3.6.4_20250805020145 |
+-----------------------------------------+--------------+---------------------------------------+
| Card  Name                     Firmware                                                          | Bus-Id       | Memory-Usage           |
| Fan   Temp                Pwr:Usage/Cap                                                          | CPU      NPU | CMM-Usage              |
| =========================================+==============+======================================= |
| 0  AX650N                     V3.6.4                                                             | 0001:01:00.0 | 148 MiB /      945 MiB |
| --   41C                      -- / --                                                            | 2%        0% | 18 MiB /     7040 MiB  |
+-----------------------------------------+--------------+---------------------------------------+

+------------------------------------------------------------------------------------------------+
| Processes:                                                                                       |
| Card      PID  Process Name                                                   NPU Memory Usage   |
| ================================================================================================ |
详情请查看
AXCL-SMI
部分
LLM-8850 Card 驱动卸载
提示
如果遇到安装问题或需要更新驱动，使用以下命令卸载驱动。
sudo apt remove axclhost
sudo apt remove axclhost
Next
目录索引
On This Page
# OpenCore For Dell 5593
此EFI适用于Dell灵越5593型号笔记本电脑（1035G1）。在暑期，经过不懈的研究，折腾了几天，终于达到90%！OC0.7.1/安装Bigsur11.5.1

## 我的配置
| 硬件 |型号  |
|--|--|
| 笔记本 | Dell 5593（Inspiron 16s） |
| CPU | Intel Core I5-1035G1（UHD G1）ice lake 10nm |
| 内存 | SK Hynix 2667Mhz 8G×1|
|SSD| TOSHIBA NVMe  512GB |
| 独显 | Nvidia MX230（已屏蔽）|
| 板载网卡 |Realtek RTL8106E PCI Express Fast Ethernet |
|  无线+蓝牙| Intel AX201 WIFI6 160Mhz|
|  |~~Qualcomm QCA9377~~（已更换）|
| 声卡 |Realtek ALC 236（已支持耳机） |
| 显示器 |内置（15.6英寸） |
|  键盘|内置 |
|  鼠标| 罗技M590|
## Tips*注意*：
1.建议解锁CFG Lock，并在Kernel->Quirks 关闭 AppleCpuCfgLock 和 AppleXcpmCfgLock，获得更好的电源管理体验
2.本机原来无线网卡为高通 ~~Qualcomm QCA9377~~，仅蓝牙可驱动，现已更换intel ax201。如对隔空投送等有需求，建议更换博通卡
3.声音、亮度调节均正常，可直接按Fx键进行调节
4.USB端口已定制，如不符合你的端口，请删除`USBPorts.kext`并自行定制
5.支持合盖睡眠、电池电量正常
6.睡眠可能有问题，有待观察（ice lake 10nm）
## 日志
##### 2021.08.07 初次上传
- OC已更新到最新0.7.1正式版，更新部分驱动，支持Bigsur11.5.1+
- 修复亮度调节快捷键（`F6`降低亮度，`F7`增加亮度）、合盖即可进入睡眠
- 调试并注入正确的声卡`layout-id`，扬声器、麦克风、耳机、均正常——ALC236
- 添加配置Apple原生主题，内置3个主题，不喜欢可自行更换
- 添加参数`igfxfw=2`修复内核崩溃问题
- 驱动触控板，支持手势操作
- 修复Windows10引导问题
- ……
---
	感谢黑果大佬们的教程及排错经验！
## 日志
如果我的分享对你有帮助，可以点个Star🌟，xiexie！

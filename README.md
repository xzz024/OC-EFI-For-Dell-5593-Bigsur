# Open Core DELL Inspiron 5593
此EFI适用于Dell灵越5593型号笔记本电脑（1035G1）。经过不懈的研究，完美度达到95%+！
已更新OC0.7.1/已安装Bigsur11.5+11.5.1

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

## 系统截图
<img src="https://z3.ax1x.com/2021/08/07/fMwQiV.png" width = "657" height = "400" alt="" align=center />
<img src="https://github.com/xzz024/OC7.1-EFI-For-Dell-5593-Bigsur/blob/main/ScreenShot/OC%20Start.png" width = "657" height = "400" alt="" align=center />
<img src="https://z3.ax1x.com/2021/08/07/fM0w0s.png" width = "657" height = "400" alt="" align=center />
<img src="https://z3.ax1x.com/2021/08/07/fMDvfP.png" width = "657" height = "400" alt="" align=center />
<img src="https://z3.ax1x.com/2021/08/07/fMr9Og.png" width = "657" height = "400" alt="" align=center />
<img src="https://z3.ax1x.com/2021/08/07/fMriwj.png" width = "657" height = "400" alt="" align=center />
<img src="https://z3.ax1x.com/2021/08/07/fMrAkn.png" width = "657" height = "400" alt="" align=center />

## 项目清单

- [x] ALC236 内部扬声器(耳机正常)
- [x] ALC236 内部麦克风(耳机不正常)
- [x] 所有的USB端口（如不符请自行定制）
- [x] 风扇调速、CPU变频 / 睡眠
- [x] 带有手势的I2C触摸板
- [x] 亮度调节快捷键
- [x] Wi-Fi and Bluetooth Intel Module（AX201）
	- [x] 跨设备复制、接力
	- [ ] 无线随航、隔空投送
	- [ ] Apple Watch解锁
- [x] Realtek RTL8100 LAN 有线网卡
- [x] 笔记本合盖睡眠
- [x] ACPI 电池
- [x] 从OpenCore启动Windows
- [x] HDMI 输出
- [ ] 睡眠唤醒（ice lake 10nm）

## Tips*注意*：
- 建议解锁CFG Lock，并在Kernel->Quirks 关闭 AppleCpuCfgLock 和 AppleXcpmCfgLock，获得更好的电源管理体验
- 本机原来无线网卡为高通 ~~Qualcomm QCA9377~~，仅蓝牙可驱动，现已更换intel ax201。如对隔空投送等有需求，建议更换博通卡
- 声音、亮度调节均正常，可直接按Fx键进行调节
- USB端口已定制，如不符合你的端口，请删除`USBPorts.kext`并自行定制
- 支持合盖睡眠、电池电量正常
- EFI已清空三码，请安装后自己注入三码，以开启iMessage、Facetime、Siri
- 睡眠可能有问题，有待观察（ice lake 10nm）

## 更新日志
##### 2021.08.07 初次上传
- OC已更新到最新0.7.1正式版，更新部分驱动最新版，支持Bigsur11.5.1+
- 修复亮度调节快捷键（`F6`降低亮度，`F7`增加亮度）、合盖即可进入睡眠
- 调试并注入正确的声卡`layout-id`，扬声器、麦克风、耳机、均正常——ALC236
- 添加配置Apple原生主题，内置3个主题，不喜欢可自行更换
- 添加参数`igfxfw=2`修复内核崩溃问题
- 驱动触控板，支持手势操作
- 修复Windows10引导问题
- ……
---
	感谢黑果大佬们的教程及排错经验！
## 最后
如果我的分享对你有帮助，可以点个Star🌟，更新提醒，xiexie！

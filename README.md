# Open Core DELL Inspiron 5593
适用于Dell灵越5593型号笔记本电脑（1035G1）。经过不懈的研究，完美度达到95%+！
已更新OC`0.7.1`/已安装`Big Sur`11.5+11.5.1

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
| 声卡 |Realtek ALC 236（已支持插孔耳机） |
| 显示器 |内置（15.6英寸） |
|  键盘|内置 |
|  鼠标| 罗技M590|

## 系统截图
<img src="https://z3.ax1x.com/2021/08/08/fQqK9P.png" width = "657" height = "436" alt="mymac" align=center />
<img src="https://z3.ax1x.com/2021/08/08/fQqa90.png" width = "657" height = "462" alt="gpu" align=center />
<img src="https://z3.ax1x.com/2021/08/08/fQOROO.png" width = "657" height = "482" alt="hidpi" align=center />
<img src="https://z3.ax1x.com/2021/08/08/fQLxRx.png" width = "657" height = "454" alt="xianka" align=center />
<img src="https://z3.ax1x.com/2021/08/08/fQOXnS.png" width = "657" height = "691" alt="usb" align=center />
<img src="https://z3.ax1x.com/2021/08/08/fQXicV.png" width = "657" height = "462" alt="wifi" align=center />
<img src="https://z3.ax1x.com/2021/08/08/fQv1Te.png" width = "657" height = "370" alt="OCStart" align=center />

## BIOS设置-5593
- `System Configuration`➡️`SATA Operation`（`AHCI`）
	- 修改前若有win10系统，请进入先安全模式修改它
- `Security`➡️`Absolute®️`（`Disable` `Absolute®️`）
- `Security`➡️`SMM Security Mitigation`（`OFF`）
- `Security`➡️`Intel®️ Platform Trust Technology On`（`OFF`）
- `Security`➡️`Intel®️ SGX`（`Disabled`）
- `Secure Boot`➡️`Enable Secure Boot`（`OFF`）
- `Secure Boot`➡️`Secure Boot Mode`（`Deployed Mode`）
- （非必须）`CFG Lock`解锁`Setup_Var 0x43 0x0`[BIOS解锁工具](https://www.jianguoyun.com/p/DaUvc2AQ_pOuCBj31IYE)`操作不当后果自负`

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
- 本机原来无线网卡为高通 ~~Qualcomm QCA9377~~，仅蓝牙可驱动，现已更换intel ax201。如对隔空投送等有需求，建议更换`博通卡`
- 声音、亮度调节均正常，可直接按Fx键进行调节
- USB端口已定制，如不符合你的端口，请删除`USBPorts.kext`并自行定制
- 支持合盖睡眠、电池电量正常
- EFI已清空三码，请安装后注入三码，以开启iMessage、Facetime、Siri
- 睡眠可能有问题，有待观察（ice lake 10nm）

## 更新日志
#### 2021.08.08 更新驱动+修复小小小问题
- 更新Intel Wifi、Bluetooth驱动至最新`V2.0.0`版本
- 小修改使安装过程更友好
- 截图添加
#### 2021.08.07 初次上传
- OC已更新到最新0.7.1正式版，更新部分驱动最新版，支持Bigsur11.5.1+
- 修复亮度调节快捷键（`F6`降低亮度，`F7`增加亮度）、合盖即可进入睡眠
- 调试并注入正确的声卡`layout-id`，扬声器、麦克风、耳机、均正常——ALC236
- 添加配置Apple原生主题，内置3个主题，不喜欢可自行更换
- 添加参数`igfxfw=2`修复内核崩溃问题
- 驱动触控板，支持手势操作
- 修复Windows10引导问题
- ……
## 教程&致谢
- [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [精解OpenCore - 黑果小兵的Blog](https://blog.daliansky.net/OpenCore-BootLoader.html)
- [使用OpenCore引导黑苹果 - Xjn's Blog](https://blog.xjn819.com/post/opencore-guide.html)
- [OpenCore Vanilla Guide](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/)
- [HiDPI是什么？以及黑苹果如何开HiDPI - 国光](https://www.sqlsec.com/2018/09/hidpi.html)
- [OpenIntelWireless](https://openintelwireless.github.io/)
- [远景论坛](https://bbs.pcbeta.com/forum.php?gid=86)
- [tonymacx86](https://www.tonymacx86.com/)
- ……

		感谢黑果大佬们的教程及排错经验！
## 最后
如果我的分享对你有帮助，可以点个Star🌟，xiexie！

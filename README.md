# Open Core DELL Inspiron 5593
适用于Dell灵越5593型号笔记本电脑（1035G1）。经过不懈的研究，完美度达到98%+！
已更新OC`0.7.1`/已安装`Big Sur`11.5.2//支持macOS Monterey 12.0 Beta5

## 我的配置
| 硬件 | 型号 |
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
<img src="https://github.com/xzz024/OC7.1-EFI-For-Dell-5593-Bigsur/blob/main/ScreenShot/wifi02.png" width = "657" height = "462" alt="wifi" align=center />
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
- [x] 所有的USB端口（如不符建议自行定制）
- [x] 风扇调速、CPU变频 / 睡眠
- [x] 带有手势的I2C触摸板
- [x] 亮度调节快捷键
- [x] Wi-Fi and Bluetooth Intel Module（AX201）
	- [x] 跨设备共享剪贴板、接力、定位服务
	- [ ] 无线随航、隔空投送
	- [ ] Apple Watch解锁
- [x] Realtek RTL8100 LAN 有线网卡
- [x] 笔记本合盖睡眠唤醒`2021-08-13`
- [x] ACPI 电池
- [x] 从OpenCore启动Windows
- [x] HDMI 输出
- [x] 深度睡眠唤醒（ice lake 10nm）`2021-08-13`
- [ ] 开机登录界面黑屏5-7秒，按键闪屏，这是Ice Lake的通病（待解决）

## Tips*注意*：
- 建议解锁CFG Lock，并在Kernel->Quirks 关闭 AppleCpuCfgLock 和 AppleXcpmCfgLock，获得更好的电源管理体验
- 本机原来无线网卡为高通 ~~Qualcomm QCA9377~~，仅蓝牙可驱动，现已更换intel ax201。如对隔空投送等有需求，建议更换`博通卡`
- 声音、亮度调节均正常，可直接按Fx键进行调节
- USB端口已定制，如不符合你的端口，请删除`USBPorts.kext`并自行定制
- 支持合盖睡眠、电池电量正常
- EFI已清空三码，请安装后注入三码，以开启iMessage、Facetime、Siri，更多[教程](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#verifying-nvram)请自行爬贴，同时别忘记用脚本Clean out old attempts
- 如果有双系统win需求，在win10下导入此注册表可解决与Mac时间不同步问题[tool.reg](https://www.jianguoyun.com/p/DWFYhFoQ_pOuCBiI1oYE)
- 如果是高通QCA9377的无线卡，且没有更换计划可使用USB网卡，驱动[RTLWlanU BigSur.kext](https://www.jianguoyun.com/p/DUGTl18Q_pOuCBj01YYE)
- 开启HIDPI见👇的教程，建议开启，开启后设置`1680×945`，类似Win10下缩放`125%`，字体更加清晰，同时记得在NVRAM中修改`UIScale`为02保持开机Logo大小一致。如果在线脚本有问题，请使用离线脚本[HIDPI](https://www.jianguoyun.com/p/DTopycAQ_pOuCBiO7YcE)开启
- ~~睡眠可能有问题，有待观察（ice lake 10nm）~~
- 登录界面屏幕显示黑色故障5-7秒或任何其他屏幕显示问题(这与所有Ice Lake相关)//可能会在Monterey中被更新修复，至少现在它有不同的“症状”

## 更新日志
#### 2021.08.13 修复睡眠问题+小优化
- 此次终于解决睡眠问题，根据Acidanthera团队的说法：睡眠出现唤醒内屏无显示问题（DC9/DC6错误）是因为从深度唤醒过程过于直接，添加参数修复。同时优化部分内容。（睡眠一晚掉电？%左右）
#### 2021.08.08 更新驱动+修复小小小问题
- 更新Intel Wifi、Bluetooth驱动至最新`V2.0.0`版本
- 小修改使安装过程更友好
- 截图添加
#### 2021.08.07 初次上传
- OC已更新到最新0.7.1正式版，更新部分驱动最新版，支持Bigsur11.5.1+
- 修复亮度调节快捷键（`F6`降低亮度，`F7`增加亮度）、合盖即可进入睡眠
- 调试并注入正确的声卡`layout-id`，扬声器、麦克风、耳机、均正常——ALC236
- 添加配置Apple原生主题，内置3个主题，不喜欢可自行更换
- 添加参数`igfxfw=2`修复内核崩溃问题，运行更加稳定
- 驱动触控板，支持手势操作
- 修复Windows10引导问题
- ……
## I5 CPU Ice Lake仿冒问题
部分参考自@FireWolf
|CPU | 主频 |睿频|线程数|三级缓存|TDP|设备 ID|加速?|
|--|--|--|--|--|--|--|--|
| 1038NG7`Pro`| 2Ghz | 3.8Ghz | 4✖️2 | 6M | 28W | `0x8A53` | ✅|
| 1035G7| 1.2Ghz | 3.7Ghz | 4✖️2 | 6M | 15W |  `0x8A52`| ✅|
| 1035G4| 1.1Ghz | 3.7Ghz | 4✖️2 | 6M | 15W | `0x8A5A` | ✅|
|1035G1 | 1Ghz | 3.6Ghz | 4✖️2 |6M  | 15W | `0x8A56` | ❌|
| 1030NG7`Air`| 1.1Ghz | 3.5Ghz |4✖️2  | 6M | 10W | `0x???` |✅ |
|1030G7 | 0.8Ghz |  3.5Ghz| 4✖️2 | 6M |  9W|  `0x8A51`| ✅|
|1030G4 | 0.7Ghz | 3.5Ghz | 4✖️2 | 6M | 9W | `0x8A5C` |✅ |

*Tips*目前`01005C8A`/`0200518A` 推荐使用，其他ID会造成睡眠无法唤醒等其他相关问题

---
## GeekBench5性能跑分（插电高性能Model测试）
- 在`Windows10 2009`下：[1035G1的具体表现](https://browser.geekbench.com/v5/cpu/9320463)
   - 单核[Single-Core Score]：`1142`
   - 多核[Multi-Core Score]：`3355`
   - 核显[Intel(R) UHD Graphics]：`5557`[详细结果](https://browser.geekbench.com/v5/compute/3228790)
   - 独显[NVDIA GeForce MX230]：`8124`[详细结果](https://browser.geekbench.com/v5/compute/3228805)

**结论：在Win10下，应该算正常环境下的性能测试，可见这颗U的最终得分并不好看，在同Ice Lake架构上对比，性能略强于`Macbook Air9,2`，弱于`Macbook Pro16,3`**

- 在`Bigsur 11.5.2`下：[1035G1的具体表现](https://browser.geekbench.com/v5/cpu/9321385)
   - 单核[Single-Core Score]：`1131`
   - 多核[Multi-Core Score]：`3154`
   - 核显[Intel(R) UHD Graphics]：`5557`[详细结果](https://browser.geekbench.com/v5/compute/3228790)
   - 独显[NVDIA GeForce MX230]：`无法驱动`[详细结果]()
## 教程&致谢
- [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [精解OpenCore - 黑果小兵的Blog](https://blog.daliansky.net/OpenCore-BootLoader.html)
- [FireWolf](https://github.com/0xFireWolf/WhateverGreen)
- [使用OpenCore引导黑苹果 - Xjn's Blog](https://blog.xjn819.com/post/opencore-guide.html)
- [WhateverGreen](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.IntelHD.en.md)
- [OpenCore Vanilla Guide](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/)
- [HiDPI是什么？以及黑苹果如何开HiDPI - 国光](https://www.sqlsec.com/2018/09/hidpi.html)
- [OpenIntelWireless](https://openintelwireless.github.io/)
- [远景论坛](https://bbs.pcbeta.com/forum.php?gid=86)
- [tonymacx86](https://www.tonymacx86.com/)
- [……](http://www.baidu.com)

		感谢黑果大佬们的教程及排错经验！
## 最后
如果我的分享对你有帮助，可以点个Star🌟

# Hackintosh Thinkpad X220 High Sierra

## 硬件信息

CPU: i5-2540M

Mem: 8G              

Storage:HP SSD S700 120GB

Integrated Graphics: HD Graphics 3000

Sound Card: CX20590    alcid 12

Wireless Card: **BCM94352hmb** 

Bios: 1.46 去除白名单 

## 简介

- 此库是为Thinkpad X220创建，OpenCore 版本0.7.6。

- 所有关于X220的资源请参考http://x220.mcdonnelltech.com/resources/，感谢McDonnell团队的付出。

- 联想5代机型之后才解除BIOS白名单限制，因此需要移除白名单，适配更多型号的无线网卡，BIOS移除了白名单，更换网卡为bcm94352hmb 已经屏蔽51和20针脚。

- config中显存为1024m，4G内存默认显存为384m，8G内存默认显存为512m。改显存为2048m,需要在config-kernel-patch-中将C745D000 000018 改为C745D000 000020  将C745D000 000040 改为C745D000 000060   （内存坏了一条当前只有4G内存，显存只改了1024m)

- 目前有线网卡、无线网卡、蓝牙、声卡、隔空投、隔空播放正常。外接显示器、facebook等没有测试 ；在使用过程中会横线、冻屏现象，偶尔有死机的情况，不知道是硬件问题还是config还需要完善。如果想稳定可以使用McDonnell团队的clover引导，参考 http://x220.mcdonnelltech.com/有详细的安装教程。

  


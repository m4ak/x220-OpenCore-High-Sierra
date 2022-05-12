# Hackintosh Thinkpad X220 High Sierra

## 硬件信息

CPU: i5-2540M

Mem: 8G              

Storage:HP SSD S700 120GB

Integrated Graphics: HD Graphics 3000

Sound Card: CX20590    

Wireless Card: BCM94352hmb 

Bios: 1.46 去除白名单 

## 简介

- 此库是为Thinkpad X220创建，OpenCore 版本0.7.6，支持Catalina。

- 所有关于X220的资源请参考http://x220.mcdonnelltech.com/resources ，感谢mcdonnell团队的付出。


- 联想5代机型之后才解除BIOS白名单限制，因此需要移除白名单，适配更多型号的无线网卡，BIOS移除了白名单，更换网卡为bcm94352hmb 已经屏蔽51和20针脚。


## bios相关

- bios设置

1. Restart > **Load Setup Defaults**
2.  Config > Power > Power On with AC Attach > **Disabled**
3.  Config > Serial ATA (SATA) > SATA Controller Mode Option > **AHCI***
4. Security > Memory protection > Execution Prevention > **Enabled***
5.  Startup > UEFI/Legacy Boot > **Both**

- bios升级

1. 将bios升级到1.46版本，如果已经是1.46版本可以直接安装修改后的bios文件，使用bios目录中的升级文件或者自行下载官方的1.46版本bios都可以，链接https://support.lenovo.com/us/en/downloads/ds018805 ，下载完后一定要验证文件大小，确保升级文件没有问题。升级之前做一下恢复默认设置不要设置什么开机密码之类的，直接在windows下运行8duj31us.exe文件可以完成升级，操作过程可以查看官方的升级文档8duj31us.txt               

   **MD5:** 87377d3ac64ce865b38ad15a56518e8

2. 将bios目录中的X220_v1.46_Modified_BIOS.zip放到带PE的U盘内，或者到http://x220.mcdonnelltech.com 自行下载，开机按F12选择以U盘启动进入PE系统，解压的X220_v1.46_Modified_BIOS.zip，运行flash.bat进行bios的更新，更新完成后提示重启机器。重启后直接进bios有高级菜单，升级成功。注意升级过程中不要断电      

   **MD5**: 4a769c4f17e8aa0dc0e6927ebe75635d

## 系统状态

正常工作：

- 有线网卡
- 无线网卡
- 蓝牙
- 声卡
- 隔空投
- 隔空播放
- 变频
- USB
- 电池

未测试：

- 外接显示器
- TRIM
- APPLE ID 
- facebook

## 其它

- 在使用过程中会横线、冻屏现象，偶尔有死机的情况，不知道是硬件问题还是config还需要完善。如果想使用clover引导，参考 http://x220.mcdonnelltech.com ，有详细的安装教程。
- EFI中没有无线网卡的驱动，无线网卡驱动使用的是AW-CE123H-10.13.0-v1.01.pkg。这个驱动包将bcm94352hmb 仿冒成bcm94360，最高支持10.13.6，安装后重启直接使用。如果安装Catalina，需要使用AirportBrcmFixup+Brcm3件套来驱动无线网卡和蓝牙。
- config中显存为1024m，4G内存默认显存为384m，8G内存默认显存为512m。改显存为2048m,需要在config-kernel-patch-中将C745D000 000018 改为C745D000 000020  将C745D000 000040 改为C745D000 000060   （内存坏了一条当前只有4G内存，显存只改了1024m)
- 自身能力有限，只能做到当前效果，期待同机型爱好者一起来完善它。


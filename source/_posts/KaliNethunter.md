---
title: nethunter与android系统装机
date: 2019-02-26 11:13:36
tags: [大一,Android]
categories: GUIDE
---
<p align = "center">只是安装了一个kali在nexus 5x(350RMB)上</p>

<!--more-->
# 装kali nethunter

## nexus 5x实体

很轻巧,做工精细,原生Android系统手感很好,就是Google需要科学上网比较伤.手机内存cpu运行不是很流畅,不能玩大型游戏.不过可以玩Google play下的小游戏.

##安装kali nethunter理论流程

1. 保存ROM包,在电脑上安装adb,fastboot等环境
2. 在系统里设置USB调试,OEM解锁(类似选项),**退出Google账户**
3. 命令行
	1. 输入```adb devices```检查设备是否连接
	2. 输入```adb reboot bootloader```进入手机BIOS模式
	3. 输入```fastboot oem unlock```或```fastboot flashing unlock```解锁oem锁,再利用```fastboot flash recovery twrp.img```重载bootloader,其中twrp.img是TWRP官网上下载的第三方bootloader
	4. 重启进recovery模式*(也可以重启再输入```adb reboot recovery```)*
	5. 点击```advanced```选项,```adb sideload```选项.
	6. pc端测试连接后,```adb sideload nethunter.zip```载入nethunter
4. 在手机端操作安装完成重启
5. 结束

## 我的第一次装机实战流程

1. 同1
2. 没有解锁oem,没有退出Google账户
3. 先谨慎的刷了一遍官网下载的Android系统,使用的是原装bootloader.
4. 没有问题就解锁oem锁,刷入twrp
5. 在twrp下完成kali nethunter的安装
6. 开机后发现安装选项选错,没有达到我预期的效果
7. 打算重装系统重新来一遍
8. 由于twrp安装后系统开机显示警告,于是就把oem锁上了
9. oem已锁的情况下无法进行data分区解密
10. 尝试进入系统,发现卡在开机界面
11. 重启重新进recovery,重新刷原生系统发现`sideload`无效.
12. 尝试用`push`方法将ROM包发送至`sdcard`,在twrp中卡刷
13. 成功刷入原生系统
14. 进入系统发现无法跳过网络验证环节
15. 尝试科学上网,失败
16. 尝试刷入第三方系统
	1. flyme失败
	2. MTC失败
	3. choroma成功
17. 进入系统开启oem锁
18. 重新用官方factory版本刷机刷回出厂
19. 重新安装twrp和kali nethunter
20. 结束

过程十分曲折,消耗了我大量精力和时间(耗时三天).结果也并不令人十分高兴(安装了一个app叫kali nethunter)并且现阶段我对这个app没有需求.

但是不是没有收获.我知道了Android系统是基于Linux系统的变种也知道了除内核外Android的运行方式.

下一次我希望可以在自己的手机上删除不想要的功能.
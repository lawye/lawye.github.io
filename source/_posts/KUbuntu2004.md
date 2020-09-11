---
title: KUbuntu2004
date: 2020-08-20 21:47:47
tags: ubuntu
categories: GUIDE
---

# KUbuntu 20.04 使用体验

实际上我原先使用的是Ubuntu with gnome，然后在一些问题的困扰下切换到了kde桌面。后面由于一些问题kde崩了，我就想着重新安装系统好了，就直接安装的KUbuntu。

<!--more-->
## 软件安装

首先是minecraft。我直接拷贝的原系统里的.minecraft文件夹。

其次是各种开发软件。我在新系统上就安装了vi，vscode，idea（java），typora（morkdown），sublimed text3（用来看文档）。

然后是一些游戏。osu!lazer，steam。

多媒体软件：2D使用的是WIMP，3D使用的是Blender和BlockBench（MC），视频剪辑暂时还没安装，没有需求。

下载软件：Ktorrent和aria2。之前配置aria2的时候吃了很多亏，现在补全了。

聊天工具：telegram，QQ-linux

翻墙：Clashr（linux版），自动生成配置文件使用了clashr for windows 软件使用代理采用了proxychains而不是系统自动代理，因为这个的pac模式有点奇怪，所以干脆直接全走代理。

文件共享：oneDrive，Resilio sync（未配置好）（权限问题）

桌面：todolist(非常方便，原因是可以自由添加，而且可以显示tab）)

输入法：fcitx rime加小鹤音形配置（位置是`~/.config/fcitx/rime/`）

## 文件目录配置

原先我是在固态上划了约60g，机械上划了两个分区，一个挂在/home上，另一个挂在/home/mega上，主要原因是无法扩展分区，所以就这么将就着用了。现在就将两个分区合并，固态上还是/，机械上的两个分区都作为/home。

windows下的E盘我通过修改`/etc/fstab`，挂载在了`/home/lawye/winfile`上。

## 其他的小设置

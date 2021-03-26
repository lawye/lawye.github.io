---
title: KDE软件管理Discover中proxy设置错误
date: 2021-03-26 09:41:40
tags: ubuntu
categories: GUIDE
---

这是一个由于数据库未更新导致的bug。

<!--more-->

## 问题表现形式

在打开Discover时会出现一行报错：Proxy cant connect: 127.0.0.1:12333

我寻思我用的代理端口是7891啊，12333是之前设置的时候尝试用过的端口，怎么会在这里出现呢

于是各种查错，把代理设置全部还原了，但是依然无法解决

## 谷歌搜索后得到解决方案

[kde论坛](https://forum.kde.org/viewtopic.php?f=309&t=161739)

实际上的原因是discover的父进程Packagekit的问题。由于Packagekit没有更新其数据库，导致proxy设置依旧保留在其数据库中。

解决方法是先删除sqlite3数据库`/var/PackageKit/transactions.db`中`Proxy`表中的记录，再重启服务`sudo systemctl restart packagekit.service`

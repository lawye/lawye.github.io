---
title: 击键动力学与py画图
date: 2019-03-09 10:23:42
tags: [大一,code,冯如杯]
categories: GUIDE
---
<p align = "center">FengRuBei</p>
<!--more-->
# 一切都是冯如惹的祸

冯如嘛,冯如杯嘛

## 击键动力学是什么

自己看[wiki](https://en.wikipedia.org/wiki/Keystroke_dynamics).

不懂就google是一个好习惯,尤其是当校园网可以上google时

## python3怎么画图

需要引入一个叫matplotlib的库:这个库的用途是画图,就是点线面.

如果画的图比较大,即数据比较多,存放在表格里,我们就需要将其保存为csv文件,并且用pandas的read_csv函数读入这个文件.如`f=read_csv("路径",engine='python')`

读入的数据分为两部分,表头和数据,分别可以用`f.columns.tolist()`和`f.values.tolist()`转换为列表.后面就是自说自话各显神通了

画线或者点的格式是`matplotlib.pyplot.plot(XList,YList,color='red',linestyle='-',marker='.')`参数自己换吧.

显示图片是`matplotlib.pyplot.show()`

这里有一张不在论文里用的图可以看一看![image](test.png)

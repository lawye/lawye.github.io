---
title: hexo与next主题与github代码仓库联合
date: 2019-03-15 14:32:01
tags: [Hexo,next]
categories: REFERENCE
---
<p align = "center">HEXO配置时可能用到的一些玩意</p>

<!--more-->

## 配置主题

>配置[github角标](http://tholman.com/github-corners/)
>更改位置在`网站位置\themes\next\layout\_layout.swig`下`<div class="headband"></div>`标签下一行.

### 链接

[一个奇怪的资源比较多的博客](https://me.idealli.com/post/e8d13fc.html)

### 发现

在`theme/next/source/css`下可以全自定义主题.只要懂一点css语法,看懂里面写的就行,甚至可以自己写一个新的主题.

## 有关hexo源码管理

实际上的`lawye.github.io`仓库`master`分支储存的是本地`public`文件夹下的内容

需要做的是将除了`public`的其余内容用另一个分支或者仓库存储

[可能有用的参考文献](https://panqiincs.me/2017/08/06/hexo-blog-code-management/)

### 已解决

首先, 我们需要采用githuub上非`master`分支存储源码, 在`master`分支上用hexo自带的`deploy`功能, 即键入

```cmd
hexo d
```

以push到远程仓库中.

根据hexo的帮助文档, 我们首先需要安装插件`hexo-deployer-git`, 采用

```cmd
npm install hexo-deployer-git --save
```

或者

```cmd
cnpm install hexo-deployer-git --save
```

命令安装.

其次, 在根目录(即`hexo init`的文件夹)下的`_config.yml`文件中修改`deploy`属性,形如

``` yml
deploy:
  type: git
  repo: <repository url>  #https://bitbucket.org/JohnSmith/johnsmith.bitbucket.io
  branch: [branch] #published
  message: [message]  #leave this blank
```

这之后就可以直接`hexo d`来推送啦

至于原来的源码请使用`git`或者`github desktop`上传到github上,~~如果嫌重复了可以把那两个文件夹ignore掉.~~ 居然已经自己把它ignore了, hexo牛逼
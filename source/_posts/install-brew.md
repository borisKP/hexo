---
title: 安装brew的终极解决方法
date: 2021-07-05 01:31:30
tags:
- 建站
- HEXO
categories:
- 折腾笔记
---
大家也许尝试过很多次，在[brew的官网](https://brew.sh/index_zh-cn)里，复制如下命令，并在终端中运行报错的情况。


```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```
![iShot2021-07-04 22.58.06](https://i.loli.net/2021/07/04/PFAYdC7HObxvQ28.png)

终极解决办法就是简单，粗暴，有效的。

<!--more-->


直接换成我们国内的源。
```shell
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```
老规矩，进入终端，复制如上的代码，选择“1”，是中科大的源，下载就好。
键入后显示如下：
```shell
XXX@XXX % /bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"


               开始执行Brew自动安装程序
              [cunkai.wang@foxmail.com]
           ['2021-07-04 22:50:14']['11.4']
        https://zhuanlan.zhihu.com/p/111014448


请选择一个下载镜像，例如中科大，输入1回车。
源有时候不稳定，如果git克隆报错重新运行脚本选择源。cask非必须，有部分人需要。
1、中科大下载源 2、清华大学下载源 3、北京外国语大学下载源  4、腾讯下载源（不推荐） 5、阿里巴巴下载源(不推荐 缺少cask源)

请输入序号: 1
```

用这个方法安装后，最骚的就是大佬的这句回复：

> **如果以后更新是国内源，软件如果国内源有缓存是从国内下载。**

再次感谢原作者大佬！！！



原文请查看知乎专栏：
[https://zhuanlan.zhihu.com/p/111014448](https://zhuanlan.zhihu.com/p/111014448)


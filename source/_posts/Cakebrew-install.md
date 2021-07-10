---
title: 非常好用的 Homebrew 图形化管理软件Cakebrew
date: 2021-07-10 22:13:14
tags:
- macOS
- 建站
categories:
- 折腾笔记
---

[Cakebrew](https://www.cakebrew.com/)是一款macOS平台的图形化管理工具。

有了它，妈妈再也不用担心我记不住`brew`命令了！

![Cakebrew-home.png](https://i.loli.net/2021/07/10/nFqP8mVHb1M2kxD.png)

<!--more-->

## Cakebrew是什么？

Cakebrew是macOS平台上一款管理Homebrew的应用，采用绝佳的可视化管理页面，从而摆脱命令行的束缚，点点鼠标、动动触摸板，即可完成全部的操作。

目前 Cakebrew 支持 Intel 和 ARM(M1) 两种架构，多国语言支持（**支持简体中文哦**）。

## Cakebrew简介
[Homebrew](https://brew.sh/)是一款基于macOS系统的package管理器。我在上一篇文章介绍了如何安装Homebrew的终极方法（[点击这里查看](https://boriskp.github.io/install-brew/)）。

但是Homebrew有个小问题~~（主要是因为我太懒）~~
就是Homebrew没有GUI，也就是没有图形化的操作界面，全部需要以命令行的形式进行操作。
对于大多数程序员还好，只要经常使用，简单几个命令也能熟记。
但对于我而言，一个优美的图形化界面更适合我。
前两天在GitHub浏览的时候，发现了这个有着3.8k Star的项目---[Cakebrew](https://www.cakebrew.com/)


## Cakebrew的UI以及大致用法演示

![Cakebrew-ui.png](https://i.loli.net/2021/07/10/53sqjZUEY9yDzGh.png)
如上图，非常直观，整个UI为分栏设计，左边是你的Formulae分类，左上角的🌐地球仪按钮是更新你的Homebrew，点击就会自动升级你的Homebrew。
右上可以看到你全部安装的Formulae以及版本信息，再也不用找个小本本一条一条记录版本信息了。
右下显示的是每个Formulae的信息，尤其可以显示“依赖”与“冲突”。看到这个我直呼：“非常的人性化”

![Cakebrew-Formulae.png](https://i.loli.net/2021/07/10/SPBEQG6wX7isgze.png)

其他用法相信聪明的你打开Cakebrew就可以完全理解。

除此之外，Cakebrew还支持直接点击自动执行`brew cleanup`命令。

> Mac电脑的内存与硬盘永远是“金子”般的存在。
> 尤其是在M1芯片这边，当你的Mac不够了的时候。
> 不妨想想，是否之前有同感Homebrew安装过很多“一次性”的开发环境和工具包。
> Homebrew有个特性，就是不会帮我们自动移除旧版本的软件包,你需要手动执行命令去移除软件包。
> 在Cakebrew中，可以用鼠标点击的方式自动执行`brew cleanup`命令用于清理。
> 强烈建议清理器，手动执行`brew cleanup -n`查看可清理的旧版本包，*注意！此命令不执行具体操作。*

![Cakebrew-cleanup.png](https://i.loli.net/2021/07/10/wC7IVoNkP2b9LUu.png)



## Cakebrew的下载与安装。

Cakebrew的安装有如下2中方式。（推荐第二种，无脑粗暴）
1.你可以直接去官网下载，然后通过直接拉入“应用程序”的文件夹中进行安装。

    官方网站：https://www.cakebrew.com/
    GitHub源码：https://github.com/brunophilipe/Cakebrew

2.当然，你可通过在 _终端_ 中输入以下命令进行自动安装。

```shell
brew install --cask cakebrew
```
实例如下：
```shell
XXX@XXX ~ % brew install --cask cakebrew
==> Downloading https://cakebrew-377a.kxcdn.com/cakebrew-1.3.zip
######################################################################## 100.0%
==> Installing Cask cakebrew
==> Moving App 'Cakebrew.app' to '/Applications/Cakebrew.app'
🍺  cakebrew was successfully installed!
```


> 需要注意的是：Cakebrew不提供Homebrew本体的安装。
> 如果你还未安装Homebrew，你可以去[Homebrew官网](https://brew.sh/)安装，
> 也可以查看下我之前的文章（[点击这里](https://boriskp.github.io/install-brew/)）


![Cakebrew-install.png](https://i.loli.net/2021/07/10/pjCehJQlHiVY8mr.png)

最后，请愉快使用的同时，记得去GitHub上给原作者星星⭐️啊！！！

**https://github.com/brunophilipe/Cakebrew**

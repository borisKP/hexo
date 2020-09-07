---
title: SSRSpeed-基于Shadowsocks(R)的批量测速工具
date: 2020-09-07 14:11:41
tags:
- NAS
- 插件
- VPS
categories:
- 折腾笔记
---

相信每位使用SS(R)的小伙伴都非常想对自己使用的机场线路进行一个全面的测速，目前比较常用的测试办法是通过设置代理为全局模式访问测速网站 [Fast](https://fast.com/) 和 [SpeedTest](https://www.speedtest.net/) 进行测试。

这样的办法只能分别对每一个节点进行测速，比较繁琐和复杂。前段时间在看毒药大佬的测速文章，发现大佬都是使用统一的工具进行测试

继而找寻了一番，最后在Github上发现了一个项目：SSRSpeed-基于Shadowsocks(R)的批量测速工具 

使用过之后发现非常不错。这里就水一个简单的Windows和Linux下的配置和使用教程。

<!--more-->


----------

项目地址：[https://github.com/NyanChanMeow/SSRSpeed/](https://github.com/NyanChanMeow/SSRSpeed/)

*因不可描述的原因，原作者删除了“中文版Readme”*

**请严格遵守项目说明：在您公开发布测速结果之前请务必征得节点拥有者的同意以避免一些令人烦恼的事情**

注意：理性测速！
因为你在测速的时候就是在挖掘线路服务器和你本地网络之间的一个临界值，对其他正在使用线路的用户会有一定影响；另外不同地区不同时间线路的效果也会有一定差别。

----------

# Windows下配置及使用 #

该项目所需环境Python3.6+，关于Python的安装请访问[ https://www.python.org/downloads/]( https://www.python.org/downloads/) 自行下载3.6+版本并安装和配置。
（截止本文发出前，Python已经更新到3.8.5版本）

**注意：在安装Python的时候，请务必勾选中如下图所示的地方，别无脑下一步。**

![Snipaste_2020-09-07_16-00-54.png](https://i.loli.net/2020/09/07/kK5TQ2Nxc4GAREs.png)

- 确保本地Python环境为Python3.6+之后，我们需要将项目下载到本地。

项目下载地址：
[https://github.com/NyanChanMeow/SSRSpeed/releases](https://github.com/NyanChanMeow/SSRSpeed/releases)
(请下载.zip文件，并解压。)

- 打开命令行，切换到解压缩好的项目路径中，安装通用依赖

```cmd
cd #完整解压缩目录
pip3 install -r requirements.txt
```



- 安装完成通用依赖之后，我们可以通过不同方式对我们使用的线路进行测试（其他参数请查看Github项目Readme）

```cmd
#输入订阅地址
python3 main.py -u https://xxx.xxx.xxx
#键入配置文件路径
python3 main.py -c \xxx\xxx\gui-config.json
```

- 然后根据提示进行操作即可，测试完成之后会输出.png的测试图，位于results文件夹内。

----------
# Linux下配置及使用 #

对于Linux环境，建议使用 Ubuntu 18.04 LTS，好处是不需要自行安装python3.6+（逃



- 首先需要检查Python版本是否符合要求，输出Python版本号大于3.6即可

```shell
root@Ubuntu:# python3
Python 3.6.7 (default, Oct 22 2018, 11:32:17) 
```

- 确保符合对应版本之后，我们还需要安装依赖 libsodium Shadowsocks-libev 以及 Simple-Obfs

- 安装libsodium

```shell
sudo apt update
apt-get install build-essential
wget https://github.com/jedisct1/libsodium/releases/download/1.0.15/libsodium-1.0.15.tar.gz
tar xf libsodium-1.0.15.tar.gz && cd libsodium-1.0.15
./configure && make -j2 && make install
ldconfig
```


- 安装Shadowsocks-libev

```shell
sudo apt install shadowsocks-libev
```

- 安装Simple-Obfs

```shell
sudo apt-get install --no-install-recommends build-essential autoconf libtool libssl-dev libpcre3-dev libev-dev asciidoc xmlto automake
git clone https://github.com/shadowsocks/simple-obfs.git
cd simple-obfs
git submodule update --init --recursive
./autogen.sh
./configure && make
sudo make install
```

- 将所有依赖安装完成之后，拉取项目文件

```Shell
apt-get install -y git
git clone -b Dev https://github.com/NyanChanMeow/SSRSpeed.git
```

- 进入到项目目录中，安装通用依赖，即可进行测试（其他参数请查看Github项目Readme）


```shell
cd SSRSpeed
pip3 install -r requirements.txt
#输入订阅地址
python3 main.py -u https://xxx.xxx.xxx
#键入配置文件路径
python3 main.py -c \xxx\xxx\gui-config.json
```

- 然后根据提示进行操作即可，测试完成之后会输出.png的测试图，位于results文件夹内


----------

感谢原文作者：[golby](https://golby.cc/index.php/172)


**如果出现测速为0，而您的机场又一切正常的情况，请参考这个[issues](https://github.com/NyanChanMeow/SSRSpeed/issues/118)，修改ssrspeed_config.json文件中，downloadlinks里第一条link失效，把链接改为第二条link即可解决。**

![Snipaste_2020-09-07_18-05-56.png](https://i.loli.net/2020/09/07/UJRlhYsP2xTdLFo.png)


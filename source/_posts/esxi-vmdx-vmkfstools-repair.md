---
title: ESXi下OpenWRT/LEDE启动报错(对象类型需要托管的 I/O)
date: 2020-10-08 00:52:58
tags:
- 服务器
- ESXi
categories:
- 折腾笔记
---

我家的网络主力设备是一台魔改的服务器，在上面安装并运行ESXi，虚拟出NAS与软路由等服务。

因考虑到这台服务器7*24的定位，在服务器前段加了一个UPS电源，并同时加了一个小米智能开关，用于查看机器的功率。

今天在对ESXi进行日常维护的时候；一时手欠，不小心点了智能开关的升级按钮，本来觉得也没啥，毕竟UPS还是会继续运行一段时间的嘛，结果不知道为何，小米智能开关升级失败，也不通电，直接就导致了UPS没电让我的ESXi自动关机了。

再启动的时候，发现ESXi可以正常启动，爱快与NAS系统都可以正常启动，唯独LEDE软路由系统无法启动，虚拟机报错(对象类型需要托管的 I/O)；感觉非常的诧异，固件是Koolshare论坛的的LEDE系统。

![VMware.png](https://i.loli.net/2020/10/07/qx4lfzwJyc3CR6r.png)

<!--more-->

在查阅了VMWare社区的帖子以及Koolshare论坛的帖子后，发现出现类似的问题不止我一个人，大家出现的问题都是因为非正常关机所导致的。貌似是vmdk文件损坏。

### 其实软路由这个东西，非正常关机才是正常啊喂~

解决办法如下：

# 1. 开启ESXi的SSH功能

进入网页版的ESXi页面，找到主机的“管理”---“服务”---“TSM-SSH”启动
![sssssh.png](https://i.loli.net/2020/10/07/iShkpoHtuAPWzJf.png)

# 2. 找到错误提示的路径

![image_1582091570860.jpeg](https://i.loli.net/2020/10/08/tKCrLfwH4SNVQdy.jpg)


# 3. 登陆SSH输入命令

非正常关机导致vmdk损坏，需要通过`vmkfstools`终端命令进行修复。

## 3.1 开启ssh并确认使用vmkfstools命令检查

```bash
vmkfstools -x check 路径
```
```bash
# vmkfstools 检查命令
vmkfstools -x check <vmdk文件>
# 执行结果
vmkfstools -x check lede.vmdk
# 以下结果表示需要修复
Disk needs repair.

# 举例：
vmkfstools -x check /vmfs/volumes/5d582a2a-40abb997-8ffd-e43a6e0448e3/LEDE/openwrt-x86-64-combined-squashfs.vmdk (里面的地址修改为你错误信息里面的地址)
Disk needs repair.

```

如上代码显示，`Disk needs repair.`则说明文件需要修复。


## 3.2 使用`repair`命令修复文件

```bash
vmkfstools -x repair 路径
```

```bash
# vmkfstools 修复命令
vmkfstools -x repair <vmdk文件>
# 执行结果
vmkfstools -x repair lede.vmdk 
# 以下结果表示修复完成
Disk was successfully repaired.

# 举例：
vmkfstools -x repair /vmfs/volumes/5d582a2a-40abb997-8ffd-e43a6e0448e3/LEDE/openwrt-x86-64-combined-squashfs.vmdk (里面的地址修改为你错误信息里面的地址)
Disk was successfully repaired.

```

如上代码显示，完成后后提示`Disk was successfully repaired.`
即代表文件已经修复完成。

重启ESXi主机，问题解决。

# 4. 尾巴

> 说到底还是固件源码的问题。

自己测试过突然断电再次通电的主机，还是会出现类似的现象，每次都要修复，找遍全网都没有一个能彻底解决的办法。

**设想一下：某一天，你家因为一次小小的断电，导致全家无法上网，而你这个唯一懂处理的人却在外地出差，要一周后才回家，对于一个现代人来说，没有网络过一周是多么痛苦的事情啊~**

实测滚回LEDE的固件2.35就不会出现此类问题。

对于如上的设想，我个人能想到的应急方案如下：

## 4.1 准备1台硬路由调试好一切（比如桥接啊，PPPoE拨号啦，WiFi账号密码啦）


让一个不懂任何运维知识的人只要远程告知插拔几条线就可以临时使用。

## 4.2 在ESXi中安装至少2台软路由。


比如设置成LEDE1与LEDE2。
其中LEDE1为主力机，长时间在线。
LEDE2为冷备，平常不开机，当LEDE1挂掉时，启动LEDE2进行补充。
（可以设置好你的LEDE1，然后备份一份，直接在LEDE2上还原即可，不过因为是一摸一样的设置，未防止IP地址冲突，请务必只开机1台，备份机配合心跳检测与故障切换就可以）

## 4.3 双机热备。

这个就不讲了，对应家庭环境实数没必要，不过家庭如果有孩子或者老人要时时刻刻看监控，还是建议上的。
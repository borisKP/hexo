---
title: 群晖DSM系统获取root权限
date: 2020-09-03 13:22:00
tags:
- 服务器
- 群晖
categories:
- 折腾笔记
---


群晖的DSM系统一直以来都以优秀的软件服务，受到广大人民的喜爱。
可是自从DSM6之后，就不允许SSH默认使用ROOT账号登陆了，只给了admin账户登陆SSH的权限，官方解释是为了安全考虑，从而使权限得到一部分限制。

这样就导致了我们在使用PUTTY或者WinSCP的时候，部分文件夹权限不够，无法操作的情况。

~~我都安装黑裙了，为毛不给我ROOT用户权限~~

那么如何在群晖中获取ROOT权限呢？步骤如下：

![1899945143.jpg](https://i.loli.net/2020/09/03/23GzRQ81EIFplgY.jpg)

<!--more-->

#### 1、登录群晖，控制面板-终端机和SNMP-开启SSH功能： ####

![Snipaste_2020-09-03_12-58-58.png](https://i.loli.net/2020/09/03/fED9AU5IamrPWei.png)

#### 2、通过SSH登陆群晖，用系统帐号及密码： ####
（win系统建议PUTTY，mac系统建议vSSH，本次仅演示PUTTY的操作）

![Snipaste_2020-09-03_13-01-38.png](https://i.loli.net/2020/09/03/ZpxmcgCyHnXGwSa.png)


#### 3、输入 `sudo -i` 回车，输入群晖admin账户的账号以及密码，切换到root用户，注意是由$变为#： ####

![Snipaste_2020-09-03_13-04-33.png](https://i.loli.net/2020/09/03/9I45zG8XSihMgTs.png)

#### 4、赋权 ####
输入如下代码，进入ssh文件并对其赋予相应的权限。

```
cd /etc/ssh  #进入ssh文件夹
chmod 755 sshd_config  #对文件"sshd_config"赋权
```

![Snipaste_2020-09-03_13-08-29.png](https://i.loli.net/2020/09/03/ojdY298J51xklRA.png)


#### 5：修改sshd_config文件 ####
使用vim进入`sshd_config` 文件。

```
vim /etc/ssh/sshd_config 
```

找到第33行的`#PermitRootLogin prohibit password`

输入`i` 编辑，将`#PermitRootLogin prohibit password` 修改为：`PermitRootLogin yes` **去掉#号**。

`ESC`键退出编辑模式，再输入 `:wq` 保存并退出。

![Snipaste_2020-09-03_13-18-18.png](https://i.loli.net/2020/09/03/pqZlj4wdXQcgmNC.png)



#### 6、修改root默认密码： ####

```
synouser --setpw root xxxxxxx    
 
#后面的xxxxxxx更换成你自己的密码
```

#### 7、`reboot` 重启群晖，就可以直接使用root及密码登陆ssh。

至此，您将获得ROOT用户权限。 

**大写的注意：**

**1.请务必对ROOT用户启用复杂密码。**

**2.请务必在使用完成后进入网页DSM关闭SSH功能。**

**3.有条件请更改SSH链接端口，不建议使用默认22端口。**



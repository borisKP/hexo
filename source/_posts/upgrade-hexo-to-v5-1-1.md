---
title: hexo版本更新报错： "external_link"
date: 2020-09-01 11:19:54
tags:
- 服务器
categories:
- 折腾笔记
---

![hexo-5.png](https://i.loli.net/2020/09/01/Es7mMCiKSYbWc4P.png)

随着2020年7月29日到来，Node.js 上最快的静态站点生成器 Hexo 发布了 5.0.0 版本。升级系统固然很简单，不过根据我的经验，在大版本更新后，一些小的坑肯定是有的，本文主要说明我在升级后遇到的坑，以及解决方案。

<!--more-->

在hexo5.0.0新版本后,运行`hexo s`或者`hexo g`的时候会出现如下的报错情况：

```
报错：
INFO  Validating config
WARN  Deprecated config detected: "external_link" with a Boolean value is deprecated. See https://hexo.io/docs/configuration for more details.
```

查回[官网更新版本信息](https://hexo.io/news/2020/07/29/hexo-5-released/)，可以看到官网的Breaking change中，有关于设置更改的选项。

![222.jpg](https://i.loli.net/2020/09/01/HEWkZs4XhMBfixz.jpg)

经过查找，解决方案如下：

打开主目录下的`_config.yml`
找到：
```
external_link: true # Open external links in new tab
```

修改成：
```
external_link:
  enable: true # Open external links in new tab
  field: site # Apply to the whole site
  exclude: ''
```
即可解决问题。

> 具体升级信息请查如下blog写的很详细。
[https://blog.skk.moe/post/hexo-5/](https://blog.skk.moe/post/hexo-5/)
[https://tommy.net.cn/2020/08/08/upgrade-hexo-to-v5-0-0/](https://tommy.net.cn/2020/08/08/upgrade-hexo-to-v5-0-0/)

---
title: 解决Github打不开问题
date: 2020-09-01 11:15:34
tags:
- 服务器
categories:
- 折腾笔记
---

github最近打不开，很久之前遇到过，但是忘记怎么解决了，查找相关资料后，今天记录在此，以备不时之需。

![5.jpeg](https://i.loli.net/2020/09/01/haKlJ5uBY8tFEpP.jpg)

<!--more-->





> **注意！如下您的网页出现如下信息，说明您可以连接入github，请检查您的域名输入是否正确，而非本文所述内容。此情况不在本文讨论范围内。**




![6.jpg](https://i.loli.net/2020/09/01/mVYFeCKNZO6sdhu.jpg)







记住3个关键网址


- github网址查询：

[https://github.com.ipaddress.com/](https://github.com.ipaddress.com/)

- github域名查询：

[https://fastly.net.ipaddress.com/github.global.ssl.fastly.net](https://fastly.net.ipaddress.com/github.global.ssl.fastly.net)

- github静态资源ip：

[https://github.com.ipaddress.com/assets-cdn.github.com](https://github.com.ipaddress.com/assets-cdn.github.com)

# github网址ip查询 #

![1.png](https://i.loli.net/2020/08/31/1OsZ8ibN9XhgY7v.png)

# github域名查询 #

![2.png](https://i.loli.net/2020/08/31/kyzQo41JCKe5R8b.png)

# github静态ip查询 #

![3.png](https://i.loli.net/2020/08/31/xSzMZUwo7afjhP2.png)



修改host文件，修改host文件，在最后附上下面的内容

```
140.82.114.4 github.com
199.232.69.194 github.global.ssl.fastly.net
185.199.108.153 assets-cdn.github.com
185.199.109.153 assets-cdn.github.com
185.199.110.153 assets-cdn.github.com
185.199.111.153 assets-cdn.github.com
```
重新刷新你的浏览器，即可访问github。

> 备注：此方法也适用于当您的git无法连接到github服务器的情况。

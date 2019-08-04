---
title: 让你的网站加速-CDN网络服务cloudflare
date: 2019-08-03 23:29:13
tags:
- 建站
categories: 
- 折腾笔记
---
既然是一个开源的博客那么我分享的东西基本上是基于免费的，如果你看过我最早的文章，你也知道，我的网站曾经备案过。根据中国的法律法规。未备案的网站，将不会被接入cdn网络服务。那么如果我们有一个未备案的网站使用的是国外的服务器，我们还想使用CDN网络服务的话，要如何呢？在这里就要请出大名鼎鼎的cloudflare了。
PS：也许有人还不知道CDN？CDN的全称是Content Delivery Network，也就是内容分发网络，CDN系统能够实时地根据网络流量和各节点的连接、负载状况以及到用户的距离和响应时间等综合信息将用户的请求重新导向离用户最近的服务节点上。最终目的就是提高网站的访问速度。
![cloudflare][1]

------------
关于cloudflare的CDN网络，如下图所示就应该很清晰了，懂的人自然懂，不懂的小白我这里就多说一句。他是一个强大的，免费的国外cdn网络提供商，cloudflare的系统服务器，会直接连接并缓存你的网页信息，然后让访问者从就近的服务器读取你网页的信息，这样速度可以成倍的提升。
![cdn.map.gif][2]
如果你像我一样，热衷于去谷歌上找一些外网资源的话，那么你一定见过如下的网站图片，见到了这个图片，说明你所要访问的网站，就是接入了cloudflare的CDN服务。
(不过是你访问的网站挂了)
![522.png][3]

------------

是的没错他的服务遍布全球，也是比较优质的免费cdn服务商。那么我们要如何使用他家的cdn服务呢？
首先第1步当然是注册账号了。
> 在你的浏览器中输入网址：[点击此处cloudflare](https://www.cloudflare.com/ "点击此处cloudflare")

![zhuye.jpg][4]

注册完成后，把你需要登录的域名通过ds绑定到他家的服务器上。
绑定过程如下图：
输入你需要绑定的域名
![bangding1.jpg][5]
无视直接“下一步”
![bangding2.jpg][6]
选择免费套餐（土豪随意）
![bangding3.jpg][7]
继续无视点击“下一步”
![bangding4.jpg][8]
然后需要把你的域名通过NS的方式接入到cloudflare,具体的NS地址如下图所示.
**（需要注意的是，每个不同的域名cloudflare会分配给你不同的NS地址，千万要填写正确哟）**
> NS：域名服务器记录，如果需要把域名交给其他DNS服务商解析，就需要添加NS记录。

![bangding5.jpg][9]
具体如何绑定NS记录，这里需要去找到你域名的挂靠服务商，添加一个NS记录即可。这里我们拿godaddy来举例。
登陆你的域名，找到DNS管理，更改DNS直接到cloudflare所给出的记录即可。在绑定完成后，耐心稍等几分钟，你就可以愉快的使用cdn服务了。是不是很简单呢？
![bangding6.jpg][10]
**注意：如果你在godaddy更新后，你的域名全部都将由cloudflare直接管理，如果你不喜欢或者有其他原因不希望cloudflare来管理你的域名，请继续往下看**

------------

那么问题来了，如果我仅仅需要一个二级域名接入cloudflare的CDN服务，或者是不方便把自己的域名直接让cloudflare进行管理，那么该怎么办呢？
当当当当~
这里重点来了~
早在2017年的时候，cloudflare推出了一个合伙人计划（[Cloudflare’s Partner Program](https://www.cloudflare.com/partners/ "Cloudflare’s Partner Program")）。其目的就是我们可以向cloudflare申请账户，利用其API进行自建服务，然后实现CNAME别名解析。
具体资料你可以上网搜索，也可以去看看这个文章：[https://www.itbulu.com/cloudflare-partner.html](https://www.itbulu.com/cloudflare-partner.html "https://www.itbulu.com/cloudflare-partner.html")
![partners.jpg][11]
简而言之，如果我们直接从Cloudflare官方申请账户和添加站点，只能更换域名DNS解析，这样的做法确实也是比较彻底和直接，但是对于有些需要变更解析和其他功能用途的，确实不是这么方便。cloudflare的合伙人计划恰恰就解决这个问题！
毕竟自建一个CloudFlare CDN服务，对于新手来说是非常困难的一件事情，但从2018年到现在，网络上已经有了许多非常优秀的第三方CloudFlare CDN服务；我这里推荐是笨牛网提供的Cloudflare免费CDN管理平台:
`https://cdn.bnxb.com/`

他家的cdn服务是做的比较好的一个。面板做的也很漂亮，内容也不错，也有一些简单的提示，可以让新手很快的入门。
这里就介绍一下怎样使用笨牛网的CloudFlare CDN服务
首先是登录你的账号，这个账号不是你在奔牛网注册的，是你在CloudFlare里面注册的账号，笨牛网仅仅是使用CloudFlare的API进行确认，安全性可以放心。
![bnxb1.jpg][12]
登录了以后首先是要绑定域名；
注意：这里需要你绑定的是根域名不是二级域名！
![bnxb2.jpg][13]
![bnxb3.jpg][14]
绑定好了以后，我们要通过cname的方式把你所需要CloudFlare提供CDN服务的域名接入其中
![bnxb4.jpg][15]
然后在你的原有服务商处，写入需要CloudFlare提供CDN服务的cname域名
最后在笨牛网提供的服务上回溯到自己的服务器。
这里建议各位使用一个cname的回溯，最好使用一个复杂的二级域名，以防止“有心人”追溯到你的原始ip并进行DDoS。

静待几分钟后（通常情况下域名服务商免费的ttl是600秒）你就可以享受免费的cdn服务了。
最后，我们去[站长工具](http://tool.chinaz.com/ "站长工具")查看一下，如果你看到现在全部的链接地址都指向CloudFlare的IP。
这说明cdn服务已经启动了。我这里是显示的国内测试地址，当然国外的cdn服务，毕竟因为你懂的原因，速度并不是很快。但是也聊胜于无，安全性，比裸奔强一个档次。
同时你也可以通过修改为静态等方式，加快你的网页访问速度。

![chinaz.jpg][16]

[1]:https://i.loli.net/2019/07/18/5d30080c386d041739.png
[2]:https://www.cloudflare.com/img/products/cdn/map.gif
[3]:https://i.loli.net/2019/07/18/5d300a50d924382847.png
[4]:https://i.loli.net/2019/07/18/5d300afb9b58a91723.jpg
[5]:https://i.loli.net/2019/07/18/5d301272505ad72056.jpg
[6]:https://i.loli.net/2019/07/18/5d3012aadf26a84259.jpg
[7]:https://i.loli.net/2019/07/18/5d3013195842b13725.jpg
[8]:https://i.loli.net/2019/07/18/5d301398974cf11904.jpg
[9]:https://i.loli.net/2019/07/18/5d30145e7b4e069426.jpg
[10]:https://i.loli.net/2019/07/18/5d30185f3a43532166.jpg
[11]:https://i.loli.net/2019/07/18/5d301d9ba814268399.jpg
[12]:https://i.loli.net/2019/07/18/5d301f8054ec758942.jpg
[13]:https://i.loli.net/2019/07/18/5d301fe9ac02744254.jpg
[14]:https://i.loli.net/2019/07/18/5d30205290c4083412.jpg
[15]:https://i.loli.net/2019/07/18/5d30214e26cad10254.jpg
[16]:https://i.loli.net/2019/07/18/5d3022f043a4936752.jpg
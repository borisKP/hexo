---
title: 关于我经常使用的图床
date: 2019-08-03 23:31:20
tags:
- 建站
categories: 
- 折腾笔记
---
![tuchuang.jpg][2]
> 图片作为互联网服务中最基础的资源之一，随着互联网基础服务越来越专业化，图片的存储、处理、分发也发展成了一项独立的基础服务。试想一下，如果每家互联网公司都要花费大量人力物力去做图片相关的技术研发，哪还有时间去做自己的业务。专业的事情还是要交给专业的人来做。图片作为互联网服务中最基础的资源之一，随着互联网基础服务越来越专业化，图片的存储、处理、分发也发展成了一项独立的基础服务。试想一下，如果每家互联网公司都要花费大量人力物力去做图片相关的技术研发，哪还有时间去做自己的业务。专业的事情还是要交给专业的人来做。


个人认为：图床是现代互联网一大“聪明”的发明，请注意，这个聪明是带引号的；
因为图床这个玩意儿，在我看来真的是一把“双刃剑”，因为通常情况下，免费的图床都会让人们不用登陆就可以上传图片，这就会导致一旦你丢失了你的图片链接，那么这张图片将彻底“迷失”在互联网之上，只要图床还在运营一天，那么你的图片将永久存在，不会被删除；
这个时候，如果这张图片恰巧是因为“手误”所上传的“nude photo”那么有可能被人看到吗？
我不知道。
### 我只知道：互联网没有Del键！###

**[维基百科关于图床的介绍][1];可以查看关于“网络安全”的类目，~~如果你不想变成下一个“陈老师”~~**
#### 请你务必注意且慎重使用图床! ####


------------


> 以下是我推荐的图床，好用与否还请你自行判断，无任何排名，仅供参考！

## 图床平台 ##

基于2019年上半年的情况，网络上的主流图床主要分为两种，一种是公共图床，一种是自建图床。公共图床也就是利用公共服务的图片上传接口，来提供图片外链的服务，比如新浪微博，SM.MS等。自建图床，也就是利用各大云服务商提供的存储空间或者自己在 VPS 上使用开源软件来搭建图床，存储图片，生成外链提供访问，比如七牛、Lychee 开源自建图床等方案。
*（我个人比较偏向于使用公共图床，图片定期备份的方案）*
### 公共图床： ###
#### SM.MS####
1. 首先要推荐的图床就是大名鼎鼎的 [SM.MS][4]了，这个图床是由 V2EX [@Showfom][5] 自建的，无外链限制，无流量限制的图床，支持 HTTPS，速度不错，自2015年运行至今了，还算稳定。
![sm.ms.jpg][3]
#### Imgur 图床 ####
2. 其次是[Imgur 图床][6]，他家也是一家老牌国外图片存储服务商，国外速度很快，口碑不错，支持 HTTPS。但是国内速度很不稳定（~~考虑到XXX的原因~~），所以追求国内速度的同学慎用。
![Imgur.jpg][7]
#### 路过图床 ####
3. [路过图床][8]支持免注册上传图片，永久存储，支持HTTPS加密访问和调用图片，提供多种图片链接格式，国内较为稳定，不过因为是国内运营，所以可能会在不通知的情况下删除图片。
![luguo.jpg][9]
#### Upload 图床 ####
4. [Uploda][10]图床属于个人使用过比较好的一个，可以上传nude类图片，支持HTTP加密访问，可以上传GIF动图，国内还算比较稳定，限制：最大5M
![uploda.jpg][11]
#### MNMLSV ####
5. [mnmlsv][12]图床，算是比较特殊，因为他是唯一一个在首页大大的写着“支持nudes”的图床，如果你需要干一些“奇怪”的事情，这个图床是一个很好的建议~
![mnmlsv.jpg][13]

### 公共图床： ###
#### 七牛云 ####
1. [七牛云][14]作为国内领先的云服务商，全网 CDN 加速，全国访问速度都不错，API 很详细，对开发者比较友好。免费用户提供 10GB 存储空间，国内和海外分别提供 10 GB 的 HTTP 免费流量，七牛的 HTTPS 流量是收费的，没有免费额度。此外，七牛还提供了针对图片的各种服务，包括图片裁剪，压缩，鉴黄等等衍生服务。如果你觉得图片尺寸太大，可以在外链后面添加参数，访问的时候七牛会自动根据你的参数对图片进行处理。唯一的缺点就是需要进行实名认证，这点不予置评~
![qiniuyun.jpg][15]

#### 又拍云 ####
2. [又拍云][16]也算是国内比较有名的云服务商了，国内拥有 200+ 的自建 CDN 节点，国内速度也不错，API 很详细，不过对于普通用户没有免费额度，目前实行的是「按照用户每日实际消耗的 CDN 流量，实行 1:1 的存储空间费免费使用」。缺点与之前的七牛一样，需要实名认证~
![upyun.jpg][17]

### 图床上传工具 ###
#### PicGo ####
上面说了那么多图床，当然得有一个图床上传工具才可以让我们愉快切慵懒的使用图床，这里我仅推荐一款图床工具：[PicGo][18],这个工具非常的强大，开源，全平台（Mac/Windows/Linux），使用 Wiki 非常丰富，上手简单，相信你使用过一次之后就会被成功被圈粉！
[点击此处][20]在GitHub下载软件。
![PicGo][19]
#### 写在最后的话 ####
下图可以说明一切，如果你的站点面向国内，乖乖备案，买个阿里云或者腾讯云的储存空间用得了。
折腾的过程就是用时间换取金钱……
![](https://upload.cc/i1/2019/07/22/xNbiKg.gif)
> 如下几个是我没有使用过，但网络上经常有人推荐的图床，在此仅做留档，如果我使用，将会贴出~
	<http://pan.duiai.cc/>
	<http://www.xiangudu.com/>
	<https://yun.aoaoao.me/>

* Ps:本人亦不对如上推荐的图床做任何担保，请各位有一定的自我识别能力，未成年人请在监护人的陪同下浏览并使用!
* 参考链接：<https://sspai.com/post/40499>

[1]:https://zh.wikipedia.org/wiki/%E7%BD%91%E7%BB%9C%E7%9B%B8%E5%86%8C
[2]:https://i.loli.net/2019/07/21/5d33487e3163061733.jpg
[3]:https://i.loli.net/2019/07/21/5d334b61199ed71338.jpg
[4]:https://sm.ms/
[5]:https://www.v2ex.com/member/Showfom
[6]:https://imgur.com/
[7]:https://i.loli.net/2019/07/21/5d334dd553bac36556.jpg
[8]:https://imgchr.com/
[9]:https://i.loli.net/2019/07/21/5d335031c967868248.jpg
[10]:https://upload.cc/
[11]:https://i.loli.net/2019/07/21/5d3350a179d6e77979.jpg
[12]:https://mnmlsv.net/
[13]:https://i.loli.net/2019/07/21/5d335254e3fbc59066.jpg
[14]:https://www.qiniu.com/
[15]:https://i.loli.net/2019/07/21/5d3354713243d84720.jpg
[16]:https://www.upyun.com/
[17]:https://i.loli.net/2019/07/21/5d335523da32e53652.jpg
[18]:https://github.com/Molunerfinn/PicGo
[19]:https://i.loli.net/2019/07/21/5d33578a5772175424.gif
[20]:https://github.com/Molunerfinn/PicGo/releases 
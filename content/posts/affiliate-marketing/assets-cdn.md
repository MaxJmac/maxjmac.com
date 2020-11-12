---
title: "Media Buy之Landing Page的资源文件CDN部署方案"
date: 2020-11-12T12:00:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Media Buy之Landing Page的资源文件CDN部署方案"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/assets-cdn/assets-cdn-head.jpg"
featuredImagePreview: ""

toc: true
autoCollapseToc: true
math: false
lightgallery: true
linkToMarkdown: true
share:
  enable: true
comment: true
---

#### 前言
最早期的时候，我是跟随《40天》教程的方法，把资源文件(img/css/js)也放到CloudFront里面，第二个月CDN的费用扣了我60多刀，当时跑的Pop。切换到Push为主之后好多了，但是我也持续的在寻找其他的部署方案。

后来有人给我推荐了fast.io，结合GitHub使用，把资源文件统一放到fast.io，LP的加载速度提升了，CDN的费用也降低了。当时fast.io是每个月100GB的免费流量，十月份的时候收到官方的邮件要开始收费了。于是又继续寻找新的替代方案，了解到fast.io也是用的CloudFlare的CDN，于是往这方向上去寻找资料。

找到资料后我就开始配置部署，并且进行小范围测试，证实方案的可靠性，现在我正在使用的LP已全部迁移至新方案，已稳定运行一个月左右，感觉比fast.io更为稳定可控。(fast.io抽过一次风导致我的css文件无法访问，LP的CTR骤降)

#### 资源准备

##### [CloudFlare](https://www.cloudflare.com/)
我们主要使用它的CDN和DNS，我的个人博客[maxjmac.com](https://maxjmac.com/)也是使用它的CDN加速。

##### [Backblaze B2](https://www.backblaze.com/)
类似于AWS的S3，是一个云存储解决方案，我们主要使用它来存储资源文件(image/css/js/video/audio等)。

##### 域名一个
用于添加站点到CloudFlare，解析到B2，二级域名也可以，但是必须把DNS托管到CloudFlare。

#### 原理解析
正常来说，云存储都是要支付带宽费用的，但是由于有[Bandwidth Alliance](https://www.cloudflare.com/bandwidth-alliance/)(带宽联盟)，我们从B2到CloudFlare的带宽费用是完全免费的，我们主要就是利用这一原理来实现这个部署方案。(低价，绝大多数时候是免费的)

#### 部署流程

##### Backblaze B2
首先创建一个Bucket，Bucket Unique Name填个唯一的就行，记得要选择Public

![](/images/create-bucket.png)

创建成功后先随便上传一张图片，然后进入Bucket，点开刚刚上传的图片，可以看到以下内容

![](/images/friendly-url.png)

把这个Friendly URL下的`f002.backblazeb2.com`部分记下来，后面会用到。

##### CloudFlare
用准备好的域名新建一个站点，进入站点后选择上方的`DNS`菜单，把域名的NAME SERVERS(名称服务器)切换成CloudFlare的，你的DNS就托管给CloudFlare了。

![](/images/nameservers1.png)

![](/images/nameservers2.png)

然后添加一个CNAME记录解析到上面记录的Friendly URL下，可以使用二级域名，我这里使用的是assets，如图

![](/images/dns.png)

上方切换到`SSL/TLS`菜单，确保加密模式设置为完全，如图

![](/images/ssl.png)

上方切换到`页面规则`菜单，按顺序添加两个页面规则，注意按顺序（即优先级），如图

![](/images/page-rule.png)

这里假设你的域名是`example.com`，你的Bucket Name是`mybucket`，规则1里面的URL就是`https://assets.example.com/file/mybucket/*`，规则2里面的URL就是`https://assets.example.com/file/*/*`，我这里转发重定向用到的URL是`https://secure.backblaze.com/404notfound`，这样别人试图通过你的域名访问其他仓库的时候，就会提示404。

最后一项配置，选择上方的`缓存`菜单，点击配置，往下滚动找到`浏览器缓存 TTL`，把时间修改为`1年`。

至此，配置部分就完成了。

#### 高效使用
你可以直接在Backblaze B2的后台直接上传文件，但是那样做的效率并不高，所以我借助的是一个叫[Cyberduck](https://cyberduck.io/download/)的软件。

首先到Backblaze B2的后台菜单App Keys下新建一个Application Key，如图

![](/images/appkey1.png)

给这个key起个名，可以叫Cyberduck说明是给这个软件用的key，选择你创建的Bucket，类型保持默认的Read and Write。创建成功后会出现下图，只会出现一次，所以记得把applicationKey复制下来。

![](/images/appkey2.png)

打开你下载的Cyberduck，新建一个连接，如图

![](/images/cyberduck.png)

选择Backblaze B2 Cloud Storage，然后填入上方的keyID和applicationKey后点击Connect即可连接上，可以看到你之前随便上传的那张图片。现在你可以方便的在这个应用上创建文件夹，批量上传文件了。

![](/images/cyberduck2.png)

这时你这个文件的访问路径就由原来的`https://f002.backblazeb2.com/file/mybucket/create-bucket.png`(不带CDN加速)变成了`https://assets.example.com/file/mybucket/create-bucket.png`(带CloudFlare CDN加速)。

#### 部署效果
话不多说，上个[GTmetrix](https://gtmetrix.com/)测速效果图，双A稳稳的。
![](/images/speedtest.png)

#### 总结
Landing Page的访问速度很重要，甚至可以说是转化的关键因素之一，必须重视。目前我使用了这个方案一个月左右，运行稳定，已将所有LP迁移至此方案。这个可作为fast.io收费后的免费解决方案。

#### 广告时间
我建立了一个知识星球，在这里分享一些我找到的公开资源和我的一些经验，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。
![](/images/contact.jpg)
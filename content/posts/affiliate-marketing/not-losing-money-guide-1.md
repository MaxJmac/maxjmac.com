---
title: "Affiliate Marketing之Media Buy不亏钱指南(中篇)"
date: 2020-12-21T17:30:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Affiliate Marketing之Media Buy不亏钱指南(中篇)"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/not-losing-money-guide-1/not-losing-money-1-head.jpg"
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

本文将以Traffic Company的`126899 - MX-Telcel-Bromance`这个offer举例。

## 创建流程

##### 1.联盟设置postback

![traffic-company-0](/images/not-losing-money-guide-1/traffic-company-0.png)

点击`Edit postback Settings`进入设置，选择Kintura，点击保存即可。

##### 2.获取Offer信息

首先我们来到Traffic Company的后台，上方的菜单选择`Promotions`-->`Offer wall`进入以下页面

![traffic-company-1](/images/not-losing-money-guide-1/traffic-company-1.png)

注意看右上角这个开关，建议关闭。在下方的输入框中输入Offer的id进行搜索，然后点击结果进入Offer页面。

![traffic-company-2](/images/not-losing-money-guide-1/traffic-company-2.png)

点击1处的`Show preview`，将图片先保存到桌面（后面会用到）。勾选2处，点击3处的按钮`Create link`获取offer链接。

![traffic-company-3](/images/not-losing-money-guide-1/traffic-company-3.png)

##### 3.新建Affiliate Network

接下来，我们到追踪器Kintura的页面，先新建Affiliate Network

![kintura-1](/images/not-losing-money-guide-1/kintura-1.png)

在红框处输入Traffic Company并选择，滚动到最下方点击保存即可。

##### 4.新建Offer

![kintura-2](/images/not-losing-money-guide-1/kintura-2.png)

填入Offer名称，按自己习惯命名即可，选择联盟，粘贴链接，如果链接中没有{cid}，点击上图中的红框部分，Kintura会自动帮你把链接补全，点击最下方保存即可。

##### 5.新建Traffic Sources

![kintura-3](/images/not-losing-money-guide-1/kintura-3.jpg)

在红框TEMPLATE处输入`Advertizer`并选择，即按模板创建，然后勾选下方的`Send Traffic Source Postback`。这里先保持默认，一会需要回来改，先到最下方点击保存即可。

##### 6.在追踪器新建Campaign

从上至下依次填入Campaign的`NAME`即名称，`TRACKING DOMAIN`和`COUNTRY`保持默认，TRAFFIC SOURCE选择刚才创建的Advertizer，`ROUTING MODE`保持默认，`COST MODEL`选择CPA，即按转化付费，填入价格，这里一开始建议使用Offer Payout的80%-90%，后面会说具体原因。这里填入0.3的90%，0.27，然后点击`Create Campaign`。

创建成功后上方会出现两个Tab，切换到`ROUTING`点击右侧下方的`+`按钮添加一个Route，如图：

![kintura-4](/images/not-losing-money-guide-1/kintura-4.png)

填入NAME后选择`Route directly to Offer(s)`，也就是直链，无需Landing Page。`FORCE OFFER REDIRECT MODE`选择`302`，点击Next后出现下方的Offer选择，选择刚才创建的Offer，点击`Save`即可。

上方的菜单切换到`LINKS & CODE`，点击`Copy Campaign URL`复制下来，后面会用到。

##### 7.设置流量源postback

首先我们到Advertizer获取5处的Postback URL，粘贴到第5步新建Traffic Sources处提到的`POSTBACK URL`替换，并保存。

![advertizer](/images/not-losing-money-guide-1/advertizer.png)

然后点击第2步，在3处粘贴我们刚刚准备的`Campaign URL`，把cost参数修改为具体数值。点击Create Test，就会出现4处的链接，点击链接后回到追踪器。点击Home菜单下的`Event Log`找到你刚才点击的事件，类似这种

![kintura-5](/images/not-losing-money-guide-1/kintura-5.png)

将最左边的`CLICK ID`复制下来，然后使用步骤1里面的链接，模拟一次转化，即把链接`http://track.kintura.io/conversion?cid=al305omEm1GI0JuA3gKc&txid=&payout=0.02`复制到浏览器访问，得到以下结果即可。

![postback](/images/not-losing-money-guide-1/postback.jpg)

##### 8.在Advertizer新建Campaign

在上方菜单的`Campaigns`-->`My Campaigns`页面中点击`+ Add Campaign`。

从上至下，`Name`填入Campaign的名称，`Campaign URL`即步骤6中最后提到的`Campaign URL`，`Preview Image`选择步骤2中保存好的Offer预览图，`Flow/Vertical`这里因为`#126899`这个offer是1click的，所以选择`Carrier Billing`，`Country`选择MX，`Bid`填入之前拟定的0.27，`Quality`强烈建议选择`Best Quality`，`Category`选择`Mainstream`，`Type`选择`Mobile`，`Connection`选择`Cellular`，`Carriers`选择我们Offer要求的`Telcel`，滚动到最下方保存即可。


至此，完整的创建流程已经演示完毕，接下来等待审核即可。

## 小结

限于篇幅，今天的内容暂时先到这里。下篇我会讲到如何选择Offer，如何根据流量源的数据挑选geo，还有一些进阶的方法和Tips。

欢迎联系我的个人微信`MaxJmac`交流

## 广告时间
我建立了一个知识星球，在这里分享一些我找到的公开资源和我的一些经验，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。
![](/images/contact.jpg)
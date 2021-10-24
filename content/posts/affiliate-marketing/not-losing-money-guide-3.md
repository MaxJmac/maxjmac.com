---
title: "Affiliate Marketing之Media Buy不亏钱指南(补充)"
date: 2021-03-25T22:48:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Kintura无法注册问题的替代方案，上中下篇的遗漏内容补充，常见问题解答以及成果展示。"
license: ""

tags: ["Affiliate-Marketing","Media-Buy","不亏钱指南"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/not-losing-money-guide-3/not-losing-money-3-head.jpg"
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

> 居然还有补充篇？没想到吧.jpg

主要是因为有不少小伙伴反映Kintura无法注册问题，还有一些上中下篇里面遗漏的点和后面想到的一些内容。

## Kintura的问题和替代方案

### Kintura的问题

不少小伙伴看了上中下篇后操作时遇到Kintura注册不下来的问题。下文我会用一个较好的替代方案来重新做个设置教程。

Kintura前阵子到现在问题(bug)挺多，时常出现postback失败、重定向无效问题。**现已不建议继续注册使用Kintura**。可能是太多免费用户涌入导致难以为继吧，在国外论坛上看到Kintura的付费用户也抱怨时常出现的问题而退款。我现在也已经完全迁移至其他Tracker。

### 替代方案

建议使用[BeMob](https://bemob.com/?ref=blyad78skl)作为替代Tracker。

BeMob的好处是每月有10万次免费事件，超出才会收费。在对比了市面上大部分的追踪器之后，我最终建议选择最为新手友好且高性价比的云追踪BeMob。

注册时如果希望以PayPal作为订阅的付费方式，可以联系在线支持开通。

官网: [https://bemob.com/?ref=blyad78skl](https://bemob.com/?ref=blyad78skl)



## BeMob设置流程

### 1.联盟postback设置

首先在BeMob中找到属于你的Domain，右上角Settings-->Domians，在最下方的Tracking Domains中可以看到有两个二级域名，如果你自己有域名建议添加你自己的域名，以避免别人的不当行为导致共享域名被标红从而影响你的Campaign。将标有Main的域名复制，如图所示

![domain](/images/not-losing-money-guide-3/tracking-domain.png)

在Traffic Company(联盟)的后台，在菜单中找到Account选项，在选项下的二级Tab postback中点击下方`Edit postback settings`按钮进入设置，选择BeMob，然后粘贴你上面复制的Main域名，然后点击保存即可。设置完如图所示

![postback-settings-0](/images/not-losing-money-guide-3/postback-settings-0.png)

你也可以选择Custom设置，如图所示

![postback-settings-1](/images/not-losing-money-guide-3/postback-settings-1.png)

设置完效果是一样的。

### 2. BeMob添加Affiliate Network

在BeMob后台的Home Tab下找到`Affiliate Networks`，点击`+ New`按钮右侧的箭头，选择`New From Template`，在弹出的框中输入`Traffic`即可看到Traffic Company，选中后点击右下角的`Next`按钮，在新的弹窗中直接点击右下角的`Save`按钮即可。

![add-network](/images/not-losing-money-guide-3/add-network.png)

### 3.获取Offer信息

![offer-information](/images/not-losing-money-guide-3/offer-information.png)

点击1处的`Show preview`，先把图片保存到本地，后面会用到。勾选2处，点击3处的`Create link`按钮，在弹出的窗口中复制Promotion URL。

### 4.BeMob添加Offer

![new-offer-0](/images/not-losing-money-guide-3/new-offer.png)

在Home Tab下找到Offers，点击下方的`+ New`按钮，在弹出的窗口中依次填入Name，Affiliate Network选择Traffic Company，把步骤3里面复制的Promotion URL粘贴到URL窗口中，注意最后的部分是`&click_id={clickid}`，下方的+{clickid}是灰色的状态则设置正确，点击右下角`Save`按钮保存即可。如下图所示

![create-offer](/images/not-losing-money-guide-3/create-offer.png)

### 5.新建流量源Advertizer

登录Advertizer后台，在上方的菜单栏中找到`Account`-->`My Account`，在中间找到`Postback URL`复制包含`&advertiser_id=`的后半部分。

在Home Tab下找到`Traffic Sources`，点击`+ New`按钮右侧的箭头选择`New From Template`，如图所示

![add-trafficsource](/images/not-losing-money-guide-3/add-trafficsource.png)

在弹出窗口中输入`Advertizer`，选中后点击`Next`，在新的弹出窗口中，将Postback URL内的`&advertiser_id=REPLACE&key=REPLACE`替换成你在Advertizer后台复制的内容，如图所示

![trafficsource-template](/images/not-losing-money-guide-3/trafficsource-template.png)

其他部分不做修改，点击右下角的`Save`按钮保存即可。

### 6.BeMob新建Campaign

在Home Tab下找到Campaigns，点击`+ New`按钮，如图所示

![new-campaign](/images/not-losing-money-guide-3/new-campaign.png)

在弹出窗口中，依次填入Name，Traffic source选择前面创建的Advertizer，下方Cost Model选择CPA，CPA cost根据offer的payout的80%-90%，这里的例子中payout是0.37，所以我这里使用较为激进的90%大约0.33。Destination选择Built-InFlow，关闭#Landings即跑直链，点击右下角的`+ Add offer` 按钮，选择前面创建的Offer，设置完如下图所示

![tracker-campaign](/images/not-losing-money-guide-3/tracker-campaign.png)

最后点击右下角的`Save`按钮保存即可。

保存成功后在弹出的窗口中复制Campaign URL一栏的内容，下一步会用到。

### 7.流量源设置postback

![cpa-conversion-test](/images/not-losing-money-guide-3/cpa-conversion-test.png)

点击1处的Start Conversion Test，将上一步复制的Campaign URL粘贴到2处，点击3处的Create Test按钮，然后点击4处的链接进行访问。

然后回到BeMob中，双击Home Tab下的Campaigns中你的Campaign，进入Report。

![live-visits](/images/not-losing-money-guide-3/live-visits.png)

然后在Live Visits下找到Click ID，这就是你刚才访问产生的Click ID，复制出来，加入到你第1步里面设置的postback URL里面，举个例子`https://maxjmac.bemobtrcks.com/postback?cid=Dmaxjmacmaxjmacmaxjmacq&payout=0.33`，注意你的二级域名和域名替换成你自己的，cid后面的值为上图复制出来的Click ID，payout后的值必须为一个具体值，我这里设置为0.33。然后将这个链接放到浏览器窗口回车访问一次，即模拟一次转化postback。出来的页面是一个标题为postback(1x1)的黑色页面即成功。

接下来刷新Home Tab下的Campaigns页面，看到Conversion一栏有数字1即为成功，再去Advertizer看看，Conversion Test已经成功，可以创建CPA Campaign了。

![postback-success](/images/not-losing-money-guide-3/postback-success.png)

### 8.在Advertizer创建Campaign

在上方菜单的`Campaigns`–>`My Campaigns`页面中点击`+ Add Campaign`。

从上至下，`Name`填入Campaign的名称，`Campaign URL`即步骤6中最后提到的`Campaign URL`，`Preview Image`选择步骤3中保存好的Offer预览图，`Flow/Vertical`这里因为`#128441`这个offer是PIN的，所以选择`Carrier Billing`，`Country`选择MX，`Bid`填入之前拟定的0.33，`Quality`强烈建议选择`Best Quality`，`Category`选择`Mainstream`，`Type`选择`Mobile`，`Connection`选择`Cellular`，`Carriers`选择我们Offer要求的`Telcel`，滚动到最下方保存即可。

至此流程结束，等待审核即可。



## 遗漏内容

下面讲讲根据小伙伴的实操反馈，结合上中下篇的内容发现的一些遗漏的地方。

### 上篇

有小伙伴表示注册Advertizer几次被拒，这里要注意注册Advertizer时填写的Offer Tpyes要选择In-house Offers和Direct Offers，Conversion Types则选择CPL，因为Advertizer当然是希望直接广告主来投放offer而不是我们，这样offer才更有竞争力。有的还会要求你在细节里面说明你的offer payout之类的，你就找几个offer举个例子，比如这样`ID/0.6$ MX/0.25$`。

### 下篇

提交Campaign时被拒绝，说Landing Page无法访问的话，一般再提一次即可，审核玄学，还是被拒的话就去问问联盟AM一切是否正常。



## Q & A

- 遇到System Pause怎么办？

  不必理会，停了就停了，继续建你的Campaign就行，挂了的又不会回来，让系统自动删除或你自己手动删除掉都可以。

- Offer下线了怎么办？

  为了避免流量浪费，我一般会找相似的offer换到Tracker里面去，实在没有再pause，然后原因选Temporary Pause，如果Offer回来了再开启，回不来了就让它自动删除。

- 每天都跑到没有Cap怎么办？

  去找其他相似offer顶上，实在没有的话就不用管放着。当然这可能导致你的Outage，但是当你没法根据cap的恢复时间来恢复的话，不管就是了。

- 如何移除CPA Trail?

  当你达到300$以上的花费并且当时的Score在90%以上时，联系右下角的在线支持，询问是否可以移除Trail，可以他就会给你移除，不行你就等过一两天再问，注意每次询问时你的Score必须在90%以上才有意义，否则他会说你的Performance不足而拒绝你。

## 成果展示

话不多说直接晒图：

![case-0](/images/not-losing-money-guide-3/case-0.png)

![case-1](/images/not-losing-money-guide-3/case-1.png)

这都是单天能跑出来的流水和收益，而且还有成长空间。

2021-07-14更新:

![case-2](/images/not-losing-money-guide-3/case-2.png)

创新高了

2021-07-15更新:

![case-3](/images/not-losing-money-guide-3/case-3.png)

又创新高了

## 总结

跑的好的小伙伴已经不是不亏钱了，已经开始赚钱了。早点把CPA Trail变成CPA，后面就是轻松工作就能带来收益。所以前期要懂得让利，尽快把CPA Trail变成CPA。

以上。


## 广告时间
我建立了一个知识星球，在这里分享一些我找到的公开资源和我的一些经验，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。
![](/images/contact.jpg)

## 关联阅读

[不亏钱指南(上篇)](https://maxjmac.com/affiliate-marketing/not-losing-money-guide-0/)
[不亏钱指南(中篇)](https://maxjmac.com/affiliate-marketing/not-losing-money-guide-1/)
[不亏钱指南(下篇)](https://maxjmac.com/affiliate-marketing/not-losing-money-guide-2/)
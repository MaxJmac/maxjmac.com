---
title: "Affiliate Marketing之Media Buy不亏钱指南(下篇)"
date: 2021-01-06T20:30:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Affiliate Marketing之Media Buy不亏钱指南(下篇)"
license: ""

tags: ["Affiliate-Marketing","Media-Buy","不亏钱指南"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/not-losing-money-guide-2/not-losing-money-2-head.jpeg"
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

> 本篇内容主要包括，如何选择Offer，如何根据流量源的数据挑选geo，还有一些进阶的方法和Tips。

## 跑前调研

### 如何挑选geo - Advertizer流量源端

因为我们这个玩法的核心是Advertizer这个流量源，所以在跑之前，我们首先要了解这个流量源，它在哪些geo的流量多，然后再根据流量去找相应的offer。

我们登录到Advertizer的后台，上方菜单选择`Tools->Insights`，`Time Frame`保持Past 24 hours不动，然后点右侧的`Run Report`就可以看到每个geo的数据。

![advertizer-insights](/images/not-losing-money-guide-2/advertizer-insights.png)

`Volume`就是过去24小时的流量，`CVR`是平均的转化率，`Competition`是竞争度，进度条越满表示竞争越大，`Trial Cost`指的是，你每提交一个该geo的Campaign，需要支付的手续费(0.5-2.5刀)，一般越热门的geo，这个手续费就越高。

我选择geo的标准一般是，过去24小时的`Volume`至少是100,000以上，或者不会低太多，然后Competition中等偏下比较好。现在Advertizer新的账号一开始无法创建一些热门geo比如ID/IN/US这些，所以剩下的选择其实不多。

### 如何挑选Offer - Traffic Company联盟端

#### 联盟AM推荐Offer

其实挑选Offer，我的首选是找联盟的AM推荐，Traffic Company的AM Hendrik是我遇到过那么多联盟里面最热情而且最有帮助的AM，一般我都会直接告诉他，我会用Advertizer跑，让他推荐一些适合这个流量源的Offer。

#### Opportunities

除此之外，就是自己去Opportunities里面找，登录到Traffic Company的后台，上方菜单`Promotions -> Opportunities`然后切换到`DIRECT OFFERS`。但是需要注意的是，这里面有坑，放在这里的并不代表就一定好跑，这里教大家如何避这个坑。

点进Offer去，有些Offer有设置Cap，也就是每天能跑的量，这个Cap是总和来的，当然你也要结合时区来看，也就是那个Timezone，Timezone的零点是会刷新这个Cap的。也就是说，你可以在这里看出，有没有别人也在跑这个Offer，如果都没人跑，但它却出现在Opportunities里面，只能说明联盟在推这个offer，仅此而已。

#### Monetizer联盟

注册链接：[https://www.monetizer.com/?pid=14945](https://www.monetizer.com/?pid=14945)

现在Monetizer不太好注册，经常会卡在联系他们那一步，你可以尝试在Advertizer右下角在线支持联系他们，问他们能否给你开立一个Monetizer的帐户。

这个是Advertizer的联盟端，你在Advertizer放出去的Offer，就会出现在Monetizer里面给别的Affiliate跑。其他人(广告主/联盟/Affiliate)放在Advertizer的，也一样出现在这里。

登录Monetizer的后台，点击左侧`Smartlink Offers`菜单，Country选择你想要查看的geo，然后点击`Filter Offers`就可以看到其他人(广告主/联盟/Affiliate)在跑的Offer，你可以看到他们的CR，Revenue，bid，EPC等等数据，需要注意的是，这里的bid，是Advertizer抽成20%之后的结果，也就是说，如果你在Advertizer设置bid 1，你在这里看到自己的Offer的payout就是0.8，所以我们可以反推他们的bid。

所以我们也可以通过Preview去Traffic Company或其他联盟找找有没有一样的Offer来跑。

## 进阶

#### Advertizer的原理

按转化付费，那这个系统怎么运转？总不能一直让我们白得流量对吧。我们了解一下Advertizer的运转原理会有助于我们理解怎么去优化和使用这个流量源。

当你的账户还是CPA Trial的时候，你每提交一个Campaign，就会扣除相应的Trial Cost，而且你的bid，Advertizer会抽成20%再给到Monetizer，也就是每个转化，他们抽20%的佣金，这就是他们的盈利模式。

除了Trial Cost以外，他们还有一个CPA Score，也就是质量分系统，如果你的这个CPA Score一直很低，就有可能被Advertizer限制每周可创建的Campaign数量（一开始是5个），最后甚至被取消创建CPA Campaign的功能。

#### 如何获得较高的CPA Score？

首先一个好的Offer很重要，什么Offer适合Advertizer的流量呢？1click/2click/PIN/SMS这种转化流程简单的Offer是最合适的。

然后就是要让利给跑Offer的人，也就是bid高一些，来获取更高的eCPM/EPC，这也是`CPA Score的根本`。一般bid你offer payout的80%-90%最佳。如果你的单Campaign Score高，可以相应调低，Score低则可以相应调高。否则你跑不了多久就遭遇`System Pause`，Trial Cost就白给了，得不偿失。

最后就是优化了。你可以在跑了一些数据之后，在Tracker的Campaign的Drill Down里面看到partner这一数据。这个partner就是在跑你Offer的Affiliate，如果他送的流量一直不转化，或者转化低，或者bot比例很高。你可以在Advertizer的Campaign里面，在`Partner ID Blacklist`这一项里面把他blacklist掉，这里就是不让他继续送量，避免降低你的eCPM/EPC，从而造成CPA Score太低。尽量保持你的CPA Score在90%以上。

## Tips

1.一开始一周只有5次创建Campaign的机会，每周日UTC0点刷新，不要一次性把次数全用完，留一些到周二周三。原因是其他Affiliate都集中在周日刷新时创建，流量竞争激烈，我们避开这种竞争，等到周二周三的时候，他们很多都被Pause了，我们再上。

2.不要让你的流量源余额低于20$，余额过低的时候系统会暂停掉你的Campaign，进而影响你的Uptime，也就是你Offer的在线时间，最终就是影响你的CPA Score。

3.有时候AM极力推荐给你的Offer跑没多久被System Pause，不一定是AM忽悠你，可能只是你提交的时间段不凑巧。同一个Offer，不同时间通过审核开始送量，得到的结果可能完全不一样。总之还是要自行测试。

4.挑选Offer不一定要高Payout的，大多数时候1click低Payou的offer会给你带来更好的效果。

## 总结

Tips暂时只想到这么多，后面有想到其他的再添加到我博客原文文章后面。

更多的信息，你可以在Advertizer后台上方菜单的`Academy`里面学习。

欢迎联系我的个人微信`MaxJmac`交流

## 广告时间
我建立了一个知识星球，在这里分享一些我找到的公开资源和我的一些经验，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。
![](/images/contact.jpg)

## 关联阅读

[不亏钱指南(上篇)](https://maxjmac.com/affiliate-marketing/not-losing-money-guide-0/)
[不亏钱指南(中篇)](https://maxjmac.com/affiliate-marketing/not-losing-money-guide-1/)
[不亏钱指南(补充)](https://maxjmac.com/affiliate-marketing/not-losing-money-guide-3/)
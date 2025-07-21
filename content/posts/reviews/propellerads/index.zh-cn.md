---
title: "PropellerAds实战指南"
date: 2025-07-21T17:50:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "分享6位数美金投放经验，涵盖Pop、Push、Telegram Ads等格式。从postback设置到CPA Goal优化，详解流量采购策略与ROI提升技巧。"
license: ""

tags: ["Affiliate-Marketing","Media-Buy","Reviews"]
categories: ["reviews"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/propellerads/hero.png"
featuredImagePreview: ""

toc: true
autoCollapseToc: true
math: false
lightgallery: true
share:
  enable: true
comment:
  enable: true
---

PropellerAds是我在Media buy生涯中接触最早的流量源之一，也是我至今仍在使用的主要平台。几年下来，这个平台见证了我从摸索阶段到现在的成长历程。

刚统计了一下我在PropellerAds的总投放金额，已经达到6位数美金，这个数字让我觉得有必要分享一些实战经验。毕竟，在这个行业里，用真金白银换来的经验往往比纯理论更有价值。

今天就介绍一下PropellerAds这个平台，希望能为正在寻找稳定流量源的小伙伴提供一些参考。

注册链接：[https://go.maxjmac.com/propellerads](https://go.maxjmac.com/propellerads)

## 界面介绍

左侧菜单中自上而下，最常用到的是Statistics（看数据的），Traffic Chart（跑前分析流量的），Audiences（做retargeting的），Tracking（设置回传的），Add Funds（充钱的）。

Statistics就是你建好的campaign都会在这里显示，跑起来后可以在这里看数据。

![traffic-chart](/images/propellerads/traffic-chart.png)

Traffic Chart这里显示的是流量源所拥有的流量，可以查看这几个广告格式在特定筛选条件下大概有多少流量，这里的数据都是根据前一天实际数据来显示的。

有Traffic Chart非常重要，在开始跑之前，我们需要挑选offer，有的offer会有一些特定要求，比如只要某个geo的某些运营商的流量，其他的一概不要。我们就可以通过Traffic Chart来查看我们要跑的广告格式，在这个geo的特定条件下，流量总量有多少，比如你要跑一个offer，需要Android流量，通过Traffic Chart发现这个geo每天只有1000次展现，那就没必要测试了。

Audiences和Tracking我会在稍后的实战中讲到。

## 实战操作指南

接下来我就通过实际建立campaign的过程中，讲解遇到的各个设置的含义以及建议。

### postback设置

在我们开始建立campaign之前，我们需要先设置好postback，这样我们才能清楚地知道是哪些流量，哪些广告位产生了转化，才能更方便地进行优化。

![tracking](/images/propellerads/tracking.png)

我这里以MaxConv这个追踪器为例，因为MaxConv并不在上图所列的模板里，所以选择最后一个Other tracker or CPA Network，选择后就会出现如下图内容：

![tracking-2](/images/propellerads/tracking-2.png)

点击2.里面的**Copy this S2S Postback URL**就可以复制Postback URL。

到MaxConv的Traffic Sources菜单中创建一个PropellerAds的模板，可以看到如下图：

![tracker-trafficsource-1](/images/propellerads/tracker-trafficsource-1.png)

我们把复制好的Postback URL粘贴到Send conversions to traffic source下方的输入框中，`http://ad.propellerads.com/conversion.php?aid=123456&pid=&tid=12345&visitor_id=${SUBID}&payout=${PAYOUT}`这里的aid和tid是你账号唯一的，我们要做的是把`${SUBID}`替换成`{external_id}`，把`${PAYOUT}`替换成`{payout}`，最终链接就是

`http://ad.propellerads.com/conversion.php?aid=123456&pid=&tid=12345&visitor_id={external_id}&payout={payout}`这样的，最后点击下方的Save保存即可。

这样当联盟的offer发生转化时，转化就能通过追踪postback给PropellerAds了。

### 创建Campaign

我们点击上方的Create campaign进入campaign的创建过程，如下图：

![create-campaign-1](/images/propellerads/create-campaign-1.png)

PropellerAds提供了5种大类的广告格式，分别是Onclick(Popunder and Direct Click), Push Notification, Survey Exit, Telegram Ads, Interstitial。这5种大类里面又分几个小类，比如Onclick里面有Popunder/Direct Click/Social Traffic三个小类，Push Notifications里面有Classic Push和In-Page Push两个小类，所以实际上是有8种广告格式。当你选择格式时，右侧的说明里面有描述该格式适合的vertical有哪些供你参考。

我们在这里将以最简单的Popunder为例，介绍各项设置的含义和作用，其他广告格式的设置都是大同小异。

#### Pricing Model

往下滚动后如下图：

![create-campaign-2](/images/propellerads/create-campaign-2.png)

Pricing Model是我们的出价模式，对于Popunder来说，建议用CPA Goal或者SmartCPM，选中后下方的蓝色方框中有该出价的特点说明。

CPA Goal是我们设置一个转化目标，PropellerAds会以这个目标自动优化，尽可能地帮你达成这个目标，比如offer的payout是$1，你可以设置个$0.8（官方建议设置为payout的70%-80%），PropellerAds的算法会尽可能地帮你优化到每次转化只需花$0.8，这样每次转化你将获得$0.2的利润。

SmartCPM是我们设置一个我们可以接受的最高的CPM出价，PropellerAds会将实际出价控制在这个值以内来为你尽可能地获取流量。

Multiformat Campaign是帮助你用相同的设置快速建一个Interstitial这个广告格式的campaign，这里不建议启用，关掉那个开关即可。

Target URL就是放我们投放的最终URL，这里通常是我们追踪器中生成的Campaign URL。

Traffic Sources下的Exclusive Inventory是PropellerAds平台自有的流量，质量高适合用来测试。Partner Traffic则是包含其他合作方的流量，质量不可控只适合用来扩量使用。下方的Include Anti-AdBlock是指包含被广告拦截器拦截的流量，测试阶段建议取消勾选。

#### GEO/Budget

继续往下滚动如下图：

![create-campaign-3](/images/propellerads/create-campaign-3.png)

Countries是选择你需要购买哪个或哪些国家/地区的流量，CPA Goal则是你的具体出价，如果上方选择的是SmartCPM这里就是设置一个你可以接受的最高CPM。

Cities是可以target到具体城市，States是州/省份。

Advertising Budget是设置预算的地方，Daily是每日预算，Total是这个Campaign的总预算。

#### Targeting

继续往下滚动，如下图：

![create-campaign-4](/images/propellerads/create-campaign-4.png)

Platform可以选择我们投放的平台，分别是Desktop和Mobile，即桌面和手机等移动设备。根据offer的实际需求去选择即可，通常建议Desktop和Mobile分开campaign进行投放。

OS是指操作系统，如果你选择Desktop，会有Windows/MacOS/Linux等选项，如果选择Mobile就会有iOS/Android等选项。选择具体操作系统后还可以选择具体的OS Version。

Graphics cards是指显卡，除非特殊需求，否则都是默认为All即可。

Device是当你选择类似iOS时，可以选择投放iPhone/iPad。

Browser是指浏览器，通常有Chrome/FireFox/Opera/Webview等选项。

Browser language是指浏览器语言，可以Target具体的浏览器语言比如中文/英文/俄语/法语等。

Connection Type里的3G/LTE指的是手机流量，选择后可以在下方的Mobile ISP中具体Target到运营商，WI-FI/Broadband指的是Wi-Fi或宽带流量，无法具体Target到运营商。

Proxy指的是代理流量，通常情况下我们都不想要代理流量，只要真实用户的流量，默认选择No proxy即可。

Zone limitation是广告位限制，这里的Include是指可以只要某些广告位的流量，即我们通常所说的白名单，Exclude是指排除某些广告位的流量，即我们通常所说的黑名单。

Audiences是指受众，我们可以在跑广告的过程中收集相关受众，比如那些已经转化了的受众，我们可以Exclude掉他们，那么广告就不会重复展现给他们。

继续往下滚动，如下图所示：

![create-campaign-5](/images/propellerads/create-campaign-5.png)

Collect an audience for retargeting是设置收集受众的地方，在Audience name那里输入一个名称即可开始收集，收集到的受众可以在上方的Targeting中使用。

Campaign Schedule是投放时段的设置，可以设置只投放某些时段，默认是7x24小时。

最后Automatically的勾选是指当审核通过后自动开始campaign。

I declare是同意遵守PropellerAds的协议，不投放成人/过于激进的广告等。

当以上所有的设置都完成后，点击右下角的Start Campaign即完成Campaign的建立。

## Telegram Ads - 不可忽视的流量新蓝海

Telegram Ads是PropellerAds新推出的一种广告格式，也是我认为当前最值得关注的流量机会。可以在[https://propellerads.com/formats/telegram-mini-apps-ads/](https://propellerads.com/formats/telegram-mini-apps-ads/)这里看到关于这个格式的详细介绍。这个格式的出现，让我们有机会接触到Telegram Mini Apps生态系统中的高质量用户。

![telegram-ads](/images/propellerads/telegram-ads.png)

### 为什么Telegram Ads值得重视？

**用户参与度极高**。根据PropellerAds的测试数据，Telegram用户在这个格式上的CTR和CR比传统展示广告高出10-20倍。这个数据让我印象深刻，因为在我们这个行业，能有这样的表现提升是相当罕见的。

**流量质量出众**。Telegram Mini Apps的用户本身就是预热过的、有参与度的受众。这些用户在使用Mini Apps时已经处于一个互动状态，比如完成任务、玩游戏、或者进行TON blockchain相关的操作。这意味着他们的转化意愿天然就比较高。

**竞争环境相对宽松**。目前这个格式还在早期阶段，每日有1亿次展示量，但竞争还没有完全激烈起来。对于经验丰富的Media Buyer来说，这种窗口期往往是最有价值的。

### 实际操作体验

广告的展示形式和Push有些相似，包含Title、Description、图标和主图，还有一个CTA按钮。用户在使用Mini App时，广告会通过任务机制或奖励系统自然触发，这种展示方式比传统的中断式广告更加用户友好。

**Auto Creatives功能**特别值得一提。PropellerAds提供ML生成的自动创意，这对于想要快速测试或者缺乏创意资源的情况很有帮助。我尝试过几次，效果确实不错，如果你刚开始没有想到很好的创意，可以使用这一特性，它会根据你的Landing Page所代表的Vertical给你自动创建Creative，你可以在其创建完成后进行筛选。

以下是关于Telegram Ads的一些Case Study，可以在里面找找灵感:

[https://propellerads.com/blog/adv-telegram-ads-format-token-case-study/](https://propellerads.com/blog/adv-telegram-ads-format-token-case-study/)

[https://propellerads.com/blog/adv-igaming-telegram-mini-app-case/](https://propellerads.com/blog/adv-igaming-telegram-mini-app-case/)

[https://propellerads.com/blog/adv-telegram-ads-minimum-budget/](https://propellerads.com/blog/adv-telegram-ads-minimum-budget/)

[https://propellerads.com/blog/adv-telegram-ads-case-study/](https://propellerads.com/blog/adv-telegram-ads-case-study/)

## PropellerAds的优点

质量高。以我在这个平台的投放经验来说，我也尝试过其他的一些流量源，在pop和push这一块没有找到质量比PropellerAds高的平台，别看其他平台的CPM/CPC比较低，很多都是刷子刷出来的流量，毫无意义。

服务支持好。他们的在线支持响应速度很快。对于新手来说，遇到问题能快速得到解决很重要。

平台功能丰富。除了基础的Pop和Push，他们新推出的Social/Survey Exit/Telegram Ads等，都是非常值得测试的广告格式。

## 我的建议

### 1.尝试新特性

当时Survey Exit刚出来的时候，我把当时在Push表现不错的Campaign复刻到了Survey Exit，表现非常好。现在Survey Exit在PropellerAds已经不算是新格式了，但是他们推出了另外的新格式，Onclick的Social和Telegram Ads，非常值得测试。

Auto creatives刚出来的时候，我也是去建了个新Campaign跑跑看，效果好得出乎我的预料，比我原有的Campaign表现还要好，而且大大降低了我的工作量。

所以我的建议是多去尝试平台的新格式，新特性，尝试去做第一个吃螃蟹的人，即使失败了损失的也只是一点点预算，但如果成功了你收获的可能就是一片竞争很小的蓝海。

### 2.耐心

在PropellerAds的所有出价模式中，有CPA Goal/SmartCPC/SmartCPM/CPC/CPM，我只推荐前三种，我最推荐的是CPA Goal，在这种出价模式下，是需要一点耐心的，至少是24-48小时的耐心。因为我们需要等待算法进行自动优化，在这种模式下我们只需要优化好Pre Lander和Offer的组合，剩下的交给算法，交给时间就行。

### 3.思路清晰

在测试的过程中，我们要始终保持思路清晰，要明确每次测试的目标是想弄清楚什么内容。不要频繁地去改动Campaign造成数据混乱，每次改动都要记录改动的时间和内容，做到有迹可循，这样当我们回看数据表现时就能知道是改动了什么导致的表现变化。

### 4.边做边学

在Media buy这个领域我始终建议边做边学，只有在实战中才能更好地发现问题，解决问题，从而获得进步。很多人都说想要系统性地学习一下Media buy，但这个领域就没有系统性一说，都是边学边做，边做边学，通过实践获得相关的知识，通过复盘获得经验。

## 总结

PropellerAds作为一个成熟的流量平台，在我多年的使用过程中证明了其价值。从最初的Pop流量到现在的Telegram Ads，平台一直在不断创新和优化。在我测试过的众多流量源中，PropellerAds在反欺诈和流量过滤方面做得相当出色，这直接影响到我们的ROI表现，毕竟劣质流量是最大的预算杀手。如果你已经在其他平台有一定经验，建议重点关注PropellerAds的新兴格式，特别是Telegram Ads和Social这两个广告格式。这些格式目前竞争相对较小，是很好的机会。

以上。

今年8月PropellerAds团队将参加China Joy大会。如需预约会面，请联系Natalya Gudimova：

📱 微信: larakoralla

💬 Telegram: @natalia_propeller



## 专属Promo Code

通过我的专属链接 [https://go.maxjmac.com/propellerads](https://go.maxjmac.com/propellerads) 注册，可使用优惠码`MAXJMAC`充值满$150赠送$30。

仅新用户有效，仅限前20名新用户。
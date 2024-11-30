---
title: "浅谈Media Buy中的追踪器工作原理"
date: 2024-11-30T20:24:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "其实追踪本身并不复杂，我们首先要清晰地知道流量流向时是**流量源>>追踪>>联盟**，以及postback时是**流量源<<追踪<<联盟**，先掌握最基础的用法跑通整个流程，再逐渐进阶到会使用自定义event的postback。"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/how-tracker-work-in-media-buy/hero.jpg"
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

### 为什么追踪器很重要

因为我们是Performance Marketer，没有追踪我们就无法知道哪个创意，哪个Landing Page，哪个offer，甚至于什么系统/浏览器/运营商等等表现更佳。没有追踪我们就相当于在盲投，无法根据数据进行优化，从而导致浪费很多不必要的预算。

### 为什么写这个内容

前阵子有个affiliate找到我，跟我说：

![conversation](/images/how-tracker-work-in-media-buy/conversation.png)

确实这个对于很多新手affiliate包括我刚入门时，这部分是很迷惑的，我当时的做法是先照着做，做多了再去理解原理，我的确也是这么过来的。

现在我已经可以很好地理解追踪的工作原理，无论换什么追踪器，联盟，流量源，我都可以快速的配置相关参数以及postback，所以希望可以借这一篇文章，把我的经验和理解分享给大家，让新手affiliate可以更快地理解这部分内容。

### 流量是如何流动的

首先我们要理解的第一个点就是，流量是如何流动的。如下图所示：

![traffic-direction](/images/how-tracker-work-in-media-buy/traffic-direction.png)

正向：用户通过流量源进入，转入到我们的追踪，追踪根据配置显示用户路径，有Landing Page则进入Landing Page，最后通过Click URL进入联盟的offer页面。

反向(postback)：如果用户产生转化，联盟通过postback告诉追踪，追踪再通过postback告诉流量源。

清晰地知道流量是如何流动的，当出现问题的时候，你就知道是哪个环节有问题，进而找到解决的方法。比如追踪收不到转化，那就是联盟那边配置的postback不正确。如果追踪能收到转化，但是流量源收不到，那就是追踪这边流量源的postback设置不正确导致的。

### 参数的含义

#### clickid

追踪的核心就是围绕这个clickid建立的，我们其实可以把clickid理解为一个用户。

用户从流量源进来，流量源赋予他一个id（我们暂时把它叫做externalid），并把它传递到追踪器，进入到追踪器后，追踪器也会赋予他一个id（我们暂时把它叫做clickid），并把这两个id一一对应，再把追踪器赋予的id也就是clickid通过offer链接的参数传递到联盟。

如果这个clickid发生了转化，联盟就把这个clickid通过postback告诉追踪器，用户转化了。追踪器再把这个clickid对应的externalid找出来，通过postback告诉流量源，这个externalid代表的用户转化了。

这样就形成了一个完整的流量流向闭环。

#### payout

payout指的是你的offer转化后，你将获得多少佣金。通常是在联盟postback到追踪器时使用，以便于你在追踪器统计收入和支出。

#### postback中用到的参数

postback主要就是用到clickid和payout这两个参数。其他的类似于transactionid(或者简写成txid)这种只是对于Upsell类型的offer会用到，还有就是自定义event，例如SignUp,FTD,AddToCart等等。postback基本最多也就用到这四个参数了，其他的postback意义不大，tracker那边都能通过clickid看得到。

#### Parameter和Placeholder

![parameter-placeholder](/images/how-tracker-work-in-media-buy/parameter-placeholder.png)

上图左侧是MaxConv中PropellerAds的模板，右侧是Binom中PropellerAds的模板。

其中Parameter指的就是参数名称，Placeholder我们可以理解为萝卜坑。参数名称可以随意命名，自己看得懂就行，不懂就直接按模板的来就是了，只要保持在流量源使用的，和在追踪器中配置的一样就行。

比如MaxConv中叫src_clid的，在Binom中叫visitor_id，叫什么不重要，它后面的萝卜坑Placeholder是**${SUBID}**就行，这样PropellerAds就能把实际的值替换掉**${SUBID}**，传递给追踪器。

### 例子

接下来我以PropellerAds作为流量源，MaxConv作为追踪器，GiddyUp作为联盟，模拟一个完整的投放过程。注意这里并不是建议用PropellerAds跑GiddyUp，仅仅是因为PropellerAds是大家熟知的流量源，而GiddyUp有丰富的电商自定义事件用于举例。

#### 1.MaxConv中新增GiddyUp联盟

![maxconv-giddyup](/images/how-tracker-work-in-media-buy/maxconv-giddyup.png)

这里值得注意的是我是直接使用MaxConv的模板创建，可以看到左侧Offer URL Suffix部分，模板中GiddyUp使用sub2作为参数接收来自追踪器MaxConv的clickid。我们需要将其修改为sub4，因为他们实际上用的是sub4，这个需要和AM沟通确认。

下方Accept Duplicate Conversions记得勾选，因为电商中会用到多个事件postback，例如AddToCart,AddPaymentInfo,InitiateCheckout等等。

右侧上方的内容只是方便你生成下方的链接用的，下方选择好Domain即可。因为联盟的postback是从联盟发起的，所以这里的作用只是展示，右侧部分不设置都是可以。

将最终的postback链接复制，下一步会用到。

#### 2.GiddyUp后台配置postback

在GiddyUp后台找到postback配置的地方，新增一个postback，如下图所示：

![giddyup-postback-event](/images/how-tracker-work-in-media-buy/giddyup-postback-event.png)

我们这里先配置一个事件postback，**Postback Type**选择Event，**Postback Level**选择Specific就是指定为某一个offer设置postback，**Event**选择Add To Cart，**Delivery Method**选择Postback，**Postback URL**这里原链接从MaxConv复制过来是这样的：

`https://maxjmac.com/conv?clid={sub4}&payout={payout_amount}&txid={OPTIONAL}&currency={OPTIONAL}&event={OPTIONAL}`

其中{OPTIONAL}部分都是可选的，意思就是可传可不传，我们这里把&txid={OPTIONAL}修改为&txid={transaction_id}，移除掉&currency={OPTIONAL}部分因为用不到，&event={OPTIONAL}修改为&event=AddToCart，这里的AddToCart你随便命名，叫A2C也行，就是最终你在追踪器那边会看到的事件名称。

注意上图中蓝色虚线框表示这个placeholder是联盟支持的意思。最后点击下方的Add按钮添加。

同样的方式配置Conversion，如下图所示：

![giddyup-postback-conversion](/images/how-tracker-work-in-media-buy/giddyup-postback-conversion.png)

区别是**Postback Type**选择Conversion，最后的**Postback URL**中的event为Paid，这里的&event=Paid部分也可以不要，那样追踪最后显示event部分就是一个“-”。

#### 3.MaxConv中新增Offer

注意URL的最后部分要拼接上Offer URL suffix，如下图：

![maxconv-offer](/images/how-tracker-work-in-media-buy/maxconv-offer.png)

如果没有其他参数，则以**?**开头加上sub4={mc_click_id}，如果已经有其他参数则以**&**开头拼接在URL的最后面。

#### 4.MaxConv中新增PropellerAds

在MaxConv中按模板新建一个PropellerAds流量源，进入PropellerAds后台的左侧Tracking菜单中，选择**Other tracker or CPA network**，如下图：

![propellerads-tracking](/images/how-tracker-work-in-media-buy/propellerads-tracking.png)

点击步骤2中的**Copy this S2S Postback URL**复制，回到MaxConv的PropellerAds流量源配置中，将URL粘贴到**Traffic source postback URL**下方的输入框中，删去**&payout=${PAYOUT}**部分，并将**${SUBID}**修改成下方Tokens中的第一个**{external_id}**，最后点击Save保存即可。如下图所示：

![maxconv-propellerads](/images/how-tracker-work-in-media-buy/maxconv-propellerads.png)

#### 5.新增测试Campaign

在MaxConv中新建一个Campaign，名称随便起，Traffic Source选择PropellerAds，点击右下角的Next进入Destinations设置，关闭掉Landers，Offers选择上面创建的Offer，点击Save保存进入到Tracking。

#### 6.测试结果

获取Tracking中的Campaign URL，粘贴到浏览器中打开，在offer页面手动触发Add To Cart事件后，你可以在MaxConv的Conversions中看到如下图的自定义事件postback：

![maxconv-conversion](/images/how-tracker-work-in-media-buy/maxconv-conversion.png)

### 总结

其实追踪本身并不复杂，我们首先要清晰地知道流量流向时是**流量源>>追踪>>联盟**，以及postback时是**流量源<<追踪<<联盟**，先掌握最基础的用法跑通整个流程，再逐渐进阶到会使用自定义event的postback。

这时你就基本掌握如何使用追踪了，换不同的流量源，不同的追踪器，不同的联盟，都是可以很快配置好的。

不懂先去照着做，再去慢慢理解。

以上！
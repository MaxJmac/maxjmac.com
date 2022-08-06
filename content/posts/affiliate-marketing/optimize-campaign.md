---
title: "Affiliate Marketing之Media Buy入门实战(八)如何优化Campaign"
date: 2020-05-22T18:40:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Affiliate Marketing之Media Buy入门实战(八)如何优化Campaign"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/optimize-campaign/optimize-campaign-head.jpg"
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

> 过早的优化是万恶之源，而太晚优化会浪费你的预算。

#### 新秀墙

相信很多新手都会遇到和我一样的一个问题，做了一系列准备之后开始信心满满充满幻想的跑Campaign，现实却泼了一盆冷水，看着预算在燃烧，心拔凉拔凉的。于是就想着赶紧停掉，是不是这个Offer不行，是不是这个Landing Page不行，上来就亏钱。

其实这是正常现象，大多数Campaign刚开始的时候都是亏钱的，当然偶尔会走狗屎运遇到上来就赚钱的（这种几率并不大，我只遇到一次）。所以这也是为什么推荐选Payout低的Offer开始的原因，Payout低的Offer通常意味着更容易转化，用户需要付出的金钱或操作比较少，我们可以用较低的预算来换取更多的数据，来进行下一步的优化。对于新手来说，掌握这种优化的方法是非常重要的，这将决定你能否在这个行业长久地生存下去。

#### 优化方法

其实优化的方法无非就是拉黑白名单，把表现不好的因素拉入黑名单，表现好的因素，列入白名单，然后新开一个Campaign，用白名单里面的因素组合来跑。但是时间上也有讲究，什么时候可以把这个因素拉入黑名单或者白名单，什么时候开始跑白名单Campaign。

与此同时，不同的流量源，优化的方法也是不一样的，因为placement在不同的流量源叫法不一样，比如在PropellerAds里面叫zoneid，在Zeropark叫target和source。但是大体上的思路，都是一样的，就是暂停掉转化低，ROI不高的各种因素，收集转化高，ROI高的各种因素，诸如placement（广告位）、OS（系统）、Operator（运营商）等等。

看似简单，但是也不能上来就把转化了的因素视为白名单，因为只转化1个的话有可能只是撞大运了，也不能上来就把转化不好的因素视为黑名单，因为有可能不是这个因素的问题，而是很多其他因素组合的结果。所以我们要有一套优化的方法论，来清晰地指导我们进行优化，而不是像无头苍蝇一样一顿操作猛如虎，一看战绩零杠五。

#### A/B Test

在介绍优化的时间点之前，先说一个新手很容易犯的一个错误，就是瞎测。举个例子，在我们跑push的时候要设置Creative（图标和文案），我之前就是，上来就整3套不同的图标和文案组合，然后跑一定数据之后对表现不好的Creative停掉，看似正确，但是忽略了一个问题，我怎么知道这个表现不好的Creative是文案不行还是图标不行？所以在我们测试之前，我们应该固定其中一个因素，比如一样的文案，3个不同的图标，就能测出哪个图标表现最好，然后再用这个图标，测试3个不同的文案，才能找到文案和图标的最佳组合。

#### 方法论/时间轴

##### 1.数据收集阶段

在这个阶段，我们一般用3组Creative，3组Landing Page，不宜过多，越多需要的预算越高，时间也越长，跑24到48个小时，或者3到10倍的Payout，这个阶段我们的主要目的是看offer能不能转化，找出表现最好的一组Creative和Landing Page，找出3-6个表现好的Placement（转化2次以上，1次的先保留）。如果没有转化或者Revenue很低，砍掉这个offer。

##### 2.狙击阶段

这里我们用阶段1里面找到的3-6个placement，结合表现最好的一组Creative和Landing Page跑48个小时，越久越好。如果你用的Zeropark，停掉那些1-2倍payout只有1个（可保留到下个阶段）或以下conversion的target，不要停source。如果你用的PropellerAds，他们只有一个placement因素就是zoneid，所以直接跑满48小时再说。这个阶段的目的是为了找出那些表现好的时段、设备、系统版本、浏览器、语言、运营商等。

##### 3.再测试阶段

在这个阶段，我们已经获得了一些表现好的诸如时段、设备、系统版本等因素，我们用这些组合去流量源新开一个Campaign，然后Target这些因素，把阶段1里面的少量转化，但是ROI为负的placement加进来重新测试，跑48小时。这时我们就能获取一批表现好的placement，作为placement的白名单来跑。

##### 4.黑白名单并行

在这个阶段，除placement外表现好的组合我们基本上都有了，就用这个组合来分别创建两个Campaign，一个是不限制placement（黑名单Campaign），一个只放表现好的placement（白名单Campaign）。一般情况这个白名单Campaign上来就是盈利的状态的，黑名单Campaign可以禁用掉那些白名单Campaign里面的placement，这时黑名单Campaign的目的是为了收集更多表现好的placement并把他们放进白名单，同时禁用那些表现不好的placement以防浪费过多的预算。

##### 5.SplitTest

新建一个和白名单一样的Campaign，SplitTest更多的Creative和Landing Page，各找出3组以上能稳定盈利的，此举的目的是为了防止用户审美疲劳（见到太多一样的广告失去兴趣），从而挖掘更多的转化。

#### 结语

其实Media Buy的过程就是测试测试再测试，通过测试找到可盈利的组合。以上只是一个常见的优化方法论，不一定完全正确，你也不必完全照着做，因为不同Payout的offer测试的预算和时间这些都不一样，你可以用这个方法作为指导，结合自己的实践经验总结出一套适用于自己跑Media Buy的方法论。

如果你对以上内容有任何疑问，或者有其他入门方面想了解的内容，欢迎留言反馈告诉我。

至此入门实战篇告一段落，后续将分享更多我在Media Buy旅途上遇到的问题和不时闪现的想法。

与此同时我建立了一个知识星球，在这里分享一些我找到的公开资源，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。
![知识星球](/images/optimize-campaign/zsxq.jpg)
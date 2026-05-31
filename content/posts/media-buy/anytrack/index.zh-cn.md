---
title: "跑Google或FB更适合的追踪器Anytrack"
date: 2026-05-31T23:30:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "分享一次因追踪器被 DDoS 导致流量空跑的真实经历，以及为什么我现在跑 Google 和 FB 都用 Anytrack 这种 Non-Redirect 类型的追踪器——即使追踪挂了，流量也能正常到达 Offer 页面。"
license: ""

tags: ["Media-Buy"]
categories: ["media-buy"]
slug: "media-buy"
hiddenFromHomePage: false

featuredImage: "/images/anytrack/hero.png"
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

> 我一直觉得，我是很幸运的。

记得去年从 ChinaJoy 回来之后，准备测试一个对于我来说是新的方向 Listicle，当时 Landing 和追踪都折腾测试了挺久，在确保一切都没问题之后，信心满满地我就上广告上线了。广告过审开始跑着了，因为是前期测试阶段，我没有放很多的预算，大概每天$200，刚开始一切正常，很快就有了第一个转化，第二天甚至有了盈利的一天。第三天几乎持平，在测试阶段这都是可以接受的范围，然而到了第四天，数据突然变得很差，LP CTR也很异常，于是我就开始了排查工作。

因为落地页加了分享页面，所以我希望是做成那种即使用户不是用的 Campaign URL 打开，仍然能追踪到的效果，这在当前市场主流的追踪器比如 Voluum, RedTrack 等都是使用的放一个 js 到落地页的方案，为此我还折腾了很久才实现页面自动加载默认 Campaign ID 的方式来达到效果。但是，那天我打开落地页却发现，Click Url没有自动替换成实际的 Offer URL，也就是说，我推广的流量最终没能跳到我的 Offer 页面，而是停留在了 click/n 这样的空白页面！怪不得 LP CTR 那么差，关键还是时灵时不灵那种搞得我找了很久的原因。最后发现是追踪器给的那个 js 文件无法正常加载导致的，吓得我马上把 campaign 暂停了。

隔天这家追踪器发了个邮件，大概意思是`We want to sincerely apologize for the downtime you may have experienced on xxxx day. A DDoS attack hit our systems and caused a service outage.`我想有的小伙伴可能知道我说的是哪家，后来赔了我几十刀到余额里。

万幸的是我当时还在测试阶段，幸亏还没有到每天花很大预算的时候，现在想想都还后怕。（这也是为什么我说我一直觉得，我是很幸运的。）

然后我就开始物色新的追踪解决方案了，其实我当时已经在使用的就有一家叫 [Anytrack](https://go.maxjmac.com/anytrack) 的，我主要是用它来跑Google的，后来想想它其实完美适配我想要的这种即使用户不是用 Campaign URL 打开，也能正确访问到我的 Offer 页面并被准确地追踪到的效果。

直到现在，我跑 Google 还是在用这个追踪，我认为这种类型的追踪最适合跑 Google 和 FB 这种价格比较贵的流量类型。因为至少它不会犯错，不会因为追踪的问题，用户就到不了你的 Offer 页面而导致你有实质性的流量费用损失。

### 追踪的类型

这里解释一下 [Anytrack](https://go.maxjmac.com/anytrack) 是什么类型。

通常来说市面上主流的追踪像 Voluum, RedTrack 这些叫 Redirect 类型的追踪器，它们需要用户通过 Campaign URL 进行访问，才能正确地跳转到你的 Funnel 中，在你的落地页内通过 Click URL 才能跳转到你的 Offer 页面。但是当用户没有通过 Campaign URL 打开你的落地页时，点击 CTA(Call To Action) 所跳转到的 Click URL 就是一个空白的页面，无法正确地跳转到 Offer 页面。

Anytrack 则属于 Non-Redirect 类型，就像跑 Google 这种不允许 Redirect 的流量源时，Redirect类型的追踪器是通过在你的落地页放一个 js 的形式去把你相应 Campaign Funnel 内的 Offer URL 获取到，然后用 js 去替换这个 Click URL来实现 Non-Redirect 的目的。但是一旦出现我遇到的那种 js 无法正确加载的时候，Click URL 就无法被正确地替换成你的 Offer 页面，就会造成你的流量花出去了，用户想跳转到你的 Offer 去转化去成交，但是点你的 CTA 打开的是一个空白的 Click URL 页面。本该是你的转化，就这么丢了，而且时灵时不灵的情况下还难以诊断原因。

### 为什么选择Anytrack

因为它天生就是做 Non-Redirect 的，它的特性是，你在追踪系统内集成你的联盟软件，比如我们跑电商常用的 Everflow，然后把 Anytrack 集成到你的落地页之后，你就可以直接在你的落地页把你的 Offer URL 放到 CTA 的位置，就可以了。是的，就可以了！即使万一追踪挂了，你的流量仍然能通过你的落地页正确地跳转到 Offer URL，因为 CTA 上面放的就是 Offer URL。这样即使我们丢失了一些追踪数据，也不至于造成流量空跑的情况出现。

### Anytrack支持哪些联盟和流量源

基本上主流的联盟软件都支持，如下图：

![support-networks](/images/anytrack/support-networks.png)

流量源支持 Google/FB/Tiktok/Bing/Taboola/Outbrain，还有GA4，如果不是这些流量源，则需要自行对接 Webhook 来做回传了。

### Tips

如果你的联盟通过使用一些 Direct Link 来减少跳转，我们可以通过使用`&sub5=--CLICK-ID--`的形式拼接到参数的最后，把 click id 带到联盟那边即可，这里的sub5只是我常用的 Everflow 的示例。

### 总结

跑Google或FB这种比较贵的流量，每日消耗比较大时，我非常建议使用 Anytrack 这类型的追踪，避免惨痛教训。

如果你觉得本文对你有帮助并且考虑试用一下 Anytrack，可以通过我的链接注册 Anytrack，链接如下：

[https://go.maxjmac.com/anytrack](https://go.maxjmac.com/anytrack)

以上！
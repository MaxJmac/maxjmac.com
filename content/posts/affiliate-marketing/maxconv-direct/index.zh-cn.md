---
title: "MaxConv无重定向跳转指南"
date: 2024-11-26T20:52:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "如何使用MaxConv来实现无重定向跳转"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/maxconv-direct/hero.jpg"
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

> 最近忙着给Binom官方做v2中文文档翻译，现在给MaxConv也写个指南吧。

> 打两个广告：
>
> 1.通过我的链接注册Binom可享受首月免费，次月四折的优惠，四折是全网最低了，你用其他流量源或联盟的链接次月最低只能六折（黑五都没这个低！）。链接如下：
>
> https://binom.org/signup?from=MAXJMAC60
>
> 或者可以直接使用优惠码: **MAXJMAC60**
>
> 2.最近MaxConv搞黑五活动，持续到12月10号，年付非常划算！链接如下：
>
> [https://maxconv.com/?utm_source=PhugoySy&utm_medium=refprog](https://maxconv.com/?utm_source=PhugoySy&utm_medium=refprog)

之前写过一篇[《Binom无重定向跳转指南》](https://maxjmac.com/affiliate-marketing/binom-no-redirect/)，其实对于云追踪来说，无重定向跳转更为方便，只需要添加一段js到你的Landing Page即可轻松实现，至于你的Landing Page放在哪里，不重要。

### 操作步骤

#### 1.获取Lander Tracking Script

![create-lander](/images/maxconv-direct/create-lander.png)

在MaxConv的后台，前往Landers >> Create，如上图所示，在弹出的窗口中，找到Lander Tracking Script这个部分，点击左上角的Copy复制代码，如下图所示：

![lander-tracking-script](/images/maxconv-direct/lander-tracking-script.png)

注意：记得选择好上方的Tracking Domain，接下来Landing Page也要使用域名相符的Click URL。

#### 2.将代码放入Landing Page

将复制的代码粘贴到你Landing Page的`</head>`标签前面即可，代码大概长这样：

![html-code](/images/maxconv-direct/html-code.png)

注意你的Click URL所使用的域名要跟代码里显示的域名一致。

回到创建Lander那里填入Landing Page的名称和地址创建好Lander。

![edit-lander](/images/maxconv-direct/edit-lander.png)

#### 3.创建Campaign

前往Campaigns >> Create创建一个新的campaign，如下图所示：

![create-campaign](/images/maxconv-direct/create-campaign.png)

在弹出的窗口中，输入Campaign Name（名称），选择Traffic Source（流量源），最重要的是下方的`Transition from Ads to Campaign`选择`Direct`，如下图所示：

![create-campaign-basic](/images/maxconv-direct/create-campaign-basic.png)

随后点击右下角的Next按钮进入下一步设置。

在Destinations部分的Default Transition to Offer选择`Direct`，下方的Transition to Offer也选择`Direct`，如下图红框中所示，至于为啥那么多地方要选Direct，我也不理解，总之都选上就不会错。

随后选择配置了Lander Tracking Script代码的Lander，以及所需的Offer即可完成Path的配置。点击右下角的Save按钮保存Campaign即可。

![create-campaign-destinations](/images/maxconv-direct/create-campaign-destinations.png)

保存后会自动跳转到Tracking Tab，在下图红框的下拉框中选择配置了Lander Tracking Script代码的Lander后，就会出现相应的Campaign URL，注意这个Campaign URL实际就是Lander的链接，只是后面配置了相应流量源的Token。这个就是我们要投放的链接了。

![campaign-tracking](/images/maxconv-direct/campaign-tracking.png)

#### 4.访问测试

将Campaign URL复制，直接到浏览器打开，点击相应的按钮后可以跳转到最终offer页面。

![campaign-test](/images/maxconv-direct/campaign-test.png)

### 总结

MaxConv的无重定向跳转配置更为简单快捷，只要一段js代码即可。

以上！
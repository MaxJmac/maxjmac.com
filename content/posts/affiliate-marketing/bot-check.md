---
title: "Affiliate Marketing之Media Buy入门实战(六)Bot检测"
date: 2020-03-21T23:15:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Affiliate Marketing之Media Buy入门实战(六)Bot检测"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/bot-check/bot-check-head.webp"
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

> 有人的地方就有江湖，有江湖就有恩怨，人就是恩怨，你怎么退出？

#### Bot是什么？

Bot又叫机器人，又叫刷子。这么来理解，就是我们买流量的时候，是从流量源买的，而流量源又是从站长那里买的，而有些站长为了多创造些利益，就会用刷子去刷一些广告，多收一些广告费。而这个广告费谁出？我们这些买流量的Affiliate。这些Bot刷走的广告费，也是我们盈利的阻碍之一，所以我们要想办法把它们检测出来，尽可能地排除掉它们。

#### 怎么检测Bot？

这是《40天》这本教程里面缺失的部分，里面都是链到STM论坛，而我们没有加入这个论坛的话就没办法访问到了。Bot检测需要配合追踪器来实现，我用的是JustATracker，再次推荐一下这个追踪器，自带检测Bot的脚本，你都不需要自己写代码了，复制粘贴就行，附注册地址[JustATracker](https://dash.justatracker.com/#/595/Signup)。

其实JustATracker的博客里面介绍过怎么检测Bot，文章地址是[《Bot分析之LP View》](https://blog.justatracker.com/lp-view/)。大家可以和本篇文章对照着看去操作就行了。

#### 实操步骤

##### 1.新建Campaign

首先我们进入JustATracker后台，进入左侧的Campaign List菜单点击`+ New`按钮新建一个Campaign，填上Campaign Name，Traffic Source，滚动到Rotator这里，左侧Landings先点击红色的垃圾桶图标删除，右侧选择你的Offer，点击右上角的`Create Campaign`。

##### 2.粘贴Bot检测代码

创建完成后会自动进入Edit Campaign的状态，滚动到最下方找到Landing Page这部分，点击展开它。你会看到`LP Click Link`和`LP View`。LP Click Link是你要替换到Landing Page里面的跳转链接，LP View就是检测Bot的脚本，你只需要点击右边的复制按钮，然后将它粘贴到你的Landing Page的`</head>`标签前面即可，不需要做任何其他的改动。

![bot-check-code](/images/bot-check/bot-check-code.jpg)

对，就两步，代码部分就完成了。你把这个Landing Page放到主机上开始跑Campaign，JustATracker就能看到相关数据。

#### 如何通过数据分辨Bot

下面我以PropellerAds的流量源以及Mobidea的offer举例。当我们加好Bot检测代码的Landing Page相关的Campaign跑了一段时间之后，我们进入到JustATracker的后台，点击左侧Campaign List菜单，找到你跑的那个Campaign，点击Actions栏目下最右侧的按钮进入Analysis Report，在左侧的下拉按钮中选择zoneid，如图

![analysis-report](/images/bot-check/analysis-report.jpg)

收起后点击Refresh按钮，然后滚动到最下方可以看到这样的一些数据

![eliminable-data](/images/bot-check/eliminable-data.jpg)

这里的sub3就是zoneid（也叫placement），Clicks是指多少人点击了这个广告，Pop流量的话是只要弹出了就算一个click，LP views就是你的广告加载完成了，我们会发现LP views少于Clicks，这是因为有些用户发现弹窗了，还没等你广告加载完就把它关闭了，由此可见Landing Page加载速度的重要性。LP Clicks就是有多少用户通过你的链接跳转到目标offer，Lp CTR就是这个点击率。Conv.就是用户最终在offer页面转化了。

由此，我们可以判断的一些点是，如果Clicks数据很大而LP views很小，基本可以判断是bot，因为正常用户虽然会关掉一些，但不会关掉那么多，例如上图标红部分的zone id，我们就可以记录下来，一行一个保存到文本文档中。还有一些很多LP views，但是却很少Lp Clicks的也值得怀疑，即使它不是bot，它也是不好的placement（广告位置），同样记录下来。还有的Lp Clicks挺高的，但是却没有转化，同样的道理，即使它不是bot，我们也要干掉它。

#### 自动记录可疑bot

在JustATracker有个功能，在左侧Optimization菜单，展开后点击Rules，在这里我们可以设置一些规则，让追踪器自动帮我们记录那些zoneid，我们点击Add添加一条规则，例如我这里设置的Clicks大于100，LP views却等于0，我就自动记录下这个zoneid到黑名单。

![optimization-rules](/images/bot-check/optimization-rules.jpg)

保存之后会全局自动地记录可疑bot，跑一段时间后我们可以在Optimization菜单的Black List里面看到，Pub Name这一栏就是zone id。

#### 在流量源里排除Bot

记录完这些zoneid之后，并不是代表它们一定是bot，只是它们非常可疑，即使它们不是，它们的也是里面掺杂了非常多，或者说它们单纯的表现不好，我们都得把它们排除掉。

我们登录到PropellerAds的后台，进入Campaigns菜单并找到你正在跑的这个Campaign点进去，滚动到下方找到Zone limitation这里，点击Exclude（排除），然后把你找到的那些zone id粘贴进来，换行符或英文的`,`逗号隔开，保存Campaign，后面流量源就不会把这些zone id的流量发送给你了。

#### 结语

至此Bot检测以及排除工作就告一段落，当然，这个优化是持续进行的，因为流量源会买更多的placement，那些新的placement都有可能成为新的Bot。这也是黑名单跑法，就是把表现不好的placement加入黑名单。

这个Bot检测依赖追踪器来进行，其他的追踪器Bot检测的方式不一样，我也只用过两个追踪器，Voluum的Bot检测方法我用过没检测出Bot，也不知道是因为方法已经过时了还是因为我跑的运营商流量所以很少Bot。在这里还是再一次推荐新人用[JustATracker](https://dash.justatracker.com/#/595/Signup)这个追踪器。

这里套用JustATracker作者的一句话作为结尾。`永恒定律: 一切没转化、不赚钱的pub都当它是刷子！`
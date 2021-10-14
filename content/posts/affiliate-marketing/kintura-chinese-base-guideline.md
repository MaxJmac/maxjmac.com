---
title: "谁说没有免费的追踪器？！Kintura中文新手使用指南"
date: 2020-06-27T22:40:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Media Buy工具免费Tracker追踪器Kintura中文新手使用指南"
license: ""

tags: ["Affiliate-Marketing","Media-Buy","Tools"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/kintura-chinese-base-guideline/kintura-chinese-base-guideline-head.jpg"
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

#### 2021.10.14 Update:

由于Kintura目前有很多的bug，且技术团队似乎不愿意继续维护，已不建议使用。其他tracker推荐可见
[https://nav.maxjmac.com/](https://nav.maxjmac.com/)

#### Kintrua简介

AI追踪器。具有Machine Learning(机器学习)功能，可以根据每个访客的geo、时间、设备类型、连接类型、浏览器等因素，自动优化发送到Landing Page和Offer的流量。

注册链接: [https://kintura.com/partner/maxjmac](https://kintura.com/partner/maxjmac)

Kintura是一款运用了Machine Learning技术的追踪器，每个月有免费的100万事件，这对于一个新手来说是完全够用的，稍后我会介绍Kintura Machine Learning的强力之处。

#### Kintura优点

首先，免费！不同于市面上动不动一个月几十刀的追踪器，Kintura每个月有免费的100万事件，这对于一个新手来说是完全够用的，对于新手来说，每个月可以省下几十刀的费用来作为测试预算是十分诱人的。

其次，重定向速度快！重定向速度对于追踪器来说，是一个非常重要的指标，我们购买的流量通过追踪器最终跳转到offer页面的速度越快，用户感知度就越小，流量浪费就越少（用户较少因为页面加载速度慢而关闭offer页）。

最后，Machine Learning技术。这对于跑多个Landing Page和多个相似类型Offer的Campaign来说是非常有用的功能。

#### Machine Learning

这是Kintura这个Tracker（追踪器）最大的优势，也是目前其他Tracker所不具备能力。主要针对于多个Landing Page和多个Offer的Campaign，单个Landing Page和Offer是否开启这个功能没有区别。

Machine Learning的工作方式是，你的Campaign会经过一个Training的阶段，大概经过5-10个转化之后，它会进入一个SmartOffer阶段。需要注意的是这个阶段它仍然在Training，大多数时候这个阶段会把所有的流量都流到你其中一个offer当中，这时候你的Campaign可能会表现比较差，因为Kintura的Machine Learning把大多数流量发送到你表现最差的那个offer，而把少数流量发送到表现比较好的offer。你可能会在这个时候考虑把表现最差的offer给移除掉，但是请不要这么做！你会因此把Machine Learning搞得混乱，把Kintura给整懵了，有点像过早的优化。随着Campaign的继续运行，Machine Learning又会把流量平均分配到多个offer中，这时你的转化率和ROI都会随着提升。Kintura的官方报告说平均会提升30%-50%的ROI。

你可以在Drilldown的Distribution看到这个过程。

![](/images/kintura-chinese-base-guideline/distribution.png)

#### Kintura界面介绍

##### 主界面Dashboard

![](/images/kintura-chinese-base-guideline/dashboard.png)

1.功能区

分别是管理Campaign，Landing Page，Offer，Affiliate Network（联盟），Traffic Source（流量源），Route（路由）的菜单。

2.时间区间选择

用于选择需要查看数据的时间范围。今天，昨天，过去24小时，过去48小时，过去3天，过去7天，过去30天，这个月，上个月等。

3.报表数据展示选择

Visits显示有多少用户访问了Campaign url，L.Clicks(Landing Page Clicks)显示用户通过Landing Page跳转到Offer的数量，O.Direct(Offer Direct)，显示用户通过Campaign Url直接访问Offer的数量（跑直链时），Conversions即转化数。后面还有其他诸如Revenue（收入），Cost（支出），Profit(利润)，CPV（每次访问花费），CTR（点击通过率，指用户从Landing Page跳到Offer的比率），CR（转化率，转化数除以访问数），ROI（投资回报率），eCPA（每次转化赚取）。可以自行选择自己关心的数据展现在报表当中。

其他界面我就不重复做介绍了，我们直接进入实操过程，过程中可以看到其他界面的常见操作。

#### 实操过程

我们以[Traffic Company](http://www.trafficcompany.com/signup?p=9319)联盟，[PropellerAds](https://partners.propellerads.com/#/app/auth/signUp?ref_id=e2e1476509ed)流量源为例，介绍从联盟，流量源配置，Landing Page，Offer，Route设置，到建立Campaign，放到流量源的整个流程。

##### 1.联盟配置

我们从左侧菜单点击Affiliate Networks，然后点击右上角的New Affiliate Network新建一个，进入页面后再PRESET这里输入Traffic Company并选择模板，下面的内容会自动填充，然后在最下方点击Save即可。

![](/images/kintura-chinese-base-guideline/template-tc.png)

登录到Traffic Company后台，鼠标移动到右上角姓名的位置，在下拉菜单中选择Account，然后找到POSTBACK这个Tab，点击下方的Edit postback settings。Status选择Enable，开启postback，然后选择Kintura的图标，最下方选择货币单位，我一般用美元US Dollar。点Save，设置完如下图即可。

![](/images/kintura-chinese-base-guideline/tc-setting.png)

##### 流量源配置

在左侧菜单点击Traffic Source，然后右上角点击New Traffic Source，进入页面后再TEMPLATE这里输入PropellerAds并选择，就会出现如下模板，勾选Send Traffic Source Postback会出现一个输入框POSTBACK URL，我们留意到字段aid和tid后面是REPLACE，这是我们要替换的内容。

![](/images/kintura-chinese-base-guideline/template-propellerads.png)

我们到PropellerAds登录，在左侧点击Tracking菜单，选择Kintura，会出现如下的界面

![](/images/kintura-chinese-base-guideline/propellerads-postback.png)

点击右侧的按钮复制这个url，回到Kintura的Traffic Source页面，然后整个粘贴到Kintura的POSTBACK URL输入框中，这里建议删除`&payout={payout}`部分(因为PropellerAds有内部的Media Buy团队，你不会希望测到的好offer被他们发现然后跟他们竞争)。

继续滚动到下方，建议添加如下两个Token并在右侧勾选，方便我们后续使用这个流量源时Drilldown这两个参数进行分析，Banner是使用Push流量时的Creative id，UserActivity是用户质量。最后点击下方的Save保存即可。

![](/images/kintura-chinese-base-guideline/propellerads-params.png)

##### Offer设置

我们以Traffic Company的#122879这个Offer作为示例（仅作为方便举例，并不是推荐跑这个offer），因为这是一个WW即全球范围的Offer，我们以IN为例。首先我们到Kintura左侧菜单点击Offers，然后右上角点击New Offer，输入Offer名称，AFFILIATE NETWORK选择Traffic Company，然后到Traffic Company的后台进入到这个Offer的详情，勾选右侧的`I have read the promotion regulations`后点击下方Create link，把链接粘贴到Kintura页面的URL下，如图

![](/images/kintura-chinese-base-guideline/kintura-offer.png)

看到{cid}标签亮起就是正确的，点击最下方的Save保存即可。

##### Landing Page设置

在左侧菜单点击Landing Pages，点击右上角New Landing Page，输入NAME和URL保存即可，这里我们还没有上传Landing Page，只是先把路径设置好，后面要把追踪器的click url放到我们的Landing Page里面再进行上传。

![](/images/kintura-chinese-base-guideline/landingpage.png)

##### Route设置

在左侧菜单点击Routes，点击右上角New Route，输入NAME，选择302，如果是跑直链则勾选`Route directly to Offer(s)`，否则直接点击Next。

![](/images/kintura-chinese-base-guideline/route.png)

选择刚才设置好的Landing Page和Offer

![](/images/kintura-chinese-base-guideline/route2.png)

点击Save即可，如果你有多个Landing Page要Split test，则在右侧点击+按钮继续添加Landing Page，如果有多个相似类型相同产品的Offer，同意点击右侧+按钮继续添加Offer。举个例子，有3个Landing Page，5个Offer，流量从Campaign进来进入到Route，会在3个Landing Page随机分配一个，5个Offer随机分配一个，如果需要自行调配比例，则拖动上图100%位置的原点来手动分配流量，但是只有一个Landing Page或Offer的话，怎么拖都是100%。

##### 建立Campaign

在左侧菜单点击Campaigns，然后点击右上角的New Campaign。输入NAME，TRAFFIC SOURCE输入PropellerAds并选择之前配置好的流量源。

![](/images/kintura-chinese-base-guideline/campaign1.png)

右上角的Machine Learning如果是跑多个Landing Page或多个Offer的话，建议开启，如果只有一个Landing Page或Offer，开不开启效果都一样。

ROUTING MODE根据Route，Landing Page，Offer的数量进行选择。

All Sticky是默认使用第一个Route，第一个Landing Page，第一个Offer。

Rotate Routes是所有都进行Rotate。

Sticky Routes则使用第一个Route，然后Rotate Landing Page和Offer。

Rotate Offers是使用第一个Route，第一个Landing Page，只Rotate Offer。

Rotate Landing Page是使用第一个Route和第一个Offer，Rotate Landing Page。

鼠标放到后面的疑问号上都有具体的解释。

如果你只有一个Landing Page或Offer，默认All Sticky即可，多个Landing Page和Offer就选Rotate Routes或者Sticky Routes，我一般只用前两种模式。

COST MODE一般使用Auto。点击Create Campaign即可。

![](/images/kintura-chinese-base-guideline/campaign2.png)

点击后滚动到上方会发现多出两个Tab，ROUTING和LINK&CODE，我们切换到ROUTING Tab下，点击Default Routes右侧的+按钮，把我们前面配置好的Route添加进去。

![](/images/kintura-chinese-base-guideline/campaign3.png)

切换到LINK&CODE Tab下，点击Copy Offer URL，获取click url，这个链接是我们要放到Landing Page里的跳转链接，然后我们把Landing Page保存并上传到服务器刚才配置好的路径下。这个click url是不会变的，所以后面所有其他Landing Page都是同样的这个click url。

![](/images/kintura-chinese-base-guideline/campaign4.png)

最后点击Copy Campaign URL，这个是我们要放到流量源的最终链接。

##### 到PropellerAds建立Campaign

把url粘贴到Target URL的位置，PropellerAds的剩余内容就不再这里重复说了。

![](/images/kintura-chinese-base-guideline/propellerads-campaign.png)

#### 总结

Kintura是一款非常适合新手使用的追踪器，免费，重定向速度快，还有AI机器学习这个别的追踪器所不具备的特性，使用配置上清晰简单，Tracker该有的功能都有。本文仅仅介绍Kintura的基础使用，更深层次的使用需要自己去探索发现。

如果你对Kintura有任何疑问，欢迎留言与我交流。

我建立了一个知识星球，在这里分享一些我找到的公开资源，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。

![](/images/contact.jpg)
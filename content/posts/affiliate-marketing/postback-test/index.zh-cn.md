---
title: "如何做postback test"
date: 2023-02-17T18:30:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "Media buy新增Affiliate Network的时候如何做postback test"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/postback-test/postback-test-head.jpg"
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
每当我们新增一个Affiliate Network(联盟)作为合作方的时候，我们首先要做的就是postback test，确保我们的tracker(追踪器)能追踪到联盟的转化。

主流的联盟程序主要有CAKE,HasOffers,Everflow等，他们都有相同的规律，而有的联盟则是自己开发程序来追踪，所以我们需要与联盟的AM(Affiliate Manager)沟通，确认所使用的参数，然后设置postback url并进行测试。

下面我将以Binom为例(不同tracker会有差异但原理一致)解释各程序如何做postback test。

### CAKE

使用CAKE的有Advidi，Clickdealer等，如果你看到的界面是类似这样的(不同联盟会使用不同的配色Logo等):

![advidi](/images/postback-test/advidi.png)

那他们就是使用的CAKE，Clickdealer的底层也是使用的CAKE，但他们的界面是自己做的。

CAKE的惯例是clickid使用`#s2#`作为参数，payout使用`#price#`作为参数，所以我们在tracker里面添加使用CAKE的联盟时，格式都是这样的:

![affiliate-network](/images/postback-test/affiliate-network.png)

第一步，我们需要把Postback URL发给AM，由AM在联盟程序(CAKE)后台进行设置。

第二步，我们问AM要一个测试offer的地址，一般你把Postback URL发给他们了他们会主动给你

![test-offer-link](/images/postback-test/test-offer-link.png)

第三步，我们在Tracker新增一个这个联盟的TEST offer，如图所示

![test-offer](/images/postback-test/test-offer.png)

注意URL里面必须要有`s2={clickid}`，同时箭头位置的Click ID是亮起的状态，不同Tracker的clickid参数不一样，有的又叫click_id或cid。这是由Tracker传递给联盟程序(CAKE)的值，CAKE那边则会读取到s2参数，如果该点击产生了转化，CAKE则会将该s2的值连同转化的payout回传给Tracker，于是Tracker将该clickid标记为Conversion并将payout显示在报表中，这就是联盟和Tracker之间追踪的原理。

第四步，新增一个TEST campaign，如图所示

![test-campaign](/images/postback-test/test-campaign.png)

Traffic Source随便选择一个你已有的，没有就先去添加一个，这个不重要。Path的设置用Direct也就是直链(不用Landing Page)，然后添加TEST-Offer。保存后获得Campaign URL(例子中的`&email={email}`是我自定义流量源的参数，不重要，可选择移除参数部分，保留亦可)，将该URL发给AM。

![fire-postback](/images/postback-test/fire-postback.png)

检查你的Conversion Log或该Campaign的Statistics，看到该转化则所有步骤完成。

### HasOffers

![hasoffers](/images/postback-test/hasoffers.png)

类似于这种界面的则使用的是HasOffers的联盟程序。

HasOffers的惯例是clickid使用`{aff_click_id}`作为参数，但是也有联盟用`{aff_sub}`或`{aff_sub2}`，所以需要你去和AM进行确认，payout则使用`{payout}`作为参数，类似于CAKE的`#price#`。

所以我们在tracker里面添加使用HasOffers的联盟时，格式都是这样的:

![affiliate-network-2](/images/postback-test/affiliate-network-2.png)

注意标红位置的参数要一样，如果联盟用的`{aff_click_id}`，你的Offer URL template那里就要用`aff_click_id`。如果联盟用的`{aff_sub}`，则你的Offer URL template那里就要用`aff_sub`，以此类推。

其他步骤都是一样的，把Postback URL发给AM，AM给你个TEST offer地址，添加TEST offer到tracker，添加TEST Campaign，然后把Campaign URL发给AM，最后看结果。参考上面CAKE的内容，就不一一赘述了。

### Everflow

![everflow](/images/postback-test/everflow.png)

类似于这种界面的就是使用的是Everflow的联盟程序。

Everflow的惯例是clickid使用`{sub1}`或`{sub2}`或`{sub3}`作为参数，payout则使用`{payout_amount}`作为参数。所以我们在tracker里面添加使用Everflow的联盟时，格式都是这样的:

![affiliate-network-3](/images/postback-test/affiliate-network-3.png)

同HasOffers，如果联盟用的`{sub1}`，你的Offer URL template那里就要用`sub1`。如果联盟用的`{sub3}`，则你的Offer URL template那里就要用`sub3`，以此类推。其他步骤都一样，参考上面CAKE的内容。

### 其他联盟程序

![goldengoose](/images/postback-test/goldengoose.png)

![trafficcompany](/images/postback-test/trafficcompany.png)

类似于Golden Goose使用的`{p1}`和`{profit}`作为clickid和payout，TrafficCompany使用的`{click_id}`和`{reward}`作为clickid和payout。

## 总结

总的来说你需要跟联盟AM确认两个参数，一个是clickid，一个是payout，这样才能正确地设置你的postback，然后进行测试来确定数据能正常追踪到。

以上。

## 广告时间
我建立了一个知识星球，在这里分享一些我找到的公开资源和我的一些经验，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。
![](/images/contact.jpg)
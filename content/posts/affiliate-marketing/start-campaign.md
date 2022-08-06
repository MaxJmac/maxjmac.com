---
title: "Affiliate Marketing之Media Buy入门实战(三)开始Campaign"
date: 2020-03-08T19:29:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Affiliate Marketing之Media Buy入门实战(三)开始Campaign"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/start-campaign/money-campaign.jpg"
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

#### 追踪器是什么

追踪器是流量源和Offer的中间人，通过追踪器我们可以知道用户在哪个geo，用的什么浏览器，什么品牌的设备，浏览器语言是什么，还有在哪个广告位点进来的，这些都是我们Campaign数据优化的依据，因此十分重要。

关于追踪器，我们不讲太多的理论，直接实战。当然你后续还是需要理解关于追踪器的原理的，但是我选择不要在入门的时候就被这个枯燥的原理吓跑了。关于追踪器原理，你可以自行搜索相关资料阅读。

#### 追踪器选择

市面上流行的追踪器有Voluum、BeMob等。BeMob我没有使用过，就不做评价了。Voluum本身是个很优秀的追踪器，使用起来也还不错，但是价格过于昂贵，没有试用，售后服务也是惨不忍睹，霸王条款，我就被坑过，我现在是不建议新手使用Voluum。

弃用Voluum后我转向了国人开发的一款追踪器[JustATracker](https://dash.justatracker.com/#/595/Signup)，初次注册后有60万的免费事件，有效期7天，这对于一个新手入门来说够用了。最关键的是这个追踪器还能很便捷的帮你检测Bot。售后也无需多说，中文沟通起来太畅通了，强烈推荐使用！！！

#### 追踪器配置

我们通过这个[JustATracker](https://dash.justatracker.com/#/595/Signup)链接注册完追踪器后，接下来就进入到追踪器的配置，今天先讲简单版本的直链配置，其实Landing Page的配置也是类似的，只是多了一个环节，这个后面的章节再说。

##### 1.设置postback

在Mobidea左侧菜单栏的*AFFILIATE NETWORK*下找到Settings，切换到Global postback这个Tab下，选择Custom选项，并在Insert your domain的输入框中设置postback的地址。

我们可以在JustATracker的[文档](https://doc.justatracker.com/zh/GetStarted/postback.html)中找到这个地址:`http://postback.xyz/postback?clickid={clickid}&payout={price}` 然后把这里的`{clickid}`替换成Mobidea里面的Token`{{EXTERNAL_ID}}`，把`{price}`替换成`{{MONEY}}`就可以了，所以最终的链接变成`http://postback.xyz/postback?clickid={{EXTERNAL_ID}}&payout={{MONEY}}`，把它填入到Inser your domain下的输入框中，滚动到下方点击Save。

##### 2.添加Offer到Offer List

我们回到JustATracker，在左侧的Ads Config菜单中找到Offer List，点击Add，然后打开你在Mobidea申请好的Offer，把页面中的Offer名称复制到Name的输入框，把Tracking这个Tab下面的Offer link复制到Url的输入框，这里我们把这个链接中`?`后面的参数部分做一点修改，把`data1=Track1&data2=Track2&tag={External_ID_from_traffic_source}&website={subID}&placement={sub_subID}`替换成`tag={justatracker_clickid}&placement={justatracker_campaignid}`。其实这里就是把data1、data2、website三个参数去掉，把tag和placement替换成JustATracker的具体参数。

Affiliate Network选择Mobidea，JustATracker会为你自动生成postback。Payout填入你Offer的Payout，点击Save就可以了。

##### 3.添加Traffic Source

继续在左侧的Ads Config菜单中找到Traffic Sources，点击Add，在Copy from template这个下拉菜单中找到PropellerAds，选择后会自动填充内容，我们只需把postback1这个输入框中的`http://ad.propellerads.com/conversion.php?aid=UNIQUEID&pid=UNIQUEID&tid=UNIQUEID&visitor_id={t_cid}`替换成`http://ad.propellerads.com/conversion.php?aid=REPLACE&tid=REPLACE&visitor_id={t_cid}`即可，点击Save保存这个Traffic Source设置。

##### 4.添加Campaign

点击左侧的Campaign List，点击"+ New"按钮，Campaign Name设置为"联盟+流量源+GEO+流量说明运营商等内容自由发挥"，举个例子我们跑的是肯尼亚Kenya的运营商Safaricom的Offer，那么命名就是`Mobidea - PropellerAds - KE - Safaricom - XXXXXXX`，其实这个命名没有任何要求，就是方便你自己分辨Campaign。

接下来Traffic Source选择PropellerAds，就是上面我们添加好的。Country输入Kenya并选择Kenya(KE)。其他内容保持不变。

因为我们跑的是直链，所以在Rotator这里左侧的Landings点击红色的删除按钮，不使用Landing Page，右侧的Offers中选择上面添加好的Offer。最后点击右上角的Create Campaign即可成功创建Campaign了。

至此，追踪器这边的配置已经完成，但是我们暂时不要关闭页面，一会流量源那边创建Campaign还需要用到这里的一些信息。

#### 在PropellerAds创建Campaign

登录PropellerAds，我们点击上方的Create Campaign。在Campaign Name这个输入框里，我们把追踪器那边设置的Campaign Name复制过来粘贴。Choose Advertising Format这里选择Onclick (Popunder)也就是Pop流量。Pricing Model选择SmartCPM。Target URL这里把追踪器那边的Campaign Link复制过来粘贴，如果没有出错的话我们可以看到下方的一些标签亮起变成黄绿色。Frequency / Capping这里我们把3改成1，就是指每个用户每24个小时只能看到1次你的广告。

中间部分不做改动，往下看到"Countries & Bid"这里，Countries输入Kenya并选择Kenya。右侧的CPM我们先不填写，一会回来填。Advertising Budget (USD)这里是指当前Campaign的每日预算和总预算，都填入10，这时下方会出现提示，不必理会。Targeting这里的Platform选择Mobile，OS选择Android和iOS，这个根据你的Offer要求来填写。中间几项不填，Connection type这里选择3G/LTE，然后Mobile ISP这里就是选择运营商，这里填写Safaricom，这些内容都是根据你的Offer来填写，你可以在Offer详情页面的Targeting页面找到Offer对运营商的要求。

接下来滚动到最下方，可以看到如图:

![](/images/start-campaign/traffic-chart.jpg)

我们的出价尽量要高于第一个流量点才会获得流量，例如上图是1.444，我们可以出价1.544。把这个值填入到刚才的CPM输入框中。然后回到上面一点勾选` I declare and guarantee that my campaign meets the Quality Guidelines `。点击 Start Campaign，如果你已经充好了钱，Campaign就进入审核了，还没充钱的话就先Save as Draft。在左侧菜单栏找到Add Funds或上方的$那里点进去充钱，充完钱记得回到Campaigns那里点击Start，就会进入审核了。

#### 结语

至此整个Campaign流程已经设置完毕，等待流量源审核通过就会输送流量到你的Offer了。如果你的设置都没有问题，流量源审核通过后你可以在追踪器那里看到有流量进来，有转化也会显示相应的转化数据，在联盟Mobidea的后台也能看到有访问数据等（联盟数据显示会有延迟）。你在"联盟+追踪器+流量源"都能看到数据的变化，那就说明你的配置没有出错，恭喜你！

有转化最好，没有转化也不要紧，毕竟现在靠直链盈利的可能性几乎为0，我们跑直链只是为了确保我们的配置不会出错。强烈不建议跳过直链直接跑Landing Page，亏10美金总比亏更多的钱好。只是我们不要在直链中投入过多的预算和精力，坚定信念，保持信心，我们下一节开始讲Landing Page。
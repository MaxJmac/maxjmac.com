---
title: "Media buy如何将流量收益最大化，获得额外30%+利润"
date: 2022-01-30T18:50:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "Landing Page上能做些什么来使Media buy的流量收益最大化，获得额外30%以上的利润。如何结合使用Propush，popunder和Back Button Redirect来提升收益。"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/maximize-traffic-revenue/maximize-traffic-revenue-head.png"
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

相信很多人都有过这个疑问，就是在跑offer的时候，到底要不要加Landing Page？

我的答案是，如果你不加，你就是在put your money on the table，也就是有钱不赚！

那Landing Page上能做些什么来赚钱？本文将给你答案。

## Propush

在本文开始之前，我会先给你介绍一个工具，这个工具很重要，叫Propush，注册链接是:

 [https://propush.me/?ref_id=egLc](https://propush.me/?ref_id=egLc)

这是一个推送订阅收集工具，收集来的订阅不是你自己来用，而是给[PropellerAds](https://partners.propellerads.com/#/app/auth/signUp?ref_id=e2e1476509ed)这个流量源使用的，他们把这个推送订阅卖给其他的用户使用，然后跟你收入分成(RevShare)。

你只需在你的Landing Page上加一段代码，即可实现这个功能。

这么简单我还需要写一篇文章来介绍吗？当然不是。

我会教你如何更加进阶地使用这一工具，以及Landing Page上还能做哪些事情来获得额外收益。

## 流量价值最大化

我们经常看到`余量变现`这个名词，这其实是区分新手和有经验的Media buyer的一个东西，就是如何将买来的流量价值最大化。

新手一般上来是找Offer，Spy一个或几个Landing Page，一个或几个Creative，然后就上Campaign了，买到的所有流量都往这个offer去，包括无效流量。

而一个有经验的Media buyer呢？他们会在Landing Page上做比较多的工作，设置很多代码，他们还会设置Rule来把不适用于这个或这些Offer的流量（无效流量），发送到其他smartlink去变现。

不要小瞧这些不起眼的小细节，正是很多这种细节的堆积，形成了新手和有经验的Media buyer之间的差距。

那么`余量变现`里面的这个余量，具体指的是什么呢？

## 余量

在我的概念里面，我把这个余量分为3种，一种是popunder，一种是BBR，还有一种就是上面所说的不适用于当前offer的流量（无效流量），我会逐一介绍。

我们先讲什么是无效流量。举个例子，如果你跑的Offer是只适用于Geo A的，但是你买流量的时候，不可避免的会有一些非Geo A或者Proxy之类的流量，这时候你就可以设置一个Rule，把购买到的非Geo A的流量，导到其他smartlink去，这样做的同时，你也一定程度上避免了被Spy。

### popunder

可能有些人也买过这种类型的流量，其实我们在自己的Landing Page上也能实现这一功能，这也是为什么我始终建议你添加Landing Page，即使是那种点击一下按钮就跳转的Landing Page。

原理就是当用户点击CTA(Call to Action)之后，打开一个新的标签用来加载Offer页面，同时将你原来的Landing Page重新定向到你其他的Funnel，可以是你的另一个offer也可以是smartlink。

这也就实现了正常跑一个Offer的流量，你加载了两个Offer，用户是可以同时在这两个Offer上都实现转化的，但你只花了一份流量的钱，仅仅是因为你在Landing Page上加了这个实现的代码。

### BBR

BBR是Back Button Redirect的简称，也就是返回按钮重定向。

![bbr-example](/images/maximize-traffic-revenue/bbr-example.png)

原理是当用户点击广告进来之后，用代码的方式将左下角这个返回按键本来要访问的页面，修改成你希望用户访问的页面。

也许有人会想当然的认为，这种根本不会转化的呀，然而根据实测的效果，是会转化的。

话不多，直接先看看效果：

![stats](/images/maximize-traffic-revenue/stats.png)



那总的来说就是Landing Page上加个订阅收集，加个popunder，加个BBR就可以了？

这么简单我还需要写一篇文章来介绍吗？当然不是。接下来的内容，才是重点！

## 如何结合Propush使用

当然，你可以照上面说的，直接在Landing Page上加个订阅，加个popunder，加个BBR，这样也没问题。

但是有些时候，Landing Page上加订阅可能会影响到LP的CTR。具体会不会影响建议你A/B测试一下，每个Geo，每个Vertical情况都不一样。

接下来我要介绍的是我正在使用的方案，示意图如下：

![secondlink](/images/maximize-traffic-revenue/secondlink.png)

这里我用一个通用类型的`推送收集LP`，类似于这样的：

![lp-example](/images/maximize-traffic-revenue/lp-example.png)

我们就是在这个推送收集LP上去集成Propush的代码，进行推送收集。

关键的是我们还可以利用Propush的TrafficBack特性，在用户完成订阅后将他们送到smartlink或者你的任意Funnel，进行二次转化。

## 配置流程

接下来，我将以Binom这个Tracker为例，完整地介绍整个配置流程。当然，你可以用任意Tracker实现这个方案。

如果你对Binom感兴趣，可以看看我的这篇文章[《Tracker中的王者--追踪器Binom完全配置安装中文指南》](https://maxjmac.com/affiliate-marketing/binom-install-chinese-guide/)，用我的推荐码可以获得30天免费试用及次月六折的优惠。

### 1. Tracker中的配置

首先我们到`Traffic Sources`这个Tab下，新建一个自定义的Traffic Source，我这里命名为Organic，具体配置如下图：

![traffic-source](/images/maximize-traffic-revenue/traffic-source.png)

然后到`Campaigns`这个Tab下，新建一个Campaign，如下图：

![campaign](/images/maximize-traffic-revenue/campaign.png)

这里的Campaign URL后面会用到，Path那边我一般是添加多个smartlink，然后根据表现，停掉那些表现差的。

### 2. Propush中的配置

我们先将推送收集LP上传到自己的服务器，获得访问的URL即可。

登录到Propush的后台，在左侧的`Sites`菜单下，点击右上角的`Add Source`按钮，在弹出的窗口中选择`Add landing page`，将你的推送收集LP的访问URL粘贴到Landing page URL下方的输入框中，点击`Add URL`进入下一步。

接下来Propush要求确认这个域名是你的，可以用两种方式，一种是下载一个文件放到你的域名的根目录下，另一种是在你刚才提交的LP上加一个meta标签。

![verify-domain](/images/maximize-traffic-revenue/verify-domain.png)

我一般使用第一种方式，将文件下载后放到域名的根目录下，点击下方的`Verify`按钮，进入审核阶段。

这里Propush会审核你的LP是否合规，这里的合规跟PropellerAds的要求差不多（不能有Adult，不能有未经授权的品牌标识等），因为我使用的是通用类型的LP，审核一般都没问题，速度快的话1分钟左右就审核通过了。

审核通过后你点击左侧`Sites`菜单，可以看到你的URL的Status是绿色`VERIFIED`的状态，点击进去进行下一步的配置。

先点击`Create Smart Tag`，弹出的窗口中，Tag name保留默认随机分配给你的就行，选项也保持默认的Rev.share，直接点击`Create`按钮，进入下一步。

![smart-tag-step-1](/images/maximize-traffic-revenue/smart-tag-step-1.png)

这里跟认证域名差不多，要求你把一个js文件放到域名的根目录下，点击上图中的`Download file`将文件下载，放到域名根目录下后，点击`Verify uploading`按钮，红色的`NOT VERIFIED`变成黄色的`CHECKING`再变成绿色的`VERIFIED`就可以了。

![smart-tag-step-2-0](/images/maximize-traffic-revenue/smart-tag-step-2-0.png)

这一步有两个开关，第一个是用来postback你的订阅用户数据的，这个完全没必要打开，一来浪费tracker的事件数，二来无意义的请求浪费tracker服务器资源，需要看数据进Propush后台就好了，收益当成额外的奖励，不用跟你的Campaign表现联系到一起。

第二个就是上面说到的TrafficBack，我们打开这个开关后，会弹出一个窗口，如下图：

![smart-tag-step-2-1](/images/maximize-traffic-revenue/smart-tag-step-2-1.png)

把左侧的4个都勾选上，Select zone的下拉菜单中点击Create zone，就会自动创建一个，然后每一行都选择上这一个，点击`Save`按钮保存。

![smart-tag-step-2-2](/images/maximize-traffic-revenue/smart-tag-step-2-2.png)

保存后你会发现下方的代码有变化，多了`window.location.replace("//");`部分，这里其实就是将用户默认的，允许订阅的，拒绝订阅的，已经订阅了的，跳转到你想让他跳转的页面去。

![smart-tag-step-2-3](/images/maximize-traffic-revenue/smart-tag-step-2-3.png)

### 3. LP代码集成

我们回到最初上传的那个推送收集LP，在head标签的最底部添加一些代码。

首先是读取地址栏参数的通用代码：

```
<script>
  function GetQueryString(name) {
    var reg = new RegExp("(^|&)"+ name +"=([^&]*)(&|$)");
    var r = window.location.search.substr(1).match(reg);
    if(r!=null)return decodeURI(r[2]); return null;
  }
</script>
```

然后是获取你的参数的代码：

```
<script>
    const key = GetQueryString("key");
    const c1 = GetQueryString("c1");
    const c2 = GetQueryString("c2");
    const redirectUrl = "https://tracker.com/click.php?key=" + key + "&c1=" + c1 + "&c2=" + c2;
  </script>
```

注意将redirectUrl的域名替换成你的。

这里的key对应的是Binom的key，这是Binom用来区分Campaign的唯一值，每个Tracker不一样，你按你的Tracker灵活应变。c1/c2则是对应我们第1步Tracker中的配置里面新建的自定义Traffic Source的Type和Geo。

最后是Propush中提供的代码，我们做一些修改：

```
<script>
    var s = document.createElement('script');
    s.src='//random.com/pfe/current/micro.tag.min.js?z=8888888'+'&sw=/sw-check-permissions-88888.js';
    s.onload = function(result) {
        switch (result) {
            case 'onPermissionDefault':
            window.location.replace(redirectUrl);break;
            case 'onPermissionAllowed':
            window.location.replace(redirectUrl);break;
            case 'onPermissionDenied':
            window.location.replace(redirectUrl);break;
            case 'onAlreadySubscribed':
            window.location.replace(redirectUrl);break;
            case 'onNotificationUnsupported':break;
        }
    }

    document.head.appendChild(s);
  </script>
```

你只需要将s.src后面的字符串替换成你的就可以了。这里我们就是将上面获取你的参数的代码里面的redirectUrl，放到`window.location.replace();`这里，用户就会在系统判定之后跳转到redirectUrl这个参数下的地址去。

推送收集LP的代码全貌如下图：

![lp-codes](/images/maximize-traffic-revenue/lp-codes.png)

### 4. Landing Page中如何使用

至此配置部分就已经全部完成了，接下来就是如何在Campaign中使用这一方案。

为避免混淆，我们假设你Tracker的域名是tracker.com，Propush中提交的推送收集LP的域名是propushlp.com。

我们在popunder和BBR的跳转链接部分，使用`https://propushlp.com/s/index.html?key=你的Campaign唯一值&c1=popunder或BBR&c2=GEO代码`这样的形式，这里的/s/index.html是你提交到Propush审核的那个推送收集LP的路径，`?`后面的三个参数则对应的是步骤3中三个参数，把具体的值传过去。

举个例子，我们步骤1中的Campaign URL是`https://tracker.com/click.php?key=keeeeeeeeeeeeeeeeeey&c1={type}&c2={geo}`，跑的是ZA(南非)。

我们popunder部分就使用`https://propushlp.com/s/index.html?key=keeeeeeeeeeeeeeeeeey&c1=popunder&c2=ZA`

BBR部分就使用`https://propushlp.com/s/index.html?key=keeeeeeeeeeeeeeeeeey&c1=BBR&c2=ZA`

这样你的推送收集LP就会根据跳转读取到key,c1,c2这三个值，然后拼接成你真正的Campaign URL，也就是步骤3中的redirectUrl，给Propush去作为TrafficBack的跳转。

以上就是所有的配置和使用流程。

## 我的实践经验

最后聊一下我使用这套方案的一些实践经验。

我在跑dating的时候，会在popunder和BBR的Funnel上放一些dating的smartlink，这样做用户可能会在你的offer和smartlink上同时转化，就像这样：

![double-conv](/images/maximize-traffic-revenue/double-conv.png)

这是我之前使用Kintura时存的图，可以看到这是来自两个联盟的Offer/smartlink，但那个用户在这两个上面都转化了。

还有就是跑Desktop的Campaign的时候，不建议使用popunder和BBR，因为用户在Desktop时，可以很明显的看到popunder，而在Mobile上是不明显的，我跑Desktop时遇到过用户在popunder上的Funnel转化，而没有在我的主Campaign上面转化。Desktop我只会加关闭/后退弹窗确认的代码。

## 总结

正如上面所说，你可以直接加订阅，加popunder，加BBR这样使用，也可以用我这一套方案。

我的建议就是测某个geo+Vertical时，你两套方案一起测试，看看在LP上直接加订阅是否会影响LP的CTR。

如果不影响，直接在LP上加就是了，popunder和BBR就直接用Campaign URL，订阅的数量会比这套方案多。

如果影响，那就用这套方案，既不影响原Campaign的表现，又可以实现订阅收集。

最后晒一下这么做的好处吧。

![extra-revenue](/images/maximize-traffic-revenue/extra-revenue.png)

纯额外收益，你的Campaign盈利的话，这就是锦上添花，你的Campaign亏损的话，相当于给你一些补偿吧。

当然，这个数值取决于你跑的量。

以上！

## 广告时间

我建立了一个知识星球，在这里分享一些我找到的公开资源和我的一些经验，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。
![](/images/contact.jpg)
---
title: "Binom无重定向跳转指南"
date: 2023-11-23T23:40:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "如何使用Binom来实现无重定向跳转，从而通过Facebook的审核，以及减少点损的目的"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/binom-no-redirect/hero.jpg"
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
最近在学习Facebook广告投放，遇到的第一个难点就是，FB是不支持跳转的，也就是说我无法像投放Push广告一样使用campaign url进行投放，因为使用campaign url的话会有一次跳转到landing page。


有小伙伴就建议我使用其他的tracker，但其他tracker要么贵要么慢，没有一个能像Binom这样满足我的所有要求，价格实惠且好用。

于是我通过查看Binom的官方文档，结合自己的实际情况，经历多次尝试和实验之后，实现了不需要重定向跳转，又可以很好地统计数据的需求。

这个需求不仅可以满足FB的审核，同时也可以在你投放其他类型的广告时(Push/Pop/Banner/Native)，避免重定向带来的点损，从而提升LP CTR及整体表现。

顺手打个广告，通过我的链接注册Binom可享受首月免费，次月四折的优惠，四折是全网最低了，你用其他流量源或联盟的链接次月最低只能六折。链接如下：

[https://binom.org/signup?from=MAXJMAC60](https://binom.org/signup?from=MAXJMAC60)

或者可以直接使用优惠码: **MAXJMAC60**

### 操作步骤

#### 1.上传Lander

首先，如往常一样清理好你的Landing Page，该压缩的图片压缩好，将文件夹压缩成zip。到Tracker后台切换到Landers这个Tab下，点击左侧的 **+ Create** 按钮，输入好LP名称后，在URL / No-redirect这一栏点击 No-redirect，在切换出的页面中点击 **Click or Drop to upload lander**，选择你的zip文件上传。上传成功后点击下方绿色的Save按钮保存即可。

![new-landing](/images/binom-no-redirect/new-landing.png)

文件默认的路径是**landers/**开头的，完整的访问地址是你tracker的任意一个domain，拼接后面的路径。举个例子，假如我tracker的domain是maxjmac.com。路径如下图：

![landers-url](/images/binom-no-redirect/landers-url.png)

那完整的访问路径就是`https://maxjmac.com/landers/us_vacuum/vacuum/index.html`。

这里landers后面的第一个us_vacuum是根据Landing的名称给的，如果你上传的时候没有填入名称，则会随机给你一串字符，后面那个vacuum则是我压缩文件的文件夹名称。

如果你不喜欢域名后带那么一长串的路径，可以切换到Files这个Tab下，这里默认就是在landers路径下。

![files](/images/binom-no-redirect/files.png)

双击进入us_vacuum这个文件夹，选中你的文件夹之后，点击上方的 **Cut** 按钮剪切。

![cut](/images/binom-no-redirect/cut.png)

然后点击To parent按钮回到上级目录，再次点击To parent按钮，回到landers文件夹同级的目录下，即域名的根目录，点击 **Paste** 按钮，将文件夹粘贴到根目录即可。
回到Landers这个Tab下找到你刚才的Landing Page，编辑路径将前面的landers/us_vacuum/删除后保存，如下图：

![short](/images/binom-no-redirect/short.png)

此时你的Landing Page访问路径就变成了`https://maxjmac.com/vacuum/index.html`。你可以直接点击上图右侧蓝色的Test进行打开测试。

#### 2.建立campaign
![campaign](/images/binom-no-redirect/campaign.png)

如上图建立好campaign之后，点击左侧的 **Advanced Settings** 展开，点击 **LP Pixel** 右侧的Copy按钮将代码复制。
再次进入Files这个Tab，找到你Landing Page所在的文件夹，选择index.html后点击上方的Edit，将代码粘贴到**</head>**标签前，保存即可，如下图：

![lp-pixel](/images/binom-no-redirect/lp-pixel.png)


#### 3.访问测试
回到刚才建好的campaign中，将Campaign URL复制出来，举个例子是这样的：

`https://maxjmac.com/click.php?key=keyxxxxxxxxxkey&ad_id={{ad.id}}&adset_id={{adset.id}}&campaign_id={{campaign.id}}&site_source_name={{site_source_name}}&placement={{placement}}`

在FB投放时，我们不能直接使用Campaign URL进行投放，因为会有一次跳转，这时我们就可以直接替换成：

`https://maxjmac.com/vacuum/index.html?ad_id={{ad.id}}&adset_id={{adset.id}}&campaign_id={{campaign.id}}&site_source_name={{site_source_name}}&placement={{placement}}`

使用上述链接进行投放时，用户是直接访问的Landing Page，没有跳转。

这里其实就是将campaign url中的参数，移到Landing Page  URL的后方进行拼接。因为campaign url中的key参数等信息，已经在LP Pixel代码中且添加到了Landing Page的head标签内了。

通过url访问，并点击最终CTA按钮后可以正常跳转到offer页面，也能正确地统计到LP CTR等信息。

![cta](/images/binom-no-redirect/cta.png)

### 总结
如果你已经测试好了Landing Page，用这套方案也许会更进一步地提升你campaign的表现，因为可以避免一些重定向导致的流量损失，同时也能很好地统计到需要的数据。

Binom的文档其实非常的全面，support也非常的nice且专业，只要准确地表达自己的需求，问题一般都能得到很好的解决。
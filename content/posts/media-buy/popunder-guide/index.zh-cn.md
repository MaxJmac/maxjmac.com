---
title: "Popunder广告完全指南：Agency的实战手册"
date: 2026-03-12T06:00:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "Popunder广告完全指南：从格式介绍到Campaign创建、出价模型选择、RON到白名单优化全流程，帮助iGaming Agency快速上手PropellerAds最经典的广告格式。"
license: ""

tags: ["Media-Buy"]
categories: ["media-buy"]
slug: "media-buy"
hiddenFromHomePage: false

featuredImage: "/images/popunder-guide/hero.jpg"
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

Popunder是PropellerAds最经典的广告格式，也是最适合快速上手的格式。不需要制作任何广告素材，直接把用户送到你的页面。

## 什么是Popunder

Popunder是一种全页面广告格式。它的工作方式很简单：

用户在浏览一个网页时，点击了页面上的某个区域，浏览器会在新的标签页（tab）中打开他想访问的页面，你的目标页面则会在原tab中加载。用户此时并不知道，等他关闭或最小化当前tab后，就会看到你的目标页面。

整个过程中，用户看到的不是一个banner，不是一段视频，而是直接看到你的Landing Page。换句话说，**你的Landing Page就是广告本身**。

很多人会把Popunder和Popup搞混。区别其实很简单：Popup是在新的标签页中打开，用户正在看的内容被打断，期待的内容变成了广告页面，侵入性很强。Popunder是在后台打开，不破坏他的浏览体验和期待的内容，相对温和。你印象里"烦人的弹窗广告"多半是Popup，Popunder的用户体验相对好得多。

## 为什么iGaming Agency应该关注Popunder

**不需要制作广告素材。** 没有banner，没有视频，没有文案。你不需要设计团队花时间做素材，也不存在素材疲劳需要频繁更换的问题。所有精力集中在funnel优化上。

**合规友好。** PropellerAds明确接受iGaming品类。不用绕政策，投放节奏自己掌控。

**数据来得快。** Popunder的流量大且成本低，能快速验证offer和Landing Page的表现。你不需要等好几天才能看到有意义的数据。

**优化逻辑简单。** 没有creative变量的干扰，效果好不好直接看Landing Page质量和offer匹配度。出了问题，排查方向很明确。

## Popunder的局限性

**Landing Page就是一切。** 因为没有creative帮你筛选用户，Landing Page的任何问题都会被放大。页面加载慢、CTA不清晰、没做本地化，数据会直接告诉你。

**用户没有主动搜索意图。** Popunder的用户不是在找你的产品，他们只是在浏览网页。流量大但意图泛，通常需要在offer页面前加一层Pre-lander来预热用户。

> **Pre-lander是什么？**
>
> 在最终offer页面前面加一个"过滤页"，用来预热用户、筛选意图。打个比方，搜索广告的用户带着明确意图来，不太需要预热，但Popunder的用户没有这个意图，直接丢到offer页面转化率会很低。Pre-lander就是解决这个问题的。iGaming常见的Pre-lander形式有quiz问答（"年龄，性别，赢了钱会做什么等"）、mini-game小游戏（转盘抽奖）、赛事预测互动页等。这层预热对转化率影响非常大。

**频次控制很重要。** 如果同一个用户反复看到你的页面，效果可能会快速下降。测试阶段建议每人每24小时不超过3次。

**不同GEO表现差异大。** 不同国家/地区的CPM、用户行为、转化率差异很大，混在一起的话数据将很难分析。**建议一个GEO一个Campaign**。

## 创建Popunder Campaign

以下以iGaming为场景，走一遍在PropellerAds上创建Popunder Campaign的完整流程。

### 1. 选择广告格式

在PropellerAds后台点击 **Create Campaign**，选择 **OnClick (Popunder)** 作为广告格式。

### 2. Traffic Type

有三种选择：

- **Websites**：标准网页流量，最常用，起步建议用这个。
- **Social Traffic**：来自社交媒体的流量。
- **Direct Click**：用户直接访问你的页面。

![Traffic Type](/images/popunder-guide/traffic-type.png)

### 3. 出价模型

这是创建Campaign时最核心的决策。

**CPA Goal（最推荐）**

设置一个目标转化成本（成效），系统自动优化。比如目标成效是$10，你可以设$8作为CPA Goal（官方建议设置为payout的80%），系统会尽可能按这个目标成效来进行自动优化。

CPA Goal需要耐心，至少给算法24-48小时的学习时间。前提是必须设置好回传，系统需要转化数据来进行学习。

**SmartCPM**

设置一个你可以接受的最高CPM出价，系统会将实际出价控制在这个范围内，帮你尽可能多地获取流量。适合前期跑RON（Run Of Network）收集zone数据，搞清楚哪些广告位表现好。

**CPM**

手动设置固定的CPM出价。适合有经验后对特定zone做精细化出价控制。

![Pricing Model](/images/popunder-guide/pricing-model.png)

> **我的建议：**直接CPA Goal起步，让算法替你做优化。找到表现好的zone后新建一个SmartCPM白名单campaign稳定放量。

### 4. Target URL

填入你的Campaign URL。如果用的是Adjust或Appsflyer等归因平台，填入归因平台生成的最终链接。URL中需要包含PropellerAds的`${SUBID}`宏，用于回传时匹配转化数据。示例：

```
https://www.yourdomain.com/landing?clickid=${SUBID}
```

这样每个访问都有唯一ID，发生转化时可以匹配回具体的campaign/zone/subzone，为后续优化提供数据基础。这也是CPA Goal能工作的前提，没有回传数据，算法无法学习。

![Target URL](/images/popunder-guide/target-url.png)

### 5. Traffic Sources

- **Exclusive Inventory**：PropellerAds自有流量，质量高，**测试阶段只开这个**。
- **Partner Traffic**：合作方流量，质量不可控，**等跑通了再开来扩量**。
- **Anti-AdBlock**：包含被广告拦截器拦截的流量，测试阶段建议关掉。

![Traffic Sources](/images/popunder-guide/traffic-sources.png)

### 6. GEO和出价

选择你要投放的国家/地区。再次强调，**一个GEO一个Campaign**。

iGaming出海的主战场是东南亚（印尼、菲律宾）、拉美（巴西、墨西哥）和印度，这些地区也是PropellerAds的流量优势区域。

如果用的是CPA Goal，这里设置目标转化成本，如果用的是SmartCPM或CPM，这里设置CPM出价。不确定出价多少的话，可以打开Automatic Bidding让平台建议一个起始值。

![GEO&Prices](/images/popunder-guide/geo-prices.png)

### 7. 预算设置

- **Daily Budget**：每日预算上限，达到后当天停止投放，次日恢复，注意这里的时区是按平台右上角的时间所在的时区。
- **Total Budget**：Campaign总预算上限，达到后停止投放。

需要注意的是，CPA Goal在学习期可能会超出日预算，这是正常的。系统在校准阶段会花得激进一些。

![Budget](/images/popunder-guide/budget.png)

### 8. Targeting

- **Platform**：Desktop和Mobile建议分开建Campaign，用户行为差异大。
- **OS**：根据要求选择，iGaming通常Android和iOS分开跑。
- **Browser / Browser Language**：按需设置。如果offer有语言要求，可以用Browser Language来过滤。
- **Connection Type**：Wi-Fi/Broadband和3G/LTE的用户行为不同，可以分开测试。
- **VPN**：默认选No VPN，只要真实用户的流量。

![Targeting](/images/popunder-guide/targeting.png)

### 9. Zone管理

Zone是PropellerAds里的广告位概念。优化Popunder Campaign很大程度上就是在做zone层面的筛选。

- **Include**（白名单）：只投放这些zone。
- **Exclude**（黑名单）：排除这些zone。
- **Zone Group**：可以把多个zone打包成一个组，方便批量管理。更新Zone Group后，所有关联的Campaign会同步更新。

刚开始不设限制，让Campaign在全网跑，跑出数据后再做白名单/黑名单。

![Zone](/images/popunder-guide/zone.png)

### 10. 受众收集和Retargeting

建议开启 **Collect users who completed conversions**，收集已转化用户的受众数据。

iGaming做retargeting价值很大。比如对已注册但未首存的用户推送首存优惠，或对已首存用户做二次激活。收集受众需要S2S回传支持。

![Retargeting](/images/popunder-guide/retargeting.png)

## 优化：从广撒网到精准投放

Popunder的优化逻辑本质上就是三步：先广撒网收集数据，再根据数据筛选出好的广告位，最后集中资源放量。

### 第一阶段：RON（Run Of Network）

Campaign刚上线时不做zone限制，让系统在全网跑，目的是收集数据。

这个阶段用SmartCPM或CPA Goal都可以。核心是让数据跑够，不要急于判断。关注这几个指标：Cost（花费）、CPM（千次展示成本）、CTR（点击率）、CR（转化率）、CPA（单次转化成本）。

### 第二阶段：分析数据，建白名单

跑出足够数据后（通常几天到一周），按zone维度分析表现：

- 有转化且CPA在可接受范围内的zone → **加入白名单**
- 花费超过2倍目标成效仍然零转化的zone → **加入黑名单**
- 花费还不够1倍目标成效的zone → **继续观察，不急着判断**

这一步决定了后续能不能跑出利润。耐心看数据，不要凭感觉砍zone。

### 第三阶段：SmartCPM放量

白名单zone + SmartCPM = 稳定产出。

放量不是简单地加预算，而是在表现好的zone上提高出价，解锁更多流量。同时可以考虑加入Partner Traffic来进一步扩大覆盖。

### 频次和投放时段

频次方面，测试阶段保守起步，建议3次/24小时。如果追求更高质量的曝光，可以降到1次/24小时。

投放时段方面，iGaming有一个天然优势：可以围绕体育赛事做dayparting。比如欧洲足球赛季期间，在赛前2小时到赛后1小时加大投放，这个时段用户的转化意愿明显更高。当然最好的方法还是全天候投放一段时间后，根据数据来做最终的判断，而不是凭感觉进行。

## Landing Page和Pre-lander

Popunder没有creative，Landing Page就是你的广告。以下几点必须做到：

**加载速度。** 页面必须在3秒内加载完成。Popunder的用户不是主动找你的，页面加载慢他们会直接关掉，连犹豫都不会有。

**CTA在首屏。** 用户打开页面就能看到行动按钮，不要让他们往下翻才找得到。

**移动端优先。** PropellerAds的大部分流量来自移动端，LP必须在手机上有良好的展示效果。

**本地化。** 语言、货币、视觉风格都要匹配目标GEO。投巴西就用葡萄牙语，投印度不能只用英语。本地化做得好不好，直接影响用户的信任感和转化率。

关于Pre-lander，iGaming的经验是互动式效果好于纯文字页面。quiz问答（"年龄，性别，赢了钱会做什么等"）、mini-game（转盘抽奖）、赛事预测页这些形式，能有效提升从Pre-lander到offer页面的转化率。冷流量需要一个互动的过程来建立兴趣，纯文字很难做到这一点。

## 常见问题

### Q1：Popunder的流量质量怎么样？会不会全是垃圾流量？

PropellerAds的Exclusive Inventory质量不错，这也是建议测试阶段只开Exclusive的原因。但和所有广告平台一样，不是每个zone都好，需要通过RON + 白名单的流程来筛选高质量zone。

### Q2：测试预算多少合适？

取决于GEO和目标成效。一个参考值：单个Campaign的测试预算至少准备目标成效的10-20倍。比如目标成效是$5，准备$50-100的测试预算，才能收集到足够的数据做判断。

### Q3：CPA Goal一直达不到目标怎么办？

按顺序排查：首先确认S2S回传是否正常工作（这是最常见的问题），其次检查Landing Page和Pre-lander的质量。如果这两方面都没问题，可能是CPA Goal设得太低，适当上调试试。另外，CPA Goal至少需要24-48小时的学习时间，不要太早下结论。

### Q4：怎么判断一个zone该加白名单还是黑名单？

看两个维度：转化数量和CPA。有转化且CPA在可接受范围内 → 白名单。花费超过2倍目标成效仍然零转化 → 黑名单。如果花费还不够（比如还没花到一倍目标成效），不要急着下判断，让数据再跑一跑。

### Q5：Popunder和Push应该先跑哪个？

建议先Popunder。不需要制作素材，上线快，数据来得快，适合先验证offer和Landing Page的表现。验证跑通后，再叠加Push这种需要素材的格式来扩量。Popunder可以作为你测试新offer的第一个触点。

## 总结

Popunder是进入PropellerAds最直接的方式，不需要素材，上线快，数据反馈快。把从RON到白名单的优化流程走一遍，这套方法论在后续其他广告格式上也同样适用。

## 广告时间

如果你想扩展更多全球流量或想测试新的买量渠道，可以通过我的专属链接注册PropellerAds：

👉 https://go.maxjmac.com/propellerads

我可以帮你对接中文AM。

还可以使用新人优惠码`MAXJMAC`充值满$150赠送$30。
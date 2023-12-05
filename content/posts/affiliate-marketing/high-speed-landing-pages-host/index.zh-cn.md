---
title: "Media Buy之免费且高速的Landing Page部署方案"
date: 2022-04-16T21:30:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "如何结合使用Netlify+Cloudflare部署一个高速且免费的Landing Page"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/high-speed-landing-pages-host/hero.png"
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

## 前言

对于新手且不懂技术的Media buyer来说，Landing Page是一个令人头疼的部分，我刚开始的时候是跟着《40天》教程使用AWS，后来因为CDN费用过高转过其他方案，可以看我早期我写过的一篇文章[《Media Buy之Landing Page的资源文件CDN部署方案》](https://maxjmac.com/affiliate-marketing/assets-cdn/),目前我的部分Landing Page也仍然在使用那篇文章中的方案，不过也正在逐渐往本篇文章将要讲述的方案迁移，部分已迁移到新方案的Landing Page加载速度和稳定性表现良好，已稳定使用一个月以上。

## 资源准备

### CloudFlare

注册地址:[https://www.cloudflare.com/](https://www.cloudflare.com/)

我们需要使用到它免费的DNS和CDN。

### GitHub

注册地址:[https://github.com/](https://github.com/)

我们主要使用它来管理我们的Landing Page，同时你也需要一个GitHub客户端，下载地址是:[https://desktop.github.com/](https://desktop.github.com/)

### Netlify

注册地址:[https://www.netlify.com/](https://www.netlify.com/)

我们需要使用它来进行静态部署，也就是存放我们的Landing Page，你可以使用GitHub帐户来直接注册Netlify，也可以注册好之后再连接GitHub帐户，这个下面会教怎么连。

### Name.com

注册地址(aff):[https://name.sjv.io/c/3104883/1005785/13165](https://name.sjv.io/c/3104883/1005785/13165)

建议使用它来购买域名，这家可以使用支付宝支付，使用promo code(优惠码): `privacyplease`可以获得免费的Whois Guard。

个人强烈建议始终使用.com域名。

## 原理解析

Netlify本身是一个免费的静态网站部署方案，主要是给个人博客使用，我的博客[https://maxjmac.com](https://maxjmac.com)最初也是使用Netlify作为部署方案。它每个月有100GB的带宽额度，看上去好像不是很够用，但是当你配合CloudFlare的CDN进行使用的话，100GB是完全足够的。所以这个方案可以说是除了域名，完全免费。

## 配置流程

#### 1. 首先去选购好你的域名

![name-0](/images/high-speed-landing-pages-host/name-0.png)

![name-1](/images/high-speed-landing-pages-host/name-1.png)

这里只演示如何使用promo code。

#### 2. 然后到GitHub创建一个代码仓库

![new-repository](/images/high-speed-landing-pages-host/new-repository.png)

登录GitHub后点击上图中红框部分（两者均可）。

![create-repository](/images/high-speed-landing-pages-host/create-repository.png)

Repository name填写一个仓库名称，选择Private，勾选Add a README file，最后点击`Create repository`即可创建。

创建成功后，点击`Code`按钮，再点击`Open with Github Desktop`，就会唤起我们前面安装好的那个GitHub Desktop应用，将仓库下载到本地，如下图：

![clone-repository](/images/high-speed-landing-pages-host/clone-repository.png)

后续我们只需要将LP放到本地仓库中，再提交到GitHub，即可自动部署，这个后面会有讲述。

#### 3. 连接Netlify和GitHub

打开[https://app.netlify.com/](https://app.netlify.com/)，点击`GitHub`直接登录。

![netlify-login](/images/high-speed-landing-pages-host/netlify-login.png)

如果是Email注册的账户，则在登录后点击右上角的头像，进入User settings，在Profile下方的Connected accounts一栏中点击`Edit settings`，然后连接GitHub即可。

回到主界面中，在Sites菜单下点击`Import from Git`，如下图：

![import-from-git](/images/high-speed-landing-pages-host/import-from-git-0.png)

在弹出的页面中点击`GitHub`按钮，如下图：

![import-from-git-1](/images/high-speed-landing-pages-host/import-from-git-1.png)

这时会弹出一个窗口，进行GitHub验证，如下图：

![import-from-git-2](/images/high-speed-landing-pages-host/import-from-git-2.png)

点击`Authorize Netlify`，进入下一步，如下图：

![import-from-git-3](/images/high-speed-landing-pages-host/import-from-git-3.png)

为安全考虑，建议只授权访问相应的仓库，选择后点击`Install`按钮。

![import-from-git-4](/images/high-speed-landing-pages-host/import-from-git-4.png)

继续点击上图中的红框部分，进入最后一步，最后一步内容无需修改，点击最下方的Deploy site即可。

#### 4. 连接Cloudflare和域名

登录Cloudflare后台后，点击`添加站点`按钮，输入你的域名后点击`添加站点`。

计划选择最下方免费的即可，如图

![cloudflare-0](/images/high-speed-landing-pages-host/cloudflare-0.png)

选择后点击`继续`，会跳到**查看您的DNS记录**这一步，先不用管，点击继续。

进入**更改您的名称服务器**这一步，按步骤，我们先到域名管理的后台[https://www.name.com/account](https://www.name.com/account)，点击Account菜单，点击你域名右侧的`MANAGE`按钮。

![cloudflare-1](/images/high-speed-landing-pages-host/cloudflare-1.png)

往下滚动找到NAMESERVERS，点击下方的Manage Nameservers链接。

![cloudflare-2](/images/high-speed-landing-pages-host/cloudflare-2.png)

删除原有的Nameservers记录，将Cloudflare的**更改您的名称服务器**页面中步骤3的两个记录添加进来。

![cloudflare-3](/images/high-speed-landing-pages-host/cloudflare-3.png)

点击下方的`完成，检查名称服务器`按钮即可。

在下一个页面中点击`查看建议`，将**启用“始终使用 HTTPS”**和**启用 Auto Minify**都应用建议。最后转到概述界面，等名称服务器生效即可，生效后会收到一封来自Cloudflare的邮件。

将Cloudflare后台的缓存菜单下的配置子菜单中的**浏览器缓存 TTL**从4小时修改为1年，如下图：

![cloudflare-4](/images/high-speed-landing-pages-host/cloudflare-4.png)

#### 5. 连接Cloudflare和Netlify

在Netlify的后台，找到Site下的`Domain settings`，如下图：

![netlify-0](/images/high-speed-landing-pages-host/netlify-0.png)

在Custom domains中点击`Add custom domain`，如下图：

![netlify-1](/images/high-speed-landing-pages-host/netlify-1.png)

输入你的域名，点击`Verify`，会显示你的域名is already registered，直接点击`Add domain`。

会来到**HTTPS**这一栏，先不要点击下面的`Verify DNS configuration`按钮，往上滚动回到刚才Domains那里，点击`Check DNS configuration`，如下图：

![netlify-2](/images/high-speed-landing-pages-host/netlify-2.png)

获取域名需要指向的记录，如下图：

![netlify-3](/images/high-speed-landing-pages-host/netlify-3.png)

在Cloudflare中分别添加不带www和带www的域名的CNAME记录，如下图：

![cloudflare-5](/images/high-speed-landing-pages-host/cloudflare-5.png)

添加完之后就去Netlify的Domain management下的HTTPS那一栏，点击`Verify DNS configuration`按钮就可以了。

至此，配置部分已全部完成。

## 如何使用

将你处理好的LP放到本地仓库的根目录下，如图：

![local-repository](/images/high-speed-landing-pages-host/local-repository.png)

打开你的GitHub Desktop客户端，你会看到如下图的内容：

![github-submit](/images/high-speed-landing-pages-host/github-submit.png)

我们在1处随意输入一个标题，方便以后你自己分辨即可，我一般以geo-landingpage名称来命名，然后点击2处按钮，此时3处的按钮会变成Push origin，点击即可。

随后到Netlify的后台，Site overview菜单下，看到如下图：

![netlify-4](/images/high-speed-landing-pages-host/netlify-4.png)

红框部分即刚才填写的标题，状态Published就代表成功了，我们可以用域名加路径访问试一下。

![visit-lp](/images/high-speed-landing-pages-host/visit-lp.png)

页面正常打开，也带有https标志，测个速试试。

![speed-test](/images/high-speed-landing-pages-host/speed-test.png)

![page-speed](/images/high-speed-landing-pages-host/page-speed.png)

几乎满分。

## 总结

这套方案可以说是经济实惠，除了域名都不要钱。性能也很好，访问速度很快。Netlify虽然每个月只给100GB的带宽，但是配合Cloudflare使用的话完全够用。配置起来也不复杂，配置好之后使用更是简单方便，只需放到本地仓库，再在GitHub Desktop应用中点击两下即可自动部署到Netlify。

以上！

## 广告时间

我建立了一个知识星球，在这里分享一些我找到的公开资源和我的一些经验，同时希望能建立一个友好的新手交流的社群，大家共同成长，成为未来大牛。
![](/images/contact.jpg)
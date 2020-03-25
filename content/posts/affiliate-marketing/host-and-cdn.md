---
title: "Affiliate Marketing之Media Buy入门实战(五)主机和CDN配置"
date: 2020-03-14T00:00:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com"
description: "Affiliate Marketing之Media Buy入门实战(五)主机和CDN配置"
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/host-and-cdn/host-and-cdn-head.jpg"
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

做好Landing Page之后，为了让全球的用户都可以访问到我们的Landing Page，我们必须把它放到服务器主机上，配置域名、DNS(Domain Name System)域名系统、CDN(Content Delivery Network)内容分发网络，以让用户能够更快的加载页面，因为没有用户愿意停留在那里等待你的广告慢慢加载。

在这里我们会用[Namecheap](https://www.anrdoezrs.net/click-9268564-11426545)作为域名注册商，Amazon S3作为Web主机，Amazon Route 53作为DNS服务提供商，Amazon Cloudfront作为CDN。你也可以用任何你喜欢服务商作为替换，但是其中哪一步不会了，你就需要自行解决了。

#### 1.注册域名

为什么选择[Namecheap](https://www.anrdoezrs.net/click-9268564-11426545)？因为他们有永久免费的WhoisGuard，这点很重要，因为很多Landing Page在某种程度上有欺骗行为，所以最好不要让你的名字和这个Landing Page产生关联。

首先在[Namecheap](https://www.anrdoezrs.net/click-9268564-11426545)上注册好账号，然后在上方菜单的Domains下的Domain Name Search页面中搜索你想要注册的域名。在这之前，你最好确定一个你要专注跑的垂直领域，比如我跑Sweepstakes(抽奖)，我注册的域名是`free-lucky-prize.com`，后面我会以这个域名作为例子进行配置上的讲解。名字没有必要太纠结，只要和你跑的Offer或其所在的垂直领域有一些关联性即可，不要花太多的时间去注册一个完美的域名，这不是最重要的东西。需要注意的是尽量注册.com域名，人们倾向于相信.com域名。

选好之后Add to cart，然后在右下角Checkout到下一个页面。Domain Registration这里的Auto-Renew关闭掉，因为不知道你会用这个域名多久，到期自行续费就行，没必要Auto-Renew。下方的WhoisGuard保持Enable状态就行，Auto-Renew也不用开。PremiumDNS没必要买，因为我们后面会用Amazon Route 53。最后Confirm Order就付费可以了。

#### 2.安装主机

先到[AWS](https://aws.amazon.com/)注册一个账号，注册完登录AWS的控制台，在左上角的服务菜单下找到存储下的S3。点击`+ Create bucket` 按钮，`Bucket name`这里填入你的域名，我这里是`free-lucky-prize.com`，`Region`保留默认值，当然你也可以选到离你目标Offer近一点的地区，但其实这个不重要，因为我们将使用CDN来全球加速。然后直接点击左下角的`Create`即可创建。

创建完成后点击你刚刚创建的Bucket名称进入设置页面，切换到`Permissions`这个Tab下，在`Block public access`这个子页面下点击右侧的`Edit`按钮，去掉勾选后点击`Save`，在弹出框中输入`confirm`后再点击`Confirm`按钮。如下图所示

![](/images/host-and-cdn/bucket-setting-block-public-access.jpg)

继续在`Permissions`这个Tab下，切换到`Bucket policy`这个子页面。然后将下面这段代码复制到编辑框中

    {
      "Version": "2012-10-17",
      "Id": "Policy1577696696528",
      "Statement": [
          {
              "Sid": "Stmt1577696677121",
              "Effect": "Allow",
              "Principal": "*",
              "Action": "s3:GetObject",
              "Resource": "arn:aws:s3:::free-lucky-prize.com/*"
          }
      ]
    }

注意这里把`free-lucky-prize.com`替换成你自己的域名也就是`Bucket name`（这一步很重要），其它部分全部不改（我当时就自作聪明去改Version日期...），点击`Save`按钮保存。出现下图的样子就是设置成功了。

![](/images/host-and-cdn/bucket-setting-bucket-policy.jpg)

切换到`Overview`这个Tab下，点击`+ Create folder`，这里输入什么其实不是非常重要，但是你新建的每一层folder都会成为你Landing Page链接的一部分，建议是方便你自己分辨，又不会让用户看到这个链接觉得欺诈就行。举个例子，假设我跑的是印度的抽奖Offer，用的是转盘类型的Landing Page，我就会这样新建folder，先创建一个名为India的folder，创建完点击这个名称进去再创建一个名为lucky-wheel的folder，进入lucky-wheel这个folder之后点击`Upload`，上传我的Landing Page，最终效果如下图

![](/images/host-and-cdn/bucket-setting-overview.jpg)

那么我的Landing Page的最终链接为`http://free-lucky-prize.com/India/lucky-wheel/index.html`。当然，等我CDN配置完就是`https`而不是`http`了。最后，在浏览器输入你自己配置好的地址测试一下，可以看到的话说明主机配置这一步就没有问题了。如果你是跑Mobile类型的话，记得用手机尝试访问一下，看看效果。

#### 3.创建CDN

点击左上角的`Services`，在输入框中输入`CloudFront`并点击进入CDN的配置页面，点击`Create Distribution`进入下一个页面，有两个`Get Started`按钮，点击Web这一栏的`Get Started`进入下一个页面。

在第一行`Origin Domain Name`这里点击输入框选择你刚刚创建的Bucket。跳过中间部分，滚动到`Distribution Settings`这里在`Alternate Domain Names(CNAMEs)`输入框中输入你的域名，带www和不带www的两种版本，都不要加`http://`。然后在下方`Default Root Object`这个输入框中输入`index.html`，如图

![](/images/host-and-cdn/cdn-setting-domain-names-1.jpg)



然后点击`Create Distribution`你大概率会遇到这个错误，如下图

![](/images/host-and-cdn/cdn-setting-error.jpg)

这是我遇到的《40天新手进阶实操教程2019中文版#完整版#》那本书里的一个坑，你回到上面`SSL Certificate `这里点击`Request or Import a Certificate with ACM`这个按钮到下一个页面，在Domain name那里输入你的域名带www和不带www的版本，如下图

![](/images/host-and-cdn/cdn-settings-request-certificate.jpg)

点击Next，选择`Email validation`也就是邮件验证，继续Next，Add Tags这里跳过，点击Review，然后点击`Confirm and request`，最后点击`Continue`，你域名注册的那个邮箱就会收到Amazon发给你的邮件。同时你也跳往下一个页面显示如图

![](/images/host-and-cdn/cdn-settings-request-certificate-pending.jpg)

去你的邮箱里面点击Amazon发给你的邮件，To approve this request后面有个链接，点击后在下一个页面点击`I Approve`按钮即可完成验证。刷新页面，显示变成下面这种状态

![](/images/host-and-cdn/cdn-settings-request-certificate-issue.jpg)

回到刚才那个页面，刷新一下重新填写内容，在`SSL Certificate`这里选择`Custom SSL Certificate`并在输入框中选择你刚才请求到的Certificate，如下图

![](/images/host-and-cdn/cdn-settings-request-certificate-custom.jpg)

这时再点击`Create Distribution`就没有问题了。

![](/images/host-and-cdn/cdn-settings-copy-domain-name.jpg)

复制`Domain Name`下面的内容到一个地方存着，我们后面的配置会用到它，Status这里In Progress先不用管，大约15分钟后会变成Deployed的，我们不用在这里等。我们进入下一步配置DNS。

#### 4.配置DNS

同样的，在左上角`Services`输入框中输入`Route 53`并点击进入DNS配置页面，点击`Create Hosted Zone`，`Domain Name`这里输入你的域名，我这里是`free-lucky-prize.com`，Comment不填，点击`Create`进入到下一个页面。点击上方的`Create Record Set`，在弹出的窗口中Name这里输入`www`，Type保持A - IPv4 address不变，`Alias`这里选择Yes，然后Alias Target这里点击后会出现一个下拉，如果你的CloudFront已经部署完成了，选择你的CloudFront配置那个域名，如果还没部署完没有显示的话，就粘贴你刚刚复制下来的Domain Name，`***.cloudfront.net`那个进去，然后点击`Create`。

再次点击上方的`Create Record Set`，重复上面的步骤，Name这里输入`www`，区别是Type这里改成AAAA - IPv6 address。

然后再添加无修饰版本，即Name这里不输入内容，Type分别配置IPv4和IPv6。配置完如图

![](/images/host-and-cdn/dns-settings.jpg)

最后，我们需要将域名指到Route 53域名服务器。注意看上图红框部分。

我们登录到Namecheap，在Domain List下找到你的域名，点击右侧`MANAGE`按钮，在`NAMESERVERS`这里改成`Custom DNS`，并在下方粘贴上图的四个地址，不要最后面的`.`，记得点绿色的小勾保存。

![](/images/host-and-cdn/namecheap-dns-setting.jpg)

最后，你可能需要等待DNS配置生效，官方说是最多48小时，实际上只要15-30分钟左右。

如何查看DNS是否已经生效？你可以到[https://dnschecker.org/](https://dnschecker.org/)输入你的域名，带www和不带的版本都试一下，如果你看到绿色的小勾，说明生效了，如果是红色的小叉，那就再等等。如果过了几小时还是没有的话，你就要检查一下上面的步骤有没有出错了。

#### Landing Page配置好之后追踪器怎么设置

登录之后在左侧菜单找到Ads Config下的Landing Page，点击Add，在弹出窗口的Name这里填上Landing Page的名称方便你自己分辨多个Landing Page，下方Url这里填入Landing Page存放的地址，点击Save即可。继续到左侧的Campaign List菜单，新建Campaign或编辑现有Campaign，在Rotator部分的左侧Landings选择相应的Landing Page即可。要Split test多个Landing Page的话就添加相应的Landing Page到Rotator并设置好权重，这个在追踪器的文档里面有详细的说明，自行查阅。文档点页面最上方的疑问号那个按钮即可进入。

#### 结语

如果一切顺利，那么恭喜你，你翻过了一座大山，毕竟这对非程序员来说并不容易。如果你遇到了些什么错误，不要着急，照着上面的步骤仔细对照应该没有问题。当然，你也可以联系我，我会尽力帮助你。我的微信号是`MaxJmac`(注意大小写)，祝你好运！
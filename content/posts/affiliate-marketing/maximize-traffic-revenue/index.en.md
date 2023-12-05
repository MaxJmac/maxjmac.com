---
title: "How to maximize traffic revenue to get extra 30% profit"
date: 2022-01-30T18:50:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "What can be done on the Landing Page to maximize the revenue from Media Buy traffic, and gain an additional profit of over 30%? How to combine the use of Propush, popunder, and Back Button Redirect to increase revenue."
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
share:
  enable: true
comment:
  enable: true
---

Most new media buyers have had this question: should I use a Landing Page when promoting offers?

My answer is, if you don't use a Landing Page, you're basically putting your money on the table, which means you're missing out on potential earnings!

So, what can you do on a Landing Page to make money? This article will show you with the answers.

## Propush

Before we begin this article, I will introduce you to an important tool called Propush. Here is the registration link:

[https://propush.me/?ref_id=egLc](https://propush.me/?ref_id=egLc)

This is a push subscription collection tool. The collected subscriptions are not used by you but are provided to [PropellerAds](https://partners.propellerads.com/#/app/auth/signUp?ref_id=e2e1476509ed), a traffic source. They sell these push subscriptions to other users, and you share the revenue with them through RevShare.

All you need to do is add a piece of code to your Landing Page to achieve that.

Do I need to write an article to introduce something that simple? Of course not.

I will teach you how to use this tool more advancedly and what else you can do on the Landing Page to generate the additional revenue.

## Maximizing the Traffic Value

We often come across the term **monetizing remnant traffic**, which is essentially something that distinguishes novice and experienced media buyers: how to maximize the value of purchased traffic.

Novices typically start by looking for offers, spying on one or several landing pages, creating one or several creatives, and then launching campaigns. All the traffic they acquire is directed to this offer, including non-converting traffic.

On the other hand, an experienced media buyer will do more work on the landing page. They will set up various tracking and optimization codes, and they will also set up rules to redirect traffic that doesn't convert for a particular offer (non-converting traffic) to other smartlinks for monetization.

These seemingly small details can make a significant difference in the performance of a media buying campaign. It's the accumulation of these details and optimizations that sets apart beginners from experienced media buyers.

So, what does the term **monetizing remnant traffic** specifically refer to?

## Remnant traffic

In my concept, I divide this **remnant traffic** into three categories: popunder, BBR (Back Button Redirect), and the traffic that doesn't match the current offer (invalid traffic). I will explain each of them.

Now, let's talk about what invalid traffic is. For example, if you're running an offer that is only suitable for Geo A, but when you buy traffic, there will inevitably be some traffic that is not from Geo A or might be from proxies. In this case, you can set up a rule to redirect the purchased non-Geo A traffic to other smart links. By doing this, you also to some extent avoid being spied upon.

### popunder

Some people may have also purchased this type of traffic. In fact, we can implement this functionality on our own Landing Page, which is why I always recommend adding a Landing Page, even if it's a simple one with just a button click that redirects.

The theory is that when a user clicks the CTA (Call to Action), a new tab is opened to load the Offer page, while simultaneously redirecting your original Landing Page to another part of your Funnel. This can be another offer or a smartlink.

This also allows you to run traffic for one offer while loading two offers. Users can potentially convert on both offers simultaneously, but you're only paying for one set of traffic costs. This is achieved simply by adding the code to your Landing Page.

### BBR

BBR stands for Back Button Redirect, which means redirecting when the back button is pressed in the browser.

![bbr-example](/images/maximize-traffic-revenue/bbr-example.png)

The theory behind BBR (Back Button Redirect) is that when a user clicks on an advertisement and lands on a page, you use code to modify the destination of the browser's back button (usually the page the user came from) to a page of your choice. This ensures that when the user clicks the back button, they are redirected to the specified page, which could be another offer or a specific funnel you want them to go through.

Indeed, some might assume that this approach wouldn't lead to conversions, but based on practical testing, it can actually result in conversions.

Certainly, let's take a look at the results:

![stats](/images/maximize-traffic-revenue/stats.png)

So, in summary, is it enough to add subscription collection, popunder, and BBR to the Landing Page?

Is it necessary to write an article to introduce such a simple thing? Of course not. The following content is the key!

## How to use Propush in combination

Certainly, you can follow the steps mentioned earlier to add a subscription code, popunder, and BBR directly to your Landing Page, and that would work.

However, there are situations where adding a subscription form on the Landing Page may affect the LP's CTR (Click-Through Rate). Whether it will have an impact or not depends on various factors, including the Geo and Vertical. I recommend conducting A/B tests to determine the specific impact for each scenario.

Next, I'm going to introduce the solution I'm currently using, illustrated in the diagram below:

![secondlink](/images/maximize-traffic-revenue/secondlink.png)

I'm using a generic type of **Push Collection LP** here, similar to this:

![lp-example](/images/maximize-traffic-revenue/lp-example.png)

I integrate the Propush code on this Push Collection LP to collect push subscribers.

The key is that we can also utilize Propush's TrafficBack feature to redirect users to a smartlink or any funnel of your choice for secondary conversion after they have subscribed.

## The configuration process

I will use Binom as an example to provide a complete overview of the configuration process. However, you can use any tracker to implement this solution.

If you are interested in Binom, you can use discount code **MAXJMAC60** to get a 30-day free trial and a 60% discount for the following month.

Link: [https://binom.org/signup?from=MAXJMAC60](https://binom.org/signup?from=MAXJMAC60)

### 1. Tracker Configuration

First, let's go to the **Traffic Sources** tab and create a custom Traffic Source. I've named it "Organic." Here are the specific configurations as shown in the image below:

![traffic-source](/images/maximize-traffic-revenue/traffic-source.png)

Next, go to the **Campaigns** tab and create a new campaign, as shown in the image below:

![campaign](/images/maximize-traffic-revenue/campaign.png)

The Campaign URL here will be used later, and in the **Path** section, I typically add multiple smartlinks and then, based on their performance, deactivate the ones that are underperforming.

### 2. Configuration in Propush

Upload the push collection LP to our own server to obtain the access URL first.

Log in to the Propush dashboard, click the **Add Source** button in the top right corner under the **Sites** menu on the left side. In the pop-up window, select **Add landing page** and paste the URL of your push collection LP into the input field below **Landing page URL**. Click **Add URL** to proceed to the next step.

Next, Propush requires you to confirm that this domain belongs to you. You can do this in two ways. One way is to download a file and place it in the root directory of your domain. The other way is to add a meta tag to the LP you submitted earlier.

![verify-domain](/images/maximize-traffic-revenue/verify-domain.png)

I usually use the first method, downloading the file and placing it in the root directory of the domain. After that, click the **Verify** button to proceed to the verification stage.

Propush will review your LP to ensure it complies with their guidelines. The compliance requirements are similar to those of PropellerAds (no adult content, no unauthorized brand logos, etc.). Since I'm using a generic type of LP, the review process is usually straightforward, and if everything is in order, it typically takes around 1 minute to pass the review.

After the review is passed, you can click on the **Sites** menu on the left, and you should see that your URL's status is green with **VERIFIED**. Click on it to proceed with the next configuration steps.

First, click on **Create Smart Tag**. In the popup window, keep the default Tag name that is randomly assigned to you. Leave the option as **Rev.share**, and click the **Create** button to proceed to the next step.

![smart-tag-step-1](/images/maximize-traffic-revenue/smart-tag-step-1.png)

The process here is similar to verifying your domain. You'll need to place a JavaScript file in the root directory of your domain. Click on the **Download file** in the image above to download the file. After placing it in your domain's root directory, click the **Verify uploading** button. The red **NOT VERIFIED** should change to yellow **CHECKING** and then to green **VERIFIED** once the verification is successful.

![smart-tag-step-2-0](/images/maximize-traffic-revenue/smart-tag-step-2-0.png)

This step has two switches. The first one is used to post back your subscription user data, and it's not necessary to turn this on. Turning it on would consume the tracker's event count and generate meaningless requests, wasting the tracker server's resources. You can monitor the data in the Propush backend without linking it directly to your campaign performance. Treat the earnings as an additional reward rather than tying them directly to your campaign's performance.

The second switch is for the TrafficBack, as mentioned earlier. When you turn on this switch, a window will pop up, as shown below:

![smart-tag-step-2-1](/images/maximize-traffic-revenue/smart-tag-step-2-1.png)

Select all four options on the left side, click **Create zone** from the dropdown menu under **Select zone**, and it will automatically create one. Then, choose this one for each row and click the **Save** button to save your settings.

![smart-tag-step-2-2](/images/maximize-traffic-revenue/smart-tag-step-2-2.png)

After saving, you will notice a change in the code at the bottom, which includes the `window.location.replace("//");` part. This part is responsible for redirecting users based on their default behavior, subscription status, and whether they accept or reject subscriptions to the page you want them to go to.

![smart-tag-step-2-3](/images/maximize-traffic-revenue/smart-tag-step-2-3.png)

### 3. Codes

Let's go back to the push collection LP that was uploaded initially, and add some code at the bottom of the head tag.

First is the generic code for reading URL parameters:

```
<script>
  function GetQueryString(name) {
    var reg = new RegExp("(^|&)"+ name +"=([^&]*)(&|$)");
    var r = window.location.search.substr(1).match(reg);
    if(r!=null)return decodeURI(r[2]); return null;
  }
</script>
```

Then the code to retrieve your parameters:

```
<script>
    const key = GetQueryString("key");
    const c1 = GetQueryString("c1");
    const c2 = GetQueryString("c2");
    const redirectUrl = "https://tracker.com/click.php?key=" + key + "&c1=" + c1 + "&c2=" + c2;
  </script>
```

Note to replace the domain in `redirectUrl` with yours.

The "key" here corresponds to Binom's key, which is used to distinguish campaigns uniquely. It's different for each tracker, so you should adapt it to your tracker. "c1" and "c2" correspond to the Type and Geo of the custom traffic source you created in the first step of your tracker's configuration.

Finally, here's the code provided by Propush, and we'll make some modifications:

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

You just need to replace the string after s.src with your own. We are taking the redirectUrl from the code where we retrieved your parameters and placing it inside `window.location.replace();`. This will make the user redirect to the address under the redirectUrl parameter after the system's determination.

The full code for the push collection LP looks like this:

![lp-codes](/images/maximize-traffic-revenue/lp-codes.png)

### 4. How to Use in Landing Page

You have completed all the configuration steps. Now, let's proceed with how to use this approach in a campaign.

To avoid confusion, let's assume your tracker domain is **tracker.com**, and the domain you submitted in Propush for push collection LP is **propushlp.com**.

In the popunder and BBR redirect link sections, use a format like this: `https://propushlp.com/s/index.html?key=YourCampaignKey&c1=popunderOrBBR&c2=GEO`. `/s/index.html` is the path to the push collection LP you submitted to Propush for review. The three parameters after the `?` correspond to the three parameters from step 3, where you pass the specific values.

For example, if your Campaign URL from step 1 is `https://tracker.com/click.php?key=keeeeeeeeeeeeeeeeeey&c1={type}&c2={geo}`, and you're running it for ZA (South Africa), you would use the following URLs in the popunder and BBR sections:

Popunder is `https://propushlp.com/s/index.html?key=keeeeeeeeeeeeeeeeeey&c1=popunder&c2=ZA`

BBR is `https://propushlp.com/s/index.html?key=keeeeeeeeeeeeeeeeeey&c1=BBR&c2=ZA`

In this way, your push collection LP will read the values of key, c1, and c2 from the redirect, then concatenate them to create your actual Campaign URL, which is the redirectUrl in step 3, and provide it to Propush for use as a TrafficBack redirect.

The content above is the entire configuration and usage process.

## My practical experience

Finally, let's discuss some of my practical experiences using this solution.

When I promoting dating offers, I place dating-related smartlinks in the popunder and BBR funnels. This allows users to potentially convert on both your offer and the smartlink simultaneously, like this:

![double-conv](/images/maximize-traffic-revenue/double-conv.png)

This is an image I saved from my previous use of Kintura. As you can see, it's an offer/smartlink combination from two different affiliate networks, but the user converted on both of them.

Another point is that when running Desktop campaigns, I don't recommend using popunder and BBR because users on Desktop can clearly see popunders, while it's less noticeable on Mobile. I've encountered situations where users converted in the popunder funnel on Desktop but didn't convert on my main campaign. For Desktop, I only add code for confirmation windows when closing or navigating back.

## Summary

As mentioned above, you can either directly add subscriptions, popunders, and BBR, or you can use my approach with this complete solution.

My suggestion is to test both approaches together when targeting a specific geo+Vertical. Check if adding subscriptions directly to the LP affects the LP's CTR.

If it doesn't affect the LP's CTR, you can simply add subscriptions directly to the LP, and for popunder and BBR, use the Campaign URL. This way, you may get more subscriptions compared to this setup.

If it does affect the LP's CTR, then you can use this setup. It won't affect the performance of the original Campaign, and you can still collect subscriptions.

Let me show you the benefits of doing this.

![extra-revenue](/images/maximize-traffic-revenue/extra-revenue.png)

Pure additional income! If your campaign is profitable, this is an extra bonus. If your campaign is losing money, it's a form of compensation.

Of course, the value of this depends on the volume of traffic you're running.

That's it!
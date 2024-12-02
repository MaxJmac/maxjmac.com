---
title: "MaxConv Non-Redirect Guide"
date: 2024-11-26T20:52:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "How to use MaxConv to achieve no-redirect track, thereby passing Facebook's advetising policy and reducing click loss."
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/maxconv-direct/hero.jpg"
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

> Recently busy translating the v2 Chinese documentation for Binom officially, now planning to write a guide for MaxConv as well.

> Two Ads from me:
>
> 1. Register for Binom through my link to enjoy the first month free and a 60% discount for the second month—the lowest price available online. With links from other traffic sources or affiliates, the second month’s lowest discount is only 40% (not even Black Friday offers this low!). Here's the link:
>
> https://binom.org/signup?from=MAXJMAC60
>
> Or you can directly use the promo code: **MAXJMAC60**
>
> 2. MaxConv is running a Black Friday promotion until December 10th—annual plans are super cost-effective! Here's the link:
>
> [https://maxconv.com/?utm_source=PhugoySy&utm_medium=refprog](https://maxconv.com/?utm_source=PhugoySy&utm_medium=refprog)

Previously, I wrote [《Binom No-Redirect Guide》](https://maxjmac.com/en/affiliate-marketing/binom-no-redirect/). For cloud tracking, non-redirect jumps are actually more convenient. You only need to add a snippet of JavaScript to your landing page to achieve it effortlessly. As for where you host your landing page, it doesn't matter.

### Steps

#### 1.Obtain the Lander Tracking Script

![create-lander](/images/maxconv-direct/create-lander.png)

In the MaxConv dashboard, go to **Landers >> Create**, as shown in the image above. In the pop-up window, locate the **Lander Tracking Script** section and click **Copy** in the top left corner to copy the code, as illustrated below:

![lander-tracking-script](/images/maxconv-direct/lander-tracking-script.png)

Note: Remember to select the appropriate **Tracking Domain** at the top. Ensure that the **Click URL** used for the landing page matches the selected domain.

#### 2.Insert the Code into the Landing Page

Paste the copied code right before the `</head>` tag in your landing page. The code should look something like this:

![html-code](/images/maxconv-direct/html-code.png)

Ensure that the domain used in your Click URL matches the domain displayed in the code.

Go back to the **Create Lander** section, enter the name and URL of your landing page, and complete the creation of the Lander.

![edit-lander](/images/maxconv-direct/edit-lander.png)

#### 3.Create Campaign

Go to **Campaigns >> Create** to create a new campaign, as shown in the image below:

![create-campaign](/images/maxconv-direct/create-campaign.png)

In the pop-up window, enter the **Campaign Name**, select the **Traffic Source**, and most importantly, set the **Transition from Ads to Campaign** option to **Direct**, as shown in the image below:

![create-campaign-basic](/images/maxconv-direct/create-campaign-basic.png)

Then click the **Next** button in the bottom right corner to proceed to the next step of the setup.

In the **Destinations** section, set the **Default Transition to Offer** to **Direct** and also select **Direct** for the **Transition to Offer** option below, as highlighted in the red box in the image. As for why so many places require selecting "Direct", I don’t fully understand either—just select it everywhere, and you won’t go wrong.

Next, select the Lander with the configured **Lander Tracking Script** code and the desired Offer to complete the Path configuration. Click the **Save** button in the bottom right corner to save the Campaign.

![create-campaign-destinations](/images/maxconv-direct/create-campaign-destinations.png)

After saving, it will automatically redirect to the **Tracking Tab**. In the dropdown menu highlighted in the red box in the image, select the Lander with the configured **Lander Tracking Script** code. The corresponding **Campaign URL** will then appear. Note that this Campaign URL is essentially the link to the Lander, with the relevant traffic source tokens appended to the end. This is the link you will use for your campaigns.

![campaign-tracking](/images/maxconv-direct/campaign-tracking.png)

#### 4.Testing

Copy the **Campaign URL**, open it directly in a browser, and click the corresponding button. It should redirect to the final offer page.

![campaign-test](/images/maxconv-direct/campaign-test.png)

### Summary

MaxConv simplifies non-redirect jump configuration, requiring only a single JavaScript code snippet added to your landing page. With straightforward setup steps, it ensures smooth and efficient tracking without the need for redirection.

That's it!
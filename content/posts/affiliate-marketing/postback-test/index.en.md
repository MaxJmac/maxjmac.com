---
title: "How to test postback with affiliate networks"
date: 2023-02-17T18:30:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "How to test postback to check if it works or not when you add a new affiliate network?"
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
Whenever we add a new Affiliate Network as a partner, the first thing we need to do is a postback test to ensure that our tracker can track the conversions from the network.

The main affiliate programs include CAKE, HasOffers, Everflow, etc., and they all follow the same pattern. Some networks use their own developed programs for tracking. Therefore, we need to communicate with the AM (Affiliate Manager) of the network to confirm the parameters being used, then set the postback URL and test.

I will use Binom as an example (different trackers might vary but the principle is the same) to explain how to test postback with various programs.

### CAKE

Advidi, Clickdealer, and others use CAKE. If you see an interface similar to this (different networks will use different color schemes and logos):

![advidi](/images/postback-test/advidi.png)

Then they are using CAKE. Clickdealer's underlying system also uses CAKE, but their interface is custom-made.

The convention with CAKE is to use `#s2#` as the parameter for clickid and `#price#` for payout. So, when we add a network using CAKE in our tracker, the format is like this:

![affiliate-network](/images/postback-test/affiliate-network.png)

The first step is to send the Postback URL to the AM, who will then set it up in the affiliate program (CAKE) backend.

The second step is to ask the AM for a test offer link. Generally, once you send them the Postback URL, they will send you one.

![test-offer-link](/images/postback-test/test-offer-link.png)

The third step is to add a TEST offer for this network in the Tracker, as shown in the image below:

![test-offer](/images/postback-test/test-offer.png)

Note that the URL must contain `s2={clickid}`, and the Click ID indicated by the arrow should be in the activated state. Different trackers use different parameters for clickid, some call it click_id or cid. This value is passed from the tracker to the affiliate program (CAKE), where CAKE will read the s2 parameter. If a conversion occurs from that click, CAKE will send back the value of s2 along with the conversion's payout to the tracker. The tracker then marks that clickid as a Conversion and displays the payout in the report. This is the principle behind tracking between the affiliate network and the tracker.

The fourth step is to add a TEST campaign, as shown in the image below:

![test-campaign](/images/postback-test/test-campaign.png)

For the Traffic Source, choose any existing one you have, or add one if you don't have it, this part is not crucial. Set the Path to Direct, which means direct linking (without a Landing Page), and then add the TEST-Offer. After saving, you will get the Campaign URL (the `&email={email}` in the example is a custom parameter for my traffic source, which is not crucial, you can choose to remove this part of the parameter or keep it). Send this URL to the AM.

![fire-postback](/images/postback-test/fire-postback.png)

Check your Conversion Log or the Statistics for that Campaign. If you see the conversion, then all the steps are completed.

### HasOffers

![hasoffers](/images/postback-test/hasoffers.png)

Networks with a similar interface like this one are using the HasOffers affiliate program.

The convention with HasOffers is to use `{aff_click_id}` as the parameter for clickid, but some networks use `{aff_sub}` or `{aff_sub2}`. Therefore, you need to confirm with the AM. Payout is represented as `{payout}`, similar to `#price#` in CAKE.

So, when we add a network using HasOffers in our tracker, the format is like this:

![affiliate-network-2](/images/postback-test/affiliate-network-2.png)

Pay attention to the parameters highlighted in red, they should match. If the network uses `{aff_click_id}`, your Offer URL template should also use `aff_click_id`. If the network uses `{aff_sub}`, then your Offer URL template should use `aff_sub`, and so on.

All the other steps are the same: send the Postback URL to the AM, get a TEST offer link from the AM, add the TEST offer to the tracker, create a TEST Campaign, and then send the Campaign URL to the AM. Finally, check the results. You can refer to the content above regarding CAKE for details, so I won't repeat them here.

### Everflow

![everflow](/images/postback-test/everflow.png)

Networks with a similar interface like this one are using the Everflow affiliate program.

The convention with Everflow is to use `{sub1}`, `{sub2}`, or `{sub3}` as parameters for clickid, and `{payout_amount}` for payout. So, when we add a network using Everflow in our tracker, the format is like this:

![affiliate-network-3](/images/postback-test/affiliate-network-3.png)

Similar to HasOffers, if the network uses `{sub1}`, your Offer URL template should also use `sub1`. If the network uses `{sub3}`, then your Offer URL template should use `sub3`, and so on. All the other steps are the same, as mentioned in the content regarding CAKE above.

### Others

![goldengoose](/images/postback-test/goldengoose.png)

![trafficcompany](/images/postback-test/trafficcompany.png)

For networks like Golden Goose, they use `{p1}` and `{profit}` as clickid and payout parameters. TrafficCompany uses `{click_id}` and `{reward}` as clickid and payout parameters.

## Summary

In summary, you need to confirm two parameters with the affiliate AM: one for clickid and one for payout. Only then can you correctly set up your postback and proceed with testing to ensure that the data can be tracked accurately.

That's it!
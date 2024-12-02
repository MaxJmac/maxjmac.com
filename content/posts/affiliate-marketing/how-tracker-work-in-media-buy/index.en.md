---
title: "A Brief Overview of How Trackers Work in Media Buying"
date: 2024-11-30T20:24:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "Tracking itself is not complicated. First, we need to clearly understand the flow of traffic: Traffic Source >> Tracker >> Affiliate Network, and for postback: Traffic Source << Tracker << Affiliate Network. Start by mastering the basic usage to run through the entire process, then gradually advance to using custom event postbacks."
license: ""

tags: ["Affiliate-Marketing","Media-Buy"]
categories: ["affiliate-marketing"]
slug: "affiliate-marketing"
hiddenFromHomePage: false

featuredImage: "/images/how-tracker-work-in-media-buy/hero.jpg"
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

### Why Trackers Are Important

As performance marketers, without tracking, we can't determine which creative, landing page, offer, or even which system/browser/carrier performs better. Without tracking, it's like running blind campaigns, unable to optimize based on data, leading to a significant waste of unnecessary budget.

### Why Write About This Topic?

Some time ago, an affiliate reached out to me and said:

![conversation](/images/how-tracker-work-in-media-buy/conversation.png)

This is indeed confusing for many newbie affiliates, including myself when I was starting out. My approach back then was to follow the steps first and figure out the principles later as I gained more experience. That’s exactly how I learned as well.

Now I have a solid understanding of how tracking works. No matter which tracker, affiliate network, or traffic source I use, I can quickly configure the relevant parameters and postbacks. Through this article, I hope to share my experiences and insights, helping new affiliates grasp this part more quickly.

### How Traffic Flows

The first point we need to understand is how traffic flows. As shown in the diagram below:

![traffic-direction](/images/how-tracker-work-in-media-buy/traffic-direction.png)

**Forward Flow:** Users enter through the traffic source, are directed to the tracker, and the tracker displays the user path based on the configuration. If there is a landing page, users are directed there; finally, they proceed to the affiliate offer page via the Click URL.

**Reverse Flow (Postback):** If a user converts, the affiliate network notifies the tracker through a postback, and the tracker then notifies the traffic source via another postback.

Clearly understanding how traffic flows allows you to identify the problematic stage when issues arise and find the solution. For example, if the tracker does not receive conversions, the issue likely lies with an incorrect postback configuration on the affiliate network's side. If the tracker receives conversions but the traffic source does not, it usually indicates an incorrect postback setup for the traffic source in the tracker.

### **Meaning of Parameters**

#### clickid

The core of tracking revolves around the **clickid**, which can be thought of as representing a user.

When a user enters through the traffic source, the traffic source assigns them an ID (let's call it **externalid** for now) and passes it to the tracker. Once in the tracker, the tracker also assigns them an ID (let's call it **clickid**) and maps the **externalid** to the **clickid**. The **clickid** is then passed to the affiliate network through parameters in the offer link.

If this **clickid** results in a conversion, the affiliate network uses a postback to notify the tracker, confirming that the user has converted. The tracker then retrieves the corresponding **externalid** and uses another postback to inform the traffic source that the user represented by this **externalid** has converted.

This creates a complete closed loop for traffic flow.

#### payout

**Payout** refers to the commission you earn when your offer converts. It is typically used when the affiliate network sends a postback to the tracker, allowing the tracker to calculate your revenue and expenses accurately.

#### **Parameters Used in Postback**

Postbacks primarily use two parameters: **clickid** and **payout**. Other parameters, such as **transactionid** (or abbreviated as **txid**), are mainly used for upsell-type offers. Additionally, custom events like **SignUp**, **FTD**, **AddToCart**, etc., may also be used.

In most cases, postbacks use at most these four parameters. Other parameters are generally unnecessary, as the tracker can retrieve all relevant information through the **clickid**.

#### Parameter & Placeholder

![parameter-placeholder](/images/how-tracker-work-in-media-buy/parameter-placeholder.png)

On the left is the MaxConv template for PropellerAds, and on the right is the Binom template for PropellerAds.

**Parameter** refers to the name of the parameter, and **Placeholder** can be understood as a "placeholder" or "slot." The parameter names can be customized as you see fit—whatever makes sense to you. If unsure, just follow the template. The key is to ensure consistency between the names used in the traffic source and those configured in the tracker.

For example, in MaxConv, it's called **src_clid**, while in Binom, it's called **visitor_id**. The name doesn't matter as long as the placeholder behind it is `${SUBID}`. This allows PropellerAds to replace `${SUBID}` with the actual value and pass it to the tracker.

### Example

Next, I will simulate a complete campaign process using **PropellerAds** as the traffic source, **MaxConv** as the tracker, and **GiddyUp** as the affiliate network. Please note that this is not a recommendation to use PropellerAds for running GiddyUp campaigns. It is simply because PropellerAds is a well-known traffic source, and GiddyUp offers a variety of e-commerce custom events, making it suitable for illustrative purposes.

#### 1.Adding GiddyUp Affiliate Network in MaxConv

![maxconv-giddyup](/images/how-tracker-work-in-media-buy/maxconv-giddyup.png)

Add GiddyUp Affiliate Network in MaxConv:

Here, it's worth noting that I created it directly using MaxConv's template. As seen on the left in the Offer URL Suffix section, the template uses `sub2` as the parameter to receive the **clickid** from MaxConv. However, this needs to be modified to `sub4` because GiddyUp actually uses `sub4`. This should be confirmed with your Affiliate Manager (AM).

Remember to check **Accept Duplicate Conversions** below, as e-commerce often uses multiple event postbacks, such as **AddToCart**, **AddPaymentInfo**, **InitiateCheckout**, etc.

The content in the upper right section is only for convenience in generating the link below. Just select the **Domain**, and you're good to go. Since the postback is initiated by the affiliate network, this section is only for display, and the right section doesn't require configuration.

Copy the final postback link generated, as it will be used in the next step.

#### 2.Configure Postback in GiddyUp Dashboard

In the GiddyUp dashboard, locate the postback configuration section and add a new postback, as shown in the image below:

![giddyup-postback-event](/images/how-tracker-work-in-media-buy/giddyup-postback-event.png)

Here, we will configure an event postback:  

- **Postback Type:** Select **Event**.  
- **Postback Level:** Select **Specific**, which means it is configured for a specific offer.  
- **Event:** Choose **Add To Cart**.  
- **Delivery Method:** Select **Postback**.  
- **Postback URL:** The original link copied from MaxConv looks like this:

`https://maxjmac.com/conv?clid={sub4}&payout={payout_amount}&txid={OPTIONAL}&currency={OPTIONAL}&event={OPTIONAL}`

The `{OPTIONAL}` parts are optional, meaning they can be included or omitted. Here’s what we’ll do:  

- Change `&txid={OPTIONAL}` to `&txid={transaction_id}`.  
- Remove `&currency={OPTIONAL}` since it’s not needed.  
- Modify `&event={OPTIONAL}` to `&event=AddToCart`. The name **AddToCart** can be anything you like, such as **A2C**; this will be the event name displayed in your tracker.  

Note that the blue dashed box in the image above indicates that the placeholder is supported by the affiliate network. Finally, click the **Add** button below to save.  

Use the same method to configure the **Conversion**, as shown in the image below:

![giddyup-postback-conversion](/images/how-tracker-work-in-media-buy/giddyup-postback-conversion.png)

The difference is that for **Postback Type**, select **Conversion**. In the final **Postback URL**, the event is set to **Paid**. The `&event=Paid` part can also be omitted; in that case, the tracker will display a "-" in the event section.

#### 3.Add an Offer in MaxConv

Make sure to append the **Offer URL Suffix** to the end of the URL, as shown in the image below:

![maxconv-offer](/images/how-tracker-work-in-media-buy/maxconv-offer.png)

If there are no other parameters, start with `?` and add `sub4={mc_click_id}`. If there are existing parameters, start with `&` and append it to the end of the URL.

#### 4.Add PropellerAds in MaxConv

In MaxConv, create a new PropellerAds traffic source using the template. Then, go to the **Tracking** menu on the left side of the PropellerAds dashboard and select **Other tracker or CPA network**, as shown in the image below:

![propellerads-tracking](/images/how-tracker-work-in-media-buy/propellerads-tracking.png)

Click **Copy this S2S Postback URL** in Step 2, then return to the **PropellerAds traffic source configuration** in MaxConv. Paste the URL into the input box under **Traffic source postback URL**. Remove the `&payout=${PAYOUT}` part, and replace `${SUBID}` with `{external_id}` from the tokens below. Finally, click **Save** to complete the setup, as shown in the image below:

![maxconv-propellerads](/images/how-tracker-work-in-media-buy/maxconv-propellerads.png)

#### 5.Create a Test Campaign

Create a new campaign in MaxConv with any name you like. Select **PropellerAds** as the **Traffic Source**, then click **Next** in the bottom right corner to proceed to the **Destinations** settings. Turn off **Landers**, select the previously created **Offer** under **Offers**, and click **Save** to move to the **Tracking** section.

#### 6.**Test Results**

Get the **Campaign URL** from the **Tracking** section, paste it into your browser, and open it. After manually triggering the **Add To Cart** event on the offer page, you can see the custom event postback in the **Conversions** section of MaxConv, as shown in the image below:

![maxconv-conversion](/images/how-tracker-work-in-media-buy/maxconv-conversion.png)

### Summary

Tracking itself is not complicated. First, we need to clearly understand the flow of traffic: **Traffic Source >> Tracker >> Affiliate Network**, and for postback: **Traffic Source << Tracker << Affiliate Network**. Start by mastering the basic usage to complete the entire process, then gradually advance to using custom event postbacks.

At this point, you’ll have a solid understanding of how to use tracking. Whether you switch to different traffic sources, trackers, or affiliate networks, you’ll be able to configure them quickly.

As always, if you don’t understand, just follow the steps first, then gradually work on understanding them.

That’s it!
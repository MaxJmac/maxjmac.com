---
title: "Popunder Complete Guide - Agency Playbook"
date: 2026-03-12T06:00:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "A complete Popunder guide for iGaming agencies: format basics, campaign setup, bidding models, RON-to-whitelist optimization, and Landing Page best practices on PropellerAds."
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

Popunder is the most classic ad format on PropellerAds, and the easiest one to get started with. No creatives needed — it sends users straight to your page.

## What Is Popunder

Popunder is a full-page ad format. It works like this:

A user is browsing a website and clicks somewhere on the page. The browser opens the page they intended to visit in a new tab, while your target page loads in the original tab. The user doesn't notice at the time. When they close or minimize their current tab, they discover your target page.

Throughout this process, the user doesn't see a banner or a video — they see your Landing Page directly. In other words, **your Landing Page is the ad itself**.

Many people confuse Popunder with Popup. The difference is straightforward: a Popup opens in a new tab, interrupting what the user is viewing — the content they expected is replaced by an ad page, which feels intrusive. A Popunder opens in the background without disrupting the browsing experience or the expected content, making it much less intrusive. What you think of as "annoying pop-up ads" are mostly Popups. Popunder offers a significantly better user experience.

## Why iGaming Agencies Should Pay Attention to Popunder

**No creatives needed.** No banners, no videos, no ad copy. Your design team doesn't need to spend time producing creatives, and there's no creative fatigue requiring constant refreshes. All your effort goes into funnel optimization.

**Compliance-friendly.** PropellerAds explicitly accepts iGaming verticals. No need to work around policies — you control your own launch schedule.

**Fast data.** Popunder delivers high volume at low cost, allowing you to quickly validate offer and Landing Page performance. You don't need to wait days to see meaningful data.

**Simple optimization logic.** Without creative variables to complicate things, performance comes down to Landing Page quality and offer fit. When something goes wrong, the troubleshooting direction is clear.

## Limitations of Popunder

**Your Landing Page is everything.** Without creatives to pre-filter users, any issue with your LP gets amplified. Slow load times, unclear CTAs, lack of localization — the data will tell you immediately.

**Users have no active search intent.** Popunder users aren't looking for your product — they're just browsing the web. Traffic volume is high but intent is broad. You'll usually need a Pre-lander before the offer page to warm up users.

> **What is a Pre-lander?**
>
> A "filter page" placed before the final offer page, designed to warm up users and filter intent. Think of it this way: search ad users come with clear intent and don't really need warming up, but Popunder users don't have that intent — sending them directly to the offer page results in very low conversion rates. That's what Pre-landers solve. Common Pre-lander formats for iGaming include quiz questionnaires ("age, gender, what would you do if you won money," etc.), mini-games (spin-the-wheel), and sports event prediction pages. This warm-up layer has a significant impact on conversion rates.

**Frequency control matters.** If the same user keeps seeing your page repeatedly, performance can drop quickly. During testing, limit exposure to no more than 3 times per user per 24 hours.

**Performance varies significantly across GEOs.** CPMs, user behavior, and conversion rates differ greatly between countries/regions. Mixing them together makes data nearly impossible to analyze. **One GEO, one Campaign** is the recommended approach.

## Creating a Popunder Campaign

Below is a complete walkthrough of creating a Popunder Campaign on PropellerAds, using iGaming as the scenario.

### 1. Select Ad Format

In the PropellerAds dashboard, click **Create Campaign** and select **OnClick (Popunder)** as the ad format.

### 2. Traffic Type

Three options available:

- **Websites**: Standard web traffic. Most commonly used — start with this one.
- **Social Traffic**: Traffic from social media sources.
- **Direct Click**: Users visit your page directly.

![Traffic Type](/images/popunder-guide/traffic-type.png)

### 3. Pricing Model

This is the most critical decision when creating a Campaign.

**CPA Goal (Most Recommended)**

Set a target cost per conversion and let the system optimize automatically. For example, if your target conversion cost is $10, you can set $8 as the CPA Goal (the official recommendation is to set it at 80% of payout). The system will do its best to optimize toward this target.

CPA Goal requires patience — give the algorithm at least 24-48 hours to learn. The prerequisite is having postback tracking set up, as the system needs conversion data to learn.

**SmartCPM**

Set the maximum CPM bid you're willing to pay, and the system will keep actual bids within that range while acquiring as much traffic as possible. Best suited for early-stage RON (Run Of Network) campaigns to collect zone data and identify which placements perform well.

**CPM**

Manually set a fixed CPM bid. Best for experienced buyers who want granular bid control on specific zones.

![Pricing Model](/images/popunder-guide/pricing-model.png)

> **My recommendation:** Start with CPA Goal and let the algorithm optimize for you. Once you've identified high-performing zones, create a new SmartCPM whitelist campaign for stable scaling.

### 4. Target URL

Enter your Campaign URL. If you're using an attribution platform like Adjust or Appsflyer, enter the final link generated by the attribution platform. The URL must include PropellerAds' `${SUBID}` macro for matching conversion data during postback. Example:

```
https://www.yourdomain.com/landing?clickid=${SUBID}
```

This gives every visit a unique ID. When a conversion occurs, it can be matched back to the specific campaign/zone/subzone, providing the data foundation for optimization. This is also the prerequisite for CPA Goal to work — without postback data, the algorithm cannot learn.

![Target URL](/images/popunder-guide/target-url.png)

### 5. Traffic Sources

- **Exclusive Inventory**: PropellerAds' own traffic. High quality. **Only enable this during testing.**
- **Partner Traffic**: Traffic from partners. Quality varies. **Enable after you've proven the funnel works, for scaling.**
- **Anti-AdBlock**: Includes traffic blocked by ad blockers. Recommended to keep this off during testing.

![Traffic Sources](/images/popunder-guide/traffic-sources.png)

### 6. GEO and Bidding

Select the countries/regions you want to target. Once again, **one GEO, one Campaign**.

The main battlegrounds for iGaming overseas expansion are Southeast Asia (Indonesia, Philippines), Latin America (Brazil, Mexico), and India — all regions where PropellerAds has strong traffic coverage.

If using CPA Goal, set your target conversion cost here. If using SmartCPM or CPM, set your CPM bid. If unsure about bidding, toggle on Automatic Bidding to let the platform suggest a starting value.

![GEO&Prices](/images/popunder-guide/geo-prices.png)

### 7. Budget Settings

- **Daily Budget**: Maximum daily spend. Once reached, delivery pauses for the day and resumes the next. Note that the timezone follows the one shown in the top-right corner of the platform.
- **Total Budget**: Overall Campaign spending cap. Delivery stops once reached.

Note that CPA Goal may exceed the daily budget during its learning phase. This is normal — the system spends more aggressively during calibration.

![Budget](/images/popunder-guide/budget.png)

### 8. Targeting

- **Platform**: Desktop and Mobile should be split into separate Campaigns due to significant differences in user behavior.
- **OS**: Select based on requirements. For iGaming, Android and iOS are typically run separately.
- **Browser / Browser Language**: Set as needed. If the offer has language requirements, use Browser Language to filter.
- **Connection Type**: Wi-Fi/Broadband and 3G/LTE users behave differently. Consider testing them separately.
- **VPN**: Default to No VPN for genuine user traffic only.

![Targeting](/images/popunder-guide/targeting.png)

### 9. Zone Management

Zones are PropellerAds' concept for ad placements. Optimizing a Popunder Campaign largely comes down to zone-level filtering.

- **Include** (Whitelist): Only deliver to these zones.
- **Exclude** (Blacklist): Exclude these zones.
- **Zone Group**: Bundle multiple zones into a group for batch management. When you update a Zone Group, all linked Campaigns update automatically.

Don't set any restrictions at launch. Let the Campaign run across the full network, then build whitelists/blacklists based on data.

![Zone](/images/popunder-guide/zone.png)

### 10. Audience Collection and Retargeting

It's recommended to enable **Collect users who completed conversions** to gather audience data from converted users.

Retargeting is highly valuable for iGaming. For example, you can push first-deposit offers to users who registered but haven't deposited, or reactivate users who've already made their first deposit. Audience collection requires S2S postback support.

![Retargeting](/images/popunder-guide/retargeting.png)

## Optimization: From Broad to Precise

The optimization logic for Popunder essentially follows three steps: cast a wide net to collect data, filter out high-performing placements based on data, then concentrate resources on scaling.

### Phase 1: RON (Run Of Network)

When a Campaign first goes live, don't set zone restrictions. Let the system run across the full network to collect data.

Either SmartCPM or CPA Goal works for this phase. The key is to accumulate enough data without rushing to judgment. Focus on these metrics: Cost, CPM (cost per thousand impressions), CTR (click-through rate), CR (conversion rate), and CPA (cost per acquisition).

### Phase 2: Analyze Data, Build a Whitelist

Once you have sufficient data (typically a few days to a week), analyze performance by zone:

- Zones with conversions and acceptable CPA → **Add to whitelist**
- Zones that spent over 2x the target conversion cost with zero conversions → **Add to blacklist**
- Zones that haven't spent enough (less than 1x target conversion cost) → **Keep observing, don't rush to judgment**

This step determines whether you can turn a profit going forward. Be patient with the data — don't cut zones based on gut feeling.

### Phase 3: Scale with SmartCPM

Whitelisted zones + SmartCPM = stable output.

Scaling isn't simply increasing the budget. It means raising bids on high-performing zones to unlock more traffic. You can also consider adding Partner Traffic to further expand coverage.

### Frequency and Scheduling

For frequency, start conservatively during testing at 3 impressions per 24 hours. For higher-quality exposure, consider reducing to 1 per 24 hours.

For scheduling, iGaming has a natural advantage: you can use dayparting around sports events. For example, during the European football season, increase delivery from 2 hours before to 1 hour after matches, when users' conversion intent is noticeably higher. That said, the best approach is to run 24/7 for a period first and let data guide your final scheduling decisions, rather than going by intuition.

## Landing Page and Pre-lander

Popunder has no creatives — your Landing Page is your ad. These points are essential:

**Load speed.** Pages must load within 3 seconds. Popunder users aren't actively looking for you. If the page loads slowly, they'll close it without a second thought.

**CTA above the fold.** Users should see the call-to-action button as soon as the page opens. Don't make them scroll to find it.

**Mobile-first.** The majority of PropellerAds traffic comes from mobile devices. Your LP must display well on phones.

**Localization.** Language, currency, and visual style must match the target GEO. Use Portuguese for Brazil. Don't use English-only for India. The quality of localization directly impacts user trust and conversion rates.

Regarding Pre-landers, the iGaming experience shows that interactive formats outperform text-heavy pages. Quiz questionnaires ("age, gender, what would you do if you won money," etc.), mini-games (spin-the-wheel), and sports prediction pages are all formats that effectively boost conversion rates from Pre-lander to offer page. Cold traffic needs an interactive process to build interest — plain text rarely achieves this.

## FAQ

### Q1: How is Popunder traffic quality? Is it all junk traffic?

PropellerAds' Exclusive Inventory has solid quality — that's why we recommend only enabling Exclusive during testing. But like any advertising platform, not every zone performs well. You need the RON + whitelist process to filter for high-quality zones.

### Q2: How much testing budget is appropriate?

It depends on the GEO and target conversion cost. A reference point: prepare at least 10-20x your target conversion cost as testing budget per Campaign. For example, if the target conversion cost is $5, prepare $50-100 in testing budget to collect enough data for sound decisions.

### Q3: What if CPA Goal keeps missing the target?

Troubleshoot in order: First, confirm that S2S postback is working properly (this is the most common issue). Second, check Landing Page and Pre-lander quality. If both are fine, the CPA Goal may be set too low — try raising it slightly. Also, CPA Goal needs at least 24-48 hours of learning time. Don't draw conclusions too early.

### Q4: How do I decide whether a zone should be whitelisted or blacklisted?

Look at two dimensions: conversion count and CPA. Conversions with acceptable CPA → whitelist. Spending over 2x the target conversion cost with zero conversions → blacklist. If spending isn't sufficient yet (hasn't reached 1x target conversion cost), don't rush to judgment — let the data accumulate.

### Q5: Should I run Popunder or Push first?

Start with Popunder. No creatives needed, fast to launch, fast data. It's ideal for validating whether an offer and Landing Page work. Once validated, layer on Push and other formats that require creatives for scaling. Popunder serves as your first touchpoint for testing new offers.

## Conclusion

Popunder is the most direct way into PropellerAds — no creatives, fast to launch, fast data feedback. Run through the RON-to-whitelist optimization process once, and this methodology applies equally to other ad formats down the line.

## AD
If you are new to PropellerAds, you can register through my exclusive link:

👉 https://go.maxjmac.com/propellerads

Use the promo code `MAXJMAC` to get a $30 bonus when you top up $150.
---
title: "High Speed Landing Pages Host"
date: 2022-04-16T21:30:00+08:00
draft: false
author: "MaxJmac"
authorLink: "https://maxjmac.com/about/"
description: "How to use Netlify and Cloudflare to host Landing Pages with high speed and FREE!"
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

## Preface

For newcomers to media buying who are not tech-savvy, the Landing Page can be a headache. Initially, I followed the '40 Days' tutorial and used AWS, but later switched to other solutions due to high CDN costs. You can see an article I wrote before, [《Media Buy之Landing Page的资源文件CDN部署方案》](https://maxjmac.com/affiliate-marketing/assets-cdn/) which some of my Landing Pages still use. However, I am gradually migrating towards the solution that will be discussed in this article. Some Landing Pages that have been migrated to the new solution show good loading speed and stability, and have been in stable use for over a month.

## Preparing Resources

### CloudFlare

You can sign up here: [https://www.cloudflare.com/](https://www.cloudflare.com/)

We will need to use their free DNS and CDN.

### GitHub

You can sign up here: [https://github.com/](https://github.com/)

We primarily use it to manage our Landing Page, and you will also need a GitHub client. You can download it from [https://desktop.github.com/](https://desktop.github.com/).

### Netlify

You can sign up here: [https://www.netlify.com/](https://www.netlify.com/)

We need to use it for static deployment, which means storing our Landing Page. You can use your GitHub account to directly sign up for Netlify, or you can sign up first and then connect your GitHub account, which will be explained later.

### Name.com

You can sign up here: [https://name.sjv.io/c/3104883/1005785/13165](https://name.sjv.io/c/3104883/1005785/13165)

It is recommended to buy domain names here. You can use the promo code `privacyplease` to get free Whois Guard.

I strongly recommend always using .com domain names.

## How it works

Netlify is a free static website deployment solution primarily intended for personal blogs. My blog [https://maxjmac.com](https://maxjmac.com) initially used Netlify as its deployment solution. It offers a monthly bandwidth limit of 100GB, which may seem insufficient, but when used in conjunction with CloudFlare CDN, 100GB is more than enough. So, this solution can be considered completely free, except for the domain name.

## Configuration Process

#### 1. Buy a domain name

![name-0](/images/high-speed-landing-pages-host/name-0.png)

![name-1](/images/high-speed-landing-pages-host/name-1.png)

Just demonstrate how to use a promo code here.

#### 2. Create a code repository on GitHub

![new-repository](/images/high-speed-landing-pages-host/new-repository.png)

After logging into GitHub, click on the highlighted area in the image (either of the two options will work).

![create-repository](/images/high-speed-landing-pages-host/create-repository.png)


Name your repository in the `Repository name` field, choose `Private`, check `Add a README file`, and finally click **Create repository** to create it.

After successfully creating the repository, click the **Code** button, then click **Open with GitHub Desktop**. This will launch the GitHub Desktop application we installed earlier and download the repository to your local folders, as shown in the image below:

![clone-repository](/images/high-speed-landing-pages-host/clone-repository.png)

All we need to do is place the Landing Page (LP) in the local repository and then commit it to GitHub. This will trigger automatic deployment, which will be explained later.

#### 3. Connect Netlify and GitHub

Visit [https://app.netlify.com/](https://app.netlify.com/), and click on **GitHub** to log in directly.

![netlify-login](/images/high-speed-landing-pages-host/netlify-login.png)

If you have registered with an email account, log in and then click on your profile picture in the top right corner. Go to **User settings**, and under the **Profile** section, click **Edit settings**. From there, you can connect your GitHub account.

Back to the main page, go to the **Sites** menu and click on **Import from Git**, as shown in the image below:

![import-from-git](/images/high-speed-landing-pages-host/import-from-git-0.png)

On the pop-up page, click the **GitHub** button, as shown in the image below:

![import-from-git-1](/images/high-speed-landing-pages-host/import-from-git-1.png)

A window will pop up for GitHub authentication, as shown in the image below:

![import-from-git-2](/images/high-speed-landing-pages-host/import-from-git-2.png)

Click **Authorize Netlify** to proceed to the next step, as shown in the image below:

![import-from-git-3](/images/high-speed-landing-pages-host/import-from-git-3.png)

For security reasons, it is recommended to grant access only to the relevant repository. Select the repository and click the **Install** button.

![import-from-git-4](/images/high-speed-landing-pages-host/import-from-git-4.png)

Continue by clicking on the red box in the image above to proceed to the final step. There is no need to modify the content in the final step. Simply click the **Deploy site** button at the bottom.

#### 4. Add a domain name to Cloudflare

After logging into the Cloudflare dashboard, click the **Add a Site** button, enter your domain name, and then click **Add Site**.

You can choose the free plan at the bottom, as shown in the image below:

![cloudflare-0](/images/high-speed-landing-pages-host/cloudflare-0.png)

After selecting the plan, click **Continue**. You will be taken to the step labeled **Review your DNS records**. You can ignore this step for now and simply click **Continue**.

Proceed to the step labeled **Change your nameservers**. Follow the steps, and first, go to the domain management backend [https://www.name.com/account](https://www.name.com/account). Click on the **Account** menu and then click the **MANAGE** button next to your domain name.

![cloudflare-1](/images/high-speed-landing-pages-host/cloudflare-1.png)

Scroll down and find "NAMESERVERS," then click the "Manage Nameservers" link below it.

![cloudflare-2](/images/high-speed-landing-pages-host/cloudflare-2.png)

Delete the existing Nameservers records and add the two records from step 3 of the Cloudflare **Change your nameservers** page.

![cloudflare-3](/images/high-speed-landing-pages-host/cloudflare-3.png)

Click the **Done, check nameservers** button at the bottom.

In the next page, click **View Recommendations**, and apply the suggestions to enable **Always Use HTTPS** and **Enable Auto Minify**. Finally, go to the overview page and wait for the nameservers to take effect. You will receive an email from Cloudflare once they are active.

Change the **Browser Cache TTL** from 4 hours to 1 year in the **Configuration** submenu under the **Cache** menu in the Cloudflare dashboard, as shown in the image below:

![cloudflare-4](/images/high-speed-landing-pages-host/cloudflare-4.png)

#### 5. Connect Cloudflare and Netlify

In the Netlify dashboard, go to **Domain settings** under your site, as shown in the image below:

![netlify-0](/images/high-speed-landing-pages-host/netlify-0.png)

In the "Custom domains" section, click on **Add custom domain** , as shown in the image below:

![netlify-1](/images/high-speed-landing-pages-host/netlify-1.png)

Enter your domain name, click **Verify**, and it will show that your domain is already registered. Simply click **Add domain**.

You'll come to the **HTTPS** section, but don't click the **Verify DNS configuration** button below. Instead, scroll up to the **Domains** section and click **Check DNS configuration**, as shown in the image below:

![netlify-2](/images/high-speed-landing-pages-host/netlify-2.png)

Retrieve the records that your domain needs to point to, as shown in the image below:

![netlify-3](/images/high-speed-landing-pages-host/netlify-3.png)

In Cloudflare, add CNAME records for both the domain without www and the domain with www, as shown in the image below:

![cloudflare-5](/images/high-speed-landing-pages-host/cloudflare-5.png)

After adding the records, go to Netlify's Domain management and click the **Verify DNS configuration** button in the HTTPS section.

That's all the configuration process.

## How to use

Place your processed LP in the root directory of your local repository, as shown in the image below:

![local-repository](/images/high-speed-landing-pages-host/local-repository.png)

Open your GitHub Desktop app, and you will see the content as shown in the image below:

![github-submit](/images/high-speed-landing-pages-host/github-submit.png)

Enter a title as needed, for your own reference in the future. I usually name it based on the geo-landing page, click the **Commit to main** button. Then the button at 3 will change to "Push origin," click it to proceed.

Then, go to the Netlify dashboard, under the **Site overview** menu, you will see something shown in the image below:

![netlify-4](/images/high-speed-landing-pages-host/netlify-4.png)

The red-boxed part is the title you filled in earlier, and if the status is **Published**, it means you've succeeded. You can access it by using the domain name followed by the path.

![visit-lp](/images/high-speed-landing-pages-host/visit-lp.png)

The page opens correctly and also displays the HTTPS symbol. Let's check the speed.

![speed-test](/images/high-speed-landing-pages-host/speed-test.png)

![page-speed](/images/high-speed-landing-pages-host/page-speed.png)

It's nearly a perfect score!

## Summary

This solution is cost-effective, requiring no expenses except for the domain name. The performance is also excellent, with fast loading speeds. Although Netlify offers only 100GB of bandwidth per month, it is entirely sufficient when used in conjunction with Cloudflare. The setup process is not complex, and once configured, it becomes incredibly easy to use. You simply need to place your Landing Page in the local repository and then click twice in the GitHub Desktop application to automatically deploy it to Netlify.

That's it!
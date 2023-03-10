---
title: How to post your Instagram feed to a Discord server
author: Ondřej Führer
date: 2022-01-08 13:27:01 +0200
categories: [Blogging, IFTTT, Instagram, Quick Tip, How To]
tags: []
pin: false
---

Since [Instagram](https://www.instagram.com) has moved all the posts behind login, it's actually not possible at the moment to use bots to scrape the content of a profile and post those items anywhere. So we need to find a different way.

Limitations: Unfortunately this will only work for your own profile, meaning you can't "scrape" someone else's account for posts. Hope it helps anyways.

## Welcome IFTTT
[IFTTT](https://www.ifttt.com) (If This Then That) is a service that helps you connect services together. You have a trigger (If This) which causes an action (Then That). In our particular case we will use Instagram trigger (when user makes a post) and make an action - post that message to a discord server.

## Step 1: Create IFTTT account
If you already have an account, feel free to skip to [Step 2](#step-2-add-a-new-recipe-with-instagram-trigger).

Head to https://www.ifttt.com and choose "Get Started".
![IFTTT - Get Started]({{ site.baseurl }}/assets/img/posts/instagram-to-discord/ifttt-get-started.png)

Choose your preferred way of signing up and do it.

## Step 2: Add a new recipe with Instagram trigger
You might be able to find a recipe to post Instagram posts to a Discord server, however they usually don't allow a lot of customisations (if you need some), so in this post I'll explain how to create your own recipe for this.

Hit the `Create` button on the screen and get started!
![IFTTT - Get Started]({{ site.baseurl }}/assets/img/posts/instagram-to-discord/ifttt-get-started.png)

Then we add a trigger by clicking on the `Add` button in the `If This` section.
![IFTTT - Get Started]({{ site.baseurl }}/assets/img/posts/instagram-to-discord/ifttt-if-this.png)

Search for Instagram service in the list and click on it.
![IFTTT - Get Started]({{ site.baseurl }}/assets/img/posts/instagram-to-discord/ifttt-search-instagram.png)

After the service is selected, you have to choose what will be your trigger. Since we want to post all the photos to our Discord server, let's choose `Any new photo by you`.
![IFTTT - Get Started]({{ site.baseurl }}/assets/img/posts/instagram-to-discord/ifttt-choose-trigger.png)


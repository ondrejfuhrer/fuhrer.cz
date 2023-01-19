---
title: Setting up HTTPS is really easy
author: Ondřej Führer
date: 2018-07-01 20:55:00 +0200
categories: [Blogging, Security]
tags: [cloudflare]
pin: false
---

Setting up HTTPS on your site is really easy, and you can get one for free.
I’ve set it for this site using a great tutorial from [httpsiseasy.com](https://www.httpsiseasy.com).
That is a great series of videos from a security researcher [Troy Hunt](https://www.troyhunt.com/).
It uses [Cloudflare](https://www.cloudflare.com) to easily add free [SSL certificate](https://www.cloudflare.com/learning/ssl/what-is-an-ssl-certificate/) to any site. 

## What is HTTPS
[HTTPS](https://en.wikipedia.org/wiki/HTTPS) is a secure version of [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) which is the protocol used to transfer data on the web. As the [HTTPS](https://en.wikipedia.org/wiki/HTTPS) version is secure, it uses certificates to encrypt data in the transfer. That means no one can read and understand the data travelling between your device (laptop, smartphone, etc) and the server the site you're visiting is running on.

## Quick HTTPS setup
Please visit [httpsiseasy.com](https://www.httpsiseasy.com) for more detailed steps.
For a quick overview, those are the steps:
1. Create [Cloudflare](https://www.cloudflare.com) account
2. Add your site to your account
3. Change DNS settings for your site to use [Cloudflare](https://www.cloudflare.com) name servers
4. Wait for [Cloudflare](https://www.cloudflare.com) to confirm the name server settings
5. Enable "Always use HTTPS" 
6. Done!

Generally speaking, [Cloudflare](https://www.cloudflare.com) functions as a [reverse proxy](https://en.wikipedia.org/wiki/Reverse_proxy) which means your visitors will go to their servers and [Cloudflare](https://www.cloudflare.com) then takes care of serving the data from original server.

As an addition it will protect your site against [DDos attacks](https://en.wikipedia.org/wiki/Denial-of-service_attack) and will add [caching](https://en.wikipedia.org/wiki/Cache_(computing)) on top of that.

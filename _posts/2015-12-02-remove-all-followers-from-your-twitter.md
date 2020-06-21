---
layout: post
title: Remove all the followers from your twitter account
date: '2015-12-02T19:55:00.000+02:00'
author: Dedunu Dhananjaya
tags:
- remove followers
- python
- Twitter
- tweepy
permalink: /2015/12/remove-all-followers-from-your-twitter.html
---

You might use social networks more often. All of us know that it is really hard to do bulk operations on Facebook and Twitter.

I wanted to remove all the followers from my twitter account. So I googled it. Then I found there is no way to remove followers. The only way is blocking them and unblocking them. But this way if you are following that person, your subscription will be removed automatically.

I tried to do this with "tweepy" Python module. You can modify the program as you need. Please be careful when you run this script, you are going to lose all your followers. To get consumer and access token keys, please visit [https://apps.twitter.com/](https://apps.twitter.com/). Make your keys safe, never share your keys publicly.

{% gist 91992ac6f1940be5d391 %}
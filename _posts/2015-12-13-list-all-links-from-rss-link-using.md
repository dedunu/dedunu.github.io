---
layout: post
title: List all the links from RSS link using Python
date: '2015-12-13T08:48:00.000+02:00'
author: Dedunu Dhananjaya
tags:
- python
- rss
- python3
permalink: /2015/12/list-all-links-from-rss-link-using.html
---

Blogs and news sites use RSS(Rich Site Summary) feeds. Python can be used to fetch updates. I have written a simple program which can fetch RSS feed and print links.

I have written the same application in both Python 2.7 and Python 3 both

{% gist 4856150e6fc8a7fe5216 %}

In Python 3, `urllib2.urlopen()` is replaced with `urllib.request.urlopen()`. Python 3 code is mentioned below.

{% gist 29858412bc0dd494520f %}
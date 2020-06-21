---
layout: post
title: 'Create PrivateBin using Python 3'
date: '2020-06-19T17:07:00.001+02:00'
author: Dedunu Dhananjaya
tags:
- python
- privatebin
permalink: /2020/06/create-privatebin-using-python-3.html
---

I wanted to create a PrivateBin note with Python. It looks so easy at a glance. But request has to be encrypted properly. 

Luckily, I found this python repository <https://github.com/r4sas/PBinCLI>. I stripped out things needed for creating post. You might need below dependencies to be installed in order to make it work.

```
requests
base58
pycryptodome
```

{% gist 75bff57e34ebf4a39356c8560434daef %}

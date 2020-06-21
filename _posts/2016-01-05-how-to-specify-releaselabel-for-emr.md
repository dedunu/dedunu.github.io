---
layout: post
title: How to specify ReleaseLabel for EMR cluster with Boto2
date: '2016-01-05T20:13:00.000+02:00'
author: Dedunu Dhananjaya
tags:
- emr
- ReleaseLabel
- python
- boto3
- boto
- boto2
- aws
- amazon
permalink: /2016/01/how-to-specify-releaselabel-for-emr.html
---

Boto is the AWS SDK for Python. You can create clusters, instances or anything using Boto. But sometimes Boto imposes limitations. I wanted to create an EMR cluster with `RelaseLabel=4.2.0`. But we were using Boto2. `ReleaseLabel` is an option in Boto3. For Boto2 there was no documented option for `RelaseLabel`.

So I found out a way to create EMR (Elastic Map Reduce) clusters using Boto 2 with a specific `ReleaseLabel`.

{% gist f362c3a17a9027ebed2b %}

I have commented `AMI Version` because `ReleaseLabel` will pick `AMI version` correctly. The above program will print the `cluster ID` in the terminal. 

Sometimes you might get an issue saying "`No Default VPC found.`". This is a network related issue. In that case, you might need to specify `subnet ID` for EMR cluster. Then you don't need to specify an availability zone.

{% gist b7a0f54d2535f74e7542 %}

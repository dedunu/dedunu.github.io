---
layout: post
title: 'Stopping unused RDS instances using AWS Lambda'
date: '2020-07-04T23:04:00.001+02:00'
author: Dedunu Dhananjaya
tags:
- aws
- rds
- python
- lambda
permalink: /2020/07/unused-rds-lambda.html
---

If you stop unused RDS instances, it will start in 7 days. It is easy, if you have one instance, you can manage manually. When you have 100s of database instances, it is a bit difficult to stop them manually. If you create a lambda function with a weekly EventBrigde (CloudWatch Events) trigger, it will keep the instances stopped.

{% gist cc66e901e29e139247690d54be77d026 %}

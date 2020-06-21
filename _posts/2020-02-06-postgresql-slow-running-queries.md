---
layout: post
title: 'PostgreSQL: Long running query detection'
date: '2020-02-06T18:07:00.001+02:00'
author: Dedunu Dhananjaya
tags:
- postgres
- performance issue
permalink: /2020/02/postgresql-slow-running-queries.html
---

I am writing this post as a note to myself. Every time I want to find slow running queries, I search and open this [medium post](https://medium.com/little-programming-joys/finding-and-killing-long-running-queries-on-postgres-7c4f0449e86d). It is a well written short post which helps me every day. But I wanted to improve that query.   

{% gist a0542b83d4d672eabbf7a17a8ed9dac3 %}

As mentioned these are pretty helpful too.

```sql
SELECT pg_cancel_backend(pid);
SELECT pg_terminate_backend(pid);
```

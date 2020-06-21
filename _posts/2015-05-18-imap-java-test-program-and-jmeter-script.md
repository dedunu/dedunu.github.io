---
layout: post
title: IMAP Java Test program and JMeter Script
date: '2015-05-18T16:24:00.000+03:00'
author: Dedunu Dhananjaya
tags:
- IMAP
- Java
- JMeter
permalink: /2015/05/imap-java-test-program-and-jmeter-script.html
---

One of my colleagues wanted to write a JMeter script to test IMAP. But that code failed. So I also got involved in that. JMeter BeanShell uses Java in the backend. First I tried with a Maven project. Finally, I could write code to list the IMAP folders. Java implementation is shown below.

{% gist a5c5498bfefe64b0bbe4 %}

Then we wrote a code to print IMAP folder count for JMeter BeanShell. Code is shown below.

{% gist 13cbacfbdf60c7692b64 %}

Complete Maven project is available on GitHub - [https://github.com/dedunu/imapTest](https://github.com/dedunu/imapTest)

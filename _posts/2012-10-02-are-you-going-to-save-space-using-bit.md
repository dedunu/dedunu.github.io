---
layout: post
title: Are you going to save space using Bit Data Type?
date: '2012-10-02T18:50:00.000+03:00'
author: Dedunu Dhananjaya
tags:
- Data Types
- English
- Architecture
- SQL Server
permalink: /2012/10/are-you-going-to-save-space-using-bit.html
---

If you have Yes or No data to store in DB, what will you select as the data type? Most of the times you will select “`Bit`”. Because it only takes 1 bit to store data. And it is the best data type for this situation. But it takes more than a bit in SQL Server. If you have an only one-bit column in your table it will allocate 7 more extra bits to store your bit data.

And if you have two-bit typed fields in your table it will waste 6 more bytes. But if you are using 8-bit typed fields in your table, it will not waste any space. Otherwise, it will take space the same as `char(1)` or `tinyint`. 
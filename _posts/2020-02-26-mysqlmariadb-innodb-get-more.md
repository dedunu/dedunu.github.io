---
layout: post
title: 'MySQL/MariaDB: InnoDB - Get more information about current transaction'
date: '2020-02-26T20:33:00.000+02:00'
author: Dedunu Dhananjaya
tags:
- mysql
- mariadb
permalink: /2020/02/mysqlmariadb-innodb-get-more.html
---

I wanted to find out how many rows were modified by the current transaction. Seems like MariaDB doesn't have a straight forward way to retrieve the transaction ID. To narrow down transactions I used the current connection as the thread ID. You can run the below command to check the information about the transaction. 

```sql
SELECT * 
FROM information_schema.innodb_trx 
WHERE trx_mysql_thread_id = CONNECTION_ID() \G
```

Here is an example:

![screenshot](https://1.bp.blogspot.com/-Yw-E1gGlmSc/Xla5xav5yrI/AAAAAAAABtQ/WgkBL9pdolwHa48yhNNEXFQq9VJ_EkG_QCLcBGAsYHQ/s1600/Screenshot%2B2020-02-26%2Bat%2B6.32.09%2BPM.png)
---
layout: post
title: How to reset replication in MySQL/MariaDB RDS?
date: '2019-05-29T23:57:00.002+03:00'
author: Dedunu Dhananjaya
tags:
- mysql
- rds
- replication
- mariadb
- aws
permalink: /2019/05/how-to-reset-replication-in-mysql-rds.html
---

`RESET SLAVE;` doesn't work in AWS MySQL RDS. You should use the below command to stop replication.

```sql
CALL mysql.rds_reset_external_master;
```

 You will see something like an error message. You can safely ignore that. Try `SLAVE STATUS\G`. If you get an empty set, your instance has successfully reset the replication.
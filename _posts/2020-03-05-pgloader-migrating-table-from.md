---
layout: post
title: 'pgloader: Migrating a table from MySQL/MariaDB to PostgreSQL'
date: '2020-03-05T12:44:00.001+02:00'
author: Dedunu Dhananjaya
tags:
- pgloader
- mysql
- rds
- postgres
- mariadb
permalink: /2020/03/pgloader-migrating-table-from.html
---

`pgloader` is a helpful tool if you want to migrate tables from MySQL/MariaDB to Postgres. This works with AWS RDS instances too.

{% gist d8b2cdbf0218b03fc0c17289ae27a726 %}

Let's say we need to migrate the `user` table from MySQL to PostgreSQL. Your `pgloader` file would look like below.

{% gist 931e113b341cad572f742bfbbd5c670d %}

You can use the below command to start the migration

```console
$ pgload user.load
```
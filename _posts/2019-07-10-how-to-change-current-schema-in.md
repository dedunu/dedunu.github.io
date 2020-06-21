---
layout: post
title: How to change the current schema in Postgres CLI
date: '2019-07-10T15:32:00.002+03:00'
author: Dedunu Dhananjaya
tags: 
- postgres
- sql
permalink: /2019/07/how-to-change-current-schema-in.html
---

If you want to see the current schema you are on.

```sql
SHOW SEARCH_PATH;
```

Normally you might be on the public schema. But if you want to change the current schema, try below command.

```sql
SET SEARCH_PATH TO test;
```

`test` is the name of the schema.
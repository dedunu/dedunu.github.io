---
layout: post
title: 'Terraform: Error locking state'
date: '2020-02-11T18:11:00.000+02:00'
author: Dedunu Dhananjaya
tags:
- aws
- terraform
permalink: /2020/02/terraform-error-locking-state.html
---

If you have Terraform state locks. Sometimes cancelling terraform commands ungracefully might leave the state file locked. This is the error you would usually see if the lock is not released.

{% gist 19cbb46ed1bca17f9d9c49bf5dd44b4a %}

If you want to release this lock. You should run below command. Then type "`yes`" and hit enter.

```console
$ terraform force-unlock <LOCK ID>
```

For example: 

```console
$ terraform force-unlock 21e2b2bb-c123-2383-eece-7a5eaab4f645
```

![screenshot](https://1.bp.blogspot.com/-FdxbUOvKOqk/XkLR2yPbJTI/AAAAAAAAGfU/0MSPTvCxqF4zHsDVEW7dmYAUeCjEB6AaACLcBGAsYHQ/s1600/Screenshot%2B2020-02-11%2Bat%2B1.29.08%2BPM.png)

> Warning: Please don't release this lock, unless you are the once who caused it. It might corrupt the state file.
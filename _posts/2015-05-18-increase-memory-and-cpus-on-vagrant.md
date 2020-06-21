---
layout: post
title: Increase memory and CPUs on Vagrant Virtual Machines
date: '2015-05-18T16:02:00.000+03:00'
author: Dedunu Dhananjaya
tags:
- vagrant
permalink: /2015/05/increase-memory-and-cpus-on-vagrant.html
---

Last post I showed how to create multiple nodes in a single Vagrant project. Usually "`ubuntu/trusty64`" box comes with 500MB. For some developers need more RAM, more CPUs. From this post, I'm going to show how to increase the memory and number of CPUs in a vagrant project. Run below commands:

```console
$ mkdir testProject1
$ cd testProject1
$ vagrant init
```

Then edit the Vagrant file like below.

{% gist 62b88beb311ea44939ed %}

Above changes will increase memory to 8GB and also it will add one more core. Run below commands to start the vagrant machine and get the SSH access.

``` console
$ vagrant up
$ vagrant ssh
```

If you have an existing project, you just have to add these lines. When you restart the project memory would be increased.

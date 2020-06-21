---
layout: post
title: Multiple nodes on Vagrant
date: '2015-05-18T15:38:00.001+03:00'
author: Dedunu Dhananjaya
tags:
- vagrant
permalink: /2015/05/multiple-nodes-on-vagrant.html
---
Recently I started working with Vagrant. A vagrant is a good tool that you can use for development. From this post, I'm going to explain how to create multiple nodes on the Vagrant project.

```console
$ mkdir testProject
$ cd testProject
$ vagrant init
```

If you run above commands, it will create a Vagrant project for you. Now we have to do changes to the vagrant file. Your initial vagrant file will look like below.

{% gist e67183ff613083fb7617 %}

You have to edit Vagrantfile add content like below.

{% gist b1190e9177e75e33d21c %}

Above sample vagrant file will create three nodes. Now run below command to start Vagrant virtual machines.

```console
$ vagrant up
```

If you followed the instruction properly, you will get an output like below.

{% gist 467280aff02bccd0b9a2 %}

If you want to connect to the master node, run below command.

```console
$ vagrant ssh master
```

If you want to connect to slave1 node, run below command.

```console
$ vagrant ssh slave1
```

Whatever the machine you want to connect you just have to type `vagrant ssh`. Hope this will help you!

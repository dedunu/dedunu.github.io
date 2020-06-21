---
layout: post
title: 'VirtualBox: How to start a virtual machine without a window on OS X?'
date: '2020-03-05T12:52:00.001+02:00'
author: Dedunu Dhananjaya
tags:
- Virtual
- osx
- VirtualBox
- Mac
- virtualization
permalink: /2020/03/virtualbox-how-to-start-virtual-machine.html
---

I use a VirtualBox for my day to day work. The whole purpose is to move it to a new laptop and start using it with all the tools, configuration files and keys. But I don't want to open the VirtualBox with a window.

![virtual_machine](https://1.bp.blogspot.com/-CZlyq8nDqc8/XmDa_xir08I/AAAAAAAABto/CINqXvaoTl8QN0Cc5zd5ms1dVpzxSFBZgCLcBGAsYHQ/s400/Screenshot%2B2020-03-05%2Bat%2B12.56.09%2BPM.png)

So I found a way to launch the virtual machine using the command line without the window. My virtual machine is called "`dev`". Use below command.

```console
$ VBoxManage startvm "dev" --type headless
```

![bash_screen](https://1.bp.blogspot.com/-8wWbsQxjCVc/XmDbVSXCMNI/AAAAAAAABtw/ljwgR_IG0HEyF9KfwQ2_oK6m5-G9cwRfwCLcBGAsYHQ/s1600/Screenshot%2B2020-03-05%2Bat%2B12.53.21%2BPM.png)
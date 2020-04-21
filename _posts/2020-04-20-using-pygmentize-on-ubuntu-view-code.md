---
layout: post
title: Using pygmentize on Ubuntu view code files
date: '2020-04-20T20:20:00.003+03:00'
author: Dedunu Dhananjaya
tags:
- terminal
- Ubuntu
- cli
modified_time: '2020-04-21T00:36:39.140+03:00'
thumbnail: https://1.bp.blogspot.com/-dHZ4vfV9c7I/Xp3ae5aYvyI/AAAAAAAABzk/Q5URlY7mnTIl6XcDekdNP0vJYA0IiFS5gCK4BGAsYHg/s72-c/ezgif.com-video-to-gif%2B%25282%2529.gif
blogger_id: tag:blogger.com,1999:blog-8327060682734922468.post-6050592202121314782
permalink: /2020/04/using-pygmentize-on-ubuntu-view-code.html
---

On the terminal, viewing code with colour might improve productivity. You can use `pygmentize` to view code in colour. Install `pygmentize` using below commands.

```console
$ sudo apt install python3-pip
$ pip3 install Pygments
```

You can use view code using:

```console
$ pygmentize -g /etc/profile.d/gawk.sh
```

If you add an alias like below you will be able to use `pygmentize` as a short command to your `.bashrc` or `.zshrc`.

```bash
alias ccat='pygmentize -g '
```
![pygmentize in action](https://1.bp.blogspot.com/-dHZ4vfV9c7I/Xp3ae5aYvyI/AAAAAAAABzk/Q5URlY7mnTIl6XcDekdNP0vJYA0IiFS5gCK4BGAsYHg/ezgif.com-video-to-gif%2B%25282%2529.gif)

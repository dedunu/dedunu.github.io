---
layout: post
title: Changing OS X native Terminal theme from commands
date: '2020-04-20T18:52:00.001+03:00'
author: Dedunu Dhananjaya
tags:
- terminal
- mac
- osx
permalink: /2020/04/changing-os-x-native-terminal-theme.html
---

I used iTerm2 for a while. But it is taking a lot of memory. I wanted to configure the native terminal application on OS X.

I have a virtual box and I used it for my development. I connect to a bridge to access production. I wanted the terminal to change colours/themes when I log in to each and every host. 

I downloaded a few themes from this repository: [https://github.com/lysyi3m/macos-terminal-themes](https://github.com/lysyi3m/macos-terminal-themes). Imported them to OS X terminal application.

Since I am using `zsh`, I added below code to `.zshrc`. If you are on `bash` please change `.bash_profile` on your mac.

{% gist 469629ab990ca2398923af8fdc7eeae5 %}

Then I change `.zshrc` on my virtual server again. It calls my mac to change the active profile.

{% gist 034f2b9c1240347383c39bbedbee0be2 %}

I use password-less login on all the servers. It makes it bit slower when you log-off and log-in.

![Profile changing in action](https://1.bp.blogspot.com/-Lrl6zSgxNM0/Xp3K1GQ0bTI/AAAAAAAABwU/vJeKY0c-pYY73YgmbJvruqPuvKHljHtBACK4BGAsYHg/ezgif.com-video-to-gif.gif)

---
layout: post
title: "Ubuntu 20.04: Build and install coreutils from the source"
date: '2020-06-09T10:13:00.003+03:00'
author: Dedunu Dhananjaya
tags:
- linux
- ubuntu
- coreutils
- make
- install
permalink: /2020/06/10/ubuntu-20-04-build-coreutils-from-the-source
---

I wanted to build and install `coreutils` on a Ubuntu server. You will be probably fine with the stable release of `coreutils` that comes with Ubuntu. First I had to install the tools needed for the build.

```console
$ sudo apt update
$ sudo apt install build-essential \
                   autoconf \
                   automake \
                   autopoint \
                   bison \
                   gperf \
                   texi2html \
                   texinfo
```

You can check the current version by running the below command.

```console
$ ls --version
ls (GNU coreutils) 8.30
Copyright (C) 2018 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Written by Richard M. Stallman and David MacKenzie.
```

Now we need to get the source code of the `coreutils`.

```console
$ git clone https://www.github.com/coreutils/coreutils.git
```

Change the directory to the repository. Execute bootstrap and configure script.

```console
$ cd coreutils
$ ./bootstrap
$ ./configure
```

Finally, build and install using the below command.

```console
$ sudo make install
```

Now you can check if it updated the version. You might see a different version.

```console
$ ls --version
ls (GNU coreutils) 8.32.22-189776
Copyright (C) 2018 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Written by Richard M. Stallman and David MacKenzie.
```

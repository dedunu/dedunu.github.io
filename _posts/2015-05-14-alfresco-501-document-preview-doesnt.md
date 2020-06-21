---
layout: post
title: Alfresco 5.0.1 Document Preview doesn't work on Ubuntu?
date: '2015-05-14T13:27:00.000+03:00'
author: Dedunu Dhananjaya
tags:
- libreoffice
- openoffice
- Ubuntu
- alfresco
permalink: /2015/05/alfresco-501-document-preview-doesnt.html
---

I recently installed Alfresco for testing in the vagrant instance. I used the Ubuntu image for the vagrant instance. But I forgot to install all the libraries which are necessary to be installed on Ubuntu before you install alfresco. But fortunately alfresco worked without those dependencies.

[http://docs.alfresco.com/5.0/concepts/install-lolibfiles.html](http://docs.alfresco.com/5.0/concepts/install-lolibfiles.html)

Above link gives you what are the libraries you should install before you install Alfresco. You should run below command to install libraries.

```console
$ sudo apt-get install libice6 libsm6 libxt6 libxrender1 libfontconfig1 libcups2
```
But still, office document previews didn't work properly. Some documents worked properly but some of them didn't. Then I tried to debug it with one of my colleagues. We found below text in our logs.

{% gist 3d748846bc7f6fc6b87e %}

Then we tried to run the soffice application from the terminal. Look what we got!

```
/home/vagrant/alfresco-5.0.1/libreoffice/program/oosplash: error while loading shared libraries: libXinerama.so.1: cannot open shared object file: No such file or directory
```

Then we realised that we should install that library on Ubuntu. Run below command on the Ubuntu server to install the missing library.

```console
$ sudo apt-get install libxinerama1
```

Make sure you run both commands above!

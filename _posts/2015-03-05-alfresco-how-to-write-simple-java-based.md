---
layout: post
title: 'Alfresco: How to write a simple Java based Alfresco web script?'
date: '2015-03-05T20:44:00.000+02:00'
author: Dedunu Dhananjaya
tags:
- webscript
- Java
- alfresco
permalink: /2015/03/alfresco-how-to-write-simple-java-based.html
---

If you want to develop a new feature for Alfresco best way is WebScript! Let's start with a simple Alfresco web script. First, you need to create an Alfresco AMP maven project using archetype. In this example, I'll use the latest alfresco version 5.0.

First I generated Alfresco All-in-One AMP. ([Please refer my blog post on generating AMP projects](http://www.dedunu.info/2015/01/how-to-generate-alfresco-5-amp-project.html).)

If you go through the files structure which is generated, you will find out a sample web script. It is a JavaScript-based WebScript. By this example, I'm going to explain how to write a simple Java-based Hello World web script.  

HelloWorldWebScript.java
{% gist 411620c73e80e81755d0 %}

service-context.xml
{% gist ef370e4d00cfd4d6b05f %}

helloworld.get.desc.xml
{% gist 534139d220554e6a3e0f %}

helloworld.get.html.ftl  
{% gist 480335164d5aa5f698fd %}

Create the above files in below locations of your maven project.

*   HelloWorldWebScript.java - `repo-amp/src/main/java/org/dedunu/alfresco/HelloWorldWebScript.java`
*   helloworld.get.desc.xml - `repo-amp/src/main/amp/config/alfresco/extension/templates/webscripts/org/dedunu/alfresco/helloworld.get.desc.xml`
*   helloworld.get.html.ftl - `repo-amp/src/main/amp/config/alfresco/extension/templates/webscripts/org/dedunu/alfresco/helloworld.get.html.ftl`
*   service-context.xml - `repo-amp/src/main/amp/config/alfresco/module/repo-amp/context/service-context.xml`

Use below command to run the maven project.

```console
$ mvn clean install -Prun 
```

It may take a while to run the project after that open a browser window. Then visit below URL  

[http://localhost:8080/alfresco/service/dedunu/helloworld](http://localhost:8080/alfresco/service/dedunu/helloworld).

![](http://3.bp.blogspot.com/-tQToG3yhLVI/VPilF8wi8bI/AAAAAAAABOw/ERDwjCoD36c/s1600/Screen%2BShot%2B2015-03-05%2Bat%2B11.32.32%2BPM.png)

The source [code of this project is available on GitHub](https://github.com/dedunumax/hello-webscript).
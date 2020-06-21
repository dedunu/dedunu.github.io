---
layout: post
title: 'Alfresco: Calculate folder size using Java based WebScript'
date: '2015-03-04T20:07:00.001+02:00'
author: Dedunu Dhananjaya
tags:
- webscript
- Java
- recursive
- folder
- alfresco
permalink: /2015/03/alfresco-calculate-folder-size-using.html
---
I was assigned to a training task to write a web script for calculating the size of a folder or a file. But you need to go through all the nodes recursively. If you don't calculate it recursively in folders you won't get accurate folder size.  

Requirements:  

*   Java Development Kit 1.7 or later
*   Text Editor or IDE (Eclipse/Sublime Text/Atom)
*   Apache Maven 3 or later
*   Web Browser (Chrome/Firefox/Safari)
  
For this project, I generated the [Alfresco 5 All-in-One maven project](http://www.dedunu.info/2015/01/how-to-generate-alfresco-5-amp-project.html). You really don't want Alfresco  Share module in this project. But I included it because you may need to find a NodeRefId. It would be easier with Share.  The source [code of this project is available at GitHub](https://github.com/dedunumax/filesize-webscript).

size.get.html.ftl
{% gist 20a17d08c6efe1f2314f %}

size.get.desc.xml
{% gist e131cbf9aaef1ffc4e60 %}

FileSizeWebScript.java
{% gist be88aaf300dac7a19ed9 %}

service-context.xml 
{% gist 3bb550ce1c3250613519 %}

Create above files in below locations of your maven project. 

*   size.get.desc.xml - `repo-amp/src/main/amp/config/alfresco/extension/templates/webscripts/org/dedunu/alfresco/size.get.desc.xml`
*   size.get.html.ftl - `repo-amp/src/main/amp/config/alfresco/extension/templates/webscripts/org/dedunu/alfresco/size.get.html.ftl`
*   FileSizeWebScript.java - `repo-amp/src/main/java/org/dedunu/alfresco/FileSizeWebScript.java`
*   service-context.xml - `repo-amp/src/main/amp/config/alfresco/module/repo-amp/context/service-context.xml`

**How to test the web script?**  

Take a terminal. Navigate to project folder. And type below command.

```console
$ mvn clean install -Prun -Dmaven.test.skip
```

It may take a while to start the Alfresco Repository and Share server. Wait till it finishes completely. 

Then open a web browser and go to [http://localhost:8080/share](http://localhost:8080/share). Then login. Go to Document library.

![](http://1.bp.blogspot.com/-3XALkt-WA60/VPdII_SUDjI/AAAAAAAABOM/UJjeLuRVu80/s1600/Screen%2BShot%2B2015-03-04%2Bat%2B11.25.58%2BPM.png)

Find a folder and click on "View Details". Then copy NodeRef from browser as shown below.

![](http://1.bp.blogspot.com/-VmlsYQdXa8E/VPdIaq0IucI/AAAAAAAABOU/4pukMQMRmE8/s1600/Screen%2BShot%2B2015-03-04%2Bat%2B11.26.05%2BPM.png)

Open a new tab and type below URL. (Replace <NodeRef> with the NodeRef you copied from Alfresco Share interface.)

[http://localhost:8080/alfresco/s/size?nodeRef=<NodeRef>](http://localhost:8080/alfresco/s/size?nodeRef=%3CNodeRef%3E)

If you have followed the instruction properly, you will get a page like below.

![](http://4.bp.blogspot.com/-09zxIR-N5dg/VPdJHJXr5pI/AAAAAAAABOc/EsSsf7swrLc/s1600/Screen%2BShot%2B2015-03-04%2Bat%2B11.25.34%2BPM.png)

If you have any questions regarding these examples, please comment!!! Enjoy Alfresco!
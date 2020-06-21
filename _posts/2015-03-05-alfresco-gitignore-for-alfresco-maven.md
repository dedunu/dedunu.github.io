---
layout: post
title: 'Alfresco: .gitignore for Alfresco Maven Projects'
date: '2015-03-05T11:39:00.002+02:00'
author: Dedunu Dhananjaya
tags:
- Java
- ".gitignore"
- git
- maven
- alfresco
permalink: /2015/03/alfresco-gitignore-for-alfresco-maven.html
---

If you are an Alfresco developer, you have to develop projects using Alfresco AMP modules. Previously Alfresco has used Ant to build projects. But latest Alfresco SDK is using Apache Maven. AMP maven projects generate a whole lot of temporary files. Those files you don't want in your version control system. 

Nowadays almost everyone is using Git. If I say Git is the most popular version control system today, I hope a lot of people would agree on that. In Git you can use the .gitignore file to mention what are the files that should not add to the repository. So if you mention the patterns on .gitignore, Git won't commit unwanted files. For that, you need a good .gitignore file. [Last year I wrote a blog post which has almost all the file patterns which you should emit from Java project](http://www.dedunu.info/2014/11/gitignore-file-for-java.html).

{% gist f0187881ea0f140d8889 %}

You can create a file called .gitignore on the root folder of your Git repository. Then copy the above content and add it to that file. After that commit that files into your Git repository. Now you don't have to worry about unwanted files.
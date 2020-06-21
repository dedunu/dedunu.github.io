---
layout: post
title: Apache Spark Job with Maven
date: '2016-05-14T20:34:00.000+03:00'
author: Dedunu Dhananjaya
tags:
- spark
- maven
permalink: /2016/05/apache-spark-job-with-maven.html
---

Today, I'm going to show you how to write a sample word count application using Apache Spark. For dependency resolution and building tasks, I'm using Apache Maven. However, you can use the SBT (Simple Build Tool). Most of the Java Developers are familiar with Maven. Hence I decided to show an example using Maven.

![screenshot1](https://2.bp.blogspot.com/-jgujxNN9trY/VzdeSKN0zZI/AAAAAAAAEpU/BawLrDYLdeUdM1lNybxr56vt4AgD_A7TACLcB/s1600/Screenshot%2Bfrom%2B2016-05-14%2B22-33-46.png)

This application is pretty much similar to the WordCount Example of the Hadoop. This job exactly does the same thing. Content of the Drive.scala is given below.

{% gist 749a390d97fd20bf0991402c0b29d7a2 %}

This job basically reads all the files in the input folder. Then tokenize every word from space ("` `"). Then count each and every word individually. Moreover, you can see that the application is reading arguments from the args variable. The first argument will be the input folder. The second argument will be used to dump the output.

Maven projects need a `pom.xml`. Content of the `pom.xml` is given below.

{% gist bcf6282d76341ea7b4ae1dd644b46245 %}

Run below command to build the Maven project:

```console
$ mvn clean package
```

Maven will download all the dependencies and all the other stuff on behalf of you. Then what you need to do is run this job. To run the job, please run below command on your terminal window.

```console
$ /home/dedunu/bin/spark-1.6.1/bin/spark-submit        \
     --class org.dedunu.datascience.sample.Driver      \
     target/sample-Spark-Job-jar-with-dependencies.jar \
     /home/dedunu/input                                \
     /home/dedunu/output
```

![screenshot2](https://2.bp.blogspot.com/-eO9vk8dFGhs/VzdegIqnPvI/AAAAAAAAEpY/aB2fO2rJVMMGXN1sIn9x0AyB-kdbRi0jwCLcB/s1600/Screenshot%2Bfrom%2B2016-05-14%2B22-33-12.png)

![screenshot3](https://2.bp.blogspot.com/-pCM8s7VSVsg/VzdekrBIyFI/AAAAAAAAEpc/MeUD8-wqaFsdNRqFDFOKhnZNVv1r2t5BgCLcB/s1600/Screenshot%2Bfrom%2B2016-05-14%2B22-33-21.png)

The output of the job will look like below.

![screen4](https://4.bp.blogspot.com/-wXLzu0vhRoo/Vzde-1QNXaI/AAAAAAAAEpk/SIrowk_0DKs9_32UDShcxIPrAEifN2sLgCLcB/s1600/Screenshot%2Bfrom%2B2016-05-14%2B22-52-26.png)

You can find the project on Github - [https://github.com/dedunu/spark-example](https://github.com/dedunu/spark-example)

Enjoy Spark!
---
layout: post
title: Hadoop MultipleInputs Example
date: '2015-05-21T13:24:00.000+03:00'
author: Dedunu Dhananjaya
tags:
- MultipleInputs
- custom RecordReader
- hadoop
- custom InputFormat
permalink: /2015/05/hadoop-multipleinputs-example.html
---

Let's assume you are working for ABC Group. And they have ABC America airline,  ABM Mobile, ABC Money, ABC Hotel, etc. ABC this and that. So you got multiple data sources. They have different types/columns. So you can't run single Hadoop Job on all the data.

You got several data files from all these businesses.

{% gist 132f2751c794342de53a %}

(Edited this data file 33 times to get it aligned. ;) Don't tell anyone!)

So your job is to calculate the total amount that one person spent for ABC group. For this, you can run jobs for each company and then run another job to calculate the sum. But what I'm going to tell you is "NOOOO! You can do this with one job." Your Hadoop administrator will love this idea.

You need to develop custom InputFormat and a custom RecordReader. I have created both of these classes inside the custom InputFormat class. Sample InputFormat should look like below.

{% gist 96594b09d0f566e88ced %}

`nextKeyValue()` method is the place where you should code according to your data files.

Developing custom `InputFormat` classes is not just enough. Also, you need to change the `main` class in your job. Your `main` class should look like below.

{% gist f55f928250b85f9fc801 %}

Line no. `26-28` adds your custom inputs to the job. Also, you don't want to set the Mapper class separately because you can't set it too. If you want you can develop separate mapper classes for your different file types. I'll write a blog post about that method also.
To build the JAR from my sample project you need Maven. Run below command to build JAR from Maven project. You can find the JAR file inside the target folder once you build the project.

```console
$ mvn clean install
```

```
/
|----/user
     |----/hadoop
          |----/airline_data
          |    |----/airline.txt
          |----/book_data
          |    |----/book.txt
          |----/mobile_data
               |----/mobile.txt
```

With this change, you may have to change the way you run the job. My file structure looks like above. I have different folders for different types. You can run the job from the command below.

```console
$ hadoop jar /vagrant/muiltiinput-sample-1.0-SNAPSHOT.jar /user/hadoop/airline_data /user/hadoop/book_data /user/hadoop/mobile_data output_result
```

If you have followed all the steps properly you will get a job's output like this.

{% gist 8dbd361316c49fcb1fc2 %}

The job will create a folder called output_result. If you want to see the content you can run below command.

```console
$ hdfs dfs -cat output_result1/part*
```

I ran my sample project on my sample data set. My result file looked like below.

```
12345678 500
23452345 937
34252454 850
43545666 1085
56785678 709
67856783 384
```

Source code of this project is available on [GitHub](https://github.com/dedunu/hadoop-multiinput-sample)

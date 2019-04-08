---
layout: post
title: "Open edX student grades download issue (404 Not\_Found)"
date: 2018-11-16
description: >-
  In this post, i will share about how to fix student data generation of Open
  edX Not Found. This problem occurs when we don’t use s3 as to save student
  data generation. To fix this problem we have to…
image: /assets/images/openedx-grade-download-problem.png
headerImage: false
author: Dwi Sulfahnur
tags:
  - E-Learning
  - Open edX
  - NginX
---

In this post, i will share about how to fix student data generation of Open edX **Not Found.** This problem occurs when we don’t use **s3** as to save student data generation.

To fix this problem we have to create a link to true location of **.csv** file (**/tmp/edx-s3/grades**) in **/edx/var/edxapp/media** directory by typing the following command.
```bash
$ ln -s /tmp/edx-s3/grades /edx/var/edxapp/media
```
Then, update nginx VirtualHost configuration of lms (**/edx/app/nginx/sites-avaliable/lms**). Find the following codes on the file:
```bash
location ~ ^/media/(?P<file>.\*) {  
    root /edx/var/edxapp/media;  
    try\_files /$file =404;  
    expires 31536000s;  
}
```

then update it with the following codes:

```bash
location ~ ^/media/(?P<file>.\*) {  
    root /edx/var/edxapp/media;  
    try\_files /$file /grades/$file;  
    expires 31536000s;  
}

location ~ ^/grades/(?P<file>.\*) {  
    root /edx/var/edxapp/media/grades;  
    try\_files /$file =404;  
    expires 31536000s;  
}
```

Restart the nginx service

```bash
$ sudo service nginx restart
```

Done 😎


[Canonical link](https://medium.com/@dwisulfahnur/open-edx-student-grades-download-issue-404-not-found-3d7995980389)

Exported from [Medium](https://medium.com) on April 6, 2019.
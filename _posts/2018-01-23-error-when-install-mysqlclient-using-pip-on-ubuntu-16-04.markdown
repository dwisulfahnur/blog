---
layout: post
title: "Error when install mysqlclient using pip on ubuntu 16.04"
date: 2018-01-23
description: Error when install mysqlclient using pip
image: /assets/images/mysql-python.png
headerImage: false
author: Dwi Sulfahnur
tags:
  - github
  - ssh keys
  - ubuntu
---
error:
```Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-build-5LHWML/mysqlclient/```

A few days ago i did deploy a django project to ubuntu server. I found a problem when installing the package requirements of this project when installing mysqlclient using pip (Python package manager). This is actually a problem I've fixed before, but I forgot how to fix it. So I think that I have to write how to fix this problem..
This problem caused by mysqlclient package depends to some package in ubuntu ```(libmysqlclient-dev)```. So, let's install it by typing the following command in your Ubuntu CLI.

```$ sudo apt-get install libmysqlclient-dev```

Solved ;-)
---
layout: post
title: "How to use MS SQL as Database Server in Django 2.1"
date: 2018-08-23
description: How to Use MS SQL Azure Database Server in Django 2.1
image: /assets/images/django2-1-mssql.png
headerImage: true
author: Dwi Sulfahnur
tags:
  - Python
  - Django
  - Django2
  - MsSQL
---


#### Install ODBC Driver for MS SQL Server

##### OS X 10.11 (El Capitan), 10.12 (Sierra), 10.13 (High Sierra), and 10.14 (Mojave)
```
$ brew update  
$ brew install -no-sandbox msodbcsql17 mssql-tools  
$ brew tap microsoft/mssql-release [https://github.com/Microsoft/homebrew-mssql-release](https://github.com/Microsoft/homebrew-mssql-release)
```
##### Ubuntu 14.04, 16.04, 17.10 and 18.04
```
$ sudo su
$ curl [https://packages.microsoft.com/keys/microsoft.asc](https://packages.microsoft.com/keys/microsoft.asc) | apt-key add -
$ curl [https://packages.microsoft.com/config/ubuntu/**_{version}_**/prod.list](https://packages.microsoft.com/config/ubuntu/%7Bversion%7D/prod.list) > /etc/apt/sources.list.d/mssql-release.list
$ exit

$ sudo apt-get update 
$ sudo ACCEPT_EULA=Y apt-get install msodbcsql17 
$ sudo ACCEPT_EULA=Y apt-get install mssql-tools 
$ echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
$ echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc 
$ source ~/.bashrc 
$ sudo apt-get install unixodbc-dev

# Adjust the {version} with your ubuntu version (14.04,16.04,17.10,18.04)
```

#### Install Django Pyodbc Azure

Install `django-pyodbc-azure` using pip on the python environment of your djangoapp.
```
pip install django-pyodbc-azure
```
#### **Update Database Configuration**

Update your databases configuration in settings file of the project like the following. Adjust the name, host, user, password, and port parameter with yours.
```
DATABASES = {  
     'default': {  
         'ENGINE': 'sql_server.pyodbc',  
         'NAME': '***',  
         'HOST': '***',  
         'USER': '***',  
         'PASSWORD': '***',  
         'PORT': 1433,  
         'OPTIONS': {  
            'driver': 'ODBC Driver 17 for SQL Server',  
         }  
     }  
}
```
Done 😉

[Canonical link](https://medium.com/@dwisulfahnur/how-to-use-ms-sql-as-database-server-in-django-2-1-42959314e8bb)

Exported from [Medium](https://medium.com) on April 6, 2019.
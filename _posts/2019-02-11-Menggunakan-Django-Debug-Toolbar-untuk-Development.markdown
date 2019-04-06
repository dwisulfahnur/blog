---
layout: post
title: "Menggunakan Django Debug Toolbar untuk Development"
date: 2019-02-11
description: Menggunakan Django Debug Toolbar untuk Development
image: /assets/images/django_toolbar.png
author: Dwi Sulfahnur
tags:
  - Django
  - Django-debug-toolbar
  - Development
---

# Menggunakan Django Debug Toolbar untuk Development

Django Debug Toolbar adalah panel set yang berfungsi untuk menampilkan berbagai informasi debug tentang (requests/respons) suatu halaman.

![](https://cdn-images-1.medium.com/max/800/1*gLVtAu6Yjs3p8-fHJrsPOQ.png)

### **Introduction**

> The Django Debug Toolbar is a configurable set of panels that display various debug information about the current request/response and when clicked, display more details about the panel’s content.

Django Debug Toolbar adalah panel set yang dapat dikonfigurasi yang menampilkan berbagai informasi debug tentang (requests/respons) dari halaman/endpoint yang kita akses dan ketika diklik, menampilkan detail lebih lanjut tentang konten panel.

Menurut saya sendiri fitur yang ada pada django-debug-toolbar sangat membantu dalam proses development.

### **Features**

Pada saat membuat postingan ini, saya menggunakan django-debug-toolbar versi 1.11 dengan beberapa panel fitur diantaranya sebagai berikut,

*   **Versions.** Menampilkan versi Python, Django, dan django-debug-toolbar yang kita gunakan
*   **Time.** Menampilkan waktu yang digunakan untuk menampilkan halaman/endpoint yang kita akses, baik itu dari sisi server maupun Client yang kita gunakan. berikut merupakan salah satu contoh hasil debug T**imes** dari django-debug-toolbar untuk halaman yang saya akses.

![](https://cdn-images-1.medium.com/max/800/1*AeouyJeR1y4p484qnGMYtQ.png)

Time Tabs of django-debug-toolbar

*   **Settings**. Menu settings akan menampilkan settings file dan daftar flag/variables yang aktif.
*   **Headers**. Menampilkan daftar header pada **request** dan **response** yang kita gunakan untuk mengakses halaman.
*   **Requests.** Menampilkan fungsi/class yang digunakan untuk menampilkan halaman tersebut dan urlName-nya. Tab **Requests** juga menampilkan **Cookies, Session**,  dan **GET/POST data.**
*   **SQL.** Tab SQL akan menampilkan jumlah **Query** yang digunakan untuk menampilkan halaman yang diakses. Tab ini juga akan menampilkan secara detail masing-masing query beserta Timeline Graphic dan waktu eksekusi query tersebut.
*   **Static Files,** Tab Static Files menampilkan static file yang ada pada halaman tersebut seperti css, js, atau images files.
*   **Templates.**
*   **Cache.**
*   **Signals.**
*   **Logging.**


### **Installation**

Proses instalasi django-debug-toolbar dapat dilakukan dengan menggunakan pip,

**pip install django-debug-toolbar**

Tambahkan sebagai INSTALLED_APPS pada settings.py file:

```
INSTALLED_APPS = [  
    ...  
    'debug_toolbar',  
]
```

Tambahkan ke main urls.py file dari django project,

```
# project/urls.py
...

if settings.DEBUG:  
    import debug_toolbar  
    urlpatterns = [  
        path('__debug__/', include(debug_toolbar.urls)),  
  
        _# For django versions before 2.0:_  
        _# url(r'^__debug__/', include(debug_toolbar.urls)),_  
  
    ] + urlpatterns
```

Tambahkan middleware untuk django-debug-toolbar:
```
MIDDLEWARE [   
    ...  
    'debug_toolbar.middleware.DebugToolbarMiddleware'
]
```

Tambahkan INTERNAL_IPS pada settings file,
```
INTERNAL_IPS = ["127.0.0.1"]
```
Django Debug Toolbar akan ditampilkan hanya jika IP yang mengakses ada pada list di INTERNAL_IPS.

Done 😉

Source: [_https://django-debug-toolbar.readthedocs.io/en/latest/installation.html_](https://django-debug-toolbar.readthedocs.io/en/latest/installation.html#internal-ips)


[Canonical link](https://medium.com/@dwisulfahnur/menggunakan-django-debug-toolbar-untuk-development-fc650be403e5)

Exported from [Medium](https://medium.com) on April 6, 2019.
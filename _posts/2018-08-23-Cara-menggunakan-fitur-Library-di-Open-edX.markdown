---
layout: post
title: "Cara menggunakan fitur Library di Open edX"
date: 2018-08-23
description: Cara menggunakan fitur Library di Open edX
image: /assets/images/openedx-library.png
author: Dwi Sulfahnur
tags:
  - Open edX 
  - Library
  - MOOC
---

# Cara menggunakan fitur Library di Open edX

Fitur Library di Open edX ini digunakan untuk untuk membuat sekumpulan components yang akan digunakan sebagai konten soal pada kursus.

Fitur _Library_ di Open edX ini digunakan untuk untuk membuat sekumpulan _components_ yang akan digunakan sebagai konten soal pada kursus.

Kelebihan dari fitur ini adalah kita dapat menampilkan komponen yang telah kita buat secara acak (**_Random_**) dalam jumlah tertentu. Misalnya kita mempunyai 8 soal yang ada pada Library, kita hanya ingin menampilkan 3 soal secara acak dari 8 soal tersebut ke setiap user.

Berikut merupakan gambar ilustrasi dari skenario diatas.

![](https://cdn-images-1.medium.com/max/800/1*DEi79REPWnYv4ErSds7pdA.png)

Semoga dipahami yah 😅. Selanjutnya kita akan coba untuk membuat _Library_ untuk kursus yang sudah ada.

Pada menu Home Studio, pilih **_New Library_** yang ada pada pojok kanan atas halaman. Anda akan diminta untuk mengisi form yang dibutuhkan.

![](https://cdn-images-1.medium.com/max/800/1*Ypfg86PC04j-VlMBjnM9DA.png)

Create Library

Langkah selanjutnya kita membuat komponen-komponen yang akan kita tambahkan ke _Library_ tersebut. Disini saya menambahkan 6 komponen problem berupa _Multiple Choice_. Selain _Problem Component_, kita juga dapat menambahkan **_Video dan HTML Component_**.

![](https://cdn-images-1.medium.com/max/800/1*P8s4hHRTocw2VfZz6x8AfQ.png)

List Component of the Library

Setelah kita mengisi _Library_ tersebut dengan _Components_, langkah selanjutnya yaitu menerapkan _library_ tersebut ke kursus. Sebelum kita menggunakan Library yang ada pada kursus, kita perlu mengaktifkan Fitur _Library_ pada kursus.

Pada menu **_Settings -> Advanced Settings,_** tambahkan  **_“library\_content”_** pada form input **_Advance Module List._**

![](https://cdn-images-1.medium.com/max/800/1*_X0Heq3o2kGbKaE1wV6RsQ.png)

Activate **Library Content** on the Course Settings

Setelah itu, pilih **_unit_** yang akan anda gunakan untuk menampilkan c_omponents_ yang ada pada _library_ yang telah dibuat. Tambahkan komponen **_Randomized Content Block_** yang ada pada **Advanced Component**

![](https://cdn-images-1.medium.com/max/800/1*5FE8L0DDiZT7DCBQfcX8WQ.png)

Add **_Randomized Content Block_** Component

Setelah **_Randomized Content Block_** dibuat, edit komponen tersebut.

*   **Count,** tentukan jumlah komponen yang akan ditampilkan ke user.
*   **Display Name,** tentukan nama dari komponen tersebut.
*   **Library,** pilih nama Library yang telah anda buat.
*   **Problem Type,** pilih tipe problem yang akan digunakan. Jika ingin menampilkan semua jenis problem anda bisa memilih pilihan default yaitu **“Any Type”.**

![](https://cdn-images-1.medium.com/max/800/1*Bsl2Oug10PrOYY3hH7wE0g.png)

Setup **Randomized Content Block** Component

Jangan lupa klik **“save”** untuk menyimpan pengaturan yang telah dilakukan dan “**Publish**” Unit tersebut.

Untuk melihat hasil dari penggunaan fitur Library ini, anda dapat melihat preview Unit dari kursus tersebut dengan menggunakan user yang berbeda.

![](https://cdn-images-1.medium.com/max/1200/1*WoY1vIFfRAMzfgtsfNNpNQ.png)

(**Left**) Access using staff user. (**Right**) Access using admin user.

Dapat kita lihat pada gambar diatas, kedua user mengakses Unit dan Kursus yang sama dan menampilkan jenis dan urutan dan komponen yang berbeda.

Terimakasih, Semoga bermanfaat 😃

Jika Anda ingin diskusi lebih lanjut tentang Open edX silahkan kontak kami di support@valutac.com

(**Editor RA**)

[Canonical link](https://medium.com/@dwisulfahnur/cara-menggunakan-fitur-library-di-open-edx-c8aea2666633)

Exported from [Medium](https://medium.com) on April 6, 2019.
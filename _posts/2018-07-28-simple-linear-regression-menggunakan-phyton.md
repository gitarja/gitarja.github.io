---
title: Simple Linear Regression Menggunakan Phyton
undefined: SUB TITLE
date: 2018-07-28 10:56:54 +0000
ttitle: Simple Linear Regression Menggunakan Phyton
banner_post: ''
tag: []

---
Nah dipostingan ini saya akan bahas tentang Simple Linear Regression. Simple Linear Regression merupakan salah satu  algoritma supervised, dengan kata lain algoritma ini belajar berdasarkan contoh pada data yang tersedia. Simple Linear Regression dapat memodelkan permasalahan hubungan linear antara sebuah input dan output.

Inti dari Simple Linear Regression adalah menyelesaikan permasalahan garis lurus. Dalam pendekatan ini nilai $$a$$ dan $$b$$ akan didapatkan dari proses learning atau training.

\$$xb + a = y$$

\$$x = input \\\\ y = output \\\\ b = gradient \\\\ a = konstanta $$

Inti dari Simple Linear Regression adalah menyelesaikan permasalahan garis lurus. Dalam pendekatan ini nilai $latex a $ dan $latex b $ akan didapatkan dari proses learning atau training.

## Contoh Permasalahan Simple Linear Regression

Ok langsung saja kita mulai ke contoh kasus. Dalam kasus ini kita akan memodelkan permasalahan mengenai permasalahan asuransi mobil.

Deskripsi data:

* x = Jumlah tuntutan
* y = Total uang yang dibayarkan untuk seluruh tuntutan

Contoh:

* x = 108 tuntutan
* y = $392.5 untuk 108 tuntutan

![Penyebaran data](/assets/DataRelation.png "Penyebaran data")

## Proses Training Simple Linear Regression

Untuk menyelesaikan permasalahan diatas, hal yang perlu kita lakukan adalah menghitung nilai a dan b, hal tersebut dapat diselesaikan dalam lima tahap dibawah ini:

* Hitung nilai rata - rata x dan y

  \$$bar{x} = \\frac{\\sum\\limits_{i=1}^{N} x_i}{N}$$

  \$$\\bar{y} = \\frac{\\sum\\limits_{i=1}^{N} y_i}{N}$$
* Hitung varince data

  \$$var(x) = \\frac{\\sum\\limits_{i=1}^{N} (x_i - \\bar{x})}{N-1}$$
* Hitung covariance data

  \$$cov(x, y) = \\frac{\\sum\\limits_{i=1}^{N} (x_i - \\bar{x})(y_i - \\bar{y})}{N-1}$$
* Hitung nilai $$b$$  

  \$$b = \\frac{cov(x, y)}{var(x)}$$
* Hitung nilai $$a$$

  \$$a = \\bar{y} - b \\bar{x}$$  
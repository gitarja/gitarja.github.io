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

$$xb + a = y$$

$x = input \\ y = output \\ b = gradient \\ a = konstanta$

Inti dari Simple Linear Regression adalah menyelesaikan permasalahan garis lurus. Dalam pendekatan ini nilai $a$ dan $b$ akan didapatkan dari proses learning atau training.

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

$$\bar{x} = \frac{\sum\limits_{i=1}^{N} x_i}{N}$$

$$\bar{y} = \frac{\sum\limits_{i=1}^{N} y_i}{N}$$

* Hitung varince data

$$var(x) = \frac{\sum\limits_{i=1}^{N} (x_i - \bar{x})}{N-1}$$

* Hitung covariance data

$$cov(x, y) = \frac{\sum\limits_{i=1}^{N} (x_i - \bar{x})(y_i - \bar{y})}{N-1}$$

* Hitung nilai $b$

$$b = \frac{cov(x, y)}{var(x)}$$

* Hitung nilai $a$

$$a = \bar{y} - b \bar{x}$$

## Implementasi Proses Training Menggunakan Pyhton

Dalam implementasi ini saya menggunakan dua library pada Pyhton [pandas ](http://pandas.pydata.org/pandas-docs/stable/index.html)dan [numpy](http://www.numpy.org/). Pandas saya gunakan untuk mebaca file csv pada file Data/data.csv dan mengkonversinya menjadi [DataFrame  ](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html)dan numpy saya gunakan untuk melakukan perhitungan statistik data. Oh ia, untuk membaca file csv pada pyhton banyak alternatif lainnya seperti menggunakan [module csv](https://docs.python.org/2/library/csv.html) pada phyton.

{% highlight python %}
#import library pandas dan inisialisasikan menjadi pd
import pandas as pd
#import library numpy dan inisialisasikan menjadi np
import numpy as np

#baca data pada file data.csv dalam folder Data menggunakan pandas
data = pd.read_csv('Data/data.csv')

#assign nilai X (Jumlah Klaim) pada variable x
x = data.X.values

#assign nilai Y (Total Pembayaran) pada variable y
y = data.Y.values

#Bagi data menjadi 2 bagian untuk train dan untuk test

#ambil nilai x dari urutan pertama hingga 10 terakhir (108 - 13)
x_train = x[:-10]
#ambil nilai y dari urutan pertama hingga 10 terakhir (392.5 - 31.9)
y_train = y[:-10]


#ambil 10 data terakhir dari x
x_test = x[-10:]
#ambil 10 data terakhir dari y
y_test = y[-10:]

#hitung nilai rata-rata x dan y
x_mean = np.mean(x_train)
y_mean = np.mean(y_train)


#hitung variance x
x_var = np.var(x_train, ddof=1)

#hitung covariance data
cov = np.cov(np.vstack((x_train, y_train)), ddof=1)[0][1]

#hitung nilai b
b = cov / x_var
#hitung nilai a
a = y_mean - (b * x_mean)
{% endhighlight %}

## Proses Testing Simple Linear Regression
Jika pada proses training kita melakukan perhitungan untuk mencari nilai $a$ dan $b$ pada model. Pada proses testing hal yang akan kita lakukan adalah melakukan prediksi dengan menghitung nilai y

$$y  = xb + a$$

## Implementasi Proses Testing Menggunakan Pyhton
Dalam implementasi ini kita akan menggunkan nilai 10 terakhir dari nilai x yaitu x_test

{% highlight python %}
#y = xb + a
predict = x_test * b + a
{% endhighlight %}

| x_test | predict |
|-------|--------|
| 15 | 64.933 |
| 8 | 41.553 |
| 29 | 111.695 |
| 30 | 115.035 |
| 24 | 94.994 |
| 9 | 44.893 |
| 31 | 118.375 |
| 14 | 61.593 |
| 53 | 191.857 |
| 26 | 101.675 |

## Evaluasi Model
Setelah melakukan proses training dan testing, hal terakhir yang harus kita lakukan adalah mengevaluasi model. Apakah model kita sudah sesuai dengan data yang ada? Dalam proses evaluasi ini saya akan menggunakan formula Root Mean Square Error atau disingkat RMSE

$$RMSE=\sqrt{\frac{\sum\limits_{i=1}^{N}(\hat{y}_i - y_i)}{N}}$$

Dimana $\hat{y}$ adalah nilai prediksi model dan $y$ adalah nilai yang seharusnya. Dengan menggunakan RMSE kita dapat mengetahui nilai rata-rata kesalahan pada model dalam meprediksi nilai total pembayaran untuk sejumlah klaim.

| x_test | predict | y_test | (predict - y_test)^2 |
| ------ |---------| -------| -------------------- |
| 15 | 64.93399 | 32.1 | 1078.07107 |
| 8 | 41.55334 | 55.6 | 197.308783 |
| 29 | 111.6953 | 133.3 | 466.76277 |
| 30 | 115.0354 | 194.5 | 6314.622553 |
| 24 | 94.99484 | 137.9 | 1840.852976 |
| 9 | 44.89343 | 87.4 | 1806.808545 |
| 31 | 118.3755 | 209.8 | 8358.440208 |
| 14 | 61.5939 | 95.5 | 1149.623703 |
| 53 | 191.8576 | 244.6 | 2781.765019 |
| 26 | 101.675 | 187.5 | 7365.926308 |
| <td colspan=3>RMSE =</td> | 56.00016244 |
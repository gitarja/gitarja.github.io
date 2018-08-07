---
title: Training and Testing
undefined: SUB TITLE
date: 2018-08-01 10:56:54 +0000
ttitle: Training and Testing
banner_post: "/assets/online-course.jpg"
tag: []

---

Training dan Testing, secara harafiah berarti latihan dan pengujian. Dalam machine learning saya rasa akan banyak dijumpai dua kata tersebut, training dan testing. Tapi, apakah pengertian training dan testing dalam konteks machine learning sama dengan perngertian secara harafiah?

## **Training tuh.......?**
Dalam konteks machine learning sebenarnya pengertian training tidak jauh berbeda dengan pengertia secara harafiah. Training = latihan. 

### **Pertanyaan pertama, siapa sih yang latihan?**
Yang jelas sih bukan Duta Cubit yang latihan dicubit. Tapi yang latihan adalah algoritma machine learning.

### **Pertanyaan kedua, bagaimana machine learning latihan?**
Algoritma machine learning akan merubah parameter pada dirinya untuk menyesuaikan dengan data yang diberikan saat latihan. Sama seperti otak manusia, dimana synapse akan melakukan perubahan saat manusia belajar.

### **Pertanyaan ketiga, kenapa harus latihan?**
ya tentu jawabaannya agar pintar, jadi machine learning akan latihan atau belajar dari data yang diberikan untuk dapat memahami informasi pada data tersebut.

Contoh: kita akan membuat sebuah aplikasi yang dapat mengenali mangga dan jeruk, maka kita memberi gambar - gambar mangga dan jeruk kepada machine learning tersebut, yang selanjutnya akan dipelajari oleh algoritma machine learning hingga algoritma tersebut dapat mengerti mana yang mangga dan mana yang jeruk. Data yang digunakan dalam proses training atau learning disebut training set.

### **Pertanyaan keempat, tipe belajaranya seperti apa ya?**
Secara umum terdapat tiga tipe belajar, supervised, unsupervised, dan semi-unsupervised.

1. Supervised
	- input data (training data) memiliki label
	- belajar berdasarkan contoh
2. Unsupervised
	- input data tidak memiliki label
	- belajar bedasarkan struktur data
3. Semi-unsupervised
	- input data terdiri dari data berlabel dan tidak
	- belajar bedasarkan contoh dan struktur data

## **Testing tuh apa sih?**
Setelah proses training dilakukan pada sebuah algoritma Machine Learning, tahap selanjutnya adalah melakukan evaluasi terhadap performa algoritma tersebut atau biasa disebut testing. Pada proses testing, performa algoritma akan diuji menggunakan testing set, dimana testing set dan training set merupakan data yang berbeda.

Sebuah algoritma machine learning dengan performa yang tinggi akan dapat mengkategorisasikan dengan benar data baru, yang berbeda dengan yang digunakan dalam proses training. Kondisi tersebut dikenal dengan generalisasi, semakin tinggi generalisasi dari sebuah algoritma makan akan semakin tinggi recognition rate-nya.

Contoh Pengujian Algoritma Klasifikasi:

Note:

- Biasanya untuk pengujian klasifikasi digunakan skema yang lebih kompleks seperti k-folds cross validation.
- Gambar dibawah ini adalah contoh pengujian sederhana algoritma klasifikasi.
- Tingkat kesalahan prediksi algortima diukur menggunakan [Root Mean Square Error.](https://www.kaggle.com/docs)


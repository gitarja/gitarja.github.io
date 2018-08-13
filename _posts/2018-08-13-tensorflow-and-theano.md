---
title: Installasi Tensorflow
undefined: SUB TITLE
date: 2018-08-13 10:56:54 +0000
ttitle: Tensorflow
banner_post: "/assets/tensorflow.jpg"
tag: []

---

## **Tensorflow?**

<p align="center"><img width="200px" height="auto" src="/assets/tensorflow.jpg"></p>

Tensorflow (TF) merupakan open-source library yang diperuntukan untuk numerical computation. Awal pengembangan TF dilakukan oleh researchers dan engineers Google brain. TF merupakan library yang cukup fleksibel dikarenakan dapat dijalankan pada berbagai jenis platform seperti CPUs, GPUs, dan TPUs. Lebih dari itu, TF juga mensupport bahasa pemograman Python, Java, Go, dan C.

Hingga saat ini TF banyak digunakan dalam pengembangan aplikasi machine learning seperti speech recognition, object recognition, dan language translation. Dikarenakan TF mensupport multiple GPU, banyak aplikasi deep learning, yang melibatkan komputasi yang cukup kompleks, diimplementasi menggunakan TF.

Pada postingan kali ini saya akan menjelaskan langkah-langkah untuk menginstall TF pada Windows. Okay sebelum menginstall TF pastikan bahwa python telas terisntall di komputer anda. Untuk instalasi python dapat dilihat [disini]({{ site.baseurl }}{% post_url 2018-07-28-langkah-pertama-menuju-machine-learning-edisi-praktisi %}).

## **Instalasi Tensorflow**
Okay sebelum menginstall TF langkah pertama adalah menentukan jenis TF yang akan diinstall, CPUs-support atau GPUs-support. Hal ini dikarenakan langkah penginstallan dari setiap jenis berbeda.
1. **Installasi CPUs-support TF** lebih mudah dibandingkan GPU-support. Jika pada komputer anda tidak terdapat NVIDIA® GPU yang disupport oleh TF lebih baik untuk menginstall CPUs-support TF.
2. **Installasi GPUs-support TF** membutuhkan langkah yang sedikit lebih rumit. Akan tetapi performa TF dengan GPUs jauh lebih cepat dibanding dengan TF dengan CPUs. Ada beberapa requirements yang harus dipenuhi sebelum menginstall GPUs-support TF.

### **Requirement untuk menginstall GPUs-support TF**
* CUDA® Toolkit 9.0. Keterangan lebih lanjut dapat dilihat [disini](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/). Pastikan bahwa pada saat menginstall CUDA® Toolkit, folder installasi ditambahkan pada ```%PATH%``` environment windows.
* NVDIA driver yang disupport oleh CUDA® Toolkit yang terinstall.
* cuDNN v7.0. Keterangan lebih lanjut dapat dilihat [disini](https://developer.nvidia.com/cudnn). *Note:* untuk mendownload cuDNN anda harus melakukan registrasi terlebih dahulu.
* GPU card yang mensupport CUDA. Keterangan lebih lanjut dapat dilihat [disini](https://developer.nvidia.com/cuda-gpus).

## **Installasi Tensorflow menggunakan Python**
Untuk memudahkan pengorganisian package TF akan diinstall menggunakan Anaconda. Apa itu Anaconda dan bagaimana menginstall Anaconda silahkan merujuk kepostingan [ini]({{ site.baseurl }}{% post_url 2018-07-28-langkah-pertama-menuju-machine-learning-edisi-praktisi %}).
1. Langkah pertama adalah membuka ```Anaconda Prompt``` dan ketikan command dibawah ini untuk membuat environment dimana kita akan gunakan untuk menginstall TF. (Rekomendasi versi Python untuk TF:3.5)
```
conda create -n tf pip python=3.5
```
2. Setelah berhasil membuat environment, langkah selanjutnya adalah mengaktifkan environment tersebut dengan command.
```
activate tf
```
3. Setelah itu kita dapat menginstall TF dengan menggunakan PIP
Untuk menginstall CPUs-support TF.
```
pip install --ignore-installed --upgrade tensorflow
```
Untuk menginstall GPUs-support TF.
```
pip install --ignore-installed --upgrade tensorflow-gpu
```


## **Memastikan installasi Tensorflow**
Okay ini adalah langkah terakhir untuk memastikan bahwa TF telah terinstall. Pertama bukan ```Anaconda Prompt``` dan aktifkan python dengan mengetikan

```
python
```

Setelah itu tuliskan kode dibawah ini untuk memastikan bahwa installasi TF telah berhasil

```python
import tensorflow as tf
hello = tf.constant('Halo, ini Tensorflow')
sess = tf.Session()
print(sess.run(hello))
```

Jika tidak terdapat permasalahan pada proses intallasi maka output dari kode diatas adalah

```
Halo, ini Tensorflow
```

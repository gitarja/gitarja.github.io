---
title: Implementasi Alex Net Menggunakan Tensorflow dengan Eager Execution
undefined: SUB TITLE
date: 2019-07-18 15:19:54 +0000
ttitle: Implementasi Alex Net Menggunakan Tensorflow dengan Eager Execution
tag: []
categories: bahasa

---

# **AlexNet**
Merupakan sebuah deep neural network model yang diusulkan oleh  Alex Krizhevsky, Ilya Sutskever, dan Geoffrey E. Hinton. AlexNet memenangkan kompetisi ImageNet Large Scale Visual Recognition Challenge (ILSVRC-2012) pada task klasifikasi dan deteksi dengan tingkat kesalahan sebesar 15.3%. AlexNet menggunakan Convolutional Neural Network (CNN) dan Feed Forward neural network untuk mengklasifikasikan gambar kedalam 1000 kategori.

Dikarenakan deep arsitektur pada AlexNet, proses training membutuhkan waktu yang cukup lama. Oleh karena itu, pada implementasinya AlexNet menggunakan GPU daripada CPU sehingga proses training dapat dipercepat. Selain CNN dan Feedforward, teknik seperti **augmentasi gambar** dan **local response normalization** juga digunakan dalam proses training untuk meningkatkan generalisasi performa dari AlexNet.

Dalam artikel ini, saya akan mengimplementasikan AlexNet menggunakan TensorFlow(TF) dengan eager execution untuk mengklasifikasikan gambar pada CIFAR10 dataset kedalam 10 kategori. Struktur network pada implementasi ini adalah modifikasi dari AlexNet. Modifikasi dilakukan dikarenakan ukuran gambar pada CIFAR10 lebih kecil, 32x32 pixels, dibanding dengan ukuran gambar pada ILSVRC(2012).

##**CIFAR10**

##**Arsitektur AlexNet**

##**Augmentasi Gambar**

##**Local Response Normalization**

##**Implementasi**
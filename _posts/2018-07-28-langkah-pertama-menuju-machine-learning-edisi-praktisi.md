---
layout: post
title: Langkah Pertama Menuju Machine Learning (Edisi Praktisi)
undefined: ''
date: 2018-07-28 00:00:00 +0000
ttitle: Langkah Pertama Menuju Machine Learning (Edisi Praktisi)
banner_post: "/assets/paket.jpg"
tag: []

---
Mungkin kata Machine Learning sudah familiar bagi mahasiswa ilmu komputer atau teknik informatika, atau bahkan siswa SMA. Singkatnya Machine Learning adalah bidang ilmu komputer yang membuat sebuah komputer dapat belajar berdasarkan data yang diberikan.

Saya rasa Machine Learning sudah populer dikalangan akademis saat ini, namun belakangan masyrakat umum pun sudah mengetahui tentang machine learning dari film - film science fiction. Dalam mempelajari Machine Learning ada dua pendekatan (pendapat sendiri), dimulai dari mempelajari teori atau langsung ke praktiknya. Kebetulan sebelum mengenal Machine Learning saya bekerja partime sebagai programmer, jadi lebih mudah untuk mempelajari Machine Learning langsung ke praktiknya. Intinya sih memahami teori dari oprek - oprek program orang.

Nah untuk belajar Machine Learning, ada beberapa bahasa pemograman yang populer dikalangan Scientific Programmer.

1. [R ](https://www.r-project.org/) ([https://www.r-project.org/](https://www.r-project.org/ "https://www.r-project.org/"))
2. [Matlab](http://www.mathworks.com/) ([http://www.mathworks.com/](https://www.r-project.org/ "https://www.r-project.org/"))
3. [Phyton](https://www.python.org/) ([https://www.python.org/](https://www.r-project.org/ "https://www.r-project.org/"))
4. [Julia ](http://julialang.org/) ([http://julialang.org/](https://www.r-project.org/ "https://www.r-project.org/"))

Untuk setiap bahasa pemograman ada kelebihan dan kekurangannya sendiri - sendiri, jadi kalau mau tau lebih detil bisa mampir ke websitenya masing-masing. Kalau pilihan saya sih Phyton. Alasannya banyak, tapi yang paling utama karena komunitas Phyton yang sudah stable dan terdapat banyak scientific library.

# **Butuh apa saja untuk mulai?**

![Paket Hot Scientific Programmer](/assets/paket.jpg "Paket Hot Scientific Programmer")
Ini paket kesukaan saya, alasannya sih gak ribet. Jadi Phyton + Anaconda Distribution (di package ini udah ada Phytonnya juga, jadi gak perlu download lg) + PyCharm (IDE).

Untuk IDE bisa banyak pilihan, yang suka pake notepad++ monggo, emacs juga bisa.

# **Anaconda?**

Mungkin ketika dengar anaconda kebayang tentang ular dari sungai amazon yang bisa makan manusia. Tp Anaconda yang ini beda, Anaconda adalah phyton distribution yang terdiri lebih dari 400 phyton package untuk science, math, engineering, dan data analysis. Sebenarnya tidak semua package akan dipakai, tapi lebih mudah untuk menggunakan Anaconda karena untuk setiap package sudah terdapat depedencies-nya juga.

# **Install apa ya pertama?**

Nah pertama download dulu Anaconda, untuk yang belum install Phyton pakai Anaconda udah langsung dapet kok, dan yang sudah install Phyton di komputernya gak perlu takut, karena gak akan bentrok.

Untuk mendownload anaconda bisa mampir ke website ini ([https://www.continuum.io/downloads](https://www.continuum.io/downloads "https://www.continuum.io/downloads")), kalau PyCharm bisa liat disini ([https://www.jetbrains.com/pycharm/download/](https://www.continuum.io/downloads "https://www.continuum.io/downloads")), kalau yang punya duit boleh pakai yg Professional, kalau saya sih yang Community.

Oh ia untuk langkah - langkah installasinya, pertama Anaconda dulu baru PyCharm, phyton base foldernya akan otomatis terbaca oleh PyCharm.

# **Project Pertama**

Ok kalau sudah install Anaconda dan PyCharm bisa langsung dicoba, nah untuk buat project baru tinggal klik Create New Project trus tentuin mau disimpan difolder apa.

\*lokasi interpreter sudah otomatis terbaca kok sama PyCharm, kalau ada 2 Phyton bisa diubah lokasi interpreternya.

![Tampilan awal PyCharm](/assets/pycharm.jpg "Tampilan awal PyCharm")

Setelah buat project, kita buat Phyton file baru

![](/assets/firstfile.png)

Ok bisa langsung dicoba untuk script dibawah ini (saya anjurkan untuk ketik ulang agar paham setiap barisnya)

> import numpy as np
>
> import matplotlib.pyplot as plt
>
> x = np.arange(-1, 1, 0.05)
>
> y = np.cos(x)
>
> plt.plot(x, y)
>
> plt.show()

![](/assets/graph.png)

Nah kalau outputnya sesuai dengan grafik diatas, maka kalian sudah siap untuk belajar machine learning. Oh ia saya anjurkan juga untuk mengambil beberapa online course untuk memudahkan memahami teori machine learning, untuk daftar online course bisa lihat di post ini.
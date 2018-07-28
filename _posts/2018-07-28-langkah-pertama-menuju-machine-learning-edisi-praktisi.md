---
layout: post
title: Langkah Pertama Menuju Machine Learning (Edisi Praktisi)
undefined: ''
date: 2018-07-28 04:38:38 +0000
ttitle: Langkah Pertama Menuju Machine Learning (Edisi Praktisi)
banner_post: ''
tag: []

---
<p style="text-align: justify;">
    Mungkin kata Machine Learning sudah familiar bagi mahasiswa ilmu komputer atau teknik informatika, atau bahkan siswa SMA. Singkatnya Machine Learning adalah bidang ilmu komputer yang membuat sebuah komputer dapat belajar berdasarkan data yang diberikan.
</p>
<h6 style="text-align: justify;"></h6>
<!--more-->
<p style="text-align: justify;">Saya rasa Machine Learning sudah populer dikalangan akademis saat ini, namun belakangan masyrakat umum pun sudah mengetahui tentang machine learning dari film - film science fiction. Dalam mempelajari Machine Learning ada dua pendekatan (pendapat sendiri), dimulai dari mempelajari teori atau langsung ke praktiknya. Kebetulan sebelum mengenal Machine Learning saya bekerja partime sebagai programmer, jadi lebih mudah untuk mempelajari Machine Learning langsung ke praktiknya. Intinya sih memahami teori dari oprek - oprek program orang.</p>
<p style="text-align: justify;">Nah untuk belajar Machine Learning, ada beberapa bahasa pemograman yang populer dikalangan Scientific Programmer.</p>

<ol>
	<li><a href="https://www.r-project.org/">R </a> (<a href="https://www.r-project.org/" target="_blank" rel="noopener">https://www.r-project.org/</a>)</li>
	<li><a href="http://www.mathworks.com/" target="_blank" rel="noopener">Matlab</a> (<a href="http://www.mathworks.com/" target="_blank" rel="noopener">http://www.mathworks.com/</a>)</li>
	<li><a href="https://www.python.org/" target="_blank" rel="noopener">Phyton</a> (<a href="https://www.python.org/" target="_blank" rel="noopener">https://www.python.org/</a>)</li>
	<li><a href="http://julialang.org/">Julia </a> (<a href="http://julialang.org/" target="_blank" rel="noopener">http://julialang.org/</a>)</li>
</ol>
<p style="text-align: justify;">Untuk setiap bahasa pemograman ada kelebihan dan kekurangannya sendiri - sendiri, jadi kalau mau tau lebih detil bisa mampir ke websitenya masing-masing. Kalau pilihan saya sih Phyton. Alasannya banyak, tapi yang paling utama karena komunitas Phyton yang sudah stable dan terdapat banyak scientific library.</p>

<h2>Butuh apa saja untuk mulai?</h2>
![Paket Hot Scientific Programmer](/assets/paket.jpg){:class="img-responsive"}
<p>Ini paket kesukaan saya, alasannya sih gak ribet. Jadi Phyton + Anaconda Distribution (di package ini udah ada Phytonnya juga, jadi gak perlu download lg) + PyCharm (IDE).

Untuk IDE bisa banyak pilihan, yang suka pake notepad++ monggo, emacs juga bisa.</p>


<h2>Anaconda</h2>
<p style="text-align: justify;">
Mungkin ketika dengar anaconda kebayang tentang ular dari sungai amazon yang bisa makan manusia. Tp Anaconda yang ini beda, Anaconda adalah phyton distribution yang terdiri lebih dari 400 phyton package untuk science, math, engineering, dan data analysis. Sebenarnya tidak semua package akan dipakai, tapi lebih mudah untuk menggunakan Anaconda karena untuk setiap package sudah terdapat depedencies-nya juga.
</p>
<h2>Install apa ya pertama?</h2>
<p style="text-align: justify;">Nah pertama download dulu Anaconda, untuk yang belum install Phyton pakai Anaconda udah langsung dapet kok, dan yang sudah install Phyton di komputernya gak perlu takut, karena gak akan bentrok. Untuk mendownload anaconda bisa mampir ke website ini (<a href="https://www.continuum.io/downloads" target="_blank" rel="noopener">Anaconda</a>). Kalau PyCharm bisa liat disini (<a href="https://www.jetbrains.com/pycharm/download/" target="_blank" rel="noopener">pycharm</a>), kalau yang punya duit boleh pakai yg Professional, kalau saya sih yang Community.</p>
<p style="text-align: justify;">Oh ia untuk langkah - langkah installasinya, pertama Anaconda dulu baru PyCharm, phyton base foldernya akan otomatis terbaca oleh PyCharm.</p>

<h2>Project Pertama</h2>
<p style="text-align: justify;">Ok kalau sudah install Anaconda dan PyCharm bisa langsung dicoba, nah untuk buat project baru tinggal klik Create New Project trus tentuin mau disimpan difolder apa.

*lokasi interpreter sudah otomatis terbaca kok sama PyCharm, kalau ada 2 Phyton bisa diubah lokasi interpreternya.</p>
![Tampilan awal PyCharm](/assets/pycharm.jpg){:class="img-responsive"}
<p style="text-align: justify;">Setelah buat project, kita buat Phyton file baru</p>
![Tampilan awal PyCharm](/assets/firstfile.png){:class="img-responsive"}
<p>Ok bisa langsung dicoba untuk script dibawah ini (saya anjurkan untuk ketik ulang agar paham setiap barisnya)</p>

{% highlight python %}
import numpy as np
import matplotlib.pyplot as plt

x = np.arange(-1, 1, 0.05)
y = np.cos(x)

plt.plot(x, y)
plt.show()
{% endhighlight %}
<p style="text-align: justify;"> Jika tidak ada error makan akan muncul graph dibawah ini </p>


<p style="text-align: justify;">Nah kalau outputnya sesuai dengan grafik diatas, maka kalian sudah siap untuk belajar machine learning. Oh ia saya anjurkan juga untuk mengambil beberapa online course untuk memudahkan memahami teori machine learning, untuk daftar online course bisa lihat di post ini.</p>
![Output grafik](/assets/graph.png){:class="img-responsive"}
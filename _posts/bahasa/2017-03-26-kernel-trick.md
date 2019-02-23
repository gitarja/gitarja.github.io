---
title: Kernel Trick
undefined: SUB TITLE
date: 2017-03-26 12:56:54 +0000
ttitle: Kernel Trick
tag: []
categories: bahasa

---

# **Apakah Kernel itu?**

Kernel? pada postingan ini saya akan menshare tentang kernel. Kernel yang saya maksud bukanlah kernel pada linux, akan tetapi pada konteks Machine Learning. Ide dasar pada penggunaan kernel pada machine learning adalah jika point negatif dan positif pada dimensi $$ \mathbb{R}^N $$ tidak dapat dipisahkan, maka transform fitur tersebut ke $$ \mathbb{R}^M $$ ($$ M > N $$) dimana point negatif dan positif dapat dipisahkan. Inti dari kernel trick adalah mentransformasi low-dimensional fitur ke higher-dimensional fitur.

Secara matematik, kernal adalah inner produk dari beberapa fitur map.

$$ K(x,y) = <\phi(x), \phi(y)> $$

Contoh:

Jika kita ingin memprediksi harga smart phone berdasarkan variable:

$$ x_1 = merek $$
$$ x_2 = model $$

$$ x = [x_1, x_2]$$

Dengan linear model kita dapat menuliskan permasalahan diatas menjadi

$$ harga = \beta_0 + \beta_1  x_1 + \beta_2  x_2$$

Namun kita juga dapat memodelkan permasalahan diatas dalam model non linear, contoh: polynominal model

$$ harga = \beta_0 + \beta_1 {x_1}^4 + \beta_2  {x_2}^4 + \beta_3  4(x_1 x_2)$$

$$ harga = \beta (x^Tx)^T(x^Tx)$$

$$ harga = \beta<\phi(x), \phi(x)>$$

Dimana $$ \phi(x) = (x^Tx)$$ dan $$ <\phi(x), \phi(x)> $$ adalah kernel, inner produk dari $$ \phi(x)$$, yang mentransform fitur x dari $$ \mathbb{R}^2 $$ ke $$ \mathbb{R}^3 $$.

# **Keuntungan dan Kelemahan Kernel Trick**
* Keuntungan
	* Pemilihan kernel yang tepat akan meningkatkan performa machine learning
	* Transformasi low-dimensional fitur ke high-dimensional fitur memungkinkan untuk 		menyelesaikan permasalahan dengan berbagai model
* Kelemahan
	* Semakin besar dimensi suatu fitur maka semakin tinggi resource yang diperlukan 	dalam komputasi
	* Tidak terdapatnya ketentuan yang baku untuk menentukan jenis kernel dan nilai 	parameter kernel, sehingga untuk mendapatkan performa yang diharapkan trial dan 	error perlu dilakukan beberapa kali.

# **Bagaimana Membuat Sebuah Kernel?**
Seperti saya jelaskan sebelumnya bahwa kernel adalah inner product dari dua atau lebih fitur map. Untuk membuat sebuah kernel terdapat beberapa langkah:

1. Definisikan fitur map yang akan memetakan fitur $latex X $ ke $latex R^x$.
2. Definisikan inner product antara fitur map $latex <,> $
3. Pastikan bahwa inner product antara fitur map adalah fungsi simetri positif semi-definite.

### **Contoh:**

Untuk fitur $$ X = [x_1, x_2] = $$ dan $$ Z = [z_1, z_2]$$ , definisikan dua fitur map $$ \phi(X) $$ dan $$ \phi(Z) $$. Dimana

$$ \phi([x_1, x_2]) = ({x_1}^2, \sqrt{2}{x_1}x_2, {x_2}^2) $$
$$ \phi([z1, z2]) = ({z_1}^2, \sqrt{2}{z_1}{z_2}, {z_2}^2) $$

Inner product dari $$ \phi(X) $$ dan $$ \phi(Z) $$ adalah $$ k(X, Z) = <\phi(X), \phi(Z)> $$

$$ k(X, Z) = {x_1}^2 {z_1}^2 + 2{x_1} {x_2} {z_1} {z_2} + {x_2}^2 {z_2}^2 = <{X, Z}> $$

Pastikan bahwa $$ k(.)$$ adalah fungsi simetri semi-definit. Jika suatu fungsi simetri positif semi-definit, maka fungsi tersebut akan memenuhi beberapa ketentuan berikut:

k(.) adalah fungsi simetri jika $$ k(X, Z) = k (Z, X) $$
Matrix yang dihasilkan oleh fungsi $$ k(x, x) $$ memiliki eigenvalue $$ \geq{0} $$

# **Demonstrasi Menggunakan Python**
Dalam demonstrasi ini saya akan mendemostrasikan kernel menggunakan phyton. Untuk variabel x dan z $$ \in{R}^{3x2} $$

```python
x = np.array([[1, 2], [2, 3], [4, 5]])
z = np.array([[8, 2], [9, 3], [10, 5]])
```

Definisikan fitur map $$ \phi(X) = ({x_1}^2, \sqrt{2}{x_1}x_2, {x_2}^2)$$

```python
def phi(x):
 x1 = np.power(x[0], 2)
 x2 = pow(2, 1/2) * x[0] * x[1]
 x3 = np.power(x[1], 2)
 return np.array([x1, x2, x3])
```

Seperti saya jelaskan sebelumnya, bahwa kernel adalah inner product dari beberapa fitur map, maka kernel $$ k(X, Z)  $$

```python
kXZ = np.inner(phi(x), phi(z))
```

Sampai tahap ini kita telah memiliki kernel fungsi yang merupakan inner product dari $$ \phi(X)$$ dan $$ \phi(Z) $$. Setelah ini kita harus memastikan bahwa kernel fungsi k(.) adalah fungsi simetri semi-definit.

### **k(.) adalah fungsi simetri**

```python
In[1]: print(k(z[0, :], x[0, :]))
Out[1]: 144
In[2]: print(k(x[0, :], z[0, :]))
Out[2]: 144
```

Matrix yang dihasilkan oleh fungsi $$ k(x, x) $$ memiliki eigenvalue $$ \geq{0} $$
```python
#definisikan variable K dengan nilai matrix 3x3 bernilai 0
K = np.zeros((3,3))
#lakukan pengulangan dari 0 sampai 2
for i in range(3):
#lakukan pengulangan dari 0 sampai 2
 for h in range(3):
#hitung nilai matrix K (i,h), untuk setiap K(i,h) = k(x_i, x_h)
  K[i, h] = k(x[i, :], x[h, :])
```

Ok pada potongan kode diatas kita telah berhasil membuat matrix K, dimana $$ K(i, h) = k(x_i, x_h)$$. Langkah selanjutnya memastikan bahwa eigenvalue matrix K $$ \geq{0} $$. Untuk hal ini kita dapat menggunakan fungsi pada numpy np.linalg.eig

```python
w, v = np.linalg.eig(K)
```

Fungsi np.linalg.eig akan menghasilkan duat output, 1: eigenvalues dan 2: eigen vectors.

```python
In[3]: w
Out[3]: 1870.731, 0.009, 4.260
```

Dari perhitungan eigenvalue diatas, bisa kita lihat bahwa seluruh eigenvalue matrix K  $$ \geq{0} $$ atau positif.

# **Apakah Kernel hanya dapat digunakan untuk Support Vector Machine?**

Istilah kernel sering dikaitkan dengan algoritma Support Vector Machine (SVM). Namun dalam pengaplikasiaannya, kernel juga dapat diadaptasi terhadap algoritma lainnya seperti Extreme Learning Machine (ELM) dan Regularized Ada-Boost. Untuk info lebih lanjut tentang kernel-trick dapat mengunjungi situs http://www.kernel-machines.org

Referensi:

1. https://ocw.mit.edu/courses/sloan-school-of-management/15-097-prediction-machine-learning-and-statistics-spring-2012/lecture-notes/MIT15_097S12_lec13.pdf
2. https://www.youtube.com/watch?v=3liCbRZPrZA
---
title: #1 DNN dengan TensorFlow
undefined: SUB TITLE
date: 2018-08-04 10:56:54 +0000
ttitle: #1 DNN dengan TensorFlow
banner_post: "/assets/DataFitting.png"
tag: []

---

Okay, dalam postingan kali ini saya akan membahas bagaimana mengembangkan deep neural network (DNN) menggunakan TensorFlow. Jika anda belum mengetahui apa itu TensorFlow (TF) harap cek link ini.

## **Matematika pada TensorFlow**
Sebelum memulai coding DNN dengan TF, saya akan memberikan sedikit penjelesan operator dan fungsi artimatika yang biasa digunakan dalam DNN menggunakan tensorflow.


### **Arithmetic Operators**
Fungsi artimatika yang biasa digunakan dalam komputasi DNN tidak terlalu kompleks. Fungsi-fungsi dasar seperti **add**, **multiply**, **substract**, atau **divide**. Pada TF operator-operator tersebut dapat digunakan, baik dalam operassi matrix, vector dan scalar.

**Beberapa fungsi aritmatika padaa TF:**
- tf.add
- tf.substract
- tf.multiply
- tf.divide
- tf.exp
- tf.pow

untuk fungsi aritmatika lainnya dapat dilihat ([disini](https://www.tensorflow.org/versions/r1.1/api_guides/python/math_ops))

**Contoh:**
Untuk menuliskan formula

$$ a = xb + b^2 $$

pada TF dapat diimplementasi dengan tahapan sebagai berikut:

1. import tensor flow sebagai tf

    ```python
    import tensorflow as tf
    ```

2. definisikan scalar variable x dan b

    ```python
    x = tf.Variable(1, name="x")
	b = tf.Variable(5, name="b")
    ```

3. formulasikan formula diatas

    ```python
    a = tf.Variable(tf.multiply(x, b) + tf.pow(b, 2), name="a")
    ```

4. inisialisasi variable, run init, dan print nilai a

    ```python
    init = tf.initialize_all_variables()
    with tf.Session() as session:
        session.run(init)
        print (session.run(a))
    ```

output dari kode diatas adalah

```python
30
```

Ok sampai tahap ini saya telah menyampaikan tentang operasi pada variable scalar. Lalu bagaimana dengan operasi vector dan matrix pada TF??

Ok untuk mengubah code diatas untuk operasi vector, perubahan hanya harus dilakukan pada inisialisasi variable

```python
x = tf.Variable([1, 2, 3], name="x")
b = tf.Variable([2, 3, 4], name="b")
```

output dari kode diatas adalah

```python
[ 6 15 28]
```

Untuk operasi matrix akan dijelaskan pada bagian selanjutnya



### **Matrix Operation**

Untuk mendefinisikan sebuah matrix x dan b dengan nilai sebagai berikut

$$ x =
\begin{bmatrix}
  1 & 2 \\
  3 & 4
 \end{bmatrix}, \ b = \begin{bmatrix}
  5 & 6 \\
  7 & 8
 \end{bmatrix}
$$

pada TF dapat dituliskan dengan code

```python
import tensorflow as tf
x = tf.Variable([[1, 2], [3, 4]], name="x")
b = tf.Variable([[5, 6], [7, 8]], name="b")
```

Sedangkan untuk dot dan inner product dari x dan b dapat dituliskan dengan

```python
dot = tf.Variable(tf.multiply(x, b), name="dot_product")
inner = tf.Variable(tf.matmul(x, b), name="inner_product")
```

*Note:* Untuk operasi matrix lainnya seperti **add**, **substract**, dan **divide** dapat menggunakan fungsi aritmatika yang dijelaskan sebelumnya.

---

Okay, sekarang kita akan melakukan perhitungan matrix yang lebih kompleks. Jika kita mengetahui nilai a dan x sebagai berikut

$$a =
\begin{bmatrix}
  11 \\
  2
\end{bmatrix} dan \ x =
\begin{bmatrix}
  7 & 9 \\
  9 & 5
\end{bmatrix}
$$

maka nilai b untuk formula $$a = bx$$ adalah $$b =x^{-1}a$$, yang dapat diformulasikan pada TF dengan

```python
x = tf.Variable([[7, 9], [9, 5]], name="x", dtype=tf.float64)
a = tf.Variable([[11], [2]], name="a", dtype=tf.float64)

b = tf.matmul(tf.matrix_inverse(x), a)
```

dan output dari variable a adalah

$$a =
\begin{bmatrix}
  -0.804 \\
  1.847
\end{bmatrix}
$$

---


## **Perceptron**

Tarah, setelah memperlajari secara singkat tentang Matematika pada TF saya rasa sekarang sudah saat kita melangkah ke jenjang yang lebih jauh, **perceptron**. Jika anda belum mengetahui apa itu perceptron bisa cek ([disini]).

Perceptron dapat diformulakan dengan

$$y = \sum_{n} w_i x_i = W^T X$$

dimana $y$ = output, $X$ = input, dan $W$ = unknown variable (weights).

**Persoalan:**

Modelkan permasalahan gerbang logika or dengan perceptron. Dimana nilai $$X = \{ x_1, x_2 \}$$ dan $t$ adalah

| $x_1$ | $x_2$ | $t$ |
|--------|--------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

### **#1 Definisikan variable**
Dalam permasalahan ini kita mengetahui bahwa terdapat tiga variable, $X$, $W$, dan $y$ dengan dimensi $1\times2$, $2\times1$, dan $1$ berurutan. Pada TF dapat dituliskan dengan

```python
n_input = 2
n_output = 1

X = tf.placeholder(tf.float64, [None, n_input], name="X")
W = tf.get_variable(name="W", shape=[n_input, n_output], initializer=tf.random_uniform_initializer, dtype=tf.float64)
t = tf.placeholder(tf.float64, [None, n_output], name="t")
```

### **#2 Definisikan perceptron dan error loss**

Setelah mendefinisikan variable inputs, weights, dan desired outputs langkah selanjutnya adalah memforumulasikan perceptron dan error loss (pada kasus ini MSE digunakan untuk menghitung error antara predicted output dan actual output).

```python
y = tf.sigmoid(tf.matmul(X, W))
mse = 0.5 * tf.reduce_mean(tf.square(y - t))
```

### **#3 Train perceptron**

Ok, setelah mendefinisikan variable, model, dan error loss pada kita dapat mentrain DNN dengan backgpropagation. Pada TF terdapat beberapa algoritma yang dapat digunakan untuk mentrain DNN. Pada postingan ini akan digunakan gradient descent dengan learning rate = 0.1. Proses training akan dilakukan sebanyak 100 iterasi menggunakan batch gradient, dimana seluruh data akan digunakan dalam satu epoch.

```python
train = tf.train.GradientDescentOptimizer(0.1).minimize(mse)

init = tf.initialize_all_variables()


#definisikan nilai
x_input = np.array([[0, 0], [0, 1], [1, 0], [1, 1]])
t_input = np.array([[0], [1], [1], [1]])

with tf.Session() as session:
    session.run(init)

    for epoch in range(100):
        _, loss = session.run([train, mse], feed_dict={X: x_input,
                                                        t: t_input})
```

## **Multiple Layer Neural Network (MLP)**

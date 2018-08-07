---
title: TF-IDF VSM Menggunakan Python
undefined: SUB TITLE
date: 2018-08-01 12:56:54 +0000
ttitle: TF-IDF VSM Menggunakan Python
banner_post: "/assets/online-course.jpg"
tag: []

---
Dalam postingan ini saya akan membahas mengenai sebuah teknik yang digunakan untuk merepresentasikan sebuah dokumen dalam sebuah vector (Vector Space Model). Namun, sebelum membahas lebih lanjut saya ingin bertanya, kira-kira mengapa sebuah dokumen harus direpresentasikan menjadi sebuah vector?

Saya rasa bagi pengguna internet, hampir setiap hari kita menggunakan Google. Dengan Google, kita dapat melakukan pencarian halaman web yang sesuai dengan kata kunci yang kita inginkan, namun bagaimana untuk menentukan kemiripan sebuah laman web dengan kata kunci yang kita masukan pada Google. Bagi manusia saya rasa sangat mudah untuk menentukan hal tersebut, namun bagaimana dengan sebuah komputer?

Dari empat kalimat dibawah ini, kita dapat menentukan bahwa kalimat yang sesuai dengan kata kunci "kehidupan mahasiswa dikampus" adalah kalimat 1, 2, dan 4. Namun bagaimana dengan komputer, bagaimana sebuah komputer dapat mengetahui bahwa kalimat 1, 2, dan 4 adalah kalimat yang sesuai dengan kata kunci "kehidupan mahasiswa dikampus"?

1. Hari ini dikampus, saya makan bersama teman-teman saya di kantin kampus, dan kami bertemu dengan mahasiswa senior yang jutek abis.
2. Duh hari ini hujan, padahal mau berangkat kekampus karena ada ujian dari dosen favoritku.
3. Malam minggu dan hujan, saatnya cari duit.
4. Waktu saya menjadi mahasiswa saya sering bekerja paruh waktu.

Ok perhatikan baik-baik, kita dapat mengetahui bahwa pada kalimat 1 dan 4 terdapat kata mahasiswa, dan pada kalimat 1, dan 2 terdapat kata kampus. Kemampuan dasar dari komputer itu adalah melakukan perhitungan, oleh karena itu pada kasus ini kita dapat menentukan kemiripan sebuah dokumen terhadap kata kunci dengan melakukan perhitungan frekuensi kehadiran kata kunci pada sebuah kalimat.

Kata kunci: kehidupan, mahasiswa, kampus

Kalimat1: kehidupan: 0, mahasiswa: 1, kampus: 2
Kalimat2: kehidupan: 0, mahasiswa: 0, kampus: 1
Kalimat4: kehidupan: 0, mahasiswa: 1, kampus: 0

Nah dari hasil diatas, dapat ditentukan bahwa dokumen atau kalimat yang paling mirip dengan kata-kunci adalah dokumen ke-1. Mungkin dari sini rekan-rekan dapat membayangkan VSM itu apa atau bagaimana sebuah dokumen dapat dicocokan satu sama lain, atau tambah bingun (karena saya tambah bingung sebenarnya).

### **Ok jadi, ........**
Vector Space Model (Vector Space Model) adalah model aljabar yang merepresentasikan kumpulan dokumen sebagai vetctor. VSM dapat diaplikasikan dalam klasifikasi dokumen, clustering dokumen, dan scoring dokumen terhadap sebuah query. Dalam VSM setiap dokumen direpresentasikan sebagai sebuah vector, dimana nilai dari setiap nilai dari vector tersebut mewakili weight sebuah term. Dalam menghitung term-weight dapat digunakan beberapa teknik seperti frequency, binary-document vector, atau tf-idf. Dalam postingan ini saya akan menggunakan tf-idf dalam menghitung term-weighting sebuah dokumen.

---
### **Definition**


- dokumen (d): dapat berupa tweet,  kalimat, atau berita.
- term (t): dapat berupa kata tungga (contoh: teman), keywords, atau phrase (contoh: teman sekolah yang baik)

---

## **TF-IDF**
---
### **Apa sih TF itu?**

TF atau term frequency adalah weighting scheme yang digunakan untuk menentukan relevansi dokumen dengan sebuah query (term). TF menentukan bobot relevansi sebuah dokumen dan term berdasarkan frekuensi kemunculan term pada dokumen terkait. Untuk menghitung TF terdapat beberapa jenis fungsi yang dapat digunakan [1]:

* Natural atau Raw-term frequency

$$tf(t, d) = f_{t, d}$$

* Logarithm

$$tf(t, d) = 1 + log(f_{t, d})$$

* Augmented

$$tf(t, d) = 0.5 + \frac{0.5*f_{t, d}}{max _{\{t \in d\}}f_{t', d}}$$

* Boolean

$$tf(t, d) =\begin{cases}x(n), & \text{if } f_{t, d} > 0\\x(n-1), & \text{otherwise} \\ \end{cases}$$

### **Contoh TF**
**kasus:** hitungan weight kata "anak" pada kalimat "anak ini bukan anak kamu"

**dokumen:** anak ini bukan anak kamu

**term:** anak

**weight t pada d:** 2

Note: pada kasus ini digunakan raw-frequency term weighting.


## **DF**

Jika TF adalah frekuensi kemunculan suatu term pada sebuah dokumen, DF merupakan jumlah dokumen dimana terdapat term yang bersangkutan. Konsep DF sendiri dilatarbelakangin oleh masalah pada TF, dimana semua term dianggap sama penting, sehingga term yang memiliki sedikit atau tidak memiliki discrimination power dapat mempengaruhi akurasi dalam menentukan relevansi antara term dan dokumen. Ide dari DF adalah dengan mengurangi bobot TF suatu term dengan membaginya dengan frekuensi term terhadap koleksi dokumen (DF). Jadi sebuah term yang memiliki bobot TF yang besar namun dengan bobot DF yang besar pula tidak akan memiliki pengaruh yang besar dalam menentukan sebuah relevansi [1].

$$df(t, doc collection) = df_t$$

### **Contoh DF*
Koleksi dokumen:

1. Yang domisili di Cibinong & sekitarnya siang ini kita olahraga bareng
2. Tau belum bogor jadi kandidat the most loveable city in the world?
3. Salam olahraga Minggu semangat..!!! @ Taman Bogor

Term: olahraga, taman

#### **DF:**

* DF (olahraga, d) = 3 (dokumen 1, 2, dan 3)
* DF (taman, d) = 1 (dokumen 1)

## **IDF**

IDF adalah inverse dari DF, IDF akan melakukan proses scaling pada TF. Term yang memiliki DF yang rendah akan memiliki IDF yang tinggi. Dengan kata lain, sebuah term yang jarang ditemui pada koleksi dokumen atau bisa dikatakan sebagai term khusus akan memiliki nilai IDF yang tinggi. Untuk menghitung IDF pada sebuah term pada sebuah koleksi dokumen dapat menggunakan fungsi dibawah ini,

$$idf_t = log (\frac{N}{df_t})$$

dimana N adalah jumlah dokumen pada koleksi.

### **Contoh IDF**
Koleksi dokumen:

1. Yang domisili di Cibinong & sekitarnya siang ini kita olahraga bareng
2. Tau belum bogor jadi kandidat the most loveable city in the world?
3. Salam olahraga Minggu semangat..!!! @ Taman Bogor


Term: olahraga, taman

#### **IDF:**

* Diketahui:
    * N = 3
    * DF (olahraga, d) = 3 (dokumen 1, 2, dan 3)
    * DF (taman, d) = 1 (dokumen 1)

Maka IDF dari term "olahraga" dan "taman"

| Term | DF | IDF |
| ---- | -- | --- |
| olahraga | 3 | 0 |
| taman | 1 | 0.477121 |

---

## **Jadi VSM itu seperti apa?**

Nah setelah beberapa penjelasan singkat tentang term-weighting diatas. Langsung saja pada bagian ini saya jelaskan contoh perhitungan VSM sebuah dokumen. Pada VSM sebuah dokumen akan direpresentasikan dalam sebuah vektor, dimana setiap nilai pada vektor tersebut mewakili bobot term yang bersangkutan.

### **Contoh VSM**

**dokumen:** sudah duah tahun kami tinggal di desa ini, pendidikan anak kami di desa ini cukup terjamin, jadi kami rasa kami akan tetap tinggal di desa ini, hingga pendidikan anak kami selesai

**vocabulary / word bank:** anak, desa, pendidikan, sekolah, guru,buku, terbatas.

**term-weighting:** Raw-Frekuensi

$$(t, d) = \frac {f_t}{max \{t \in d \}}$$

**Keterangan:**

* jumlah kata pada dokumen: 31

Word | Bank | Frekuensi | VSM |
---- | ---- | --------- | --- |
anak | 2 | 0.064516129 |
desa | 3 | 0.096774194 |
pendidikan | 1 | 0.032258065 |
sekolah | 0 | 0 |
guru | 0 | 0 |
buku | 0 | 0 |
terbatas | 0 | 0 |

**Maka VSM untuk kalimat :**

"sudah duah tahun kami tinggal di desa ini, pendidikan anak kami di desa ini cukup terjamin, jadi kami rasa kami akan tetap tinggal di desa ini, hingga pendidikan anak kami selesai"

$$[0.0645, 0.0968, 0.0322, 0, 0, 0, 0]$$

## **Implementasi TF-IDF VSM Menggunakan Phyton**
**Keterangan:**

* Dalam implementasi ini, saya menggunakan 10 docs (kalimat) yang diambil secara acak dengan topik "penggunaan vaksi palsu"
* Wordbank (kata yang dianggap berkaitan topik diatas)
    * vaksin
    * posko
    * kesehatan
    * penumpang
    * kereta
    * kemanan
* Term-weighting yang digunakan adalah Tf-Idf
	* Tf weighting scheme: log normalization
	* Idf weighting scheme: inverse document frequency smooth
* Log base yang saya gunakan adalah base 10

```python
#import library pandas dan inisialisasikan menjadi pd
import pandas as pd
#import library numpy dan inisialisasikan menjadi np
import numpy as np
#dari library math import function log
from math import log


#hapus seluruh tanda baca dan angka
def removeNonWord(doc):
    #hapus seluruh kata yang mengandung angka, contoh: perempuan2
    result = doc.replace({'\w*\d\w*': ''}, regex=True)
    #hapus seluruh karakter yang tidak termasuk alphabet
    result = result.replace({'[\W_]+': ' '}, regex=True)
    #remove null dari hasil final
    return result[result.notnull()]

def idf(doc, wordBank):
    #hitung jumlah doc
    N = len(doc.index)
    #buat dataframe dengan header word dan idf
    result = pd.DataFrame(columns=['word', 'idf'])
    #untuk setiap kata pada wordBank lakukan.....
    for index, word in wordBank.iterrows():
        #hitung jumlah doc yang mengandung kata word['words']
        dft = np.sum(doc.str.contains(word['words']))
        #hitung inverse document frequency smooth
        idft = log(N / (dft + 1), 10)
        #tambahkan idf untuk setiap kata pada data frame
        result = result.append(pd.Series([word['words'],  idft], index=['word', 'idf']), ignore_index=True)
    #return variable result
    return result


#funtion to calculate tf
def tf(doc, wordBank):
    #split kata berdasarkan spasi
    wordList = doc.str.split(' ')
    #hitung jumlah kata pada setiap doc
    maxFt = [len(s)  for s in wordList]
    #buat DataFrame kosong untuk menyimpan hasil perhitungan Tf
    result = pd.DataFrame()
    #untuk setiap word dalam wordbank lakukan ....
    for index, word in wordBank.iterrows():
        #hitung frekuensi kata untuk setiap doc
        ft = np.add([s.count(word['words']) for s in wordList], 0)
        #tf log normalization
        ftd = 1 + np.log10(ft)
        #tambahkan hasil perhitungan tf kedalam DataFrame
        result = result.append(pd.Series(ftd), ignore_index=True)
    #replace -inf with zero
    result = result.replace(-np.inf, 0)
    #return variable result
    return result

def tfIdf(tf, idf):
    #buat DataFrame kosong untuk menyimpan hasil perhitungan Tf-Idf
    result = pd.DataFrame()
    #untuk setiap tf
    for i in tf:
        #tf idf untuk document term weighting tf * idf
        tfIdf = tf[i] * idf['idf']
        #tambahkan hasil perhitungan tf idf kedalam DataFrame
        result = result.append(pd.Series(tfIdf), ignore_index=True)
    #return variable result
    return result



# membaca file doc.csv menggunakan pandas
# doc.csv berisi 10 kalimat
doc = pd.read_csv('data/doc.csv', encoding='utf-8')

# membaca file wordBank.csv
# wordBank.csv berisi kata-kata penting atau keywords yang dianggap relevan dengan topik dalam sebuah kasus
vocabulary = pd.read_csv('data/wordBank.csv', encoding='utf-8')


#ubah seluruh huruf menjadi huruf kecil
doc = doc['sentences'].str.lower()

#panggil fungsi removeNonWord
doc = removeNonWord(doc)

#hitung nilai IDF
resultIDF = idf(doc, vocabulary)

#hitung nilai TF
resultTF = tf(doc, vocabulary)

#hitung nilai Tf-Idf
resultTfIdf = tfIdf(resultTF, resultIDF)

print(resultTfIdf)
```


Nah sekian pembahasan mengenai TF-IDF VSM menggunakan Python, mohon komentar dan masukan ya.

### **Download** [disini](https://github.com/gitarja/blog/tree/master/VSM_TFIDF) bro...

## **Daftar Pustaka:**

[1] Manning, C. D.; Raghavan, P.; Schutze, H. (2008). "Scoring, term weighting, and the vector space model". Introduction to Information Retrieval. p. 100.

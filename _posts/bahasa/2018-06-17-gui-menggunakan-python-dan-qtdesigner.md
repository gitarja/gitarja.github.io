---
title: GUI Menggunakan Python dan QtDesigner
undefined: SUB TITLE
date: 2018-06-17 10:56:54 +0000
ttitle: GUI Menggunakan Python dan QtDesigner
banner_post: "/assets/online-course.jpg"
tag: []
categories: bahasa
layout: inner

---

Halo semuanya, pada postingan ini saya akan menjelaskan tentang proses pembuatan Graphical User Interface (GUI) menggunakan Python dan QtDesigner.

## **QtDesigner**
Pada Python sendiri sebenarnya terdapat beberapa API yang dapat digunakan untuk membuat GUI, seperti wxPython, TKInter, PyGtk, ataupun PyQt. Untuk list lengkap API yang dapat digunakan untuk membuat GUI pada Python dapat dilihat disini.

Kenapa dalam postingan ini saya menggunakan PyQt, jawabannya, karena PyQt satu-satunya API untuk GUI yang pernah saya coba hehe. Namu dalam postingan ini saya akan menjelasakna tentang penggunakan QtDesigner dalam membuat GUI pada Python.

QtDesigner sendiri adalah tools yang dapat digunakan untuk mendesain dan mem-build Graphical User Interfaces menggunakan QtComponents. QtDesigner dapat digunakan tidak hanya untuk membuat aplikasi desktop, tapi juga aplikasi mobile.

## **PyQt**
Seperti saya jelaskan sebelumnya, bahwa pada postingan ini saya akan menggunakan QtDesigner dan Python untuk membuat GUI applikasi. PyQt merupakan API yang berfungsi sebagai binding antara Python dan Qt cross-platform framework. PyQt menyediakan binding untuk Qt versi 4 dan 5. Pada Anaconda PyQT dapat diinstall dengan mengetikan code dibawah ini pada Anaconda terminal

```python
conda install -c anaconda pyqt
```


## **Let's Start**
Ok sekarang saya akan mulai menjelaskan langkah-langkah untuk membuat aplikasi GUI menggunakan QtDesigner dan Python.

Sebelum memulai membuat GUI aplikasi, pastikan tiga aplikasi ini telah ter-install di komputer anda. Jika anda belum menginstall Anaconda dan Jetbrains, bisa lihat postingan ini.

- Anaconda
- QtDesigner (jika telah menginstall pyQt pada Anaconda, QTDesigner dapat ditemukan di directory\_anaconda/Library/bin/designer.exe)
- Jetbrains PyCharm

## **Langkah pertama**
Ok pertama buka aplkasi QtDesigner dan pilih Main Window dari panel templates forms

|![](/assets/qtgui/mainscreen-qtdesigner.png)|
|:--:|
| *Tampilan QTDesigner* |

Ok jika telah memilih Main Window, klick create, maka akan tampil Window form seperti gambar dibawah. Pada form ini kita dapat menaruh berbagai macam widget. Saya menempatkan tiga widgets pada Windows form.

1. Text Edit (objectName: setTextEdit)
2. Push Button (objectName: setButton)
3. Label (objectName: setLabel)

Oh ia untuk memudahkan proses pemanggilan object, saya mengubah objectName untuk setiap widget dengan value seperti diatas. Window form saya simpan dengan nama **MainView.ui**.

|![](/assets/qtgui/mainscreen-qtdesigner.png)|
|:--:|
| *Widgets pada QTDesigner* |

Sampai tahap ini, Windows form yang telah dibuat menggunakan QtDesigner sudah dapat dibinding dengan Python. Akan tetapi untuk memudahkan proses import dan penggunaan object, saya akan mengimport file .ui menjadi file Python. Proses konversi ini sangat mudah, cukup menggunakan script pada Anaconda command prompt

```python
pyuic5 NamaFileUi.ui -o NamaOutputFilePython.py
```
pada kasus ini

```python
pyuic5 MainView.ui -o MainView.py
```

Setelah script diatas dijalankan, makan akan terdapat file Main.py. File ini merupakan Windows form yang telah kita buat sebelumnya.

##**Menjalankan GUI Application**
Setelah berhasil membuat GUI pada QtDesigner dan mengkoversi file .ui menjadi file Python. Langkah selanjutnya adalah dengan membuat script untuk menjalankan GUI application yang telah kita buat sebelumnya. Hal ini sangatlah mudah, pertama buatlah sebuah file Python yang akan menjalankan file MainView.py. Dalam tutorial ini saya mebuat file Main.py. Jadi dalam projek saya terdapat dua file, Main.py dan MainView.py

|![](/assets/qtgui/projectex.png)|
|:--:|
| *Structure file pada projek* |


Untuk dapat mengakses GUI element pada class MainView dari file Main.py, kita perlu melakukan proses import, hal ini dapat dilakukan dengan menambahkan script

```python
import MainView.py
```

## **Script Main.py**
Pada implementasi ini saya menggunakan PyQT versi 5.
```python
from PyQt5 import QtWidgets
import sys
import MainView

#membuat pewarisan pada Python, dalam kasus ini class Main mewarisi class MainView
#langkah ini dilakukan agar kita dapat melakukan modifikasi pada class MainView tanpa harus mengubah pada class tersebut
#cukup melakukan modifikasi pada class Main
class Main(QtWidgets.QMainWindow, MainView.Ui_MainWindow):
    def __init__(self):
        super().__init__()
        #setupUi merupakan fungsi dari class MainView yang berfungsi untuk melakukan setup
        #sesuai dengan apa yang telah didefinisikan sebelumnya
        self.setupUi(self)
        #jalankan fungsi setValue ketika setButtton diclick
        self.setButton.clicked.connect(self.setValue)

    #definisikan fungsi setValue
    def setValue(self):
    #set nilai setLabel dengan nilai setTextEdit
        self.setLabel.setText(self.setTextEdit.toPlainText())

def main():
    app = QtWidgets.QApplication(sys.argv)  #buat instance baru QtGui
    winForm = Main()                    #inisialisasi variable winForm sebagain class Main
    winForm.show()                      #tampilkan windows form
    sys.exit(app.exec_())               #eksekusi applikasi

if __name__ == '__main__':              #jika file dijalanakan secara langsung, maka jalankan fungsi main()
    main()
```

Jika file Main.py dijalankan, maka akan tampil Window form seperti dibawah ini

|![](/assets/qtgui/mainform.png)|
|:--:|
| *Tampilan GUI yang dibuat* |

## **Tautan bermanfaat**
 - Tutorial QtDesigner dan Python (bahasa Inggris, inspirasi postingan ini)
	- [https://nikolak.com/pyqt-qt-designer-getting-started/](https://nikolak.com/pyqt-qt-designer-getting-started/)

- Inheritance pada Python
	- [http://learnpythonthehardway.org/book/ex44.html](http://learnpythonthehardway.org/book/ex44.html)

- Link full code
	- [https://github.com/gitarja/blog/tree/master/QTGui](https://github.com/gitarja/blog/tree/master/QTGui)
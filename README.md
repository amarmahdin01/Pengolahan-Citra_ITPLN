PROJEK UAS PENGOLAHAN CITRA A
Perkenalkan saya Muhammad Amar Mahdin 202131043. Pada project ini saya mendapatkan judul DETEKSI PLAT NOMOR.

Sebelum ke program, terlebih dahulu saya akan menjelaskan apa itu Deteksi Plat Nomor dan kegunannya.

Deteksi Plat Nomor
Deteksi plat nomor adalah proses komputerisasi untuk mengenali dan memperoleh informasi dari plat nomor kendaraan yang terdapat dalam gambar atau video. Tujuan dari deteksi plat nomor adalah untuk mengotomatisasi dan mempermudah proses identifikasi kendaraan, seperti yang sering dilakukan dalam sistem keamanan lalu lintas, sistem parkir otomatis, atau penegakan hukum.

Proses deteksi plat nomor melibatkan beberapa langkah. Pertama, algoritma pengolahan citra digunakan untuk mengenali dan memisahkan wilayah plat nomor dari gambar atau video yang lebih besar. Kemudian, teknik pengolahan citra lebih lanjut diterapkan untuk meningkatkan kejelasan dan kekontrasan plat nomor yang terdeteksi.

Setelah itu, deteksi karakter atau Optical Character Recognition (OCR) diterapkan pada wilayah plat nomor yang telah diisolasi. OCR menggunakan algoritma untuk mengenali dan mengubah karakter plat nomor menjadi teks yang dapat dibaca oleh mesin. Informasi ini kemudian dapat digunakan untuk mengidentifikasi kendaraan, memeriksa keabsahan plat nomor, dan melakukan tindakan lainnya seperti pencarian dalam basis data atau perbandingan dengan daftar kendaraan yang dicurigai.

Deteksi plat nomor telah menjadi aplikasi yang penting dalam berbagai bidang, termasuk sistem keamanan, pengawasan lalu lintas, dan pengenalan kendaraan otomatis.

Penjelasan Program
import cv2 as cv import matplotlib.pyplot as plt import imutils

Program tersebut menggunakan dua library, yaitu OpenCV (cv2) dan Matplotlib (plt), untuk melakukan deteksi plat nomor pada gambar. Dalam program tersebut, modul "imutils" juga digunakan, yang merupakan pustaka utilitas yang memudahkan penggunaan OpenCV.

plat = cv.imread("plat.jpg")

Pada program ini dengan variabel plat, cv.imread() untuk membaca gambar dengan nama plat.jpg.

plat1 = cv.cvtColor(plat,cv.COLOR_BGR2GRAY) img_crop = plat1[430:505,260:470]

variabel plat1 cv.cvtColor(cv.COLOR_BGR2GRAY) program untuk mengunah warna rgb menjadi skala abu-abu. img_crop untuk crop image sesau value yang di berikan.

fig, axes = plt.subplots(1, 2, figsize = (10, 11)) ax = axes.ravel()

ax[0].imshow(plat) ax[0].set_title('Gambar Asli') ax[1].imshow(img_crop, cmap = 'gray') ax[1].set_title('Plat Terdeteksi')

Program tersebut menggunakan library Matplotlib untuk menampilkan dua gambar secara bersamaan dalam satu jendela dengan ukuran yang ditentukan (10x11). Program tersebut juga menggunakan subplots untuk membuat grid dengan 1 baris dan 2 kolom, sehingga menampilkan dua gambar secara horizontal.

(these, imgb) = cv.threshold(img_crop, 0,255, cv.THRESH_BINARY + cv.THRESH_OTSU)

edge = cv.Canny(img_crop, 100, 150)

cv.threshold(img_crop, 0, 255, cv.THRESH_BINARY + cv.THRESH_OTSU): Fungsi ini digunakan untuk melakukan thresholding pada gambar img_crop. cv.Canny(img_crop, 100, 150. Fungsi ini digunakan untuk mendeteksi tepi pada gambar img_crop menggunakan algoritma Canny Edge Detection.

fig, axes = plt.subplots(1, 2, figsize = (10, 11)) ax = axes.ravel()

ax[0].imshow(cv.cvtColor(imgb, cv.COLOR_BGR2RGB)) ax[0].set_title('Hasil Binary') ax[1].imshow(edge, cmap = 'gray') ax[1].set_title('Setelah Edges')

Sama seperti program diatas, tetapi pada ini menampilkan binery dan edges.

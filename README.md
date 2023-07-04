# Deteksi Plat Nomor (Crop & Identifikasi Nomor)

Pengolahan citra adalah proses untuk melakukan pengolahan dan menganalisis citra digital dengan mengambil informasi yang ada. Pencatatan plat nomor dengan cara manual dirasa kurang efisien karena memerlukan ketelitian akibat buruknya dapat terjadi kekeliruan. Sehingga diterapkanlah pendeteksian plat nomor menggunakan pengolahan citra dengan tujuan mempermudahkan dalam hal pencatatan, pendeteksian, dan pencarian plat nomor.

## Proses pada deteksi plat nomor
Proses-proses yang dapat dilakukakan dalam Deteksi Plat Nomor diantaranya yaitu :
1. Grayscaling
Grayscaling merupakan proses merubah citra asli atau citra RGB menjadi citra abu-abu. Nilai intensitasnya dimulai dari 0 hingga 255. Semakin kecil nilainya maka hasil warna yang didapatkan semakin gelap atau hitam. Namun, jika semakin besar nilainya maka hasil warna yang didapatkan semakin terang atau putih.

2. Bilateral Filter
Bilateral filter disini digunakan untuk mengurangi noise pada gambar karena dikhawatirkan dapat mempengaruhi deteksi plat nomor seperti noise salt-and-pepper atau noise gaussian. Kemudian mempertahankan tepi agar tetap akurat dan memperbaiki kualitas gambar untuk meningkatkan hasil dan keakuratan deteksi plat nomor. 

3. Edges dan Canny
Edges disini digunakan untuk memperjelas garis batas dari citra agar dapat mengidentifikasi area plat nomor dan mempermudahkan proses deteksi plat nomor. Algoritma canny juga digunakan disini.

4. Contour
Contour digunakan untuk menemukan garis yang membentuk plat nomor. Caranya dengan menggunakan algoritma segmentasi berbasis kontur seperti fungsi yang digunakan yaitu 'cv2.findContours()'.

5. Zoom
Zoom digunakan untuk memperbesar area yang telah terdeteksi plat nomor.

6. Crop
Crop digunakan untuk memotong atau menyeleksi area dari plat nomor, sehingga nantinya area plat nomor tersebut dapat diolah lebih lanjut dengan teknik pengolahan citra yang ada.

7. Binerisasi
Binerisasi merupakan proses yang mengubah citra asli atau citra RGb menjadi citra biner atau citra 2-bit. Pada prosesnya digunakan threshold tertentu. Jika nilai grayscalenya kurang atau sama dengan dari nilai threshold maka diubah menjadi 0. Namun, jika berkebalikkan maka diubah menjadi 255.

## Langkah-langkah penyelesaian
Berikut ini merupakan langkah penyelesaian dari pendeteksian plat nomor :
1. Buka aplikasi Jupyter Notebook
2. Buat project baru
3. Install library openCV, imutils, numpy dan matplotlib (jika belum ada). Tunggu hingga proses instalasi selesai
4. Import library openCV, imutils, numpy dan matplotlib ke dalam script
5. Memuat gambar 'mobil.jpeg' dan tampilkan gambar menggunakan library matplotlib
6. Ubah citra asli ke dalam bentuk citra abu-abu dengan grayscale. Selanjutnya, berikan bilateral filter pada citra abu-abu dan gunakan algoritma canny.
7. Tampilkan hasil dari citra abu-abu 'Gambar Asli' dan citra yang telah diberikan algoritma canny 'After Edges'.
8. Gunakan contour dengan fungsi 'cv2.findContours()' pada citra sebelumnya. Fungsi 'drawContours()' digunakan setelah mengidentifikasi contour menggunakan metode 'cv2.findContours()' agar dapat memvisualisasikan dengan jelas area plat nomor yang telah terdeteksi, sehingga memudahkan dalam analisis dan validasi hasil deteksi.
9. Fungsi 'bitwise_and()' digunakan setelahnya untuk melakukan masking 'mask' pada citra dengan hasil segmentasi tersebut. Jadi hanya piksel yang berada pada area plat nomor yang akan dipertahankan, sedangkan piksel luar area akan dihapus atau diubah menjadi piksel hitam.
10. Crop citra yang telah terseleksi oleh fungsi 'bitwise_and()'.
11. Citra yang telah di crop diubah ke dalam bentuk biner dan edges.
12. Tampilkan output yang dihasilkan, mulai dari 'Gambar Asli', 'Plat Terdeteksi', 'Binary Image', 'Edges Image'.
13. Menyimpan hasil dari plat nomor yang telah terdeteksi dengan fungsi 'cv2.imwrite' dan format gambar yang digunakan adalah JPG.

## Jurnal yang berkaitan dengan deteksi plat nomor
Judul           : Deteksi Plat Nomor Kendaraan Berbasis Phyton

Penulis         : Karunia Windu Wati

Tahun terbit    : 2021

### Abstrak

Plat nomor kendaraan merupakan identitas dari setiap kendaraan yang beroperasi di jalan raya. Setiap kendaraan memiliki kode yang bervariasi untuk kode wilayah,kode angka,dan kode daerah yang dimiliki. Peningkatan kendaraan bermotor terdata sekitar 5000.000 unit pada tahun 2015 – 2018 untuk kendaraan roda dua, dan 800.000 unit untuk kendaraan roda empat. setiap tahunnya. Untuk mengurangi potensi gangguan yang terjadi, seperti menumpuknya antrian parkir hingga mengganggu ketertiban lalu lintas, dibutuhkan beberapa cara untuk mengatasi hal tersebut, salah satunya dengan menggunakan sistem deteksi yang cepat dan mudah menggunakan pengolahan citra dengan metode Contour. Contour merupakan metode yang digunakan untuk mendeteksi suatu ketinggian dari beda posisi objek dengan tinggi latar belakang. Dalam penelitian ini juga digunakan sistem deteksi kendaraan dengan menggunakan bahasa pemrograman python yang mudah dan cepat dipahami, untuk mendeteksi suatu plat nomor kendaraan berbentuk gambar menjadi teks. Pada penelitian ini terdapat 9 tahapan pengolahan citra yaitu baca gambar, resize, Grayscale,Smooth filter,Contours, Masking, Segmentasi, Medianblur,Recognisi. Dari hasil pengujian di dapatkan untuk akurasi nya dari ke -10 data uji 7 plat terdeteksi dengan akurasi baik 100% yaitu tahapan baca gambar, rezize, grayscale, filter smoooth, canny edge detection, segmentasi/crop, median blur,.contour,masking, recognation . Untuk 3 plat yang ada yaitu recognisi, dan contour, kurang maksimal terdeteksi pada beberapa gambar. Untuk total akurasi keseluruhan adalah 70%

Kata Kunci : Python,Contour,OpenCv,presentase

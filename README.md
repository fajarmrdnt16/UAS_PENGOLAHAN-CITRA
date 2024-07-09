# UAS_FAJAR MARDIANTO_311910599
1. Kode: Baca gambar dan ubah menjadi gambar RGB.
   import numpy as np
import matplotlib.pyplot as plt
import cv2

%matplotlib inline

# Read in the image
image = cv2.imread('foto/foto.jpg')

# Change color to RGB (from BGR)
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image)
![image](https://github.com/fajarmrdnt16/UAS_PENGOLAHAN-CITRA/assets/81574674/863857d6-9434-474d-abe7-f8becd1ae34d)
2. langkah selanjutnya kita harus menyiapkan data untuk K mean. Gambar adalah bentuk 3 dimensi tetapi untuk menerapkan k-means clustering pada gambar tersebut kita perlu membentuknya kembali menjadi array 2 dimensi.
Code:
# Membentuk ulang gambar menjadi susunan piksel 2D dan 3 nilai warna (RGB)
pixel_vals = image.reshape((-1,3))

# Ubah ke float type
pixel_vals = np.float32(pixel_vals)
3. Selanjutnya kita akan mengimplementasikan algoritma K mean untuk mensegmentasi suatu gambar. 

Kode: Mengambil k = 3, artinya algoritma akan mengidentifikasi 3 cluster pada gambar.
#baris kode di bawah ini menentukan kriteria agar algoritme berhenti berjalan, 
#yang akan terjadi adalah 100 iterasi dijalankan atau epsilon (yang merupakan akurasi yang dibutuhkan)
#menjadi 85%
criteria = (cv2.TERM_CRITERIA_EPS + cv2.TERM_CRITERIA_MAX_ITER, 100, 0.85)

# lalu lakukan K clustering dengan jumlah cluster yang ditetapkan sebagai 3
# juga pusat acak pada awalnya dipilih untuk pengelompokan k
k = 3
retval, labels, centers = cv2.kmeans(pixel_vals, k, None, criteria, 10, cv2.KMEANS_RANDOM_CENTERS)

# mengonversi data menjadi nilai 8-bit
centers = np.uint8(centers)
segmented_data = centers[labels.flatten()]

# membentuk ulang data menjadi dimensi gambar asli
segmented_image = segmented_data.reshape((image.shape))

plt.imshow(segmented_image)
Output:
![image](https://github.com/fajarmrdnt16/UAS_PENGOLAHAN-CITRA/assets/81574674/9df8493f-7162-4616-8a77-eda896e38fea)
4. Jika kita mengubah nilai k menjadi 8 , kita mendapatkan Output berikut :
![image](https://github.com/fajarmrdnt16/UAS_PENGOLAHAN-CITRA/assets/81574674/c57cd00f-e493-4758-a37e-b5f0cb29f248)




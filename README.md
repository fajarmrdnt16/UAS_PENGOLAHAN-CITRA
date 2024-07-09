# UAS_FAJAR MARDIANTO_311910599
#1. Kode: Baca gambar dan ubah menjadi gambar RGB.
![image](https://github.com/fajarmrdnt16/UAS_PENGOLAHAN-CITRA/assets/81574674/863857d6-9434-474d-abe7-f8becd1ae34d)
#2. Langkah selanjutnya kita harus menyiapkan data untuk K mean. Gambar adalah bentuk 3 dimensi tetapi untuk menerapkan k-means clustering pada gambar tersebut kita perlu membentuknya kembali menjadi array 2 dimensi.
Code:
#Membentuk ulang gambar menjadi susunan piksel 2D dan 3 nilai warna (RGB)
pixel_vals = image.reshape((-1,3))

#Ubah ke float type
pixel_vals = np.float32(pixel_vals)
#3. Selanjutnya kita akan mengimplementasikan algoritma K mean untuk mensegmentasi suatu gambar. 
Output:
![image](https://github.com/fajarmrdnt16/UAS_PENGOLAHAN-CITRA/assets/81574674/9df8493f-7162-4616-8a77-eda896e38fea)
#4. Jika kita mengubah nilai k menjadi 8 , kita mendapatkan Output berikut :
![image](https://github.com/fajarmrdnt16/UAS_PENGOLAHAN-CITRA/assets/81574674/c57cd00f-e493-4758-a37e-b5f0cb29f248)




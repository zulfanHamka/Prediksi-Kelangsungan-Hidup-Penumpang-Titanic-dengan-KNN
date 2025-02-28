# Analisis Data Titanic dengan K-Nearest Neighbors (KNN)

Analisis ini dilakukan untuk memprediksi keselamatan penumpang Titanic berdasarkan berbagai faktor seperti kelas tiket, gender, usia, jumlah saudara dan anak, harga tiket, serta asal keberangkatan. Proses ini melibatkan beberapa tahapan, termasuk impor dataset, preprocessing, encoding, normalisasi, split data, dan pembuatan model menggunakan algoritma K-Nearest Neighbors (KNN).

## Import Library
Pada tahap awal, kita mengimpor beberapa library yang diperlukan, seperti:
- `numpy` dan `pandas` untuk manipulasi data
- `matplotlib.pyplot` dan `seaborn` untuk visualisasi
- `sklearn` untuk preprocessing, normalisasi, dan pembuatan model

## Load Dataset
Dataset Titanic diimpor dari file Excel dan ditampilkan dalam bentuk tabel untuk memahami struktur datanya. Beberapa kolom yang tidak relevan seperti `IdPenumpang`, `Nama`, `NoTiket`, dan `KodeKursi` dihapus agar analisis lebih fokus.

## Exploratory Data Analysis (EDA)
Informasi tentang dataset diperiksa untuk melihat jumlah data, tipe data, dan nilai yang hilang. Terdapat missing values pada kolom `Usia` dan `AsalKeberangkatan`, sehingga perlu dilakukan imputasi data.

## Preprocessing
- Nilai yang hilang pada `Usia` digantikan dengan nilai rata-rata.
- Data `AsalKeberangkatan` juga diperbaiki untuk menghindari missing values.

## Encoding
Variabel kategori (`Gender` dan `AsalKeberangkatan`) dikonversi menjadi tipe `category`, lalu diubah menjadi kode numerik menggunakan `.cat.codes`.

## Normalisasi
Fitur numerik dinormalisasi menggunakan `StandardScaler` untuk meningkatkan performa model.

## Train-Test Split
Dataset dibagi menjadi dua bagian:
- **Train set** (80%) untuk melatih model
- **Test set** (20%) untuk menguji model

## Modeling dengan KNN
- Model K-Nearest Neighbors (KNN) dilatih dengan jumlah tetangga (`k=5`).
- Model diuji dengan data test dan performa diukur menggunakan `accuracy_score`.

## Evaluasi Model
- Akurasi pada training set: **85.53%**
- Akurasi pada test set: **81.56%**

## Optimasi Model
- Dilakukan pencarian nilai `k` terbaik dari 1 hingga 15.
- Ditemukan bahwa `k=11` memberikan akurasi terbaik sebesar **85.47%**.

Dengan demikian, model KNN dapat digunakan untuk memprediksi keselamatan penumpang Titanic dengan tingkat akurasi yang cukup baik.


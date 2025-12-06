# TUGAS_BESAR-MID-_APPLIED-MACHINE

Identifikasi Provinsi dengan Performa Terbaik pada OSN Menggunakan Metodologi CRISP-DM dan Machine Learning
Gambaran Proyek
Proyek ini bertujuan untuk menganalisis dan mengelompokkan provinsi di Indonesia berdasarkan performa mereka dalam ajang Olimpiade Sains Nasional (OSN) tingkat SMP dari tahun 2009 hingga 2025.

Menggunakan metodologi CRISP-DM (Cross-Industry Standard Process for Data Mining), proyek ini berfokus pada analisis efisiensi (Win Rate), yaitu perbandingan antara jumlah prestasi yang diraih dengan jumlah peserta yang dikirimkan, bukan hanya berdasarkan total perolehan medali semata.

Solusi akhir dari proyek ini berupa Dashboard Web Interaktif berbasis Gradio yang memungkinkan pengguna melakukan analisis klasterisasi secara real-time.

Metodologi (CRISP-DM)
Proyek ini mengikuti 6 tahapan standar CRISP-DM:

1. Business Understanding (Pemahaman Bisnis)
Masalah: Adanya ketimpangan prestasi pendidikan antar provinsi dan kesulitan dalam mengidentifikasi provinsi yang memiliki efisiensi tinggi (bukan hanya mengirim banyak peserta).

Tujuan: Mengelompokkan provinsi menjadi kategori performa (misalnya: Elite, Potensial, Perlu Evaluasi) untuk mendukung strategi pembinaan yang lebih tepat sasaran.

2. Data Understanding (Pemahaman Data)
Dataset: DATASET OSN.csv

Rentang Waktu: 2009 - 2025

Variabel Utama: Provinsi, Medali (Emas, Perak, Perunggu, Finalis), dan Tahun.

3. Data Preparation (Persiapan Data)
Agregasi Data: Mengubah data level transaksional (per Siswa) menjadi data level agregat (per Provinsi).

Logika Prestasi: Memasukkan status "Finalis" sebagai pencapaian prestasi (poin 1), selain Emas (poin 4), Perak (poin 3), dan Perunggu (poin 2).

Feature Engineering: Menghitung variabel Win Rate dengan rumus: (Total Prestasi / Total Peserta) * 100.

4. Modeling (Pemodelan)
Algoritma: K-Means Clustering (Unsupervised Learning).

Fitur Model: Menggunakan dua dimensi utama yaitu Kuantitas (Total Peserta) dan Kualitas (Win Rate).

5. Evaluation (Evaluasi)
Silhouette Score: Digunakan untuk mengukur validitas dan kualitas pemisahan antar klaster (rentang nilai -1 hingga 1).

Elbow Method: Digunakan sebagai panduan visual untuk menentukan jumlah klaster (K) yang paling optimal.

6. Deployment (Penerapan)
Platform: Library Python Gradio.

Fitur: Antarmuka web yang menyediakan slider untuk pengaturan jumlah klaster, filter tahun, grafik scatter plot interaktif, dan tabel peringkat detail.

Teknologi yang Digunakan
Bahasa Pemrograman: Python

Pengolahan Data: Pandas, NumPy

Machine Learning: Scikit-Learn

Visualisasi Data: Matplotlib, Seaborn

Deployment Interface: Gradio

Cara Menjalankan Project
Ikuti langkah-langkah berikut untuk menjalankan aplikasi ini:

Instalasi Library Pastikan Python telah terinstal, kemudian jalankan perintah berikut di terminal: pip install pandas numpy scikit-learn matplotlib seaborn gradio

Persiapan Dataset Pastikan file "DATASET OSN.csv" berada di dalam direktori atau folder yang sama dengan file kode program.

Eksekusi Program Jalankan file script Python atau notebook Jupyter. python app.py

Akses Dashboard Setelah program berhasil dijalankan, akses tautan yang muncul di terminal:

Tautan Lokal: http://127.0.0.1:7860

Tautan Publik: URL dengan akhiran .gradio.live (jika fitur share diaktifkan).

Struktur Data
Berikut adalah gambaran transformasi data yang dilakukan dalam proyek ini:

Data Mentah (Input) Data awal berupa daftar transaksional peserta (per baris adalah satu siswa).

Plaintext

Nama Peserta       Provinsi        Medali     Tahun
---------------------------------------------------
Siswa A            Jawa Barat      Emas       2024
Siswa B            Jawa Barat      Finalis    2024
Siswa C            DKI Jakarta     Perak      2024
Data Terproses (Output Agregasi) Data setelah diproses (Grouping) agar siap dimasukkan ke algoritma K-Means (per baris adalah satu provinsi).

Plaintext

Provinsi       Total Peserta   Total Prestasi   Win Rate (%)
------------------------------------------------------------
Jawa Barat     2               2                100.0
DKI Jakarta    1               1                100.0
Interpretasi Hasil Cluster
Model K-Means akan mengelompokkan provinsi ke dalam beberapa tingkatan (Tier) berdasarkan karakteristik berikut:

Tier Elite/Dominan: Provinsi yang memiliki jumlah partisipan tinggi dan rasio kemenangan (win rate) yang tinggi.

Tier High Performance: Provinsi dengan jumlah partisipan sedang namun sangat efisien dalam meraih prestasi.

Tier Potensial: Provinsi dengan partisipasi tinggi namun rasio kemenangan masih rata-rata.

Tier Perlu Evaluasi: Provinsi dengan rasio kemenangan di bawah rata-rata.

Kontribusi
Proyek ini disusun untuk memenuhi tugas Mata Kuliah Data Science.

Nama: RAMA BRAMANTHIYO SUSANTO PUTRA

Kelas: 5AI-A

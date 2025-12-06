# JUDUL PROYEK : Identifikasi Provinsi dengan Performa Terbaik pada OSN Menggunakan Metodologi CRISP-DM dan Machine Learning

# GAMBARAN PROYEK : 
Proyek ini bertujuan untuk menganalisis dan mengelompokkan provinsi di Indonesia berdasarkan performa mereka dalam ajang Olimpiade Sains Nasional (OSN) tingkat SMP dari tahun 2009 hingga 2025. Menggunakan metodologi CRISP-DM (Cross-Industry Standard Process for Data Mining), proyek ini berfokus pada analisis efisiensi (Win Rate), yaitu perbandingan antara jumlah prestasi yang diraih dengan jumlah peserta yang dikirimkan, bukan hanya berdasarkan total perolehan medali semata. Solusi akhir dari proyek ini berupa Dashboard Web Interaktif berbasis Gradio yang memungkinkan pengguna melakukan analisis klasterisasi secara real-time.

# METODOLOGI (CRISP-DM): Proyek ini mengikuti 6 tahapan standar sebagai berikut:

Business Understanding (Pemahaman Bisnis) Masalah utama adalah adanya ketimpangan prestasi pendidikan antar provinsi dan kesulitan dalam mengidentifikasi provinsi yang memiliki efisiensi tinggi (bukan hanya mengirim banyak peserta). Tujuannya adalah mengelompokkan provinsi menjadi kategori performa (misalnya: Elite, Potensial, Perlu Evaluasi) untuk mendukung strategi pembinaan yang lebih tepat sasaran.

Data Understanding (Pemahaman Data) Dataset yang digunakan adalah DATASET OSN.csv dengan rentang waktu tahun 2009 sampai 2025. Variabel utamanya meliputi Provinsi, Medali (Emas, Perak, Perunggu, Finalis), dan Tahun.

Data Preparation (Persiapan Data) Dilakukan agregasi data untuk mengubah data level transaksional (per Siswa) menjadi data level agregat (per Provinsi). Logika prestasi yang digunakan adalah memasukkan status "Finalis" sebagai pencapaian prestasi (poin 1), selain Emas (poin 4), Perak (poin 3), dan Perunggu (poin 2). Feature Engineering dilakukan dengan menghitung variabel Win Rate dengan rumus: (Total Prestasi dibagi Total Peserta) dikali 100.

Modeling (Pemodelan) Algoritma yang digunakan adalah K-Means Clustering (Unsupervised Learning). Fitur model menggunakan dua dimensi utama yaitu Kuantitas (Total Peserta) dan Kualitas (Win Rate).

Evaluation (Evaluasi) Menggunakan Silhouette Score untuk mengukur validitas dan kualitas pemisahan antar klaster (rentang nilai -1 hingga 1). Serta menggunakan Elbow Method sebagai panduan visual untuk menentukan jumlah klaster (K) yang paling optimal.

Deployment (Penerapan) Platform yang digunakan adalah Library Python Gradio. Fiturnya meliputi antarmuka web yang menyediakan slider untuk pengaturan jumlah klaster, filter tahun, grafik scatter plot interaktif, dan tabel peringkat detail.

# TEKNOLOGI YANG DIGUNAKAN : 
Bahasa Pemrograman Python, Pengolahan Data dengan Pandas dan NumPy, Machine Learning dengan Scikit-Learn, Visualisasi Data dengan Matplotlib dan Seaborn, serta Interface Deployment menggunakan Gradio.

# CARA MENJALANKAN PROJECT:

Langkah 1: Instalasi Library Pastikan Python telah terinstal, kemudian jalankan perintah berikut di terminal: pip install pandas numpy scikit-learn matplotlib seaborn gradio

Langkah 2: Persiapan Dataset Pastikan file bernama DATASET OSN.csv berada di dalam direktori atau folder yang sama dengan file kode program.

Langkah 3: Eksekusi Program Jalankan file script Python atau notebook Jupyter dengan perintah: python app.py

Langkah 4: Akses Dashboard Setelah program berhasil dijalankan, akses tautan yang muncul di terminal. Untuk lokal akses ke http://127.0.0.1:7860 dan untuk publik akses URL dengan akhiran .gradio.live (jika fitur share diaktifkan).

# STRUKTUR DATA:

Data Mentah (Input) Data awal berupa daftar transaksional peserta di mana setiap baris mewakili satu siswa. Kolom terdiri dari Nama Peserta, Provinsi, Medali, dan Tahun. Contoh: Siswa A dari Jawa Barat meraih Emas tahun 2024.

Data Terproses (Output Agregasi) Data setelah diproses (Grouping) agar siap dimasukkan ke algoritma K-Means di mana setiap baris mewakili satu provinsi. Kolom terdiri dari Provinsi, Total Peserta, Total Prestasi, dan Win Rate (Persen). Contoh: Jawa Barat mengirim 2 peserta, meraih 2 prestasi, maka Win Rate adalah 100 persen.

INTERPRETASI HASIL CLUSTER: Model K-Means akan mengelompokkan provinsi ke dalam beberapa tingkatan (Tier) berdasarkan karakteristik berikut:

Tier Elite atau Dominan: Provinsi yang memiliki jumlah partisipan tinggi dan rasio kemenangan (win rate) yang tinggi.

Tier High Performance: Provinsi dengan jumlah partisipan sedang namun sangat efisien dalam meraih prestasi.

Tier Potensial: Provinsi dengan partisipasi tinggi namun rasio kemenangan masih rata-rata.

Tier Perlu Evaluasi: Provinsi dengan rasio kemenangan di bawah rata-rata.

# KONTRIBUSI : 
Proyek ini disusun untuk memenuhi tugas Mata Kuliah APPLIED MACHINE LEARNING

Nama: RAMA BRAMANTHIYO SUSANTO PUTRA 

Kelas: 5AI-A

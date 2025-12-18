📘 Prediksi Pendonor Darah Potensial (Blood Transfusion Prediction)

👤 Informasi

Nama: Muhammad Daffa Samudra

NIM: 233307054

Repo: https://github.com/daffasamudra/Blood-Transfusion-Model.git

Video: https://drive.google.com/drive/folders/1PEU-K95x_u5mSGGtHYTkewnVcRTPLJlP?usp=sharing

1. 🎯 Ringkasan Proyek

Proyek ini bertujuan untuk membantu pusat layanan transfusi darah dalam memprediksi apakah seorang pendonor lama akan kembali mendonorkan darahnya di masa depan.

Domain: Kesehatan / Manajemen Stok Darah.

Metode: Melakukan data preparation (Handling Imbalance & Scaling).

Modeling: Membangun 3 model yaitu KNN (Baseline), Random Forest (Advanced), dan Neural Network (Deep Learning).

Hasil: Melakukan komparasi performa untuk menentukan model dengan akurasi terbaik.

2. 📄 Problem & Goals

Problem Statements:

Ketidakseimbangan data (imbalanced data) membuat model sulit mendeteksi pendonor potensial (kelas minoritas).

Pusat layanan darah membutuhkan efisiensi dalam menargetkan pendonor lama agar hemat waktu dan biaya pemasaran.

Goals:

Mengidentifikasi pola fitur yang paling berpengaruh terhadap keputusan donor.

Membangun model klasifikasi dengan akurasi yang kompetitif (> 75%).

Menentukan algoritma terbaik antara pendekatan klasik, ensemble, dan deep learning.

📁 Struktur Folder

project/
│
├── data/                                   # Dataset sumber (transfusion.data)
├── images/                                 # Hasil visualisasi & plot evaluasi
│   ├── Matriks-Korelasi-Antar-Fitur.jpg
│   ├── Persentase Pendonor... .jpg
│   ├── SEBARAN-FITUR.jpg
│   ├── Tabel-Banding.jpg
│   ├── VISUAL-KNN.jpg
│   ├── VISUAL-RF.jpg
│   └── Visual-MLP.jpg
├── models/                                 # Model yang sudah dilatih (.pkl)
│   ├── model_deeplearning.pkl
│   ├── model_knn.pkl
│   └── model_rf.pkl
├── notebooks/                              # Jupyter Notebook utama
│   └── UAS_DATA_SIENCE_Transfusion.ipynb
├── src/                                    # Source code pendukung (jika ada)
├── Cheklist Submit.md                      # File checklist
├── LAPORAN PROYEK AKHIR MATA KULIAH.docx   # Laporan lengkap proyek
├── LICENSE                                 # Lisensi proyek
├── README.md                               # Dokumentasi proyek ini
└── requirements.txt                        # Daftar library & dependencies


3. 📊 Dataset

Sumber: UCI Machine Learning Repository (Blood Transfusion Service Center).

Jumlah Data: 748 Baris.

Tipe: Tabular (Numerik).

Fitur Utama

Fitur

Deskripsi

Recency (R)

Bulan sejak donasi terakhir.

Frequency (F)

Total jumlah donasi.

Monetary (M)

Total volume darah (c.c.).

Time (T)

Bulan sejak donasi pertama kali (lama menjadi anggota).

Target

1 = Mendonor kembali, 0 = Tidak mendonor.

4. 🔧 Data Preparation

Langkah-langkah yang dilakukan dalam memproses data sebelum pemodelan:

Data Cleaning: Memeriksa missing values (Dataset bersih/tidak ada missing value).

Feature Selection: Menghapus fitur Monetary karena memiliki korelasi sempurna (1.0) dengan Frequency, sehingga informasi menjadi redundan.

Handling Imbalance: Menggunakan teknik SMOTE (Synthetic Minority Over-sampling Technique) pada data training untuk menyeimbangkan kelas minoritas (Donor) agar model tidak bias.

Scaling: Menggunakan StandardScaler untuk menormalisasi fitur Recency, Frequency, dan Time. Langkah ini krusial untuk algoritma KNN dan Neural Network.

Splitting: Data dibagi menjadi 80% Training dan 20% Testing.

5. 🤖 Modeling

Tiga algoritma yang dikembangkan dalam proyek ini:

Model 1 – Baseline (KNN):
Menggunakan algoritma K-Nearest Neighbors sebagai pembanding dasar. Model ini mengklasifikasikan berdasarkan mayoritas kelas dari tetangga terdekat.

Model 2 – Advanced ML (Random Forest):
Menggunakan Random Forest Classifier (Ensemble Method). Model ini dipilih karena kemampuannya menangani outlier dan memberikan informasi feature importance.

Model 3 – Deep Learning (MLP):
Menggunakan Multilayer Perceptron (Neural Network) dengan framework TensorFlow/Keras. Arsitektur terdiri dari Input Layer, Hidden Layers dengan aktivasi ReLU, Dropout untuk mencegah overfitting, dan Output Layer dengan aktivasi Sigmoid.

6. 🧪 Evaluation

Evaluasi dilakukan menggunakan metrik Accuracy Score dan analisis Confusion Matrix.

Hasil Komparasi

Model

Accuracy Score

Analisis Singkat

KNN (Baseline)

0.72

Masih menghasilkan banyak False Negative.

Random Forest

0.73

Stabil, menemukan bahwa fitur 'Time' sangat berpengaruh.

Deep Learning

0.77

Model Terbaik. Mampu menangkap pola data lebih baik dibanding metode tradisional.

7. 🏁 Kesimpulan

Berdasarkan eksperimen yang dilakukan:

Model Terbaik: Deep Learning (MLP) terbukti memberikan akurasi tertinggi sebesar 77% pada data uji.

Insight Data:

Dataset memiliki ketimpangan kelas yang signifikan (76% Tidak Donor vs 24% Donor).

Analisis Feature Importance dari Random Forest menunjukkan bahwa Time (lama menjadi anggota) dan Recency (jarak donasi terakhir) adalah dua faktor penentu utama seseorang akan mendonor kembali.

8. 🔮 Future Work

Rencana pengembangan selanjutnya:

[X] Menambah Data: Mengumpulkan lebih banyak data historis untuk meningkatkan performa model Deep Learning.

[X] Hyperparameter Tuning: Melakukan GridSearch atau Bayesian Optimization untuk mencari parameter terbaik bagi Random Forest dan MLP.

[X] Deployment: Membuat aplikasi web sederhana menggunakan Streamlit agar model dapat digunakan oleh staf medis secara langsung.

9. 🔁 Reproducibility

Untuk menjalankan proyek ini di komputer lokal Anda:

1. Clone Repository:

git clone [Link Repo Anda]


2. Install Dependencies:
Pastikan Python sudah terinstal, lalu jalankan:

pip install -r requirements.txt


3. Run Notebook:
Jalankan file Jupyter Notebook yang ada di folder notebooks/.

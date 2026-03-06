# MLOps Fraud Detection System

## Overview

Project ini merupakan implementasi sistem **Machine Learning Operations (MLOps)** yang bertujuan untuk mendeteksi potensi **fraud (penipuan) pada transaksi perbankan** menggunakan pendekatan Machine Learning.

Dalam sistem perbankan modern, jumlah transaksi yang sangat besar membuat proses identifikasi fraud secara manual menjadi tidak efektif. Oleh karena itu, sistem deteksi fraud berbasis Machine Learning digunakan untuk menganalisis pola transaksi dan mengidentifikasi aktivitas yang mencurigakan secara otomatis.

Proyek ini berfokus pada pembangunan pipeline Machine Learning yang terstruktur dan mengikuti praktik standar industri, mulai dari pengolahan data hingga proses evaluasi model. Selain itu, proyek ini juga mengimplementasikan konsep **MLOps** dengan menggunakan GitHub sebagai platform pengelolaan kode serta GitHub Codespaces sebagai lingkungan pengembangan yang dapat direproduksi.

Dengan pendekatan ini, proyek tidak hanya berfungsi sebagai eksperimen model Machine Learning, tetapi juga sebagai fondasi untuk pengembangan sistem Machine Learning yang lebih kompleks di masa depan.

---

# Project Objectives

Tujuan utama dari proyek ini adalah:

* Mengembangkan sistem Machine Learning untuk mendeteksi transaksi fraud pada data perbankan.
* Menerapkan praktik **MLOps workflow** dalam pengembangan proyek Machine Learning.
* Menggunakan **struktur repository standar industri** untuk proyek Machine Learning.
* Menggunakan **GitHub Codespaces** sebagai lingkungan pengembangan yang konsisten.
* Mengimplementasikan **GitHub Flow** sebagai strategi pengelolaan branch dan eksperimen model.

---

# Project Structure

Repository ini disusun menggunakan struktur direktori yang umum digunakan dalam proyek Machine Learning agar kode tetap rapi, modular, dan mudah dikembangkan.

Struktur direktori utama pada proyek ini adalah sebagai berikut:

MLOps-Fraud-Detection

data
│
├── raw
│   Dataset mentah yang belum diproses

├── processed
│   Dataset yang sudah melalui tahap preprocessing

notebooks
│
└── eda.ipynb
Notebook untuk eksplorasi data (Exploratory Data Analysis)

src
│
├── data
│   ├── load_data.py
│   └── preprocess.py

├── features
│   └── build_features.py

├── models
│   ├── train_model.py
│   └── evaluate_model.py

└── inference
└── predict.py

configs
│
└── config.yaml

tests
│
└── test_model.py

scripts

requirements.txt
README.md
LICENSE

Struktur ini memisahkan setiap komponen pipeline Machine Learning sehingga proses pengembangan menjadi lebih terorganisir.

---

# Machine Learning Workflow

Pipeline Machine Learning dalam proyek ini terdiri dari beberapa tahap utama.

## 1 Data Collection

Dataset transaksi perbankan akan disimpan pada folder:

data/raw

Dataset ini berisi berbagai informasi transaksi seperti:

* jumlah transaksi
* waktu transaksi
* tipe transaksi
* akun pengirim
* akun penerima
* label transaksi (fraud atau non-fraud)

---

## 2 Data Preprocessing

Tahap preprocessing bertujuan untuk membersihkan dan menyiapkan data sebelum digunakan oleh model Machine Learning.

Proses ini dilakukan menggunakan script:

src/data/preprocess.py

Beberapa proses yang dilakukan antara lain:

* membersihkan data yang tidak valid
* menangani missing values
* encoding fitur kategorikal
* normalisasi nilai numerik

Hasil preprocessing akan disimpan pada folder:

data/processed

---

## 3 Feature Engineering

Tahap ini bertujuan untuk membuat fitur tambahan yang dapat membantu model dalam mengenali pola fraud.

Script yang digunakan:

src/features/build_features.py

Contoh fitur yang dapat dibuat antara lain:

* frekuensi transaksi dalam periode waktu tertentu
* rasio jumlah transaksi
* pola transaksi mencurigakan

---

## 4 Model Training

Setelah data siap digunakan, model Machine Learning akan dilatih menggunakan script berikut:

src/models/train_model.py

Beberapa algoritma yang dapat digunakan untuk fraud detection antara lain:

* Logistic Regression
* Random Forest
* Gradient Boosting
* XGBoost

Model yang sudah dilatih dapat disimpan dan digunakan kembali untuk proses prediksi.

---

## 5 Model Evaluation

Setelah proses training selesai, performa model akan dievaluasi menggunakan:

src/models/evaluate_model.py

Beberapa metrik evaluasi yang dapat digunakan antara lain:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC AUC

Evaluasi ini penting untuk mengetahui kemampuan model dalam mendeteksi transaksi fraud secara akurat.

---

## 6 Model Inference

Tahap terakhir adalah melakukan prediksi menggunakan model yang sudah dilatih.

Script yang digunakan:

src/inference/predict.py

Output dari model berupa prediksi apakah suatu transaksi termasuk:

0 = Non Fraud
1 = Fraud

---

# Development Environment

Proyek ini menggunakan **GitHub Codespaces** sebagai lingkungan pengembangan berbasis cloud.

Keuntungan menggunakan Codespaces antara lain:

* tidak perlu instalasi Python secara lokal
* environment dapat dijalankan langsung melalui browser
* dependency proyek dapat diinstal secara otomatis
* proyek dapat dijalankan kembali dengan konfigurasi yang sama

Environment yang digunakan pada proyek ini adalah:

Python 3.10

---

# How to Run the Project in Codespaces

Berikut langkah-langkah menjalankan proyek menggunakan GitHub Codespaces.

## Step 1 Open Repository

Buka repository proyek ini di GitHub.

---

## Step 2 Start Codespaces

Klik tombol:

Code

kemudian pilih tab:

Codespaces

Lalu klik:

Create Codespace

GitHub akan secara otomatis membuat environment development untuk proyek ini.

---

## Step 3 Install Dependencies

Setelah Codespaces berjalan, buka terminal dan jalankan perintah berikut:

pip install -r requirements.txt

Perintah ini akan menginstal seluruh library yang dibutuhkan oleh proyek.

---

## Step 4 Exploratory Data Analysis

Untuk memahami dataset, buka notebook berikut:

notebooks/eda.ipynb

Notebook ini digunakan untuk:

* memahami struktur dataset
* melakukan visualisasi data
* mengidentifikasi pola awal dalam data

---

## Step 5 Training Model

Untuk melatih model Machine Learning jalankan perintah berikut:

python src/models/train_model.py

Script ini akan melatih model menggunakan dataset yang telah diproses.

---

## Step 6 Evaluasi Model

Untuk mengevaluasi performa model jalankan:

python src/models/evaluate_model.py

Script ini akan menghasilkan metrik performa model.

---

## Step 7 Prediction

Untuk melakukan prediksi pada data baru jalankan:

python src/inference/predict.py

Model akan memprediksi apakah transaksi termasuk fraud atau tidak.

---

# Branching Strategy (GitHub Flow)

Proyek ini menggunakan **GitHub Flow** sebagai strategi pengelolaan kode.

Langkah kerja GitHub Flow adalah sebagai berikut:

1. Membuat branch baru dari branch main

git checkout -b feat/initial-eda

2. Melakukan perubahan atau eksperimen pada kode

3. Commit perubahan

git commit -m "Add initial EDA notebook"

4. Push branch ke repository GitHub

git push origin feat/initial-eda

5. Membuat Pull Request untuk menggabungkan perubahan ke branch main.

Pendekatan ini memudahkan pengelolaan eksperimen dalam proyek Machine Learning.

---

# Future Improvements

Beberapa pengembangan yang dapat dilakukan di masa depan antara lain:

* otomatisasi pipeline Machine Learning
* deployment model menggunakan Docker
* integrasi CI/CD pipeline
* monitoring performa model
* implementasi sistem fraud detection secara real-time

---

# Author

Irmalia Dwi Kautsar
Informatics Engineering Student
Universitas Brawijaya

---

# License

Proyek ini dibuat untuk keperluan pembelajaran pada mata kuliah MLOps.

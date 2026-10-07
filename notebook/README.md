# Folder Notebook - Pipeline Eksperimen CRISP-DM

## Panduan Penggunaan

Jalankan notebook secara berurutan sesuai nomor file:

### 1. `01_eda_eksplorasi.ipynb`
**Tujuan**: Exploratory Data Analysis (EDA) dan Pemahaman Dataset

Apa yang akan dilakukan:
- Memuat dataset dari `data/raw/predict_students_dropout_and_academic_success.csv`
- Menampilkan statistik deskriptif (mean, median, std) untuk setiap kolom
- Visualisasi distribusi variabel numerik dan kategori
- Identifikasi nilai kosong (missing values)
- Analisis korelasi antar fitur
- Deteksi ketidakseimbangan kelas (class imbalance) pada target `Status`

Output:
- Grafik & insight awal yang akan digunakan di Bab IV skripsi

---

### 2. `02_persiapan_data.ipynb` (akan dibuat)
**Tujuan**: Data Preprocessing & Balancing

Apa yang akan dilakukan:
- Cleaning data: imputasi nilai kosong, penghapusan duplikat
- Encoding variabel kategori (One-Hot Encoding / LabelEncoder)
- Normalisasi/Standarisasi fitur numerik (StandardScaler)
- Pembagian data latih/uji dengan stratified split (80:20)
- Penanganan ketidakseimbangan kelas menggunakan Borderline-SMOTE atau SMOTE-NC

Output:
- Dataset siap latih di `data/processed/` 
- Visualisasi perbandingan sebelum & sesudah SMOTE

---

### 3. `03_pemodelan.ipynb` (akan dibuat)
**Tujuan**: Pelatihan Model Random Forest & XGBoost

Apa yang akan dilakukan:
- Melatih model Random Forest dengan hyperparameter default
- Melatih model XGBoost dengan hyperparameter default
- Hyperparameter tuning menggunakan GridSearchCV atau RandomizedSearchCV
- Simpan model terlatih ke `model/` dalam format `.pkl`

Output:
- Model terbaik untuk setiap algoritma
- Log hyperparameter optimal

---

### 4. `04_evaluasi.ipynb` (akan dibuat)
**Tujuan**: Evaluasi & Interpretasi Model

Apa yang akan dilakukan:
- Hitung metrik: Accuracy, Precision, Recall, F1-Score, ROC-AUC, PR-AUC
- Buat confusion matrix & visualisasi ROC curve
- Feature importance dari Random Forest & XGBoost
- Analisis SHAP untuk interpretasi keputusan model
- Buat tabel perbandingan kedua model

Output:
- Tabel hasil evaluasi (untuk Tabel Hasil Penelitian di Bab IV)
- Grafik SHAP (untuk visualisasi Bab IV)

---

## Catatan Penting

- **Bersihkan Keluaran Sel**: Sebelum commit ke Git, jalankan `Kernel > Restart & Clear Output` agar file notebook tidak terlalu besar.
- **Struktur Path Relatif**: Semua path di notebook gunakan relatif terhadap folder `mahasiswa-dropout/`:
  - Data raw: `data/raw/predict_students_dropout_and_academic_success.csv`
  - Data processed: `data/processed/X_train.pkl` dll.
  - Model: `model/rf_tuned.pkl`
- **Markdown Dokumentasi**: Setiap cell Python didahului dengan Markdown cell yang menjelaskan tujuan & insight dalam bahasa Indonesia yang mudah dipahami.

---

## Referensi Pustaka Inline

Setiap notebook mencantumkan komentar referensi ke artikel terkait di `literatur/tabel_penelitian_terdahulu.md` untuk memudahkan cross-reference saat penulisan skripsi.

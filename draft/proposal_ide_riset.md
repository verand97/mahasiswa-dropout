# Draf Proposal Ide Riset: Mahasiswa Dropout & Keterlambatan Kelulusan
**Domain**: Educational Data Mining (EDM) & Machine Learning  
**Status**: Draf Alternatif 1  
**Target Program Studi**: S1 Teknik Informatika  

---

## 1. Usulan Judul Skripsi
1. **Penerapan Algoritma CatBoost dan Borderline-SMOTE Berbasis Explainable AI (SHAP) untuk Deteksi Dini Risiko Mahasiswa Dropout** *(Rekomendasi Utama)*
2. **Analisis Prediksi Keterlambatan Kelulusan Mahasiswa Berdasarkan Data Akademik Semester Awal Menggunakan Ensemble Learning**
3. **Komparasi Algoritma Random Forest dan XGBoost dengan Penanganan Ketidakseimbangan Kelas untuk Klasifikasi Retensi Mahasiswa**

---

## 2. Latar Belakang & Fenomena Lapangan (Berita Riil)
* **Fenomena Nasional**: Angka putus kuliah (*dropout*) dan keterlambatan kelulusan masih menjadi isu krusial di perguruan tinggi Indonesia. Biaya kuliah, adaptasi akademik pada tahun pertama, dan kondisi sosio-ekonomi keluarga sering kali menjadi kendala utama kelangsungan studi mahasiswa.
* **Permasalahan Nyata di Kampus**: 
  - Bagian akademik dan dosen pembimbing akademik (PA) umumnya baru menyadari mahasiswa berada dalam kondisi kritis pada semester-semester akhir (semester 6 atau 7), saat batas masa studi hampir habis.
  - Perguruan tinggi membutuhkan sistem peringatan dini (*Early Warning System*) yang mampu memprediksi risiko putus kuliah secara akurat hanya berdasarkan performa akademik semester 1 dan 2 beserta faktor demografi.
* **Kelemahan Penanganan Konvensional**: Evaluasi manual berdasarkan IPK semata sering kali terlambat dan tidak mampu menangkap interaksi kompleks antara faktor sosio-ekonomi (pekerjaan orang tua, beasiswa, status pembayaran kuliah) dan beban kredit mata kuliah yang diambil.

---

## 3. Rumusan Masalah & Research Questions (RQ)
1. **RQ1**: Bagaimana pengaruh penanganan ketidakseimbangan kelas (*class imbalance*) menggunakan Borderline-SMOTE terhadap kemampuan model dalam mendeteksi mahasiswa yang berisiko dropout (*metrik Recall*)?
2. **RQ2**: Algoritma *Ensemble Learning* mana (antara CatBoost, Random Forest, dan XGBoost) yang menghasilkan performa klasifikasi terbaik pada data akademik mahasiswa?
3. **RQ3**: Atribut akademik dan sosio-ekonomi apa saja yang menjadi faktor paling kritis pemicu risiko putus kuliah berdasarkan analisis *Explainable AI (SHAP)*?

---

## 4. Informasi & Metadata Dataset Riil
* **Nama Dataset**: Predict Students' Dropout and Academic Success
* **Sumber Resmi**: UCI Machine Learning Repository (Dataset ID: 697)
* **Tautan Unduh**: https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success
* **Asal Data**: Data riil dari institusi pendidikan tinggi (*Polytechnic Institute of Portalegre, Portugal*)
* **Jumlah Data**: 4.424 baris
* **Jumlah Atribut**: 36 kolom (35 fitur prediktor + 1 target)
* **Target / Label**: `Target` dengan 3 kelas awal: *Dropout*, *Enrolled*, dan *Graduate* (dapat difokuskan menjadi biner: *Dropout* vs *Non-Dropout* / *Retained*).
* **Karakteristik Data Mentah (Belum Diolah)**:
  - Data terdiri atas variabel demografi (usia, jenis kelamin, status pernikahan), variabel sosio-ekonomi (kualifikasi/pekerjaan orang tua, status beasiswa, status tunggakan SPP), serta capaian akademik semester 1 & semester 2 (unit kurikulum terdaftar, dievaluasi, disetujui, dan nilai rata-rata).
  - Skala nilai antar fitur bervariasi (rentang nilai akademik 0-20, usia, dan kode kategori nominal).
  - Terdapat ketimpangan kelas (proporsi mahasiswa dropout ~32% berbanding mahasiswa yang bertahan/lulus ~68%).

---

## 5. Celah Penelitian (Research Gap vs Studi Terdahulu)
* **Studi Terdahulu**: 
  - Sebagian besar riset sebelumnya hanya membandingkan algoritma klasik (seperti Naive Bayes atau C4.5) tanpa menangani ketimpangan data secara spesifik.
  - Model yang dibangun sering kali berstatus *"black-box"*; hanya menghasilkan persentase akurasi tanpa menjelaskan **mengapa** seorang mahasiswa diklasifikasikan berisiko dropout.
* **Celah yang Diisi Penelitian Ini**:
  1. Penerapan teknik balancing *Borderline-SMOTE* yang fokus memperkuat sampel pada batas keputusan (*decision boundary*).
  2. Integrasi *Explainable AI (XAI)* menggunakan nilai SHAP (*SHapley Additive exPlanations*) untuk menghasilkan interpretasi global (faktor paling dominan secara umum) dan interpretasi lokal (faktor penyebab pada kasus individu mahasiswa tertentu).

---

## 6. Rencana Alur Kerja Metodologi (CRISP-DM)
1. **Business/Academic Understanding**: Perumusan tujuan Early Warning System dan penentuan metrik evaluasi utama (Recall & F1-Score pada kelas Dropout).
2. **Data Understanding**: Eksplorasi distribusi fitur, korelasi antar unit kurikulum semester 1 & 2, dan proporsi kelas target.
3. **Data Preparation**: 
   - Mapping label (Biner: Dropout vs Non-Dropout).
   - Encoding fitur kategorikal.
   - Penskalaan fitur numerik (StandardScaler / RobustScaler).
   - Penanganan ketidakseimbangan kelas dengan Borderline-SMOTE pada data training.
4. **Modeling**:
   - Baseline model: Logistic Regression.
   - Candidate models: Random Forest, XGBoost, CatBoost.
   - Hyperparameter tuning menggunakan Stratified 5-Fold Cross Validation.
5. **Evaluation**:
   - Evaluasi kuantitatif: Accuracy, Precision, Recall, F1-Score, dan ROC-AUC.
   - Analisis interpretasi model menggunakan SHAP Summary Plot dan Waterfall Plot.

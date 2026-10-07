# Folder Data Raw (Data Mentah)

## Aturan Penting

**Berkas di folder ini TIDAK BOLEH diedit atau diubah secara manual.**

Seluruh pra-pemrosesan data dilakukan melalui script Python / Jupyter Notebook dan hasilnya disimpan di folder `data/processed/`.

## Metadata Dataset Utama

- **Nama File**: `predict_students_dropout_and_academic_success.csv`
- **Sumber Resmi**: UCI Machine Learning Repository (Dataset ID: 697)
- **Tautan Resmi**: https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success
- **Sitasi Asli**: Realinho, V., Machado, J., Baptista, L., & Martins, M. V. (2021). *Predict Students' Dropout and Academic Success*. Data, 6(11), 110. https://doi.org/10.3390/data6110110
- **Jumlah Data**: 4.424 baris
- **Jumlah Fitur**: 37 kolom (36 atribut prediktor + 1 target `Status`)
- **Distribusi Target**:
  * Graduate: 2.209 data (49,9%)
  * Dropout: 1.421 data (32,1%)
  * Enrolled: 794 data (18,0%)
- **Format Delimiter**: Semicolon (`;`)
- **Ukuran File**: 528.772 bytes (516,38 KB)
- **MD5 Checksum**: `379b3177e077b8187b20317b81929729`
- **Tanggal Unduh**: 4 Oktober 2026

## Akses Dataset

Jika file belum ada, unduh dari:
```
https://archive.ics.uci.edu/static/public/697/predict+students+dropout+and+academic+success.zip
```

Ekstrak file CSV dan letakkan di folder ini. Verifikasi nama file dan jumlah baris sebelum memulai notebook EDA.

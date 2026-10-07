# Folder Data Processed (Data Olahan)

## Aturan Penting

**Seluruh berkas di folder ini WAJIB dihasilkan oleh skrip/kode (bukan manual).**

Berisi data hasil pembersihan missing values, encoding, normalisasi, dan pembagian train/test.

## Berkas yang Akan Disimpan (Output Notebook)

Setelah menjalankan `02_persiapan_data.ipynb`, folder ini akan berisi:

1. **Train Set**:
   - `X_train.pkl` – Fitur data latih (setelah preprocessing & SMOTE)
   - `y_train.pkl` – Label data latih

2. **Test Set** (tanpa SMOTE):
   - `X_test.pkl` – Fitur data uji (asli, tanpa oversampling)
   - `y_test.pkl` – Label data uji

3. **Metadata & Scaler**:
   - `scaler.pkl` – StandardScaler untuk normalisasi
   - `encoder.pkl` – OneHotEncoder atau LabelEncoder untuk kategori
   - `preprocessing_log.txt` – Laporan singkat jumlah baris & kolom sebelum/sesudah

## Cara Menggunakan File Processed

Di notebook `03_pemodelan.ipynb` dan seterusnya:

```python
import pickle

with open('data/processed/X_train.pkl', 'rb') as f:
    X_train = pickle.load(f)
    
with open('data/processed/y_train.pkl', 'rb') as f:
    y_train = pickle.load(f)
    
# Lanjutkan training model...
```

## Catatan Reproducibility

- Setiap kali preprocessing dilakukan ulang, pastikan random_state=42 agar split data konsisten.
- Simpan seed/random_state di file `preprocessing_log.txt` untuk dokumentasi.

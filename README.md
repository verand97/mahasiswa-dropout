# Proyek Skripsi: Prediksi Mahasiswa Dropout

Repositori ini adalah direktori utama untuk proyek penelitian skripsi:
**Komparasi Algoritma Random Forest dan XGBoost dengan Penanganan Ketidakseimbangan Kelas untuk Prediksi Status Dropout Mahasiswa**

## Lokasi Dataset
Dataset mentah (raw) tersimpan secara permanen di:
`data/raw/predict_students_dropout_and_academic_success.csv`

## Cara Menjalankan Notebook
Sangat disarankan untuk membuka Jupyter Notebook / VS Code dari folder `mahasiswa-dropout` ini (sebagai working directory).

```bash
cd C:\Users\veram\skripsi\riset-data\mahasiswa-dropout
jupyter notebook
```

Dengan begitu, path dataset di dalam kode Python cukup dipanggil menggunakan:
```python
import pandas as pd
df = pd.read_csv('data/raw/predict_students_dropout_and_academic_success.csv', sep=';')
```

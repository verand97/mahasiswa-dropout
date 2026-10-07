# Folder Model - Artefak Model Terlatih

## Panduan Penggunaan

Simpan model terlatih dalam format `.pkl` atau `.joblib` setelah menjalankan notebook `03_pemodelan.ipynb`.

## Konvensi Penamaan Berkas

Gunakan format: `[NAMA_MODEL]_[VERSI_ATAU_TANGGAL].pkl`

Contoh:
- `random_forest_tuned_20261007.pkl` – Random Forest dengan tuning GridSearch
- `xgboost_tuned_20261007.pkl` – XGBoost dengan tuning GridSearch
- `baseline_rf_default.pkl` – Random Forest model baseline (hyperparameter default)

## Berkas yang Akan Disimpan

Setelah `03_pemodelan.ipynb` selesai:

1. **Model Utama**:
   - `random_forest_tuned.pkl` – Model Random Forest terbaik (setelah tuning)
   - `xgboost_tuned.pkl` – Model XGBoost terbaik (setelah tuning)

2. **Model Baseline** (optional):
   - `random_forest_baseline.pkl` – Sebagai pembanding
   - `xgboost_baseline.pkl` – Sebagai pembanding

3. **Hyperparameter Log**:
   - `hyperparameter_tuning_log.txt` – Hasil GridSearchCV:
     * Best params untuk RF
     * Best params untuk XGB
     * Best CV score masing-masing

## Cara Memuat Model untuk Evaluasi

Di notebook `04_evaluasi.ipynb`:

```python
import pickle
import sklearn

with open('model/random_forest_tuned.pkl', 'rb') as f:
    rf_model = pickle.load(f)

with open('model/xgboost_tuned.pkl', 'rb') as f:
    xgb_model = pickle.load(f)

# Prediksi pada test set
y_pred_rf = rf_model.predict(X_test)
y_pred_xgb = xgb_model.predict(X_test)
```

## Catatan

- Jangan commit model file `.pkl` ke Git jika ukurannya >50 MB
- Jika perlu, dokumentasikan model weights & hyperparameter final di `hyperparameter_tuning_log.txt`
- Setiap model harus disertai ringkasan akurasi & F1-score di log

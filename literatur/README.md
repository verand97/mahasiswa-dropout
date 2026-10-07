# Folder Literatur - Pemetaan Penelitian Terdahulu & Referensi

## Panduan Penggunaan

Folder ini memuat semua referensi ilmiah dan pemetaan state-of-the-art untuk penelitian.

### Struktur Berkas

1. **`tabel_penelitian_terdahulu.md`** (UTAMA)
   - Tabel komparatif 10+ artikel jurnal yang terverifikasi DOI aktif
   - Kolom: Peneliti, Judul, Jurnal/Indeks, Dataset, Metode, Metrik, Hasil, Research Gap
   - Setiap artikel harus:
     * Diterbitkan 2021–2026 (3–5 tahun terakhir) atau relevan dengan dataset UCI 697
     * Minimal SINTA 3 atau Scopus/IEEE/Springer Nature (internasional bereputasi)
     * DOI dapat diverifikasi aktif via https://doi.org/...
     * Membahas prediksi dropout atau student success dengan machine learning

2. **`referensi_lengkap.bib`** (optional)
   - File BibTeX untuk Zotero / Mendeley export
   - Memudahkan auto-cite di Word via plugin Mendeley/Zotero

3. **PDF Artikel** (optional, jika ukuran kecil)
   - Jika artikel berukuran <10 MB, boleh disimpan di sini
   - Namai: `[Pengarang_Tahun].pdf` (contoh: `Villar_2024.pdf`)
   - Jangan push PDF besar ke Git; cukup catat URL di tabel

### Status Referensi Saat Ini

#### Terverifikasi (7 artikel):
1. Villar & de Andrade (2024) – Springer Nature – DOI: 10.1007/s44163-023-00079-z ✓
2. Ridwan & Priyatno (2024) – JECA ✓
3. [Artikel 3–7 dari refrensi7artikel.md] ✓

#### Masih Perlu Ditambah (3 artikel):
- Target total 10 artikel
- Prioritas: Scopus Q2–Q4, SINTA 1–3, IEEE Xplore, atau Springer Nature
- Topik fokus:
  * Explainable AI / SHAP untuk education
  * Borderline-SMOTE atau ADASYN untuk imbalanced learning
  * XGBoost / LightGBM / CatBoost untuk prediksi akademik

### Cara Mencari & Verifikasi Artikel

1. **Query Database**:
   - Google Scholar: `student dropout machine learning 2024`
   - Scopus: Filter publikasi 2021–2026, Education & Computer Science
   - IEEE Xplore: Query `dropout prediction`
   - Springer: Direct search pada Springer Nature portal

2. **Verifikasi DOI**:
   - Buka https://doi.org/[DOI_NUMBER]
   - Verifikasi judul, penulis, tahun publikasi sesuai daftar
   - Catat abstrak ringkas & metode utama

3. **Cek Indeks Jurnal**:
   - Scopus → SJRQ1–Q4
   - SINTA → Check via sinta.kemdikbud.go.id
   - IEEE → langsung teridentifikasi dari URL
   - Springer Nature → tercatat otomatis

### Integrasi ke Skripsi

Saat menulis Bab II (Tinjauan Pustaka):
1. Copy 5–7 artikel paling relevan dari tabel ke slide presentasi / draft Bab II
2. Tulis ulang hasil penelitian setiap paper dalam kalimat Anda sendiri (hindari copy-paste)
3. Identifikasi research gap eksplisit di setiap artikel
4. Ringkas posisi penelitian Anda vs 10 artikel tersebut

### Tools Manajemen Sitasi (Optional)

- **Mendeley**: Plugin untuk Word/LibreOffice, auto-cite
- **Zotero**: Open-source, terintegrasi dengan Firefox/Chrome
- **BibTeX + Overleaf**: Untuk laporan LaTeX (jika diperlukan)

Untuk sementara, gunakan format **APA 7** manual di daftar pustaka skripsi.

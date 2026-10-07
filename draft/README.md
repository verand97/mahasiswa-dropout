# Folder Draft - Naskah Proposal & Skripsi

## Panduan Penggunaan

Simpan berkas naskah proposal, bab-bab skripsi, dan formulir pengajuan di folder ini.

### Konvensi Penamaan Berkas

1. **Proposal & Formulir**:
   - `form_pengajuan_proposal_skripsi.md` – Form pengajuan judul penelitian ke dosen pembimbing
   - `proposal_ide_riset.md` – Uraian singkat ide penelitian
   - `bab1_pendahuluan.md` – Draft Bab I (Latar Belakang, Rumusan Masalah, Tujuan)

2. **Versi File**:
   - Gunakan penomoran versi: `bab2_v1.docx`, `bab2_v2.docx` (hindari `bab2_final.docx`)
   - Atau gunakan timestamp: `proposal_20261007.docx`

3. **Format Dokumen**:
   - Markdown (`.md`) untuk draft ringkas & kolaborasi Git
   - Word (`.docx`) atau PDF (`.pdf`) untuk versi final atau evaluasi dosen

### Struktur Isi per File

#### 1. `form_pengajuan_proposal_skripsi.md`
Berisi formulir 2-kolom sesuai template UNISNU:
- Nama, NIM, Kelas
- Judul penelitian
- Rumusan masalah (integrated paragraph)
- Latar belakang (3 paragraf: masalah riil, solusi metodologi, tujuan)
- Tinjauan pustaka (5–7 referensi dengan research gap)
- Daftar pustaka (format APA 7)

#### 2. `proposal_ide_riset.md`
Deskripsi singkat (1–2 halaman) yang memuat:
- Latar belakang & motivasi
- Rumusan masalah & pertanyaan penelitian
- Tujuan penelitian
- Dataset & metodologi ringkas
- Kontribusi yang diharapkan

#### 3. `bab1_pendahuluan.md`
Bab I lengkap skripsi:
- Latar belakang masalah (2–3 halaman)
- Identifikasi masalah
- Rumusan masalah (pertanyaan penelitian)
- Tujuan penelitian
- Manfaat penelitian (teoritis & praktis)
- Batasan penelitian

### Status Saat Ini

- `form_pengajuan_proposal_skripsi.md` – Draft tersedia
- `proposal_ide_riset.md` – Draft tersedia
- `bab1_pendahuluan.md` – Draft tersedia
- `refrensi7artikel.md` – Daftar 7 artikel terverifikasi (akan digabung ke `literatur/tabel_penelitian_terdahulu.md`)

### Integrasi dengan Notebook

Ketika menyelesaikan notebook eksperimen (04_evaluasi.ipynb), salin hasil & visualisasi ke:
- Bab III (Metodologi): Gambaran alur CRISP-DM dan preprocessing
- Bab IV (Hasil & Pembahasan): Tabel evaluasi model, grafik ROC, interpretasi SHAP

---

## Tips Penulisan

1. **Gunakan Markdown untuk Draft Kolaboratif**: Lebih mudah di-review via Git diff & tidak bergantung pada Microsoft Word.
2. **Pisahkan Konsep dari Implementasi**: Hindari menjelaskan kode Python di Bab III; fokus pada metodologi.
3. **Referensi Konsisten**: Setiap klaim faktual harus merujuk ke artikel di `literatur/tabel_penelitian_terdahulu.md`.
4. **Gaya Penulisan**: Lihat skill `academic-writing` untuk panduan menulis proposal & skripsi dalam bahasa Indonesia yang akademis dan natural.

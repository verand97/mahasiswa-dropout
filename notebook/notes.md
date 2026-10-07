===============================================================================
= 1. REKOMENDASI JALUR TERBAIK UNTUK PEMULA: JALUR KOMPARASI & VISUALISASI
===============================================================================
=

     Untuk mahasiswa yang baru memulai, SANGAT DISARANKAN memilih:
     "Komparasi Model (Random Forest vs XGBoost vs CatBoost) + Borderline-SMOTE +
     SHAP"

     Mengapa jalur ini paling ramah untuk pemula?
     - Masalahnya Logis & Masuk Akal:
       Anda tidak perlu pusing membayangkan rumus abstrak seperti partikel fisika
     (PSO)
       atau mutasi kromosom biologi (Algoritma Genetika).
       Ceritanya sangat dekat dengan kehidupan kampus:
       "Mahasiswa terancam DO karena SKS semester 1 tidak lulus dan menunggak SPP."
     - Pustaka Python Sudah Sangat Rapi:
       Di Python, menjalankan Random Forest, XGBoost, dan CatBoost itu perintahnya
       hampir serupa (hanya 3-4 baris kode: panggil model -> latih data -> uji).
     - Mudah Dijelaskan Saat Sidang:
       Dosen penguji akan senang karena Anda membawa grafik visual yang mudah
     dipahami
       (grafik SHAP), bukan sekadar rumus matematika yang rumit.

     ===============================================================================
     =
     2. ROADMAP BELAJAR SAMBIL JALAN (DIBAGI 4 TAHAP SANTAI)
     ===============================================================================
     =

     Kita tidak akan mengerjakan semuanya sekaligus. Kita pecah menjadi 4 tahap
     kecil:

     TAHAP 1: KENALAN DENGAN DATANYA (SEPERTI MELIHAT TABEL EXCEL)

     - Fokus: Bukan koding, melainkan memahami arti kolom data.
     - Yang Dipelajari:
       * "Oh, di data ini ada kolom status SPP, status beasiswa, nilai semester 1 &
     2."
       * "Oh, ternyata dari 4.424 mahasiswa, ada yang lulus, ada yang DO, ada yang
     masih aktif."
     - Output: Anda paham variabel apa saja yang menentukan seorang mahasiswa bisa
     lulus atau DO.

     TAHAP 2: JALANKAN NOTEBOOK EDA (MELIHAT GAMBAR & GRAFIK)

     - Fokus: Melihat pola data lewat diagram batang dan diagram lingkaran.
     - Yang Dipelajari:
       * Melihat bukti nyata: "Ternyata mahasiswa yang DO nilai rata-rata semester
     1-nya memang anjlok."
       * Menyadari masalah data: "Wah, yang DO cuma 32%, sisanya lulus. Ini yang
     namanya data tidak seimbang (imbalance)!"
     - Output: Anda mulai paham kenapa kita butuh teknik penyeimbang data
     (Borderline-SMOTE).

     TAHAP 3: MENJALANKAN MODEL & MEMBACA KARTU HASIL

     - Fokus: Membiarkan komputer yang berhitung, tugas kita hanya membaca
     rapor/hasilnya.
     - Yang Dipelajari:
       * Komputer akan melatih ketiga model.
       * Anda cukup melihat tabel evaluasi: "Model CatBoost dapat nilai Recall 85%,
     Random Forest 79%. Berarti CatBoost lebih jago menangkap mahasiswa yang
     berisiko DO."
       * Melihat grafik SHAP: Melihat panah merah-biru yang menunjukkan faktor apa
     yang bikin risiko naik.
     - Output: Anda punya tabel perbandingan model dan grafik untuk Bab IV skripsi.

     TAHAP 4: MENYUSUN NASKAH SKRIPSI (BAB 1 S/D BAB 3)

     - Fokus: Menuangkan hasil eksperimen ke dalam format laporan skripsi kampus
     UNISNU.
     - Yang Dipelajari:
       * Menulis Latar Belakang (masalah DO di kampus).
       * Menulis Landasan Teori (penjelasan sederhana tentang algoritma yang sudah
     dipelajari).
       * Menulis Metodologi Penelitian (tahapan CRISP-DM yang sudah kita jalankan).

     ===============================================================================
     =
     3. CARA KITA BEKERJA SAMA (PERAN SAYA SEBAGAI ASISTEN & TUTOR ANDA)
     ===============================================================================
     =

     Agar Anda tidak terbebani secara teknis:
     1. Kode & Script Disediakan Lengkap:
        Seluruh script Python di folder notebook/ sudah saya susun rapi dengan
     komentar
        penjelas berbahasa Indonesia yang mudah dibaca.
     2. Penjelasan dengan Analogi Sederhana:
        Setiap kali ada istilah asing (seperti hyperparameter, decision tree,
     recall),
        akan saya jelaskan memakai analogi sehari-hari sampai Anda benar-benar
     paham.
     3. Bebas Bertanya Kapan Saja:
        Jika Anda melihat baris kode atau grafik yang tidak dimengerti, cukup
     tanyakan:
        "Ini maksudnya apa ya?" Kita bahas pelan-pelan tanpa istilah rumit.

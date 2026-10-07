# BAB I
# PENDAHULUAN

## 1.1 Latar Belakang Masalah
Pendidikan tinggi memegang peranan strategis dalam mencetak sumber daya manusia yang berkualitas, berdaya saing, dan berakhlak mulia guna mendukung pembangunan nasional. Keberhasilan suatu perguruan tinggi tidak hanya diukur dari banyaknya jumlah mahasiswa baru yang diterima setiap tahunnya, melainkan juga dari persentase mahasiswa yang berhasil menyelesaikan studinya secara tepat waktu (*retention and graduation rate*). Angka putus kuliah (*dropout*) dan keterlambatan penyelesaian studi menjadi salah satu indikator krusial dalam evaluasi mutu dan akreditasi program studi maupun institusi perguruan tinggi di Indonesia, sebagaimana tertuang dalam standar akreditasi Badan Akreditasi Nasional Perguruan Tinggi (BAN-PT) serta Indikator Kinerja Utama (IKU) perguruan tinggi.

Fenomena putus kuliah berdampak merugikan bagi berbagai pihak. Bagi institusi perguruan tinggi, tingginya angka *dropout* menurunkan efisiensi alokasi sumber daya akademik, merugikan secara finansial, dan menurunkan reputasi akreditasi kampus. Bagi mahasiswa dan keluarga, putus studi mengakibatkan kerugian materiil, hilangnya waktu produktif, dan hambatan psikologis di masa depan. Berdasarkan observasi pada pola pengelolaan akademik di perguruan tinggi, evaluasi terhadap mahasiswa bermasalah umumnya baru disadari secara intensif pada semester-semester akhir (semester 7 atau 8), yaitu ketika batas masa studi (*drop-out limit*) sudah hampir habis. Pada tahapan tersebut, berbagai upaya intervensi akademik sering kali sudah terlambat untuk menyelamatkan kelulusan mahasiswa.

Seiring berkembangnya pemanfaatan teknologi informasi di bidang pendidikan (*Educational Data Mining*), perguruan tinggi memiliki peluang besar untuk memanfaatkan data historis akademik guna membangun Sistem Peringatan Dini (*Early Warning System*). Penelitian pendidikan membuktikan bahwa capaian akademik pada tahun pertama perkuliahan (Semester 1 dan 2)—seperti jumlah satuan kredit semester (SKS) yang berhasil diselesaikan, nilai rata-rata semester, serta kondisi kedisiplinan finansial perkuliahan (kelancaran pembayaran uang kuliah)—merupakan indikator penentu yang sangat kuat untuk memproyeksikan apakah seorang mahasiswa mampu bertahan hingga lulus atau berisiko mengalami putus studi.

Meskipun demikian, pembangunan model prediksi *dropout* menggunakan teknik *machine learning* pada data riil menghadapi sejumlah tantangan metodologis yang signifikan. Tantangan pertama adalah ketimpangan data kelas (*class imbalance problem*), di mana jumlah mahasiswa yang mengalami *dropout* secara alami jauh lebih sedikit dibandingkan jumlah mahasiswa yang berhasil lulus. Penggunaan algoritma klasifikasi standar tanpa penanganan ketidakseimbangan kelas akan menghasilkan model yang mengalami bias terhadap kelas mayoritas (*Graduate*), sehingga menghasilkan akurasi yang tampak tinggi secara semu, namun gagal mendeteksi mahasiswa yang sebenarnya berada dalam kondisi darurat putus studi (*low recall on minority class*).

Penelitian terdahulu yang dilakukan oleh Villar dan de Andrade (2024) pada dataset mahasiswa mencoba mengatasi ketimpangan kelas menggunakan teknik *Synthetic Minority Over-sampling Technique* (SMOTE) standar. Namun, SMOTE standar memiliki kelemahan mendasar karena memperlakukan seluruh sampel minoritas secara seragam tanpa memperhatikan posisi batas keputusan (*decision boundary*), sehingga rentan menghasilkan sampel sintetis di wilayah *noise* yang mengaburkan batas pemisah antar-kelas. Temuan ini diperkuat oleh Endahti (2026) yang menganalisis bias keputusan SMOTE konvensional dan merekomendasikan perlunya kehati-hatian dalam menghasilkan sampel sintetis di sekitar batas kelas. Penelitian lain oleh Ridwan dan Priyatno (2024) serta Devkishan et al. (2024) menerapkan algoritma *Extreme Gradient Boosting* (XGBoost) dan *Ensemble Learning*, namun belum membandingkan performanya dengan arsitektur *boosting* mutakhir seperti *Categorical Boosting* (CatBoost) yang secara teoritis lebih unggul dalam memproses data dengan dominasi variabel kategorikal sosio-ekonomi dan demografi.

Tantangan kedua yang tidak kalah penting adalah sifat model *machine learning* yang berstatus kotak hitam (*black-box model*). Algoritma ensemble yang kompleks dapat menghasilkan prediksi dengan presisi tinggi, namun tidak mampu menjelaskan secara transparan alasan di balik suatu keputusan prediksi. Kajian terkini oleh Bettahi et al. (2025), Albugami et al. (2026), serta Nti dan Ramanayake (2026) menegaskan urgensi penerapan kerangka kerja *Explainable AI* (XAI) dalam prediksi retensi mahasiswa di perguruan tinggi. Tanpa adanya keterjelasan faktor penyebab secara individual, pihak program studi dan Dosen Pembimbing Akademik (DPA) tidak dapat merumuskan tindakan intervensi yang presisi dan tepat sasaran bagi mahasiswa yang terindikasi berisiko.

Untuk menjembatani kesenjangan penelitian (*research gap*) tersebut, penelitian ini mengusulkan sebuah pendekatan komparasi yang komprehensif antara tiga algoritma ensemble berbasis pohon, yaitu *Random Forest* (mewakili metode *bagging*), *XGBoost* (mewakili metode *gradient boosting* standar), dan *CatBoost* (mewakili metode *boosting* khusus data kategorikal). Ketimpangan kelas ditangani secara adaptif menggunakan algoritma **Borderline-SMOTE**, yang berfokus menghasilkan sampel sintetis hanya pada wilayah kritis di ambang batas keputusan (*danger borderline*). Selanjutnya, model terbaik diintegrasikan dengan metode **Explainable AI (XAI)** berbasis **SHAP (SHapley Additive exPlanations)** untuk menghasilkan interpretasi global mengenai faktor dominan pemicu *dropout* di tingkat institusi, serta interpretasi lokal berupa visualisasi *waterfall plot* untuk merekomendasikan tindakan intervensi personal bagi setiap mahasiswa yang terindikasi berisiko tinggi.

## 1.2 Identifikasi Masalah
Berdasarkan latar belakang masalah yang telah diuraikan, dapat diidentifikasi beberapa permasalahan sebagai berikut:
1. Penanganan dan pendampingan terhadap mahasiswa bermasalah di perguruan tinggi sering kali terlambat dilakukan karena evaluasi akademik belum memanfaatkan sistem deteksi dini berbasis data historis semester awal.
2. Dataset akademik mahasiswa memiliki karakteristik ketimpangan kelas (*class imbalance*) yang signifikan antara mahasiswa lulus (*Graduate*) dan mahasiswa putus studi (*Dropout*), yang menyebabkan algoritma klasifikasi konvensional menghasilkan prediksi bias ke kelas mayoritas.
3. Penerapan teknik penyeimbangan data konvensional (SMOTE standar) pada penelitian terdahulu masih menimbulkan tumpang tindih data sintetis di wilayah data pencilan (*outlier/noise*).
4. Belum adanya kajian komparatif yang komprehensif antara arsitektur *Random Forest*, XGBoost, dan CatBoost yang dioptimasi khusus untuk mengukur efektivitas pendeteksian mahasiswa *dropout* pada data campuran numerik dan kategorikal.
5. Model klasifikasi *machine learning* berkinerja tinggi umumnya bersifat *black-box*, sehingga pihak manajemen kampus dan dosen pembimbing kesulitan memahami faktor penyebab individual mahasiswa mengalami ancaman putus kuliah.

## 1.3 Batasan Masalah
Agar penelitian ini terarah, fokus, dan tidak menyimpang dari tujuan utama, maka ruang lingkup penelitian dibatasi sebagai berikut:
1. Dataset yang digunakan adalah data riil *Predict Students' Dropout and Academic Success* dari UCI Machine Learning Repository (ID: 697) dengan skala 4.424 baris data dan 36 atribut prediktor (demografi, sosio-ekonomi, dan capaian akademik semester 1 dan semester 2).
2. Fokus klasifikasi diformulasikan sebagai klasifikasi biner (*binary classification*) antara status mahasiswa yang berhasil lulus (*Graduate*) dan mahasiswa yang putus kuliah (*Dropout*). Data mahasiswa berstatus aktif (*Enrolled*) dieksklusikan dari pemodelan utama guna memperoleh batas target evaluasi yang definitif.
3. Algoritma *machine learning* yang diteliti dan dibandingkan dibatasi pada 3 (tiga) algoritma berbasis pohon (*tree-based ensemble*), yaitu *Random Forest*, *Extreme Gradient Boosting* (XGBoost), dan *Categorical Boosting* (CatBoost).
4. Penanganan ketidakseimbangan kelas (*class imbalance*) difokuskan menggunakan metode **Borderline-SMOTE** pada data latih (*training set*).
5. Validasi model dilakukan menggunakan skema *Stratified K-Fold Cross Validation* guna menjamin kestabilan distribusi kelas pada setiap lipatan data uji.
6. Metrik evaluasi yang digunakan meliputi *Accuracy*, *Precision*, *Recall*, *F1-Score*, *ROC-AUC*, dan kurva *Precision-Recall AUC* (PR-AUC), dengan penekanan utama pada peningkatan metrik *Recall* kelas *Dropout*.
7. Analisis keterjelasan model (*Explainable AI*) dibatasi menggunakan kerangka kerja SHAP (*SHapley Additive exPlanations*) yang mencakup *SHAP Summary Plot* (interpretasi global) dan *SHAP Waterfall Plot* (interpretasi lokal kasus perorangan).
8. Sistem cerdas yang dihasilkan diwujudkan dalam bentuk prototipe antarmuka berbasis web interaktif (*Streamlit*).

## 1.4 Rumusan Masalah
Berdasarkan batasan masalah di atas, rumusan masalah dalam penelitian ini adalah:
1. Bagaimana pengaruh penerapan teknik penyeimbangan data **Borderline-SMOTE** terhadap peningkatan kinerja deteksi kelas minoritas (*Dropout*) pada data akademik mahasiswa?
2. Bagaimana perbandingan performa klasifikasi antara algoritma *Random Forest*, *XGBoost*, dan *CatBoost* dalam memprediksi risiko *dropout* mahasiswa berdasarkan metrik *Recall*, *F1-Score*, dan *PR-AUC*?
3. Algoritma manakah yang menghasilkan kinerja paling optimal sebagai model terbaik untuk sistem deteksi dini risiko *dropout* mahasiswa?
4. Bagaimana implementasi metode *Explainable AI* menggunakan SHAP mampu mengidentifikasi variabel-variabel penentu pemicu *dropout* secara transparan, baik pada tingkat global maupun tingkat individual mahasiswa?

## 1.5 Tujuan Penelitian
Adapun tujuan yang hendak dicapai melalui penelitian ini adalah:
1. Menganalisis dan membuktikan efektivitas penerapan algoritma **Borderline-SMOTE** dalam mengatasi permasalahan ketidakseimbangan kelas pada dataset prediksi kelulusan mahasiswa.
2. Menguji, membandingkan, dan mengevaluasi kinerja algoritma *Random Forest*, *XGBoost*, dan *CatBoost* secara empiris menggunakan skema validasi berstrata (*Stratified Cross-Validation*).
3. Menentukan arsitektur model *ensemble* terbaik yang menghasilkan sensitivitas (*Recall*) tertinggi dalam mendeteksi mahasiswa yang berisiko mengalami putus studi.
4. Menerapkan kerangka kerja **Explainable AI (SHAP)** untuk memetakan kontribusi fitur global dan menghasilkan visualisasi rekomendasi akademik individual (*waterfall plot*) yang dapat diinterpretasikan secara jelas oleh pengambil kebijakan kampus.
5. Membangun prototipe aplikasi sistem peringatan dini (*Early Warning System*) berbasis web interaktif untuk mempermudah simulasi pemantauan status akademik mahasiswa.

## 1.6 Manfaat Penelitian
Penelitian ini diharapkan memberikan kontribusi dan manfaat, baik secara teoritis maupun praktis:

### 1. Manfaat Teoritis (Keilmuan)
- Memberikan kontribusi ilmiah dalam bidang *Educational Data Mining* (EDM) dan *Machine Learning*, khususnya mengenai kajian perbandingan efektivitas keluarga algoritma *tree-based ensemble* (*Random Forest*, XGBoost, dan CatBoost) pada data akademik bertipe campuran.
- Memperkaya literatur penelitian terkait integrasi teknik *resampling* adaptif (Borderline-SMOTE) dengan teknik interpretasi *Explainable AI* (SHAP) untuk menyelesaikan permasalahan klasifikasi pada domain data pendidikan yang tidak seimbang.

### 2. Manfaat Praktis
- **Bagi Perguruan Tinggi (UNISNU Jepara / Institusi Kampus)**:
  Memberikan alat bantu analitik berbasis kecerdasan buatan (*Decision Support System*) yang mampu memproyeksikan potensi *dropout* sejak tahun pertama, sehingga pimpinan kampus dapat merumuskan kebijakan retensi mahasiswa yang lebih preventif dan terukur guna mempertahankan akreditasi institusi.
- **Bagi Dosen Pembimbing Akademik (DPA)**:
  Menyediakan informasi transparan mengenai faktor-faktor kritis penyebab seorang mahasiswa mengalami penurunan kinerja akademik, sehingga bimbingan, konseling, dan rekomendasi solusi dapat disesuaikan dengan kondisi spesifik mahasiswa yang bersangkutan (misalnya bantuan remedial SKS atau fasilitasi bantuan finansial).
- **Bagi Mahasiswa**:
  Membantu mahasiswa mendeteksi tanda-tanda awal kemunduran studi mereka lebih awal, sehingga mahasiswa dapat segera berbenah dan memperbaiki strategi perkuliahan sebelum menghadapi sanksi akademik atau batas akhir masa studi.


---

## 1.7 Daftar Pustaka Rujukan Utama (Terverifikasi 3 Tahun Terakhir)
1. Albugami, S., Wali, A., & Almagrabi, H. (2026). Predicting student dropout in Saudi Universities using machine learning and explainable AI. *PeerJ Computer Science*, 12, e3490. DOI: [10.7717/peerj-cs.3490](https://doi.org/10.7717/peerj-cs.3490)
2. Bettahi, A., Belouadha, F.-Z., & Harroud, H. (2025). A Modular and Explainable Machine Learning Pipeline for Student Dropout Prediction in Higher Education. *Algorithms*, 18(10), 662. DOI: [10.3390/a18100662](https://doi.org/10.3390/a18100662)
3. Devkishan, T. S., Singh, S. K., & Bharti, A. K. (2024). Implementation of Machine Learning and Ensemble Learning Techniques to Proactively Predict Students' Academic Success in the Realm of Higher Education. *2024 4th International Conference on Technological Advancements in Computational Sciences (ICTACS)*, IEEE Xplore. DOI: [10.1109/ictacs62700.2024.10840530](https://doi.org/10.1109/ictacs62700.2024.10840530)
4. Endahti, J. L. (2026). Analisis Pengaruh SMOTE Terhadap Bias Keputusan Model Machine Learning pada Prediksi Dropout Mahasiswa. *Rabit : Jurnal Teknologi dan Sistem Informasi Univrab*, 11(2), 210–221. DOI: [10.36341/rabit.v11i2.8275](https://doi.org/10.36341/rabit.v11i2.8275)
5. Nti, I. K., & Ramanayake, S. (2026). Explainable machine learning for student dropout prediction and tailored interventions in online personalized education. *Discover Artificial Intelligence*, 6(1), 1016. DOI: [10.1007/s44163-026-01016-6](https://doi.org/10.1007/s44163-026-01016-6)
6. Ridwan, A., & Priyatno, A. M. (2024). Predict Students' Dropout and Academic Success with XGBoost. *Journal of Education and Computer Applications (JECA)*, 1(2), 78–86. DOI: [10.69693/jeca.v1i2.13](https://doi.org/10.69693/jeca.v1i2.13)
7. Villar, A., & de Andrade, C. R. V. (2024). Supervised machine learning algorithms for predicting student dropout and academic success: a comparative study. *Discover Artificial Intelligence*, 4(1), 79. DOI: [10.1007/s44163-023-00079-z](https://doi.org/10.1007/s44163-023-00079-z)

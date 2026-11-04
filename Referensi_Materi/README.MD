# Pengenalan Algoritma Klasifikasi di Machine Learning 🚀

Halo semuanya! Buat kalian yang sedang belajar atau mengambil mata kuliah/topik *Machine Learning* (ML), khususnya pada bab **Klasifikasi**, dokumen ini dirancang khusus untuk membahas secara ringkas apa itu klasifikasi, algoritma apa saja yang sering dipakai, apa *plus-minus* (kelebihan & kekurangan) masing-masing, serta kapan waktu yang tepat untuk menggunakannya (kecocokan data). 

Semoga penjelasan dengan bahasa yang santai ini bisa membantu kalian lebih paham, ya!

---

## Apa itu Klasifikasi? 🤔
Dalam dunia *Machine Learning*, klasifikasi adalah teknik dari *Supervised Learning* (pembelajaran yang punya label/kunci jawaban) yang bertugas untuk mengelompokkan atau menebak data baru ke dalam kategori tertentu. 
*Contoh kasus:* Mesin memilah apakah sebuah email itu "Spam" atau "Bukan Spam", atau menebak apakah sebuah sentimen di Twitter itu "Positif" atau "Negatif".

Berikut adalah 5 algoritma klasifikasi yang paling sering jadi andalan untuk riset atau skripsi:

---

### 1. K-Nearest Neighbor (KNN)
*   **Gimana Cara Kerjanya?** KNN berprinsip pada kedekatan atau "tetangga". Kalau ada data baru, dia akan mencari sejumlah $k$ data terdekat dari data latih (*training data*), lalu melakukan sistem *voting* (suara terbanyak).
*   **Kelebihan:** Sangat mudah dipahami konsepnya dan tidak membutuhkan fase *training* yang kompleks (makanya sering dijuluki *lazy learner*). Tidak ada asumsi aneh-aneh terkait bentuk distribusi datanya.
*   **Kekurangan:** Saat jumlah data sangat besar, waktu komputasinya akan melambat drastis karena harus mengukur jarak ke semua data latih. Selain itu, algoritma ini cukup rentan terhadap *noise*. Berdasarkan riset terbaru di tahun 2025, *"Ketergantungan pada kedekatan jarak ini menyebabkan KNN mudah mengalami kesalahan klasifikasi pada pose (data) yang kompleks atau bervariasi"* (SEMNASA, 2025, hal. 9) [2].
*   **Kecocokan Data:** Paling pas dipakai buat dataset berukuran kecil hingga menengah, dan ketika kita memiliki fitur (kolom) yang tidak terlalu banyak.

### 2. Support Vector Machine (SVM)
*   **Gimana Cara Kerjanya?** SVM bekerja dengan mencari garis pemisah atau *hyperplane* terbaik (dengan jarak/margin yang paling maksimal) untuk memisahkan satu kelas dengan kelas lainnya di dalam ruang dimensi.
*   **Kelebihan:** Performanya luar biasa bagus untuk mendapatkan akurasi tinggi, sangat tangguh pada ruang dimensi yang tinggi, dan bisa menangani data yang tidak bisa dipisahkan secara linear berkat fungsi *Kernel Trick*. Pada penelitian prediksi skor bola, SVM bahkan terbukti lebih unggul dibanding algoritma lainnya (Karim dkk., 2023) [1].
*   **Kekurangan:** Pemilihan parameter *(hyperparameter tuning)* cukup *tricky* dan butuh waktu komputasi yang memakan memori *(memory-intensive)* kalau diaplikasikan ke dataset raksasa.
*   **Kecocokan Data:** Sangat disarankan untuk data teks (seperti NLP/Analisis Sentimen), pengenalan gambar, dan kasus-kasus di mana akurasi menjadi prioritas absolut dan kelasnya cukup jelas batasnya.

### 3. Random Forest (RF)
*   **Gimana Cara Kerjanya?** RF menggunakan sistem gotong royong *(ensemble)*. Model ini menumbuhkan banyak sekali Pohon Keputusan (*Decision Tree*), lalu mengambil keputusan berdasarkan *voting* terbanyak dari pohon-pohon tersebut.
*   **Kelebihan:** Sangat kebal terhadap *outlier* (data pencilan) dan jarang mengalami *overfitting* (terlalu menghafal data latih). *"Model ensemble seperti Random Forest lebih stabil dalam menangani variasi fitur ... dibandingkan metode lainnya"* (SEMNASA, 2025, hal. 8) [2].
*   **Kekurangan:** Modelnya bertindak bak "kotak hitam" *(black box)*, sehingga kita agak susah kalau ditanya dosen kenapa algoritma ini mengambil keputusan A atau B (kurang *interpretable* dibandingkan Decision Tree tunggal).
*   **Kecocokan Data:** Ini ibarat "senjata pamungkas". Cocok untuk dataset campuran berupa data tabular (baris & kolom tipe numerik maupun kategorikal) yang kotor, besar, dan memiliki banyak fitur kompleks.

### 4. Decision Tree (Pohon Keputusan)
*   **Gimana Cara Kerjanya?** Memecah data berdasarkan aturan kondisional (seperti "Jika A, maka B") dari akar sampai ke ujung daun (*leaf*) yang merupakan keputusan akhir.
*   **Kelebihan:** Paling gampang dijelaskan ke orang awam. Bentuknya persis seperti *flowchart* atau peta jalan manusia berpikir.
*   **Kekurangan:** Sangat gampang terkena penyakit *overfitting*, yaitu terlalu sempurna menebak data *training*, tetapi hancur saat dites ke data baru (kecuali dilakukan pemangkasan / *pruning*).
*   **Kecocokan Data:** Sangat cocok dipakai di kasus bisnis medis atau *finance* (seperti penentuan kelayakan kredit pinjaman) di mana penjelasan / argumen *mengapa* keputusan itu diambil jauh lebih penting dibandingkan akurasi semata.

### 5. Naive Bayes
*   **Gimana Cara Kerjanya?** Memanfaatkan rumus probabilitas Teorema Bayes dari ilmu Statistika. "Naive" (naif) merujuk pada asumsinya yang menganggap semua variabel independen atau tidak ada hubungannya satu sama lain.
*   **Kelebihan:** Kecepatannya secepat kilat! Proses pelatihan datanya sangat efisien, walaupun datanya banyak.
*   **Kekurangan:** Asumsinya yang bilang bahwa antar fitur tidak ada hubungannya itu sering kali kurang realistis di dunia nyata.
*   **Kecocokan Data:** Rajanya untuk klasifikasi berbasis teks dan dokumen. Cocok banget untuk kasus penyaringan email *Spam* atau pengelompokan topik berita berita karena cara kerjanya yang menghitung frekuensi probabilitas kata.

---

## 📚 Referensi Akademis (2022 - 2026)
Di bawah ini adalah daftar referensi jurnal / prosiding yang dikutip dalam penjelasan di atas. Sangat valid untuk kalian gunakan sebagai daftar pustaka:

1. **Karim, A. A., Prasetyo, M. A., & Saputro, M. R. (2023).** *"Perbandingan Metode Random Forest, K-Nearest Neighbor, dan SVM Dalam Prediksi Akurasi Pertandingan Liga Italia"*. Prosiding Seminar Nasional Teknologi Dan Sains Tahun 2023, Vol. 2, Universitas Nusantara PGRI Kediri.
   *   **Kutipan tentang KNN (Hal. 378):** *"K-Nearest Neighbor atau disebut juga lazy learner (pembelajar yang malas) mengklasifikasikan data berdasarkan kemiripan atau kedekatan terhadap data lainnya."* 
   *   https://proceeding.unpkediri.ac.id/index.php/stains/article/view/2877
2. **SEMNASA (Seminar Nasional AMIKOM Surakarta). (2025).** *"Perbandingan Random Forest, K-Nearest Neighbor, Support Vector Machine, dan Multi-Layer Perceptron untuk Deteksi Postur Duduk Berdasarkan Ekstraksi Pose MediaPipe"*. e-ISSN: 3031-5581.
   *   **Kutipan tentang RF (Hal. 33):** *"Temuan ini mengindikasikan bahwa model ensemble seperti Random Forest lebih stabil dalam menangani variasi fitur pose tubuh dibandingkan metode lainnya."*
   *   **Kutipan tentang Kekurangan KNN (Hal. 35):** *"Ketergantungan pada kedekatan jarak ini menyebabkan KNN mudah mengalami kesalahan klasifikasi pada pose duduk yang kompleks atau bervariasi."*
   *   https://ojs.amikomsolo.ac.id/index.php/semnasa/article/view/934
3. **Praneswara, A. O. (2023).** *"Perbandingan K-Nearest Neighbors, Support Vector Dan Random Forest Pada Prediksi Medical Cost"*. Indonesian Journal of Computer Science.
   *   **Konteks (Hal. 2035):** Penelitian publik yang memvalidasi perbandingan akurasi ketiga algoritma utama dalam memprediksi biaya, menunjukkan kemampuan SVM, KNN, dan RF dalam mengkategorisasi metrik dataset kesehatan.
   * https://www.ijcs.net/ijcs/index.php/ijcs/article/view/3298

# Klasifikasi Diabetes dengan Support Vector Machine (SVM)

Proyek latihan *machine learning* untuk memprediksi risiko diabetes menggunakan algoritma **Support Vector Classifier (SVC)** dari Scikit-Learn.

## Dataset
- **Sumber:** [Pima Indians Diabetes Dataset](https://github.com/npradaschnor/Pima-Indians-Diabetes-Dataset) (National Institute of Diabetes and Digestive and Kidney Diseases)
- **Ukuran:** 768 baris, 9 kolom (8 fitur klinis dan 1 target `Outcome`)

## Alur Pengerjaan
1. **Data Loading & Pengecekan:** Memuat `diabetes.csv` dan memastikan tidak ada *missing values* maupun duplikat.
2. **Preprocessing:** Memisahkan fitur dan target, melakukan standarisasi dengan `StandardScaler`, serta membagi data latih dan uji (67% : 33%).
3. **Modeling:** Melatih model klasifikasi menggunakan `SVC()`.
4. **Evaluasi:** Mengukur performa model dengan skor akurasi sebesar **75,59%**.

## Library yang Digunakan
- `pandas`
- `scikit-learn`

## Cara Menjalankan
1. Pastikan file `diabetes.csv` berada di direktori yang sama dengan file notebook (`.ipynb`).
2. Jalankan seluruh *cell* pada Jupyter Notebook secara berurutan.
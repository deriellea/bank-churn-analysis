# Bank Churn Analysis

## 1. Project Overview

Proyek ini berfokus pada analisis data nasabah bank untuk memprediksi *customer churn*. Tujuan utamanya adalah untuk mengidentifikasi customer bank yang berpotensi untuk berhenti (*churn*), sehingga memungkinkan strategi retensi yang proaktif

### Tujuan Utama

-   Memprediksi *customer churn* menggunakan teknik *machine learning*.
-   Mengevaluasi performa model menggunakan *F1 Score*.
-   Memberikan wawasan tentang faktor-faktor yang memengaruhi *customer churn*.

### Variabel Target

-   `Exited`: Menunjukkan apakah seorang customer bank telah *churn* (1) atau tidak (0).

### Metrik Evaluasi

-   *F1 Score*: Dipilih untuk menyeimbangkan *precision* dan *recall*, yang krusial untuk meminimalkan baik *false positive* (upaya retensi yang sia-sia) maupun *false negative* (kehilangan nasabah).

## 2. Data Understanding

Dataset berisi informasi tentang nasabah bank, termasuk detail demografi dan keuangan.

### Deskripsi Kolom

| Nama Kolom       | Deskripsi                                               |
| ------------------ | --------------------------------------------------------- |
| Surname          | Nama belakang                                           |
| CreditScore      | Skor kredit                                             |
| Geography        | Negara (Germany / France / Spain)                         |
| Gender           | Jenis kelamin (Female / Male)                             |
| Age              | Usia                                                    |
| Tenure           | Lama menjadi nasabah (dalam tahun)                      |
| Balance          | Saldo rekening                                          |
| NumOfProducts    | Jumlah produk perbankan yang digunakan                  |
| HasCrCard        | Status kepemilikan kartu kredit (0 = Tidak, 1 = Ya)     |
| IsActiveMember   | Status keanggotaan aktif (0 = Tidak, 1 = Ya)            |
| EstimatedSalary  | Perkiraan gaji                                          |
| Exited           | Apakah berhenti menjadi nasabah? (0 = Tidak, 1 = Ya)    |

### Karakteristik Data

-   Dataset terdiri dari 10.000 entri.
-   Berisi tipe data numerik, kategorikal, dan boolean.
-   Variabel target (`Exited`) tidak seimbang (*imbalanced*).

## 3. Data Preparation

Langkah-langkah persiapan data berikut dilakukan:

-   Memeriksa nilai yang hilang (*missing values*) (Tidak ada yang ditemukan).
-   Memeriksa nilai duplikat (Tidak ada yang ditemukan).
-   Mengubah kolom `Geography` dan `Gender` menjadi tipe data kategorikal.

## 4. Exploratory Data Analysis (EDA)

-   Menganalisis distribusi variabel target (`Exited`), mengungkapkan ketidakseimbangan.
-   Memeriksa nilai unik dalam kolom kategorikal (`Geography`, `Gender`).
-   Menghasilkan statistik deskriptif untuk kolom numerik.

## 5. Modeling

-   Beberapa model *machine learning* dilatih dan dievaluasi, hasil akhir menggunakan Model GradientBoostingClassifier().
-   *Hyperparameter tuning* dilakukan untuk mengoptimalkan performa model.
-   *F1 Score* digunakan sebagai metrik evaluasi utama.

## 6. Evaluation

-   Performa model dievaluasi berdasarkan *F1 Score*.
-   *Confusion matrix* dan *classification report* digunakan untuk menganalisis hasil.
-   Analisis biaya-manfaat dilakukan untuk menilai dampak finansial model.

## 7. Conclusion

-   Proyek berhasil mengembangkan model untuk memprediksi *customer churn*.
-   Faktor-faktor kunci yang memengaruhi *churn* telah diidentifikasi.
-   Rekomendasi untuk strategi retensi telah diberikan.

## 8. Recommendations

-   Mengimplementasikan sistem peringatan dini untuk mendeteksi nasabah berisiko tinggi.
-   Segmentasi nasabah yang diprediksi *churn* berdasarkan fitur penting (`Age`, `NumOfProducts`, `IsActiveMember`) untuk upaya retensi yang ditargetkan.
-   Menggunakan strategi *cross-selling* produk untuk meningkatkan loyalitas nasabah.

## 9. Files

-   `Bank_Churn_Analysis_Final.ipynb`: Jupyter Notebook yang berisi analisis.
-   `churn.csv`: Dataset yang digunakan untuk analisis.

## 10. How to Run

1.  Pastikan Anda telah menginstal Python 3.x.
2.  Instal *library* yang diperlukan:
    ```bash
    pip install numpy pandas scikit-learn seaborn matplotlib statsmodels imbalanced-learn category_encoders xgboost
    ```
3.  Jalankan Jupyter Notebook `Bank_Churn_Analysis_Final.ipynb`.

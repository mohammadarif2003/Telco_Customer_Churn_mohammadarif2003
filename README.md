# Prediksi Churn Pelanggan Telco (Telco Customer Churn Prediction)

Proyek ini bertujuan untuk menganalisis data pelanggan dari sebuah perusahaan telekomunikasi (Telco) dan membangun model machine learning untuk memprediksi pelanggan mana yang kemungkinan besar akan berhenti berlangganan (churn). Dengan memprediksi churn, perusahaan dapat mengembangkan program retensi yang lebih terfokus dan efektif.

## 📊 Dataset

Dataset yang digunakan dalam proyek ini berasal dari Kaggle dan disediakan oleh IBM.

- **Sumber**: [Telco Customer Churn on Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data)
- **Pembaruan oleh IBM**: [Telco Customer Churn Community Blog](https://community.ibm.com/community/user/businessanalytics/blogs/steven-macko/2019/07/11/telco-customer-churn-1113)

Dataset ini berisi informasi tentang:
- **Pelanggan yang Churn**: Kolom `Churn` menunjukkan apakah pelanggan berhenti berlangganan dalam sebulan terakhir.
- **Layanan Pelanggan**: Layanan yang digunakan seperti telepon, internet, keamanan online, backup online, proteksi perangkat, dukungan teknis, TV streaming, dan film streaming.
- **Informasi Akun**: Masa berlangganan (tenure), jenis kontrak, metode pembayaran, tagihan elektronik, biaya bulanan, dan total biaya.
- **Informasi Demografis**: Jenis kelamin, rentang usia, serta status memiliki pasangan dan tanggungan.

## 🚀 Alur Kerja Proyek

Proyek ini mengikuti langkah-langkah standar dalam sebuah proyek data science:
1.  **Eksplorasi Data (EDA)**: Memahami distribusi data, hubungan antar fitur, dan statistik deskriptif.
2.  **Pra-pemrosesan Data**: Menangani nilai yang hilang, melakukan encoding pada fitur kategorikal, dan melakukan penskalaan pada fitur numerik.
3.  **Pembangunan Model**: Melatih beberapa model klasifikasi untuk memprediksi churn, yaitu:
    - Logistic Regression
    - Random Forest
    - Gradient Boosting
    - XGBoost
4.  **Evaluasi Model**: Mengevaluasi kinerja setiap model menggunakan metrik seperti Accuracy, Precision, Recall, F1-Score, dan AUC.
5.  **Analisis Fitur Penting**: Mengidentifikasi fitur-fitur yang paling berpengaruh dalam memprediksi churn menggunakan model terbaik.

## 📈 Hasil Analisis

### Perbandingan Kinerja Model

Berikut adalah tabel perbandingan hasil dari keempat model yang diuji pada data tes.

| Model                   | Accuracy | Precision | Recall | F1-Score | AUC   |
| ----------------------- | -------- | --------- | ------ | -------- | ----- |
| **Logistic Regression** | 0.787    | 0.619     | 0.513  | 0.561    | 0.832 |
| **Random Forest**       | 0.787    | 0.633     | 0.479  | 0.545    | 0.817 |
| **Gradient Boosting**   | 0.790    | 0.639     | 0.479  | 0.547    | 0.834 |
| **XGBoost**             | 0.763    | 0.566     | 0.471  | 0.514    | 0.810 |

**Analisis Hasil:**
- **Gradient Boosting** menunjukkan performa terbaik secara keseluruhan, terutama dengan nilai **AUC (0.834)** dan **Accuracy (0.790)** tertinggi. Ini menandakan kemampuan model yang sangat baik dalam membedakan antara pelanggan yang akan churn dan yang tidak.
- **Logistic Regression** juga menunjukkan hasil yang kompetitif dengan **Recall (0.513)** dan **F1-Score (0.561)** tertinggi, menjadikannya alternatif yang baik jika interpretabilitas model menjadi prioritas utama.

### Faktor Paling Berpengaruh (Feature Importance)

Berdasarkan model **Gradient Boosting** yang memiliki performa terbaik, berikut adalah fitur-fitur yang paling signifikan dalam memprediksi churn:

1.  **`tenure` (Masa Berlangganan)** - (Importance: 0.313): Faktor paling dominan. Semakin singkat masa berlangganan seorang pelanggan, semakin tinggi kemungkinan mereka untuk churn.
2.  **`InternetService_Fiber optic`** - (Importance: 0.208): Pelanggan yang menggunakan layanan internet Fiber Optic memiliki kecenderungan churn yang tinggi.
3.  **`PaymentMethod_Electronic check`** - (Importance: 0.094): Metode pembayaran dengan cek elektronik juga menjadi indikator kuat churn.
4.  **`TotalCharges` & `MonthlyCharges`**: Total dan biaya bulanan juga berkontribusi signifikan, meskipun tidak sebesar tenure.
5.  **`Contract_Two year` & `Contract_One year`**: Pelanggan dengan kontrak jangka panjang (1 atau 2 tahun) cenderung lebih setia dan memiliki kemungkinan churn yang lebih rendah.

## 💡 Kesimpulan dan Rekomendasi Bisnis

### Kesimpulan
- **Model Terbaik**: **Gradient Boosting** adalah model yang paling direkomendasikan untuk memprediksi churn pelanggan karena memiliki keseimbangan yang baik antara akurasi dan kemampuan diskriminatif (AUC).
- **Faktor Utama Pendorong Churn**: Faktor utama yang mempengaruhi pelanggan untuk churn adalah **masa berlangganan yang singkat**, penggunaan layanan **internet fiber optic**, dan metode pembayaran melalui **cek elektronik**.

### Rekomendasi Bisnis
1.  **Fokus pada Pelanggan Baru**: Buat program loyalitas atau penawaran khusus untuk pelanggan dengan masa berlangganan (tenure) rendah untuk meningkatkan retensi sejak dini.
2.  **Evaluasi Layanan Fiber Optic**: Lakukan investigasi lebih mendalam mengenai kepuasan pelanggan fiber optic. Mungkin ada masalah terkait harga, kualitas layanan, atau stabilitas yang perlu diperbaiki.
3.  **Optimalkan Metode Pembayaran**: Analisis mengapa pelanggan yang menggunakan cek elektronik cenderung churn. Dorong pelanggan untuk beralih ke metode pembayaran yang lebih "lengket" seperti auto-debit atau kartu kredit dengan memberikan insentif.
4.  **Promosikan Kontrak Jangka Panjang**: Tawarkan diskon atau keuntungan tambahan bagi pelanggan yang bersedia beralih ke kontrak 1 atau 2 tahun, karena ini terbukti efektif mengurangi churn.

## 🛠️ Cara Menjalankan Kode

1.  **Kloning Repositori**:
    ```bash
    git clone https://github.com/NAMA_USER_ANDA/NAMA_REPO_ANDA.git
    cd NAMA_REPO_ANDA
    ```
2.  **Instalasi Dependensi**:
    Pastikan Anda memiliki library Python yang diperlukan. Anda dapat menginstalnya menggunakan pip:
    ```bash
    pip install pandas numpy scikit-learn xgboost matplotlib seaborn jupyter
    ```
3.  **Jalankan Notebook**:
    Buka dan jalankan file `.ipynb` (misalnya, `telco_churn_prediction.ipynb`) menggunakan Jupyter Notebook atau Google Colab.

## 🔮 Langkah Selanjutnya (Future Work)

- **Hyperparameter Tuning**: Melakukan tuning lebih lanjut pada model Gradient Boosting untuk meningkatkan performanya.
- **Deployment**: Menyebarkan model terbaik ke dalam sebuah aplikasi web atau API untuk penggunaan secara real-time.
- **Analisis Lebih Dalam**: Melakukan analisis kohort untuk memahami perilaku churn berdasarkan kapan pelanggan bergabung.

## 📄 Lisensi

Proyek ini dilisensikan di bawah Lisensi MIT. Lihat file `LICENSE` untuk detailnya.

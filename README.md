# Air Quality Prediction / Prediksi Kualitas Udara dalam beberapa jam
- **Nama**         : Irsyad Umar Fakhrizal
- **NIM**          : A11.2022.14094
- **Mata Kuliah**  : Data Mining

## 1. Ringkasan dan Permasalahan
Kualitas udara yang buruk dapat berdampak negatif terhadap kesehatan manusia. Oleh karena itu, prediksi kualitas udara menjadi penting untuk mitigasi dan perencanaan kebijakan lingkungan.

### Tujuan
- Memprediksi konsentrasi CO(GT) dalam beberapa jam kedepan berdasarkan dataset AirQualityUCI.csv
- Menggunakan beberapa model untuk analisis deret waktu
- Mengevaluasi performa model

### Alur Penyelesaian
Berikut adalah bagan alur penyelesaian proyek ini:

![Load](https://github.com/user-attachments/assets/4ee17050-f5d3-443e-b806-772a6872c00b)

## 2. Penjelasan Dataset, EDA dan Proses Features Dataset
Dataset yang digunakan berasal dari **AirQualityUCI.csv** yang diambil dari **UCI Repository**. Data tersebut berisi 9358 contoh respons rata-rata per jam dari serangkaian 5 sensor kimia oksida logam yang tertanam dalam Perangkat Multisensor Kimia Kualitas Udara. Data yang direkam dari bulan Maret 2004 hingga Februari 2005 (satu tahun). Data memiliki 15 Feature.
### Proses Features
- **Pembersihan Data**: Menghapus nilai yang tidak valid
- **Visualisasi**: Menggunakan grafik garis dan histogram untuk memahami pola data.
- **Transformasi Data**: Normalisasi atau differencing untuk membuat data stasioner jika diperlukan, Menggabungkan 2 Feature jadi satu yaitu Date dan Time menjadi Datetime dan di set sebagai index

## 3. Proses Learning / Modeling
Sebelum di Modeling dilakukan Analisis Time series terlebih dahulu yaitu dengan menguji stasionaritas data menggunakan **ADF**, kemudian menggunakan **ACF** dan **PACF** untuk menganalisis hubungan deret waktu di masa lalu dan di masa depan
### Modeling dilakukan menggunakan beberapa teknik:
- **Single Exponential Smoothing**: Model sederhana untuk tren data.
- **Double Exponential Smoothing**: Menyesuaikan data dengan tren yang lebih kompleks.
- **ARIMA**: Model yang mempertimbangkan autoregresi, differencing, dan moving average untuk membuat prediksi berbasis deret waktu.

## 4. Performa Model
Model dievaluasi menggunakan:
- **Root Mean Squared Error (RMSE)**: Mengukur seberapa dekat prediksi dengan nilai aktual.
- **Mean Absolute Percentage Error (MAPE)**: Mengukur kesalahan rata-rata dalam bentuk persentase.
- **Visualisasi Prediksi**: Membandingkan hasil prediksi dengan data aktual untuk melihat pola yang dipelajari model.

## 5. Diskusi Hasil dan Kesimpulan
Dari hasil evaluasi, model ARIMA menunjukkan performa yang lebih baik dibandingkan model eksponensial dalam menangkap pola waktu. Namun, prediksi kualitas udara dapat lebih akurat jika menggunakan pendekatan hybrid atau melibatkan variabel eksternal seperti kondisi cuaca. Model ini dapat diimplementasikan dalam aplikasi berbasis web menggunakan Streamlit untuk memudahkan pengguna dalam melihat prediksi kualitas udara secara real-time.

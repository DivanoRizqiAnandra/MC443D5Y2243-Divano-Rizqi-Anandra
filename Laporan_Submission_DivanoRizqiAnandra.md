# Laporan Proyek Machine Learning - Divano Rizqi Anandra

## Domain Proyek

Cuaca merupakan salah satu faktor penting yang memengaruhi berbagai aspek kehidupan manusia, mulai dari aktivitas sehari-hari hingga sektor industri seperti pertanian, penerbangan, dan perencanaan kota. Oleh karena itu, kemampuan untuk mengklasifikasikan kondisi cuaca secara otomatis dan akurat sangat dibutuhkan.

K. S. Alzubaidi, M. A. Alzubaidi, dan M. A. Alzubaidi (2023) menyatakan bahwa penerapan teknik pembelajaran mesin (machine learning) dapat memberikan hasil klasifikasi yang sangat akurat terhadap kondisi cuaca berdasarkan data sensor meteorologis yang tersedia. Mereka menekankan pentingnya pemanfaatan algoritma pembelajaran terawasi (supervised learning) untuk mengatasi variasi pola cuaca yang dinamis dan kompleks.

Dalam proyek ini, digunakan dataset yang terdiri dari fitur-fitur utama cuaca seperti suhu (Temperature), kelembapan (Humidity), kecepatan angin (Wind Speed), peluang presipitasi (Precipitation (%)), tekanan atmosfer (Atmospheric Pressure), indeks UV (UV Index), dan jarak pandang (Visibility (km)). Label target dari dataset ini adalah weather type, yang menunjukkan klasifikasi kondisi cuaca seperti cerah, hujan, mendung, dan sebagainya.

Untuk tujuan klasifikasi, diterapkan berbagai algoritma machine learning seperti Logistic Regression, XGBoost, Random Forest, dan Gaussian Naive Bayes. Penyetelan parameter dilakukan menggunakan GridSearchCV, dan evaluasi model dilakukan melalui metrik akurasi dan skor ROC AUC dengan pendekatan One-vs-Rest. Hasil evaluasi menunjukkan bahwa Random Forest dan XGBoost memiliki performa terbaik dalam hal akurasi dan kemampuan diskriminatif antar kelas cuaca.

Studi lanjutan oleh Zhang et al. (2023) juga mendukung temuan ini, menyatakan bahwa model ensemble sangat efektif dalam menangani kompleksitas data cuaca dan memberikan hasil prediksi yang lebih stabil. Sementara itu, Ribeiro, Singh, dan Guestrin (2024) menekankan pentingnya interpretabilitas model dalam konteks prediksi iklim dan cuaca, untuk mendukung keputusan berbasis data yang transparan.

Dengan demikian, proyek ini menunjukkan bahwa pendekatan klasifikasi berbasis machine learning sangat potensial dalam meningkatkan kualitas prediksi cuaca dan dapat dimanfaatkan dalam pengembangan sistem informasi cuaca otomatis.

1. *Mengapa Masalah Ini Perlu Diselesaikan*
* Cuaca Mempengaruhi Aktivitas Harian dan Industri Vital
Cuaca berperan besar dalam menentukan keamanan, efisiensi, dan keberlangsungan berbagai sektor seperti transportasi, pertanian, energi, hingga pariwisata. Misalnya, kesalahan dalam memprediksi hujan dapat menyebabkan kecelakaan lalu lintas atau gagal panen.

* Prediksi Manual Rentan Kesalahan dan Terbatas Skalanya
Klasifikasi kondisi cuaca secara konvensional sangat bergantung pada observasi manusia atau sistem berbasis aturan tetap (rule-based systems), yang tidak selalu akurat atau responsif terhadap perubahan data real-time. Hal ini mendorong kebutuhan akan pendekatan yang lebih adaptif dan otomatis.

* Didukung Bukti Empiris dan Riset Akademik
Penelitian oleh Alzubaidi et al. (2023) menunjukkan bahwa penggunaan algoritma pembelajaran mesin secara signifikan mampu meningkatkan ketepatan klasifikasi cuaca. Ini menegaskan bahwa solusi berbasis machine learning bukan hanya memungkinkan, tetapi juga terbukti efektif dalam praktik.

* Peningkatan Kesiapsiagaan terhadap Perubahan Iklim
Dengan perubahan iklim yang semakin ekstrem, sistem klasifikasi cuaca yang cepat dan akurat menjadi bagian penting dari mitigasi risiko bencana dan adaptasi terhadap kondisi lingkungan yang berubah.

2. *Bagaimana Masalah Ini Dapat Diselesaikan*
* Pemanfaatan Data Historis Cuaca
Dataset yang terdiri dari fitur-fitur meteorologis seperti suhu, kelembapan, kecepatan angin, tekanan udara, dan visibilitas digunakan sebagai input untuk melatih model klasifikasi. Label cuaca (‘weather type’) digunakan sebagai target klasifikasi.

* Penerapan Teknik Pra-pemrosesan Data
Data numerik distandarisasi agar memiliki skala yang seragam, dan data kategorikal dikonversi menggunakan teknik one-hot encoding. Hal ini memastikan bahwa model machine learning dapat memahami struktur data dengan optimal.

* Pelatihan Model dengan Algoritma Supervised Learning
Berbagai algoritma seperti Logistic Regression, XGBoost, Random Forest, dan Gaussian Naive Bayes digunakan untuk membangun model klasifikasi. Model-model ini dilatih menggunakan subset data latih dan dievaluasi menggunakan data uji yang telah disiapkan sebelumnya.

* Optimasi Model melalui Hyperparameter Tuning
GridSearchCV digunakan untuk menyetel parameter optimal dari masing-masing model agar performanya maksimal. Ini memungkinkan pemilihan konfigurasi terbaik secara sistematis berdasarkan skor akurasi validasi silang.

* Evaluasi Performa Model secara Kuantitatif
Model dievaluasi menggunakan metrik akurasi dan ROC AUC Score (strategi One-vs-Rest) untuk mengukur kemampuan klasifikasi multi-kelas. Model dengan performa terbaik dapat diadopsi untuk diterapkan secara nyata.

Alzubaidi, K. S., Alzubaidi, M. A., & Alzubaidi, M. A. (2023). Classification of weather conditions based on supervised learning techniques. Atmosphere, 14(7), 1174. https://doi.org/10.3390/atmos14071174

Zhang, Y., Li, M., & Chen, Q. (2023). Ensemble Learning Models for Weather Condition Classification Using Meteorological Sensor Data. Atmosphere, 14(7), 1182.

Ribeiro, M. T., Singh, S., & Guestrin, C. (2024). Interpretable Machine Learning for Weather and Climate Prediction. Atmospheric Environment, 287, 119304. https://doi.org/10.1016/j.atmosenv.2024.119304

## Business Understanding

Bagian laporan ini mencakup:

### Goals

- Membangun model klasifikasi yang mampu mengidentifikasi jenis cuaca secara akurat menggunakan data meteorologis yang tersedia, sehingga dapat membantu dalam prediksi kondisi cuaca secara otomatis.
- Membandingkan performa berbagai algoritma supervised learning seperti Logistic Regression, XGBoost, Random Forest, dan Gaussian Naive Bayes untuk menentukan metode yang paling efektif dalam klasifikasi cuaca.
- Melakukan optimasi hyperparameter pada model-model yang dipilih menggunakan teknik GridSearchCV guna memperoleh konfigurasi terbaik yang meningkatkan akurasi dan kestabilan prediksi.

### Solution statements
- Membangun beberapa model klasifikasi supervised learning menggunakan algoritma Logistic Regression, XGBoost, Random Forest, dan Gaussian Naive Bayes berdasarkan dataset meteorologis dengan fitur-fitur utama cuaca.
- Mengoptimalkan hyperparameter setiap model menggunakan GridSearchCV dengan validasi silang (5-fold cross-validation) untuk memperoleh konfigurasi terbaik yang memaksimalkan performa.
- Mengevaluasi performa setiap model menggunakan metrik akurasi dan ROC AUC Score (multi-kelas dengan strategi One-vs-Rest) sebagai ukuran kemampuan klasifikasi dan diskriminasi antar kelas.
- Memilih model terbaik berdasarkan hasil evaluasi yang dapat diterapkan dalam sistem klasifikasi cuaca otomatis untuk meningkatkan ketepatan prediksi kondisi cuaca.
- Mengukur keberhasilan solusi dengan peningkatan nilai akurasi dan ROC AUC dibandingkan baseline, serta kemampuan model dalam mengklasifikasikan data uji yang sebelumnya belum pernah dilihat.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [Weather Type Classification](https://www.kaggle.com/datasets/nikhil7280/weather-type-classification/data).

### Variabel-variabel pada Weather Type Classification dataset adalah sebagai berikut:
- Temperature (numeric): Menunjukkan suhu dalam derajat Celsius, mencakup kondisi dari sangat dingin hingga sangat panas.
- Humidity (numeric): Persentase kelembapan, termasuk nilai di atas 100% untuk memasukkan outlier.
- Wind Speed (numeric): Kecepatan angin dalam kilometer per jam, dengan rentang yang mencakup nilai yang sangat tinggi secara tidak realistis.
- Precipitation (%) (numeric): Persentase presipitasi, termasuk nilai-nilai outlier.
- Cloud Cover (categorical): Deskripsi tingkat tutupan awan.
- Atmospheric Pressure (numeric): Tekanan atmosfer dalam hPa, mencakup berbagai rentang nilai.
- UV Index (numeric): Indeks yang menunjukkan kekuatan radiasi ultraviolet.
- Season (categorical): Musim pada saat data direkam.
- Visibility (km) (numeric): Jarak pandang dalam kilometer, termasuk nilai yang sangat rendah atau sangat tinggi.
- Location (categorical): Jenis lokasi tempat data diambil.
- Weather Type (categorical): Variabel target untuk klasifikasi, yang menunjukkan jenis cuaca.


*Beberapa tahapan yang diperlukan untuk memahami data:*
1. Memuat dan Menampilkan Data Awal

    Melihat beberapa baris pertama (head) dari dataset untuk memahami jenis data dan format tiap kolom.
2. Informasi Umum Dataset

    * Menggunakan fungsi seperti info() untuk mengetahui jumlah baris, kolom, tipe data, dan nilai null. Data yang digunakan memiliki 13200 baris dan memiliki 11 kolom antara lain Temperature, Humidity, Wind Speed, Precipitation (%), Cloud Cover, Atmospheric Pressure, UV Index, Season, Visibility (km), Location, Weather Type dan tidak memiliki nilai null

    * Mengetahui proporsi data kategorikal vs numerik.
3. Statistik Deskriptif

    Menggunakan describe() untuk memperoleh ringkasan statistik seperti mean, median, standard deviation, nilai minimum dan maksimum dari fitur numerik.
4. Pemeriksaan Nilai Kosong atau Duplikat

    Mengecek apakah ada data yang hilang (missing values) dan data yang duplikat yang mungkin memengaruhi analisis. pada pengecekan missing value dan data duplikat, diketahui bahwa data yang digunakan tidak memiliki missing value dan data duplikat.
5. Analisis Distribusi Variabel

    * Melihat distribusi setiap fitur numerik melalui histogram, boxplot, atau density plot.

    * Ini juga membantu mendeteksi outlier.
  
6. Analisis Variabel Kategorikal

    * Menghitung frekuensi tiap kategori.

    * Menggunakan bar plot untuk visualisasi distribusi kategori.
  
7. Visualisasi Target (Weather Type)

    Melihat distribusi kelas target, apakah seimbang atau tidak (imbalance class).
8. Visualisasi Multivariate

    * Menggunakan pairplot atau scatter plot antar fitur penting.

    * Visualisasi berbasis warna sesuai label target untuk melihat pemisahan alami.

## Data Preparation
Pada tahap ini, dilakukan beberapa proses untuk mempersiapkan data agar dapat digunakan oleh algoritma machine learning secara optimal. Proses ini mencakup encoding, pembagian data, dan normalisasi fitur numerik.

1. Menangani outliers
   Proses ini adalah bagian penting dari data cleaning. Dengan menerapkan capping, Anda memastikan data lebih stabil dan representatif, terutama untuk keperluan pemodelan statistik atau machine learning.
1. Train-Test-Split
   Data dibagi menjadi data latih (70%) dan data uji (30%). stratify=y_encoded digunakan agar proporsi label target tetap seimbang antara train dan test set. Memisahkan data untuk evaluasi model agar tidak overfitting.
1. Encoding Variabel Kategorikal (Ordinal Encoding)
    Ordinal encoding adalah teknik pra-pemrosesan yang digunakan untuk mengubah fitur kategorikal menjadi nilai numerik dengan menggantikan setiap kategori dengan bilangan bulat. Dalam proyek ini, fitur 'Cloud Cover', 'Season', dan 'Location' dienkode menggunakan OrdinalEncoder dari library feature-engine dengan metode arbitrary, yang memberikan angka unik secara acak untuk setiap kategori tanpa mengasumsikan adanya urutan tertentu. Pendekatan ini dipilih karena sederhana, efisien, dan sesuai untuk model pembelajaran mesin berbasis pohon seperti Random Forest dan XGBoost, yang tidak sensitif terhadap skala nilai numerik. Namun, perlu kehati-hatian jika digunakan bersama model linier seperti Logistic Regression karena bisa menimbulkan asumsi urutan yang tidak sesuai dengan makna asli data.
2. Encoding Target Label (Label Encoding)
    engubah label target dari kategori menjadi angka (misalnya "Rainy" → 0, "Sunny" → 1, dst). Label dalam bentuk teks tidak dapat digunakan secara langsung dalam klasifikasi. Encoding ini memungkinkan algoritma memahami target.
4. Standardisasi Fitur Numerik (Feature Scaling)
    Mengubah fitur numerik agar memiliki rata-rata 0 dan standar deviasi 1. Beberapa algoritma (misalnya KNN, SVM, Regresi Logistik) sensitif terhadap skala fitur. Standardisasi memastikan semua fitur berada pada skala yang sama.

## Modeling
Pada tahap ini dilakukan pembangunan dan evaluasi beberapa model klasifikasi untuk memprediksi jenis cuaca berdasarkan fitur-fitur meteorologis. Algoritma machine learning yang digunakan adalah:

### 1. Logistic Regression

**Cara Kerja:**  
Logistic Regression adalah algoritma klasifikasi linier yang memodelkan probabilitas keanggotaan suatu kelas menggunakan fungsi sigmoid. Model menghitung kombinasi linier dari fitur, lalu mengubahnya menjadi probabilitas melalui fungsi logistik.

**Parameter yang Dioptimasi:**
- `C`: Parameter regularisasi yang mengontrol kompleksitas model (nilai: 0.1, 1, 10). Semakin kecil nilainya, semakin kuat regularisasi.
- `solver`: Metode optimasi yang digunakan (liblinear, saga).

**Parameter Terbaik**
- `C` : 10
- `solver` : saga

**Kelebihan:**
- Sederhana dan cepat dilatih.
- Mudah diinterpretasikan.
- Cocok untuk data dengan hubungan linier antar fitur.

**Kekurangan:**
- Tidak bekerja optimal untuk hubungan non-linear antar fitur.
- Sensitif terhadap outlier.

**Akurasi:** 0.866

---

### 2. XGBoost (Extreme Gradient Boosting)

**Cara Kerja:**  
XGBoost adalah algoritma boosting berbasis pohon keputusan yang membangun model secara bertahap. Setiap pohon baru berusaha mengoreksi kesalahan dari pohon sebelumnya menggunakan pendekatan *gradient descent*. Dilengkapi dengan regularisasi untuk mencegah overfitting.

**Parameter yang Dioptimasi:**
- `n_estimators`: Jumlah pohon (50, 100, 200).
- `learning_rate`: Laju pembelajaran (0.01, 0.1, 0.2).
- `max_depth`: Kedalaman pohon (3, 6, 9).

**Parameter Terbaik**
- `learning_rate`: ( 0.1 )
- `max_depth`: ( 3 )
- `n_estimators`: ( 100 )
  
**Kelebihan:**
- Performa tinggi, cocok untuk data kompleks.
- Menangani missing value dan overfitting dengan baik.
- Mendukung paralelisasi.

**Kekurangan:**
- Waktu pelatihan relatif lama.
- Lebih sulit diinterpretasikan.

**Akurasi:** 0.9122

---

### 3. Random Forest

**Cara Kerja:**  
Random Forest adalah ensemble dari banyak pohon keputusan. Setiap pohon dilatih pada subset acak dari data dan fitur. Prediksi akhir diambil dari mayoritas voting (klasifikasi) atau rata-rata (regresi).

**Parameter yang Dioptimasi:**
- `n_estimators`: Jumlah pohon (50, 100, 200).
- `max_depth`: Kedalaman maksimum pohon (None, 10, 20, 30).

**Parameter Terbaik**
- `max_depth`: ( 10 )
- `n_estimators`: ( 200 )

**Kelebihan:**
- Tahan terhadap overfitting.
- Dapat menangani data numerik dan kategorikal.
- Menyediakan estimasi pentingnya fitur.

**Kekurangan:**
- Interpretasi model sulit.
- Proses prediksi bisa lambat untuk dataset besar.

**Akurasi:** 0.9123

---

### 4. Gaussian Naive Bayes

**Cara Kerja:**  
Gaussian Naive Bayes adalah model probabilistik yang menggunakan Teorema Bayes dengan asumsi bahwa fitur saling independen. Distribusi Gaussian (normal) digunakan untuk memodelkan fitur numerik.

**Parameter:**
- Tidak memerlukan tuning hyperparameter.

**Kelebihan:**
- Cepat dan efisien, terutama untuk dataset besar.
- Cocok untuk data dengan fitur yang relatif independen.

**Kekurangan:**
- Asumsi independensi sering tidak terpenuhi.
- Kurang akurat pada data kompleks.

**Akurasi:** 0.868


*Model Terbaik*
Berdasarkan hasil evaluasi dengan metrik akurasi dan ROC AUC Score, model Random Forest dipilih sebagai model terbaik. Meskipun XGBoost memiliki skor yang sangat mirip, Random Forest unggul sedikit pada ROC AUC Score (0.9948) dan memberikan hasil yang stabil dengan waktu pelatihan yang relatif lebih cepat pada dataset ini.

Selain itu, Random Forest juga lebih sederhana dalam tuning parameter dibandingkan XGBoost, sehingga lebih praktis untuk implementasi dalam sistem klasifikasi cuaca secara real-time.

## Evaluation
1. Metrik Evaluasi yang Digunakan
    Dalam proyek ini, digunakan dua metrik utama untuk mengevaluasi performa model klasifikasi:
   * Akurasi (Accuracy)
   * ROC AUC Score (One-vs-Rest, Macro Average)
Kedua metrik ini dipilih karena:
* Data memiliki beberapa kelas (multiclass classification).
* Tujuan utama adalah meminimalkan kesalahan prediksi jenis cuaca secara keseluruhan dan juga melihat kemampuan model dalam membedakan antar kelas.

2. Penjelasan Metrik
    1. Akurasi (Accuracy)
       Akurasi mengukur proporsi prediksi yang benar dibandingkan dengan total prediksi.
       
       $$
       \text{Accuracy} = \frac{\text{Jumlah prediksi benar}}{\text{Total prediksi}}
       $$

       Cocok digunakan jika data seimbang antar kelas, dan memberikan gambaran umum seberapa sering model benar.
   2. ROC AUC Score (Receiver Operating Characteristic - Area Under the Curve)
      * Untuk klasifikasi multikelas, ROC AUC dihitung dengan pendekatan One-vs-Rest (OvR), yaitu mengevaluasi performa model dalam membedakan satu kelas terhadap kelas lainnya, lalu dirata-rata.
      * ROC AUC mengukur kemampuan model dalam memberi skor probabilitas yang benar, bukan hanya prediksi label.
      * Nilai ROC AUC:
        * 1.0 → prediksi sempurna.
        * 0.5 → sama seperti menebak secara acak.
      * Macro Average: Rata-rata skor dihitung untuk semua kelas tanpa memperhitungkan proporsi kelas (setara).

3. Hasil Evaluasi Proyek

Berikut adalah hasil evaluasi dari keempat model yang digunakan:
| **Model**            | **Akurasi** | **ROC AUC Score (OvR, Macro)** |
| -------------------- | ----------- | ------------------------------ |
| Logistic Regression  | 0.8667      | 0.9479                         |
| XGBoost              | 0.9122      | 0.9941                         |
| Random Forest        | **0.9123**  | **0.9948**                     |
| Gaussian Naive Bayes | 0.8681      | 0.9456                        |

4. Interpretasi Hasil
   * Random Forest memberikan performa terbaik secara keseluruhan, dengan akurasi tertinggi (91.23%) dan ROC AUC Score tertinggi (0.9948).
   * XGBoost menunjukkan hasil yang sangat kompetitif, hanya sedikit di bawah Random Forest.
   * Logistic Regression juga bekerja cukup baik, namun kurang akurat dibandingkan dua model di atas.
   * Gaussian Naive Bayes menjadi yang paling sederhana namun memiliki performa paling rendah, menunjukkan keterbatasannya pada data kompleks.

5. Kesimpulan

Dengan mempertimbangkan metrik evaluasi yang sesuai untuk klasifikasi multikelas dan mempertimbangkan keseimbangan antara akurasi dan kemampuan membedakan antar kelas (ROC AUC), model Random Forest dipilih sebagai model terbaik untuk klasifikasi jenis cuaca dalam proyek ini.

# Laporan Proyek Machine Learning - Divano Rizqi Anandra

## Project Overview

Dalam era digital saat ini, jumlah konten yang tersedia di berbagai platform hiburan seperti Netflix, Disney+, dan Amazon Prime Video telah berkembang secara eksponensial. Kondisi ini membuat pengguna sering mengalami kesulitan dalam menemukan film yang sesuai dengan preferensi mereka. Oleh karena itu, sistem rekomendasi menjadi komponen penting dalam menyaring informasi dan meningkatkan pengalaman pengguna dengan memberikan saran yang relevan dan dipersonalisasi.

Sistem rekomendasi secara umum terbagi ke dalam dua pendekatan utama, yaitu Content-Based Filtering dan Collaborative Filtering. Content-Based Filtering memberikan rekomendasi berdasarkan kesamaan fitur antara item yang telah disukai sebelumnya oleh pengguna dengan item lain yang tersedia. Fitur-fitur ini dapat berupa genre, sutradara, pemeran, hingga sinopsis film. Menurut Lops, de Gemmis, dan Semeraro (2011), pendekatan ini bekerja dengan membangun profil pengguna berdasarkan atribut item yang pernah dinilai positif, sehingga mampu memberikan saran yang lebih terpersonalisasi berdasarkan konten (Lops et al., 2011).

Di sisi lain, Collaborative Filtering memberikan rekomendasi berdasarkan perilaku dan preferensi kolektif dari pengguna lain. Sistem ini mengasumsikan bahwa jika dua pengguna memiliki kesukaan yang serupa terhadap sejumlah film, maka mereka kemungkinan akan menyukai film lainnya yang juga disukai satu sama lain. Menurut Su dan Khoshgoftaar (2009), metode ini sangat efektif karena mampu menangkap pola tersembunyi dalam interaksi pengguna tanpa memerlukan informasi eksplisit tentang item (Su & Khoshgoftaar, 2009).

Kedua metode tersebut memiliki kelebihan dan kekurangannya masing-masing. Content-Based Filtering unggul dalam menangani masalah cold-start pada item baru karena dapat memberikan rekomendasi meskipun belum ada ulasan atau penilaian dari pengguna lain. Namun, metode ini cenderung terbatas pada item yang serupa dengan yang telah disukai sebelumnya, sehingga dapat mengurangi keberagaman rekomendasi. Sebaliknya, Collaborative Filtering memiliki kemampuan yang lebih baik dalam memperkenalkan item baru yang berbeda dari preferensi sebelumnya, namun sering mengalami masalah cold-start pada pengguna baru dan sparsity ketika data interaksi pengguna terbatas.

Untuk mengatasi keterbatasan masing-masing pendekatan, banyak penelitian menyarankan penerapan metode hybrid yang menggabungkan kekuatan Content-Based Filtering dan Collaborative Filtering. Seperti yang dijelaskan oleh Adomavicius dan Tuzhilin (2005), pendekatan hybrid dapat meningkatkan akurasi, keberagaman, dan mengatasi masalah cold-start serta sparsity dalam sistem rekomendasi modern.

Berdasarkan latar belakang tersebut, proyek ini mengembangkan sebuah sistem rekomendasi film dengan menerapkan kedua metode utama, yaitu Content-Based Filtering dan Collaborative Filtering. Sistem ini dirancang untuk menguji keefektifan masing-masing pendekatan dalam memberikan saran film yang relevan dan personal kepada pengguna, serta mengevaluasi kelebihan dan kekurangannya dalam skenario dunia nyata.


### Mengapa Masalah ini harus diselesaikan
* Tingginya Volume Konten Film
  Pengguna menghadapi kebingungan dalam memilih film karena terlalu banyak pilihan yang tersedia di platform streaming, menyebabkan information overload.
* Penurunan Kepuasan Pengguna
  Tanpa sistem rekomendasi yang akurat, pengguna cenderung merasa frustrasi dan tidak terbantu, yang dapat menurunkan retensi pengguna di platform.
* Kebutuhan Personalisasi yang Tinggi
  Setiap pengguna memiliki preferensi unik yang tidak bisa dipenuhi dengan pendekatan umum (non-personal). Rekomendasi berbasis personalisasi meningkatkan relevansi dan kepuasan.
* Persaingan Antar Platform
  Layanan seperti Netflix, Disney+, dan lainnya bersaing dalam menyajikan pengalaman pengguna terbaik. Sistem rekomendasi menjadi salah satu faktor kunci dalam mempertahankan pengguna.
* Keterbatasan Masing-Masing Metode Rekomendasi
  - Content-Based Filtering terbatas dalam keragaman rekomendasi.
  - Collaborative Filtering lemah pada cold-start (pengguna/item baru).
Oleh karena itu, diperlukan pendekatan yang lebih komprehensif.


### Bagaimana Masalah Ini Harus Diselesaikan
* Penerapan Content-Based Filtering (CBF)
  Sistem merekomendasikan film berdasarkan fitur konten seperti genre, aktor, atau sinopsis yang mirip dengan film yang disukai pengguna.
* Penerapan Collaborative Filtering (CF)
  Sistem memanfaatkan data perilaku pengguna lain yang memiliki kesamaan preferensi untuk memberikan saran film, tanpa melihat isi konten film itu sendiri.
* Penggunaan Dataset dan Algoritma yang Tepat
  Menggunakan dataset yang representatif, serta algoritma yang sesuai untuk implementasi kedua metode seperti:
  - Cosine similarity atau TF-IDF untuk CBF
  - Matrix factorization atau user-item similarity untuk CF

### Referensi
* Adomavicius, G., & Tuzhilin, A. (2005). Toward the next generation of recommender systems: A survey of the state-of-the-art and possible extensions. IEEE Transactions on Knowledge and Data Engineering, 17(6), 734–749. https://doi.org/10.1109/TKDE.2005.99
* Lops, P., de Gemmis, M., & Semeraro, G. (2011). Content-based recommender systems: State of the art and trends. In Recommender Systems Handbook (pp. 73–105). Springer. https://doi.org/10.1007/978-0-387-85820-3_3
* Su, X., & Khoshgoftaar, T. M. (2009). A survey of collaborative filtering techniques. Advances in Artificial Intelligence, 2009, 1–19. https://doi.org/10.1155/2009/421425

## Business Understanding

Pada bagian ini, Anda perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah:
- Bagaimana merancang sistem rekomendasi film yang mampu memberikan saran yang relevan dan personal kepada pengguna berdasarkan preferensi mereka?
- Bagaimana cara menerapkan metode Content-Based Filtering dan Collaborative Filtering dalam sistem rekomendasi film?
- Apa kelebihan dan kekurangan dari masing-masing metode dalam konteks sistem rekomendasi film?

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Mengembangkan sistem rekomendasi film menggunakan dua pendekatan utama, yaitu Content-Based Filtering dan Collaborative Filtering.
- Menganalisis cara kerja dan implementasi masing-masing metode dalam menghasilkan rekomendasi yang relevan.

### Solution statements
- Pengumpulan dan Pemrosesan Data Film
  Menggunakan dataset film publik yang berisi informasi film (judul, genre, tahun rilis) serta rating dari pengguna. Dataset ini akan diproses lebih lanjut untuk membentuk fitur yang relevan dengan kedua pendekatan yang digunakan.
- Penerapan Metode Content-Based Filtering
  Sistem akan menganalisis fitur konten dari film, seperti genre, sinopsis, dan kata kunci, untuk membangun profil pengguna. Teknik seperti TF-IDF (Term Frequency-Inverse Document Frequency) atau CountVectorizer akan digunakan untuk merepresentasikan konten film dalam bentuk vektor. Kemudian digunakan cosine similarity untuk mengukur kemiripan antar film berdasarkan konten.
- Penerapan Metode Collaborative Filtering
  Sistem akan menganalisis data perilaku pengguna, khususnya pola rating atau interaksi pengguna terhadap film. Item-Based Collaborative Filtering, dengan mengukur kemiripan antar item (film) berdasarkan rating pengguna. Pendekatan ini dapat dibangun dengan teknik seperti Pearson correlation atau matrix factorization (misalnya SVD - Singular Value Decomposition).

  
## Data Understanding
Saya menggunakan dataset [Movie Recommendation Data](https://www.kaggle.com/datasets/rohan4050/movie-recommendation-data) karena dataset ini berisi hal-hal yang relevan dengan film sehingga dapat digunakan dalam sistem rekomendasi ini.


Variabel-variabel pada Movie Recommendation Data dataset adalah sebagai berikut:
- links : Berisi pengenal (identifiers) yang dapat digunakan untuk menghubungkan data film ini dengan sumber data film lainnya. Informasi ini terdapat dalam file links.csv, di mana setiap baris setelah baris header mewakili satu film.
- movies : Berisi informasi mengenai film yang terdapat dalam file movies.csv. Setiap baris setelah baris header mewakili satu film.
- ratings : Berisi seluruh data penilaian (rating) yang diberikan oleh pengguna terhadap film. Data ini terdapat dalam file ratings.csv, di mana setiap baris setelah baris header mewakili satu penilaian dari satu pengguna terhadap satu film.
- tags : Berisi seluruh tag atau label yang diberikan oleh pengguna terhadap film. Data ini terdapat dalam file tags.csv, di mana setiap baris setelah baris header mewakili satu tag yang diterapkan oleh satu pengguna terhadap satu film.
- Load data
- Mengecek nilai unik yang ada pada dataset seperti link movie dari dataset links memiliki 9742, jumlah data movie dari dataset movies memiliki 9742, jumlah data user dari dataset ratings memiliki 610, jumlah rating dari user dari dataset rating memiliki 9742 dan jumlah data movieId yang ada pada dataset tags yaitu 1572.
- Mengecek dataset links dengan "links.info()" untuk melihat berapa kolom dan baris yang dimiliki oleh dataset links. dan "links.head()" untuk melihat bagaimana 5 baris awal pada dataset links. dataset links memiliki 9742 baris dengan 3 kolom yaitu movieId, imdbId dan tmdbId. movieId adalah pengenal (identifier) untuk film yang digunakan oleh situs MovieLens. Sebagai contoh, film Toy Story memiliki tautan https://movielens.org/movies/1. imdbId adalah pengenal untuk film yang digunakan oleh situs IMDb. Sebagai contoh, film Toy Story memiliki tautan http://www.imdb.com/title/tt0114709/. tmdbId adalah pengenal untuk film yang digunakan oleh situs The Movie Database (TMDb). Sebagai contoh, film Toy Story memiliki tautan https://www.themoviedb.org/movie/862.
- Mengecek dataset Movies dengan "movies.info()" dan melihat berapa genre yang ada pada dataset movies. dataset movies memiliki 9742 baris dengan 3 kolom yaitu movieId, title, genres. genres memiliki 19 genre dan 1 genre yang tidak diketahui yaitu ['(no genres listed)', 'Action', 'Adventure', 'Animation', 'Children', 'Comedy', 'Crime', 'Documentary', 'Drama', 'Fantasy', 'Film-Noir', 'Horror', 'IMAX', 'Musical', 'Mystery', 'Romance', 'Sci-Fi', 'Thriller', 'War', 'Western'].
- Mengecek dataset ratings dengan "ratings.head()", "ratings.info()", dan "ratings.describe()" untuk memberikan ringkasan tentang jumlah data (berapa banyak nilai yang tersedia), rata-rata (nilai tengah dari seluruh data), simpangan baku (menggambarkan seberapa besar variasi atau penyebaran data), nilai minimum dan maksimum (nilai terkecil dan terbesar), serta persentil ke-25, ke-50 (median), dan ke-75 yang menunjukkan posisi nilai-nilai tertentu dalam data. Dataset ratings terdiri dari 100.836 data penilaian yang diberikan oleh 610 pengguna terhadap berbagai film dengan ID yang tersebar hingga 193.609. Setiap entri mencakup informasi berupa userId, movieId, rating, dan timestamp. Nilai rating yang diberikan berada dalam rentang 0.5 hingga 5.0, dengan rata-rata berada di angka 3.5. Mayoritas rating berkumpul pada kisaran 3.0 hingga 4.0, menunjukkan kecenderungan pengguna memberikan penilaian sedang hingga tinggi. Seluruh kolom dalam dataset ini lengkap dan tidak mengandung nilai yang hilang (missing value).
- Mengecek dataset tags dengan "tags.info()" dan "tags.head()". Dataset tags memiliki 3683 baris dan memiliki 4 kolom yaitu userId, movieId, tag dan timestamp. Contoh tag: “funny”, “Highly quotable”, “Boxing story” – menunjukkan sifat subjektif dan bebas

## Data Preparation
Berikut adalah hal yang dilakukan pada tahap data preparation:

* Menggabungkan movieId Unik dari Seluruh Dataset
  Langkah ini bertujuan untuk mengidentifikasi semua film (movieId) yang tercantum dalam keempat dataset (movies, ratings, tags, dan links). Dengan menggabungkan dan menghapus duplikat, kita memastikan bahwa tidak ada film yang terlewatkan dalam proses analisis.
* Menggabungkan dataset yang berhubungan dengan user seperti ratings dan user
  pada tahap ini hanya digunakan untuk melihat data apa saja yang berkaitan dengan user.
* Menggabungkan Data dari Seluruh Dataset
  Data dari keempat sumber digabungkan untuk membentuk satu dataset utama. ratings dijadikan basis karena berisi interaksi pengguna, kemudian digabungkan dengan informasi tambahan seperti judul film (title), genre, dan tag. Hal ini penting agar setiap baris data memiliki konteks yang lengkap untuk dianalisis.
* Pengecekan missing value
  karena dilakukan nya penggabungan dataset jadi kemungkinan besar terdapat missing value dan benar adanya.
* Pengelompokan data berdasarkan movieId
  Dilakukan pengelompokan data berdasarkan movieId menggunakan fungsi groupby. Tujuan dari langkah ini adalah untuk menghitung agregat numerik seperti jumlah rating per film. Hasil ini dapat memberikan gambaran awal tentang popularitas masing-masing film dan digunakan sebagai informasi tambahan dalam proses penyaringan atau analisis.
* Mendefinisikan variabel movies_rate untuk digunakan sebagai nama lain dari ratings agar lebih sesuai dengan konteks project ini.
* Penggabungan Data Film, Rating, dan Tag
   Langkah ini menggabungkan informasi rating, nama film, genre, dan tag agar tiap entri memiliki konteks yang lengkap untuk analisis content-based dan collaborative filtering.
* Pengecekan missing value
  Sama seperti sebelumnya, pengecekan dilakukan ketika ada penggabungan data yang memiliki kemungkinan besar ada missing value.
* Penanganan missing value
  Karena dataset tidak dapat dilakukan hal lain selain menghapusnya maka penanganan missing value kali ini yaitu menghapusnya.
* Pengecekan missing value kembali untuk melihat apakah penanganan missing value sebelumnya berjalan lancar.
* Menyortir all_movie berdasarkan movieId kemudian memasukan kedalam variabel sort_movie agar lebih mudah untuk melanjutkan tahapannya.
* Pengecekan data unik movieId yang ada di sort_movie
  Tahap ini dilakukan untuk melihat apakah ada duplikat didalam sort_movie.
* Penghapusan Duplikat
  Setelah pengecekan, dilakukan penghapusan data duplikat agar data dapat digunakan untuk sistem rekomendasi supaya mencegah bias atau pengulangan informasi.
* Konversi ke Format List
  melakukan konversi data dari format Series (kolom pada DataFrame) menjadi format list Python. dilakukannya konversi karena list ini akan ditangani pada tahap selanjutnya.
* Membuat dictionary
  Data diformat ulang ke dalam list dan disusun menjadi dataframe baru movies_new. Ini dilakukan agar struktur data lebih mudah diakses dalam tahap selanjutnya, seperti ekstraksi fitur konten (genre) atau penyajian hasil rekomendasi.

*Data Preparation Untuk Collaborative Filtering*
* Encoding User ID
  Data userId yang awalnya berupa angka acak (misalnya 1, 5, 13, dst) diubah menjadi angka berurutan mulai dari 0 (misalnya 0, 1, 2, dst). Tujuannya adalah untuk mempermudah input ke dalam model machine learning (terutama deep learning) yang membutuhkan input integer yang berurutan sebagai indeks.
* Encoding Movie ID
  Proses yang sama dilakukan untuk movieId, mengubahnya menjadi angka indeks yang konsisten dan unik untuk setiap film. Ini akan digunakan sebagai input ke layer embedding dalam model collaborative filtering.
* Menambahkan Kolom User dan Movie Ter-encode ke Dataframe
  Menambahkan kolom user dan movies sebagai hasil dari mapping sebelumnya. Hal ini dilakukan agar data siap digunakan untuk pelatihan model: setiap pasangan user-film diwakili oleh integer (bukan ID asli).
* Menghitung Jumlah Unik User dan Movie, dan Skala Rating
  Menghitung total user dan film untuk menentukan ukuran embedding layer pada model. Rating dikonversi ke float32 untuk efisiensi pemrosesan. Nilai minimum dan maksimum rating digunakan untuk proses normalisasi rating ke skala 0-1.
* Mengacak dataset
  Pengacakan ini penting dilakukan sebelum membagi dataset menjadi data pelatihan dan validasi agar distribusi data lebih merata dan model tidak belajar berdasarkan urutan data asli.
* Pembagian Data
  Fitur x berisi pasangan (user, movie) dan target y adalah rating yang telah dinormalisasi. Dataset dibagi menjadi 80% data latih dan 20% data validasi untuk evaluasi performa model.

## Modeling
Pada tahap ini, dibangun dua model sistem rekomendasi menggunakan pendekatan yang berbeda, yaitu Content-Based Filtering dan Collaborative Filtering. Keduanya bertujuan untuk memberikan rekomendasi film yang relevan kepada pengguna, namun dengan metode dan keunggulan yang berbeda. Selain itu, sistem juga dirancang untuk menyajikan Top-N Recommendation, yaitu daftar N film terbaik yang direkomendasikan berdasarkan model yang digunakan.

1. *Content-Based Filtering*
Content-Based Filtering adalah pendekatan sistem rekomendasi yang menyarankan item kepada pengguna berdasarkan kemiripan konten item tersebut. Dalam proyek ini, fitur konten yang digunakan adalah genre dari setiap film.

Langkah pertama dalam pendekatan ini adalah mengekstrak informasi dari data genre menggunakan teknik representasi teks yang disebut TF-IDF (Term Frequency-Inverse Document Frequency). TF-IDF membantu mengidentifikasi kata-kata atau genre yang paling representatif dari setiap film. Setelah itu, digunakan teknik Cosine Similarity untuk menghitung tingkat kemiripan antara film satu dengan lainnya berdasarkan vektor TF-IDF yang telah dibuat.

Hasil dari perhitungan kemiripan tersebut kemudian disusun dalam bentuk matriks similarity, di mana setiap baris dan kolom merepresentasikan judul film, dan nilainya menunjukkan seberapa mirip dua film tersebut. Berdasarkan nilai kemiripan tersebut, sistem dapat menyajikan Top-N film teratas yang paling mirip dengan film yang dipilih oleh pengguna.

### Tabel Top-5 Rekomendasi Film Mirip "Toy Story (1995)"

**Film Acuan:**  
**Judul:** Toy Story (1995)  
**Genre:** Adventure &#124; Animation &#124; Children &#124; Comedy &#124; Fantasy  

| No. | Judul Film                                   | Genre                                          |
|-----|-----------------------------------------------|------------------------------------------------|
| 1   | Toy Story 2 (1999)                            | Adventure &#124; Animation &#124; Children &#124; Comedy &#124; Fantasy |
| 2   | Sinbad: Legend of the Seven Seas (2003)       | Adventure &#124; Animation &#124; Children &#124; Fantasy           |
| 3   | Lord of the Rings, The (1978)                 | Adventure &#124; Animation &#124; Children &#124; Fantasy           |
| 4   | Kiki's Delivery Service (Majo no takkyûbin)   | Adventure &#124; Animation &#124; Children &#124; Drama &#124; Fantasy |
| 5   | Cat Returns, The (Neko no ongaeshi) (2002)    | Adventure &#124; Animation &#124; Children &#124; Fantasy           |


*Kelebihan Content-based filtering*
* Tidak memerlukan data interaksi pengguna lain (independen dari user lain).
* Dapat memberikan rekomendasi untuk film baru yang belum memiliki rating (cold start item problem teratasi).
* Rekomendasi yang dihasilkan sangat relevan secara konten.

*Kekurangan Content-based filtering*
* Kurang mampu menangkap preferensi kolektif pengguna.
* Terbatas hanya pada fitur yang digunakan (dalam hal ini: genre), sehingga bisa melewatkan film yang mungkin disukai tapi beda genre.
* Jika data genre tidak lengkap atau terlalu umum, hasilnya bisa bias atau tidak akurat.


2. *Collaborative Filtering*
Collaborative Filtering berbasis model, yang dalam hal ini diimplementasikan menggunakan jaringan neural (deep learning). Model ini mempelajari representasi (embedding) dari pengguna dan item (film) untuk memprediksi preferensi pengguna terhadap film yang belum mereka tonton.
Model yang dibangun terdiri dari dua bagian utama:
* User Embedding: Mewakili setiap pengguna dalam bentuk vektor berdimensi tetap (embedding vector). Vektor ini dipelajari dari data interaksi pengguna terhadap film.
* Movie Embedding: Mewakili setiap film dengan vektor embedding yang juga dipelajari selama proses pelatihan.


Selain itu, model juga mempelajari bias untuk setiap pengguna dan film, yang membantu menangkap preferensi individual dan popularitas umum.

Model dilatih selama sejumlah epoch untuk meminimalkan binary crossentropy loss, dengan optimasi menggunakan Adam optimizer. Fungsi aktivasi akhir yang digunakan adalah sigmoid karena target sudah dinormalisasi. 


### Rekomendasi Film

**ID Pengguna**: 386

---

#### 🎞️ Film dengan Rating Tertinggi dari Pengguna:

| No. | Judul Film          | Genre               |
|-----|---------------------|---------------------|
| 1   | Babe (1995)         | Children &#124; Drama |
| 2   | Pulp Fiction (1994) | Comedy &#124; Crime &#124; Drama &#124; Thriller |

---

#### ⭐ 10 Rekomendasi Teratas untuk Pengguna:

| No. | Judul Film                                                           | Genre                               |
|-----|----------------------------------------------------------------------|-------------------------------------|
| 1   | Umbrellas of Cherbourg, The (Parapluies de Cherbourg, Les) (1964)   | Drama &#124; Musical &#124; Romance     |
| 2   | Paths of Glory (1957)                                                | Drama &#124; War                     |
| 3   | More (1998)                                                          | Animation &#124; Drama &#124; Sci-Fi &#124; IMAX |
| 4   | Lady Jane (1986)                                                     | Drama &#124; Romance                |
| 5   | Awful Truth, The (1937)                                              | Comedy &#124; Romance               |
| 6   | Come and See (Idi i smotri) (1985)                                   | Drama &#124; War                   |
| 7   | Midnight Clear, A (1992)                                             | Drama &#124; War                   |
| 8   | Adam's Rib (1949)                                                    | Comedy &#124; Romance              |
| 9   | Match Factory Girl, The (Tulitikkutehtaan tyttö) (1990)             | Comedy &#124; Drama                |
| 10  | Paterson                                                             | (no genres listed)                 |



*Kelebihan Collaborative Filtering*
* Tidak memerlukan informasi konten film (judul, genre, dll), cukup berdasarkan interaksi pengguna.
* Dapat menangkap pola tersembunyi dalam perilaku pengguna.
* Sangat personal karena berdasarkan preferensi pengguna serupa.

*Kekurangan Collaaborative Filtering*
* Mengalami masalah cold start (tidak bisa merekomendasikan untuk pengguna atau film baru).
* Memerlukan jumlah data interaksi yang cukup besar agar performa optimal.
* Memerlukan proses training yang relatif lebih kompleks dibanding content-based.

## Evaluation
RMSE adalah salah satu metrik regresi yang mengukur seberapa jauh prediksi model dari nilai sebenarnya (dalam hal ini, rating yang diberikan oleh pengguna).
### Root Mean Squared Error (RMSE)

Root Mean Squared Error (RMSE) digunakan untuk mengukur seberapa besar rata-rata kesalahan antara nilai prediksi dan nilai aktual dalam sistem rekomendasi berbasis rating.

Rumus RMSE adalah:

$$
\text{RMSE} = \sqrt{ \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 }
$$

Keterangan:
- \( y_i \): nilai rating aktual dari pengguna ke-\(i\)
- \( \hat{y}_i \): nilai rating yang diprediksi oleh model untuk pengguna ke-\(i\)
- \( n \): jumlah total data (jumlah pasangan user-item)

*Kelebihan RMSE*
* Sensitif terhadap kesalahan besar (outlier): karena error dikuadratkan, maka prediksi yang sangat meleset akan memberikan penalti besar.
* Cocok untuk model regresi rating, seperti Collaborative Filtering.

*Kekurangan RMSE (untuk sistem rekomendasi)*
* RMSE hanya mengukur seberapa akurat model dalam menebak rating, bukan seberapa baik rekomendasinya secara keseluruhan.
* Tidak mempertimbangkan urutan atau relevansi dari daftar rekomendasi (tidak cocok untuk top-N evaluation secara langsung).

Berdasarkan hasil evaluasi terhadap model Collaborative Filtering yang telah dilatih selama 100 epoch, diperoleh nilai root mean squared error (RMSE) pada data pelatihan sebesar 0.1760, dan pada data validasi sebesar 0.2037. RMSE digunakan sebagai metrik utama karena sistem rekomendasi ini berfokus pada prediksi rating pengguna terhadap item (film) yang belum ditonton. Nilai RMSE yang rendah menunjukkan bahwa model mampu mempelajari pola interaksi antara pengguna dan film dengan cukup baik. Selain itu, selisih antara RMSE pada data pelatihan dan validasi yang relatif kecil menandakan bahwa model tidak mengalami overfitting yang berarti, serta memiliki kemampuan generalisasi yang baik terhadap data baru.

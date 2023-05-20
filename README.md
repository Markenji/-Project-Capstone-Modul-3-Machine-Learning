
# Customer Analytics: Ecommerce Customer Churn
#####
 Dibuat oleh : Adha Ozy Prima Dewangga
## Business Problem


### Business Context
E-commerce, atau sering disebut sebagai perdagangan elektronik, merujuk pada aktivitas jual beli produk atau jasa yang dilakukan secara daring atau online melalui internet. E-commerce melibatkan transaksi bisnis antara penjual dan pembeli yang dilakukan secara elektronik, tanpa adanya interaksi fisik langsung antara penjual dan pembeli.Ecommerce Customer Churn adalah istilah yang digunakan untuk menggambarkan proses atau keadaan di mana pelanggan dalam bisnis e-commerce atau toko online berhenti menggunakan layanan atau berhenti melakukan pembelian dari toko tersebut. Dalam kata lain, customer churn terjadi ketika pelanggan yang sebelumnya aktif dalam berbelanja di toko online, kemudian berhenti melakukan transaksi atau tidak lagi berinteraksi dengan toko tersebut. Oleh sebab itu, perusahaan membutuhkan strategi bisnis yang tepat guna mencegah customer churn.

Target :


0 : Pelanggan Tidak Churn

1 : Pelanggan Churn

### Problem Statement :

Proses untuk menangani pelanggan yang akan melakukan churn akan membutuhkan waktu dan sumber daya yang tidak sedikit jika perusahaan akan mengarahkan semuanya pada seluruh pelanggan yang ada tanpa dada penyaringan yang tepat. Perusahaan ingin menerapkan program loyalitas yang menarik, seperti poin hadiah, diskon eksklusif, atau keanggotaan khusus, dapat menjadi cara efektif untuk mendorong pelanggan untuk tetap berada di dalam ekosistem toko online dan melakukan pembelian lagi. Program loyalitas yang dirancang dengan baik dapat memberikan insentif bagi pelanggan untuk tetap setia dan berbelanja lebih sering.

Jika program loyalitas diberikan kepada semua pelanggan, dikhawatirkan anggaran untuk biaya program loyalitas sia-sia jika pelanggan tersebut memang tidak berniat untuk churn

### Goals :
Berdasarakan permasalahan yang telah terlihat, perusahaan ingin memiliki kemampuan untuk membaca kemungkinan untuk seorangn pelanggan untuk churn, sehingga pemberian program loyalitas tertuju pada pelanggan yang ingin churn saja.

Selain itu, perusahaan ingin mengetahui apa yang menjadi faktor-faktor yang membuat seorang pelanggan ingin churn, faktor-faktor tersebut akan digunakan untuk menentukan strategi atau langkah yang tepat untuk perusahaan kedepanya.

### Analytic Approach :
Jadi yang akan kita lakukan adalah menganalisi data untuk menemukan pola yang membedakan pelanggan yang akan melakukan churn dan yang tidak

Kemudian kita akan membangun model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas seorang pelanggan di E-Commerce akan churn atau tidak

Metric Evaluation :
![alt text](https://github.com/Markenji/-Project-Capstone-Modul-3-Machine-Learning/blob/main/Picture/Metric%20Evaluation.png?raw=true)

Type 1 error : False Negatif
Konsekuensi: Pelanggan benar-benar churn, efek sampingnya perusahaan harus mencari pelanggan baru dengan cara iklan.

Type 2 error : False Positif
Konsekuensi: Perusahaan sia-sia memberikan biaya program loyalitas pada pelanggan yang tidak churn, efek sampingnya perusahaan kehilangan uang untuk promosi.

Berdasarkan konsekuensinya, maka sebisa mungkin yang akan kita lakukan adalah membuat model yang dapat mengurangi pelanggan churn dari perusahaan E-Commerst tersebut, tetapi tanpa membuat kesalahan dalam pemberian program loyalitas di rencanakan perusahaan. Dikarenakan biaya iklan cenderung lebih mahal daripada biaya promosi diskon dalam jangka pendek. Di sisi lain, promosi diskon adalah metode pemasaran yang bisa lebih ekonomis karena hanya melibatkan pengurangan harga produk atau layanan. Jadi kita ingin sebanyak mungkin prediksi kelas positif yang benar, dengan sesedikit mungkin prediksi false positive. Jadi nanti metric utama yang akan kita gunakan adalah roc_auc.

## Konten Utama


#### Library
![Pandas License](https://img.shields.io/badge/pandas-1.4.2-lightgrey)  
![Pandas License](https://img.shields.io/badge/numpy-1.23.2-yellow)  
![Pandas License](https://img.shields.io/badge/seaborn-0.11.2-blue)  
![Pandas License](https://img.shields.io/badge/matplotlib-3.5.1-red)<br>
![scikit-learn ](https://img.shields.io/badge/scikit--learn-1.2.2-coral?labelColor=grey&style=flat)<br>
![imblearn ](https://img.shields.io/badge/imblearn-0.0-olive?labelColor=grey&style=flat)<br>
![category-encoders ](https://img.shields.io/badge/category--encoders-2.6.0-emerald?labelColor=grey&style=flat)<br>
![lightgbm ](https://img.shields.io/badge/lightgbm-3.3.5-pink?labelColor=grey&style=flat)<br>
![xgboost](https://img.shields.io/badge/xgboost-1.7.5-navy?labelColor=grey&style=flat)<br>


<h4>E-commerce Customer Churn</h4>
<h4>Konteks</h4>
<p>Kumpulan data milik perusahaan E-niaga online terkemuka. Perusahaan ritel online (E-commerce) ingin mengetahui pelanggan yang akan melakukan churn, sehingga mereka dapat mendekati pelanggan untuk menawarkan beberapa promo.</p>
<h5><b>Fitur</b></h5>
<table>
  <tr>
    <th>Attribute</th>
    <th>Data Type</th>
    <th>Description</th>
  </tr>
  <tr>
    <th><b>Tenure</b></th>
    <td>Float</td>
    <td>Masa jabatan pelanggan di perusahaan.</td>
  </tr>
  <tr>
    <th><b>WarehouseToHome</b></th>
    <td>Float</td>
    <td>Jarak antara gudang ke rumah pelanggan.</td>
  </tr>
  <tr>
    <th><b>NumberOfDeviceRegistered</b></th>
    <td>Integer</td>
    <td>Jumlah total penipuan terdaftar pada pelanggan tertentu.</td>
  </tr>
  <tr>
    <th><b>PreferedOrderCat</b></th>
    <td>Text</td>
    <td>Kategori pesanan pilihan pelanggan pada bulan lalu.</td>
  </tr>
  <tr>
    <th><b>SatisfactionScore</b></th>
    <td>Integer</td>
    <td>Skor memuaskan pelanggan pada layanan.</td>
  </tr>
  <tr>
    <th><b>MaritalStatus</b></th>
    <td>Text</td>
    <td>Status perkawinan pelanggan.</td>
  </tr>
  <tr>
    <th><b>NumberOfAddress</b></th>
    <td>Integer</td>
    <td>Jumlah total yang ditambahkan pada pelanggan tertentu.</td>
  </tr>
  <tr>
    <th><b>Complaint</b></th>
    <td>Integer</td>
    <td>Setiap keluhan telah diajukan pada bulan lalu.</td>
  </tr>
  <tr>
    <th><b>DaySinceLastOrder</b></th>
    <td>Float</td>
    <td>Hari sejak pemesanan terakhir oleh pelanggan.</td>
  </tr>
  <tr>
    <th><b>CashbackAmount</b></th>
    <td>Float</td>
    <td>Average cashback in last month.</td>
  </tr>
  <tr>
    <th><b>Churn</b></th>
    <td>Boolean</td>
    <td>Bendera churn.</td>
  </tr>
</table>

<p>Sumber Data : <a href="https://drive.google.com/drive/folders/1PITb78NtK9Ra6wOkQdXCIgItZkj29Ves">Klik disini</a></p>
<p>Data Awal Terdiri dari : 3941 baris × 11 kolom</p>

## Daftar Isi Main Project ipynb
 - [Data Understanding & Data Cleaning](#Data-Understanding-&-Data-Cleaning)
 - [Data Analysis](#Data-Analysis)
 - [Feature selection, & Feature Engineering](#Feature-selection,-&-Feature-Engineering)
 - [Analytics (Algorithm, Evaluation Metrics)](#Analytics-(Algorithm,-Evaluation-Metrics))
 - [Conclusion and Recommendation/Improvement](#Conclusion-and-Recommendation/Improvement)
 - [Pickle](#Pickle)

### Data Understanding & Data Cleaning 

#### Data Understanding

##### E-commerce Customer Churn

###### Konteks

- Kumpulan data milik perusahaan E-niaga online terkemuka. Perusahaan ritel online (E-commerce) ingin mengetahui pelanggan yang akan melakukan churn, sehingga mereka dapat mendekati pelanggan untuk menawarkan beberapa promo.

#### Data

#### Data Cleaning

- Ada data yang hilang/kosong dibeberapa fitur/kolom. Oleh sebab itu, kita akan memperbaiki semua datanya dan membuatnya menjadi siap pakai untuk melakukan analisa terhadap masalahnya dan juga pembuatan model machine learningnya.
    - Duplicated Data 
    - Statistik Missing Values
    - Handling Missing Values

### Data Analysis

- Penilaian Normalitas
    - Grapical Methods
- Checking Outlier
- Imbalance Classification
### Feature selection, & Feature Engineering

#### Data Preparation
    - Mengecek Missing Value pada Data
    - Handling Missing Value Menggunakan KNNImputer
    - Data splitting
### Analytics (Algorithm, Evaluation Metrics)

#### Modeling & Evaluation
    - Model Benchmarking : Test Data
    - Test Oversampling with K-Fold Cross Validation
    - Evaluation Metrics Without Oversampling
    - Evaluation Metrics With Oversampling
    - Hyperparameter Tuning
    - Feature Importances
    - Shapley Value of Explanations (SHAP)

### Conclusion and Recommendation/Improvement

#### Recommendation 

Hal-hal yang bisa dilakukan untuk mengurangi adanya masalah customer churn antara lain sebagai berikut:
- Memberikan promo program loyalitas pada pelanggan yang masih baru agar mereka tidak memiliki potensi untuk churn.
- Pelanggan dengan masa Tenure tertentu diberikan reward untuk yang sudah lama sedangkan yang baru akan diberikan promo khusus.
- Memperbanyak warehouse khususnya diwilayah yang menjadi tempat pembelian terbanyakan sehingga proses pengataran kepelanggan atau customer lebih cepat.
- Menentukan casback yang sesuai agar baik customer atau penjual tidak dirugikan.
- Melakukan pembaruan pada aplikasi mobile dan website e-commerce agar customer merasakan user experience yang berkesan.
- Menangani Komplain pada customer secara edukatif dan ramah untuk mengurangi potensi customer churn.
- Pada pelanggan baru akan diberikan hadiah gratis berupa sticker atau tas agar memberikan kesan tersendiri.
- Diadakanya udian berhadiah atau diberikan kesempatan bagi pelanggan dengan masa Tenur lebih dari 1 tahun untuk mengikuti udian berhadiah seperti lotre.

Hal-hal yang dapat dilakukan untuk mengembangkan model agar lebih baik lagi, seperti:
- Model ini baik untuk melakukan prediksi. Jika menggunakan parameter yang sudah ada contoh pada Kolom MaritalStatus terdapat 3 pilihan dimana Single, Married, dan Divorced jika parameter ini tidak ada perubahan dan pada kolum lainya belum ada tambahan maka model ini cocok untuk melakukan prediksi dengan bagus.
- Model tidak akan baik untuk melakukan prediksi. jika pada kolum atau parameter kolum mengalami perubahan atau penambahan sehingga memerluhkan proses permodelan dari awal lagi.
- Membandingkan model yang ada dimana pada model dilakukan feature engineering untuk menghingkan missing value dan merubah data kategorical dengan model yang lebih simple. Dimana model yang lebih simple itu adalah menggunakan fillna menggunakan modus atau median dan menggunakan pd.get_dummy untuk merubah data kategorical yang ada pada dataset.
- Menambahkan fitur-fitur atau kolum baru yang memberikan kemungkinan minat customer meningkat, seperti customer adalah customer loyal atau tidak, history jumlah pembelian customer, dan Alamat dari customer.
- Mencoba mengunakan teknik oversampling yang beragam selain RUS seperti; ROSE (Random Under Sampling Examples), Borderline-SMOTE, SMOTE (Synthetic Minority Over-sampling Technique), dan ADASYN (Adaptive Synthetic Sampling).
- Mencoba teknik sederhana dalam oversampling seperti class_weight pada algorithma yang support Imbalance Classification.

### Pickle

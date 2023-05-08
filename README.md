
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

## Konten Utama

![Pandas License](https://img.shields.io/badge/pandas-1.4.2-lightgrey)  
![Pandas License](https://img.shields.io/badge/numpy-1.23.2-yellow)  
![Pandas License](https://img.shields.io/badge/seaborn-0.11.2-blue)  
![Pandas License](https://img.shields.io/badge/matplotlib-3.5.1-red)
![scikit-learn ](https://img.shields.io/badge/scikit--learn-1.2.2-coral?labelColor=grey&style=flat)<br>
![imblearn ](https://img.shields.io/badge/imblearn-0.0-olive?labelColor=grey&style=flat)<br>
![category-encoders ](https://img.shields.io/badge/category--encoders-2.6.0-emerald?labelColor=grey&style=flat)<br>
![lightgbm ](https://img.shields.io/badge/lightgbm-3.3.5-pink?labelColor=grey&style=flat)<br>
![xgboost](https://img.shields.io/badge/xgboost-1.7.5-navy?labelColor=grey&style=flat)<br>


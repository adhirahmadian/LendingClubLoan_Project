# LendingClubLoan_Project
# Overview

LendingClub adalah perusahaan pinjaman peer-to-peer asal USA dan berkantor pusat di San Francisco, California. Perusahaan ini memberikan pinjaman secara peer-to-peer pertama dengan jasa keamanan sebagai nilai jual yaitu dengan Securities and Exchange Commission (SEC), selain itu perusahaan ini juga menawarkan perdagangan pinjaman di pasar sekunder. LendingClub adalah platform pinjaman peer-to-peer terbesar di dunia.

Tujuan dari analsis data ini adalah untuk memprediksi calon nasabah membayar lunas pinjamannya

# Code Resources

Python Version: 3.7

Packages: pandas, numpy, sklearn, matplotlib, seaborn, keras.

https://www.kaggle.com/wordsforthewise/lending-club

# Data Cleaning

Setelah mendapatkan dataset, saya melakukan _data cleaning_ agar dapat digunakan untuk _modelling_. 
* mengeliminasi _employer title_ dan _employer length_.
* membaurkan _title_ dengan _purpose_.
* mengisi _missing data_ _mort_acc_ dengan rataan nilai _mort_acc_ terhadap _total_acc_.

# EDA

Berikut adalah beberapa contoh hasil analisis data

>![Melihat Data kemampuan nasabah melunasi pinjaman](/loan_status.png)

Kurva 1 menunjukan seberapa banyak nasabah yang dapat melunasi pinjamannya dan yang tidak

>![Data berdasarkan Grade](/grade.png)

Kurva 2 menunjukan kemampuan nasabah melunasi pinjamannya berdasarkan _grade_ dari nasabah tersebut.
# Model Building

Pertama, saya mengubah variabel kategori menjadi variabel dummy, lalu membagi data _training_ menjadi 20% dari data total. 

Dengan metode _deep learning_ _keras_, saya menggunakan _Neural Network_ dengan _input layer_ sebanyak 78 sel. _Hidden layer_ yang saya gunakan adalah sel sebelumnya dibagi 2 dengan metode aktivasi _ReLU_ (_Rectified Linear Unit_). Sedangkan _output layer_ nya menggunakan metode aktivasi _sigmoid_, optimasi _'adam'_ dan loss _'binary-crossentropy'_. Metode ini digunakan karena pada kasus ini hanya ada 2 output yaitu Ya (_Full Paid_) atau Tidak (_Charged Off_).

![Model](/model.png)

dari grafik bisa kita lihat hubungan kurva hasil _training_ (_loss_) dan validasi data (_val_loss_). Dengan model ini saya akan mencoba untuk memprediksi data random. 

# Model Performance

Setelah diuji coba menggunakan data acak, dengan model ini saya yakin 89% bisa memprediksi apakah calon nasabah bisa membayar lunas pinjamannya. 

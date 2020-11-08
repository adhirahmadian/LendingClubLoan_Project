# LendingClubLoan_Project
# Overview

LendingClub adalah perusahaan pinjaman peer-to-peer AS, yang berkantor pusat di San Francisco, California. Perusahaan ini adalah perusahaan yang memberikan pinjaman secara peer-to-peer pertama dengan penawaran keamanan sebagai nilai jual yaitu dengan Securities and Exchange Commission (SEC), dan menawarkan perdagangan pinjaman di pasar sekunder. LendingClub adalah platform pinjaman peer-to-peer terbesar di dunia.

Tujuan analsis ini adalah untuk memprediksi apakah seorang calon nasabah akan bisa membayar lunas hutang yang dipinjam atau tidak

# Code Resources

Python Version: 3.7

Packages: pandas, numpy, sklearn, matplotlib, seaborn, keras.

https://www.kaggle.com/wordsforthewise/lending-club

# Data Cleaning

Setelah mendapatkan data, saya melakukan data cleaning agar dapat digunakan untuk _modelling_. 
* mengeliminasi _employer title_ dan _employer length_.
* menyatukan _title_ dengan _purpose_.
* mengisi _missing data_ _mort_acc_ dengan rataan nilai _mort_acc_.

# EDA

Berikut adalah beberapa contoh hasil analisis data

* ![Melihat Data kemampuan nasabah melunasi pinjaman](/loan_status.png)
* ![Data berdasarkan Grade](/grade.png)

# Model Building

Pertama, saya mengubah variabel kategori menjadi variabel dummy. Saya juga membagi data _training_ menjadi 20% dari data total. 

Dengan _deep learning_ _with keras_,disini saya menggunakan _Neural Network_ dengan _input layer_ sebanyak 78 dan untuk hidden layer adalah layer sebelumnya dibagi 2 dengan metode aktivasi _ReLU_ (_Rectified Linear Unit_), dengan output layernya 1 dengan metode aktivasi _sigmoid_ dan optimasi _'adam'_ dan loss _'binary-crossentropy'_. Metode ini digunakan karena pada kasus ini hanya ada 2 output yaitu Ya (_Full Paid_) atau Tidak (_Charged Off_).

* ![Model](/model.png)

dari grafik bisa kita lihat bahwa kurva hasil _training_ (_loss_) dan kurva hasil _test_ (_val_loss_) _overfitting_. sehingga model ini bisa digunakan untuk memprediksi data input lainnya. 

# Model Performance

dari hasil _modelling_ didaptakan nilai f-score sebesar 89%, dan setelah diuji coba menggunakan data acak ternyata model bisa memprediksi seorang calon nasabah apakah bisa membayar lunas hutang yang dipinjam atau tidak

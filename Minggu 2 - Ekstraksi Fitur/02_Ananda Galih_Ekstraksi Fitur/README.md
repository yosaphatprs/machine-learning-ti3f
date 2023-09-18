# NOTES

## Fitur

- fitur = data berbentuk nilai (atribut, ciri)
- beberapa model hanya cocok dengan beberapa jenis fitur, begitu juga sebaliknya.
- Untuk mendapatkan fitur yang sesuai dengan data, model, dan tujuan pembelajaran mesin, dapat dilakukan proses perekayasaan fitur atau lebih sering dikenal dengan istilah **feature engineering**.
Jumlah fitur yang kita gunakan juga sangat penting. Jika fitur yang digunakan terlalu sedikit, maka model pembelajaran mesin tidak dapat belajar dengan baik. Jika fitur yang digunakan terlalu banyak, proses pembelajaran akan berlangsung lebih lama dan ada kemungkinan model menjadi lebih sulit untuk menemukan pola-pola unik didalam fitur-fitur tersebut. Kedua hal tersebut dikenal dengan istilah **underfitting** dan **overfitting**.

## Ekstraksi Fitur

- cara mendapatkan fitur dari sebuah data --> **feature extraction**
- **feature extraction** adalah proses pengurangan (reduksi) dimensi dari sebuah data mentah menjadi nilai-nilai atau variabel-variabel yang mudah dikelola oleh perangkat komputasi


## Data Imputation
- teknik untuk mengganti nilai yang hilang didalam sebuah data
- cara : Menggantinya dengan nilai mean, median, modus, hapus data "NaN"

## Normalisasi
- salah satu teknik penyekalaan fitur untuk menghasilkan nilai fitur yang berada dalam rentang baru, yaitu antara 0 dan 1. 

## Standarisasi
- Model pembelajaran mesin dapat bekerja lebih baik ketika dilatih pada data yang terstandarisasi. Standarisasi melibatkan penyekalaan ulang pada distribusi nilai, sehingga didapatkan nilai tengah (mean) dari data yang diamati adalah 0 dan nilai standar deviasinya adalah 1.

## Encoding
- data kategorikal harus diubah ke dalam bentuk numerikal.
- Ordinal encoding (setiap kategori yang unik diberi nilai integer)
- One-hot encoding (merepresentasikan nilai kategorikal menggunakan 1 fitur biner untuk setiap nilai yang memungkinkan. seperti true(1) or false(0))
- Dummy variable encoding (variabel encoding setiap nilai fitur akan diwakili oleh dua nilai biner)

## Strategi Pembuatan Data Latih, Validasi, dan Uji

### random split dan Stratified Split
- random = langsung memilih secara acak data yang akan kita gunakan sebagai data
- Stratified = membagi data kedalam porsi latih, validasi, dan uji sesuai dengan proporsi setiap label atau kelas

### Cross Validation
- mengevaluasi model dengan cara melakukan evaluasi berganda (membagi data menjadi data latih dan uji) sebagai **fold** 
- Besaran spliting data akan ditentukan oleh nilai k-nya. Sebagai contoh, jika kita menggunakan nilai , maka data akan dibagi menjadi 4 bagian. Salah satu dari bagian tersebut akan menjadi data validasi. Kemudian, untuk setiap iterasi, data validasi akan diganti sesuai dengan jumlah fold.

# Kode Program

- dr.head() --> menampilkan data teratas
- df.info() --> cek info jumlah data, type, dll
- df.isnull().sum() --> cek jumlah data yg hilang
- df = df[['Survived', 'Pclass', 'Age', 'Sex', 'Cabin']] --> pilih atribut yang sesuai
- le = LabelEncoder() --> Membuat objek LabelEncoder sebagai 'le' untuk encoding.
- df['Sex'] = le.fit_transform(df['Sex']) --> proses encoding
- std = StandardScaler()
- df['Age'] = std.fit_transform(df[['Age']])

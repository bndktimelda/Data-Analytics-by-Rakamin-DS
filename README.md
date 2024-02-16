README

# Analisis Aktivitas Customer Telepon

## Latar Belakang & Tujuan
Jalur telepon (fixed line), walau sudah banyak tergeser oleh telepon seluler dan paket data internet, rupanya masih memiliki konsumen setia, baik karena kebiasaan maupun kebutuhan. Dalam Notebook ini akan dieksplorasi hubungan antara demografi konsumen dengan nilai tagihan, metode pembayaran, dan churn rate.

## Hipotesis
* Sebagian besar konsumen memiliki tagihan bulanan yang relatif kecil
* Layanan telepon masih populer di kalangan lansia
* Nilai tagihan yang lebih besar dan keberadaan pasangan serta tanggungan (orangtua/anak) mendorong konsumen untuk churn/berhenti berlangganan

## Data
<br>Data diperoleh dari homework set Rakamin sebagai bagian dari modul visualisasi data dalam Python. Dataset yang digunakan kurang-lebih sudah siap diolah, hanya membutuhkan fill null dan alterasi datatype pada kolom TotalCharge (total tagihan)
* fill null values: baris null dianggap tidak ada tagihan atau 'No Charges'
* change datatype: dari object menjadi numerik

## Hasil Analisis
### 1. Hubungan monthly charge dengan metode bayar
<br> Rataan tagihan bulanan ditemukan paling tinggi pada metode pembayaran cek elektronik. Autodebet bank dan kartu kredit berimbang di urutan kedua dengan rata-rata sekitar 70 USD/bulan, dan angka terkecil ditemukan pada pembayaran lewat cek manual, 50 USD/bulan.

### 2. Pengelompokan konsumen
<br> Kebanyakan pelanggan menjalani tenure kurang dari 21 bulan (low tenure) atau lebih dari 40 bulan (high tenure). Dengan jumlah mendekati 1500, kelompok medium tenure (berlangganan antara 21-40 bulan) adalah segmen pelanggan yang paling kecil dari penyedia layanan telecom ini.
<br> Hampir semua pelanggan usia lanjut yang tercatat dalam dataset ini mengambil paket layanan telepon; hanya 10% yang tidak menggunakan paket telepon.

### 3. Faktor-faktor yang kemungkinan memengaruhi churn decision
###3a. Nilai tagihan
<br> Kebanyakan pelanggan memiliki total tagihan sampai USD 1000.  Jumlah konsumen yang memutuskan churn cenderung meningkat dengan besaran tagihan dan ditemukan paling banyak pada angka tagihan bulanan 80 USD. Akan tetapi, jumlah ini berkurang pada jumlah tagihan 81-100 USD/bulan dan turun banyak pada konsumen yang ditagih lebih dari 100 USD/bulan.

### 3b. Komposisi rumah tangga konsumen
<br> Dilakukan perhitungan distinct customers untuk membandingkan jumlah konsumen dengan komposisi berikut:
* No-No = tidak ada pasangan maupun tanggungan
* No-Yes = tidak memiliki pasangan, hanya tanggungan
* Yes-No = berpasangan, tidak ada tanggungan
* Yes-Yes= punya pasangan dan tanggungan
<br> Dari perbandingan antara komposisi keluarga dan churn decision, tidak dapat disimpulkan bahwa memiliki pasangan dan dependents memengaruhi keputusan berhenti berlangganan.

### 3c. Metode pembayaran
<br>Ditemukan jumlah pelanggan yang membayar dengan cek elektronik dan churn tidak berbeda signifikan dengan jumlah yang masih menggunakan layanan telecom. Proporsi ini tidak terlihat pada churn decision metode pembayaran lainnya - pada metode transfer bank, kartu kredit, dan cek asli, jauh lebih banyak pelanggan yang masih berlangganan ketimbang sudah churn.

## Kesimpulan
* Sebagian besar konsumen memiliki tagihan bulanan di bawah 1000 USD
* Layanan telepon masih populer di kalangan lansia
* Nilai tagihan yang lebih besar meningkatkan kemungkinan berhenti berlangganan sampai batas tertentu

## Saran
* Dapat dipertimbangkan membuat loyalty program untuk memberi insentif pada konsumen lama dan menarik konsumen dengan tenure < 21 bulan agar terus berlangganan

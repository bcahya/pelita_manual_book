# Cost Adjustment

Cost Adjustment adalah proses penyesuaian nilai valuasi produk atau barang yang sudah tercatat di sistem. Penyesuaian ini dilakukan karena:

- Perbedaan harga
- Kesalahan pencatatan sebelumnya

Cost Adjustment tidak melakukan revaluasi terhadap transaksi historis. Sistem hanya akan menggunakan nilai cost baru untuk transaksi berjalan dan transaksi berikutnya.

## Ketentuan Costing Method

Costing Method tidak boleh diubah setelah digunakan dalam transaksi. Pembatasan ini bertujuan untuk:
- Menjaga konsistensi data
- Menjaga integritas transaksi
- Menghindari ketidaksesuaian laporan costing

Jika perusahaan perlu menggunakan costing method yang berbeda, buat product atau article baru lalu arahkan ke Product Category yang sesuai.
## Langkah Cost Adjustment di Sistem

Ikuti langkah berikut untuk melakukan Cost Adjustment:
1. Buka menu **Cost Adjustment**
2. Klik **New**
3. Pilih **Costing Method** pada produk
4. Pilih **Movement Date**

![Cost Adjustment](../Cost_Adjus.png "Cost Adjustment") {#Figure42}

5. Masuk ke tab **Cost Adjustment Line**
6. Pilih produk yang akan disesuaikan
7. Input nilai harga baru pada field **New Cost Price**
8. Input **Charge**

![Cost Adjustment Line](../Cost_Adjs_Line.png "Cost Adjustment Line") {#Figure43}

8. Klik **save**
9. Klik **complete**

## Revaluasi HPP

cost adjustment adalah proses revaluasi. proses revaluasi ini dapat dilakukan untuk produk dan produk di level batch/lot. apabila ada revaluasi hpp pada produk di level batch/lot maka user dapat melakukan penyesuaian melalui fitur cost adjusment. untuk langkah-langkah proses cost adjustment dapat dilakukan melalui proses diatas, namun pada field Attribute Set Instance input ASI atas produk yang akan diproses. 

Sistem akan menghitung harga rata-rata berdasarkan harga beli produk terakhir pada masing-masing Batch atau Lot. Metode ini membantu menjaga akurasi nilai persediaan pada setiap Batch atau Lot. 

Revaluasi harga ini dapat user cek di master produk yang diproses melalui tab Cost. setelah dilakukan cost adjustment, akan muncul average PO di product tersebut yang mana value pada current cost price ini sesuai dengan price saat dilakukan cost adjustment.

Mekanisme yang dilakukan sistem saat dilakukan cost adjustment adalah sebagai berikut:

Setiap Cost Adjustment, baik yang menggunakan **Attribute Set Instance (ASI)** maupun yang tidak menggunakan ASI, akan menghasilkan satu record pada tabel **Transaction (M_Transaction)**. Nilai yang dicatat pada Transaction diambil dari jurnal akuntansi yang terbentuk saat Cost Adjustment diproses.

Jika **Current Cost Price** lebih kecil daripada **New Cost Price**, berarti terjadi kenaikan nilai persediaan. Sistem akan menggunakan **nilai jurnal pada sisi Debit** sebagai nilai koreksi. Apabila jurnal yang terbentuk merupakan **Debit pada akun Asset (Persediaan)**, maka **Movement Type** pada Transaction akan diisi **I+ (Inventory In)** sebagai penanda adanya penambahan nilai persediaan.

Jika **Current Cost Price** lebih besar daripada **New Cost Price**, berarti terjadi penurunan nilai persediaan. Sistem akan menggunakan **nilai jurnal pada sisi Kredit** sebagai nilai koreksi. Apabila jurnal yang terbentuk merupakan **Kredit pada akun Asset (Persediaan)**, maka **Movement Type** pada Transaction akan diisi **I- (Inventory Out)** sebagai penanda adanya pengurangan nilai persediaan.


Nilai jurnal yang digunakan sebagai dasar koreksi (baik dari sisi Debit maupun Kredit) akan disimpan pada kolom **Correction Amount** di Transaction.

Informasi **Organization**, **Product**, dan **Attribute Set Instance (ASI)** pada Transaction akan mengikuti data yang terdapat pada dokumen **Cost Adjustment**. Karena Cost Adjustment hanya mengubah **nilai (cost)** dan tidak mengubah **jumlah stok**, maka **Movement Quantity** akan selalu diisi **0**.

Kolom **Physical Inventory Line** pada Transaction akan diisi menggunakan **Inventory Line** yang berasal dari **Cost Adjustment Line**, sehingga transaksi tetap memiliki referensi ke dokumen sumbernya.

Kolom **Locator** pada Transaction bersifat wajib (mandatory). Oleh karena itu, sistem akan menggunakan **Locator In Transit** yang telah dikonfigurasi pada **Document Type** Cost Adjustment sebagai nilai locator transaksi.

|Kondisi|Nilai yang Digunakan|Movement Type|
|---|---|---|
|Current Cost Price < New Cost Price|Nilai jurnal Debit Asset|**I+ (Inventory In)**|
|Current Cost Price > New Cost Price|Nilai jurnal Kredit Asset|**I- (Inventory Out)**|

> **Catatan:** Transaction yang dibuat dari Cost Adjustment hanya berfungsi sebagai pencatatan perubahan **nilai persediaan (cost)**. Transaksi ini **tidak memengaruhi kuantitas stok**, sehingga **Movement Quantity** selalu bernilai **0**.
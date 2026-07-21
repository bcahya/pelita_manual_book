# Cost Adjustment

Cost Adjustment adalah proses penyesuaian nilai valuasi produk atau barang yang sudah tercatat di sistem. Penyesuaian ini dilakukan karena:

- Perbedaan harga
- Kesalahan pencatatan sebelumnya

Cost Adjustment tidak melakukan revaluasi terhadap transaksi historis. Sistem hanya menggunakan nilai cost baru untuk transaksi berjalan dan transaksi berikutnya.
## Ketentuan Costing Method

Costing Method tidak dapat diubah setelah digunakan dalam transaksi. Pembatasan ini bertujuan untuk:

- Menjaga konsistensi data.
- Menjaga integritas transaksi.
- Menghindari ketidaksesuaian laporan costing.

Jika perusahaan perlu menggunakan costing method yang berbeda, buat product atau artikel baru dan arahkan ke Product Category yang sesuai.
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

Cost Adjustment dapat digunakan untuk melakukan revaluasi HPP pada produk di level **Batch/Lot**. Langkah-langkahnya sama dengan proses Cost Adjustment di atas, namun pada field **Attribute Set Instance**, input ASI atas produk yang akan diproses.

Sistem menghitung harga rata-rata berdasarkan harga beli produk terakhir pada masing-masing Batch atau Lot, sehingga akurasi nilai persediaan per Batch atau Lot tetap terjaga.

Hasil revaluasi dapat dicek di master produk melalui tab **Cost**. Setelah Cost Adjustment selesai, **Average PO** akan muncul pada produk tersebut dengan nilai **Current Cost Price** sesuai harga saat Cost Adjustment diproses.

## Mekanisme Cost Adjustment di Sistem

Setiap Cost Adjustment — baik yang menggunakan **ASI** maupun tidak — menghasilkan satu record pada tabel **Transaction (M_Transaction)**. Nilai yang dicatat pada Transaction diambil dari jurnal akuntansi yang terbentuk saat Cost Adjustment diproses.

Berikut ketentuan Movement Type berdasarkan kondisi harga:

|Kondisi|Nilai yang Digunakan|Movement Type|
|---|---|---|
|Current Cost Price < New Cost Price|Nilai jurnal Debit Asset|**I+ (Inventory In)**|
|Current Cost Price > New Cost Price|Nilai jurnal Kredit Asset|**I- (Inventory Out)**|

Ketentuan tambahan pada Transaction:

- **Organization**, **Product**, dan **ASI** mengikuti data pada dokumen Cost Adjustment.
- **Movement Quantity** selalu bernilai **0** karena Cost Adjustment hanya mengubah nilai (_cost_), bukan jumlah stok.
- **Physical Inventory Line** pada Transaction diisi menggunakan **Inventory Line** dari Cost Adjustment Line, sehingga transaksi tetap memiliki referensi ke dokumen sumber.
- **Locator** pada Transaction menggunakan **Locator In Transit** yang dikonfigurasi pada Document Type Cost Adjustment, karena field ini bersifat mandatory.

Nilai jurnal yang digunakan sebagai dasar koreksi — baik dari sisi Debit maupun Kredit — disimpan pada kolom **Correction Amount** di Transaction.

> **Catatan:** Transaction yang dibuat dari Cost Adjustment hanya mencatat perubahan **nilai persediaan (_cost_)** dan **tidak mempengaruhi kuantitas stok**, sehingga **Movement Quantity** selalu bernilai **0**.
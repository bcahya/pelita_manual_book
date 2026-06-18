# Purchase Order

Purchase order adalah dokumen yang digunakan untuk mencatat dan mengelola proses pemesanan barang atau jasa kepada supplier. Dokumen ini berisi informasi mengenai supplier, produk yang dipesan, jumlah, harga, tanggal pemesanan, metode pembayaran, serta informasi pendukung lainnya.

Di dalam sistem iDempiere, Purchase Order berfungsi sebagai dasar untuk proses pengadaan barang, mulai dari pembuatan pesanan hingga penerimaan barang dan proses penagihan (Invoice). Dengan menggunakan Purchase Order, perusahaan dapat memastikan bahwa seluruh transaksi pembelian terdokumentasi dengan baik dan sesuai dengan proses bisnis yang telah ditetapkan.
## Alur Proses Purchase Order

1. Buka menu **Purchase Order**
2. Input **Business Partner**
3. Input **warehouse** untuk penempatan produk
4. Masuk ke tab **PO Line**
5. Pilih **product** yang akan diproses
6. Input **qty** product
7. Klik **save**
8. Klik **complete** dokumen
## Pengelolaan Purchase Order
### Perubahan Business Partner pada Purchase Order

Apabila terdapat kesalahan dalam pemilihan **Business Partner (Supplier)**, perubahan Business Partner tidak dilakukan secara langsung pada dokumen Purchase Order, melainkan melalui menu **SIS Change BP PO**.

Melalui menu tersebut, user dapat memilih dokumen Purchase Order yang akan diubah beserta Business Partner penggantinya. Ikuti langkah berikut untuk melakukan perubahan Business Partner:
1. Buka menu Purchase Order
2. Pilih dokumen yang akan dilakukan perubahan
3. Klik ikon **Setting** (⚙), kemudian klik **SIS Change BP PO**. 
4. Input **Business Partner** terupdate
5. Klik **ok**

Setelah proses berhasil, informasi Business Partner pada dokumen Purchase Order akan diperbarui secara otomatis.

**Catatan:** Perubahan Business Partner hanya dapat dilakukan pada Purchase Order yang masih berstatus **Draft**.
### Perubahan Warehouse pada Purchase Order

Apabila terdapat perubahan tujuan gudang (Warehouse) pada Purchase Order, perubahan dilakukan melalui menu **SIS Change Warehouse Order**.

Setelah proses perubahan selesai, sistem akan memperbarui informasi Warehouse pada Purchase Order dan mencatat detail perubahan tersebut pada tab **Listing PO Warehouse** sebagai referensi riwayat perubahan Warehouse. Ikuti langkah berikut untuk melakukan perubahan Warehouse:
1. Buka menu Purchase Order
2. Pilih dokumen yang akan dilakukan perubahan
3. Klik ikon **Setting** (⚙), kemudian klik **SIS Change Warehouse Order** 
4. Input **Warehouse** terupdate
5. Klik **ok**

**Catatan:** Perubahan Warehouse hanya dapat dilakukan pada Purchase Order yang masih berstatus **Draft**.
### Menutup Purchase Order

Purchase Order yang telah berstatus **Complete** dapat ditutup (**Close**) apabila proses pembelian telah selesai atau tidak akan dilakukan transaksi lanjutan terhadap dokumen tersebut. Proses penutupan dilakukan melalui menu **SIS Close Document PO**.

Setelah Purchase Order berstatus **Closed**, dokumen tidak dapat digunakan untuk proses transaksi lanjutan dan dianggap telah selesai sesuai dengan proses bisnis yang berlaku.

> **Catatan:** Proses **Close** hanya dapat dilakukan pada Purchase Order yang telah berstatus **Complete**.
### Menghapus Purchase Order

Purchase Order dapat dihapus apabila dokumen tidak lagi diperlukan, misalnya karena:

- Terjadi kesalahan input data.
- Purchase Order dibuat secara tidak sengaja (duplicate).
- Transaksi dibatalkan sebelum diproses lebih lanjut.
- Alasan operasional lainnya sesuai kebijakan perusahaan.

Proses penghapusan dilakukan melalui menu **SIS Delete Document PO**.

> **Catatan:** Hanya Purchase Order dengan status **Draft** yang dapat dihapus menggunakan menu ini.
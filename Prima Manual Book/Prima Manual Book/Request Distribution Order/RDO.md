# Request Distribution Order 

Request Distribution Order (RDO) adalah instrumen pengendalian distribusi yang digunakan untuk memonitor, mengalokasikan, dan mendistribusikan barang **non-produksi** ke warehouse tujuan secara terstruktur dan dapat ditelusuri.

## Konfigurasi Request Distribution Order (RDO)

Sebelum proses RDO dijalankan, pastikan konfigurasi berikut sudah diselesaikan:
1. Warehouse dan Locator tujuan sudah didefinisikan dengan jelas.
2. Document Type untuk delivery, receipt dan cancel delivery sudah dikonfigurasi agar sistem dapat mencatat pergerakan barang secara akurat.
3. Produk yang akan didistribusikan sudah diinput melalui menu **Product Access** menggunakan fitur **Generate Product**.
4. Field **Organization** wajib diisi pada seluruh transaksi operasional untuk menjaga integritas data. 

## Konfigurasi Sistem

1. Buka menu **System Configurator**.
2. Klik **New**.
3. Isi field **Name** dengan **SIS_RDO_Cancel_Delivery_DocType_ID**.
4. Isi field **Configured Value** dengan **Doc Type ID** yang akan digunakan sesuai kebijakan perusahaan.

![sys](../Screenshot_2026-08-18_173456.png "Konfigurasi Cancel Delivery RDO") {#Figure246}

5. Pilih **Configuration Level** = **Client**.
6. Klik **save**.
## Konfigurasi Document Type RDO

Pada konfigurasi Document Type RDO, terdapat beberapa field utama yang wajib diisi:

| Field                        | Keterangan                                                                                                                                                                                                                                                       |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Document type delivery       | Digunakan untuk mencatat barang keluar dari warehouse asal                                                                                                                                                                                                       |
| Document type receipt        | Digunakan untuk mencatat penerimaan barang di warehouse tujuan                                                                                                                                                                                                   |
| Document type pembatalan RDO | Document type untuk mencatat pembatalan transaksi RDO                                                                                                                                                                                                            |
| Product Access               | Apabila **Di-Centang** maka transaksi akan difilterberdasarkan produk sesuai konfigurasi                                                                                                                                                                         |
| Check SubBrand Capacity      | Apabila **Di-Centang**, sistem akan memeriksa kapasitas locator sebelum melakukan complete RDO. Jika kapasitas masih mencukupi, sistem mengizinkan transaksi diproses. Jika kapasitas terlampaui, sistem menolak transaksi dan menampilkan error **Over Capacity |
| RDO Type                     | ada 2 tipe yaitu outlet dan pusat.                                                                                                                                                                                                                               |
| Multi Warehouse Tujuan       | Apabila di-centang, maka warehouse tujuan dalam satu RDO bisa lebih dari satu. Jika tidak maka warehouse tujuan hanya bisa satu.                                                                                                                                 |
"Konfigurasi RDO"{#Tabel4}
## Alur Proses Request Distribution Order di Sistem

1. Lakukan assign produk melalui fitur **Generate Product** pada menu **Product Access**.
2. Buka menu **SIS RDO**


	![RDO](../RDO_1.png "RDO") {#Figure30}


	
3. Jalankan proses **Generate RDO Line** untuk menampilkan daftar produk yang sudah dikonfigurasi.

4. Pilih produk yang akan didistribusikan sesuai kebutuhan.


	![Generate RDO](../Generate_RDO_Line.png "Generate RDO Line") {#Figure31}




5. Validasi **quantity** distribusi.
6. Tentukan **Warehouse dan Locator Tujuan**.
7. Klik **Complete Document** untuk menyelesaikan proses RDO.

Setelah dokumen di-complete, sistem akan otomatis membuat dokumen:

- Inventory Move Delivery
- Inventory Move Receipt, sesuai konfigurasi di document type.

Kedua dokumen tersebut akan terbentuk dalam status **Draft** dan perlu diproses lebih lanjut sesuai alur operasional.
## Back Order Pada RDO

Jika quantity distribusi yang diproses lebih kecil dari quantity permintaan, sistem akan otomatis membuat Back Order untuk sisa quantity yang belum terpenuhi.

Dengan mekanisme ini, proses distribusi tetap dapat dilanjutkan tanpa harus membuat dokumen baru secara manual.

## Mekanisme Pembatalan RDO

Transaksi RDO hanya dapat dibatalkan jika dokumen **Receipt (penerimaan)** belum di-complete. Jika dokumen Receipt sudah di-complete, RDO tidak dapat dibatalkan.

Ikuti langkah berikut untuk membatalkan transaksi RDO:

1. Buka menu **SIS RDO**.
2. Pilih dokumen yang akan diproses.
3. Klik **Document Action Void**.

Berikut ketentuan pembatalan berdasarkan status dokumen Delivery:

- **Jika dokumen Delivery sudah di-complete** — Sistem otomatis membuat dokumen Movement pembalik atas Delivery tersebut dengan status complete.

![pembalik](../doc_pembalik.png "Document Movement Pembalik") {#Figure246}

- **Jika dokumen Delivery belum di-complete** — Status dokumen Receipt yang sebelumnya _In Progress_ otomatis ter-_void_.

![recipt](../receipt.png "Document Receipt Void") {#Figure247}

## Generate Multi Movement Tujuan

Saat melakukan RDO, warehouse tujuan untuk setiap produk dapat berbeda-beda. Untuk mengakomodasi kondisi ini, sistem mendukung **RDO dengan multi warehouse tujuan**.

RDO menggunakan mekanisme **intransit** — sebelum dipindahkan ke warehouse tujuan, sistem terlebih dahulu memindahkan produk dari gudang asal ke warehouse intransit.

Untuk RDO dengan multi warehouse tujuan, sistem membuat **satu dokumen Inventory Move Delivery** yang memuat seluruh produk yang diproses di RDO Line.

Ikuti langkah berikut untuk memproses RDO dengan multi warehouse tujuan:

1. Buka menu **SIS RDO**.
2. Tentukan **warehouse** dan **locator** asal.
3. Klik **Generate RDO Line**.
4. Tentukan **produk** dan **quantity** yang akan diproses.
5. Klik **SIS Generate RDO Line**.
6. Masuk ke tab **Line**.
7. Tentukan **warehouse** dan **locator** tujuan untuk produk yang akan diproses.

![wh](../rdo_line.png "Penentuan Warehouse Tujuan") {#Figure306}

8. Klik **Save**.
9. Ulangi langkah 7–8 untuk produk lainnya.
10. Klik **Complete**.

Saat RDO di-complete, sistem otomatis membuat dokumen **Inventory Move Delivery** dan **Inventory Move Receipt** (sesuai konfigurasi di document type). 

![deliv](../deli_rdo.png "Inventory Move Delivery") {#Figure307}

![receipt](../receipt_rdo.png "Inventory Move Receipt") {#Figure308}

Dokumen Inventory Move Receipt yang ter-create dikonsolidasikan berdasarkan **warehouse tujuan** — jika beberapa produk dalam satu RDO memiliki warehouse tujuan yang sama, sistem menggabungkannya dalam satu dokumen. Dengan demikian, jumlah dokumen Inventory Move yang terbentuk sesuai dengan jumlah warehouse tujuan yang berbeda pada RDO Line.

## Mekanisme Inventory Move Receipt

Pada mekanisme RDO sebelumnya, saat RDO di-complete sistem otomatis membuat dokumen **Inventory Move Delivery** dan **Receipt**. Saat ini telah dilakukan penyesuaian — penerimaan (_receipt_) dapat dilakukan secara manual, sehingga saat RDO di-complete sistem **tidak lagi** otomatis membuat Inventory Move Receipt.

Untuk mengakomodasi hal ini, terdapat tambahan konfigurasi pada **Document Type RDO** melalui field **Auto Create Receipt Movement Doc**:

- **Auto Create Receipt Movement Doc = Y** — Saat RDO di-complete, sistem otomatis membuat Inventory Move Delivery dan Receipt.
- **Auto Create Receipt Movement Doc = N** — Saat RDO di-complete, sistem hanya membuat Inventory Move Delivery. Inventory Move Receipt dibuat secara manual.

### Langkah Membuat Inventory Move Receipt Manual

Ikuti langkah berikut untuk membuat Inventory Move Receipt secara manual yang mereferensikan Inventory Move Delivery:

1. Buka menu **Inventory Move**.
2. Klik **New**.
3. Tentukan **Document Type**.
4. Input dokumen **Inventory Move Delivery** pada field **Movement Reference**.
5. Informasi RDO otomatis tersalin ke Inventory Move Receipt.
6. Field **Warehouse From** terisi otomatis sesuai warehouse tujuan dari Inventory Move Delivery.
7. Field **Warehouse To** terisi otomatis.
8. Klik **Generated Movement Line**.
9. Klik **OK**.

Sistem otomatis menyalin Move Line dari Inventory Move Delivery, dengan **Locator tujuan** sesuai RDO Line.

10. Verifikasi **produk**, **quantity**, serta **Locator** asal dan tujuan.
11. Klik **Save**.
12. Klik **Complete** pada dokumen.

Untuk memproses Inventory Move Receipt dari Generate RDO, user dapat memproses Inventory Move seperti mekanisme sebelumnya — seluruh informasi pada Inventory Move bersumber dari RDO dan RDO Line.
## RDO Sub Brand

Pada proses Inventory Move, terdapat kebutuhan untuk mendistribusikan produk berdasarkan kategori **Sub Brand** tanpa perlu menentukan produk satu per satu. Setiap produk sudah memiliki kategori Sub Brand yang telah diidentifikasi oleh perusahaan, sehingga user cukup menentukan Sub Brand yang akan diproses.

### Mekanisme RDO Sub Brand

1. Buka menu **SIS RDO**.
2. Tentukan **Document Type**.
3. Tentukan **Warehouse** dan **Locator** asal.
4. Tentukan **Sub Brand**.
5. Klik **Save**.
6. Masuk ke tab **RDO Line**.
7. Tentukan **quantity** yang akan diproses.
8. Tentukan **Warehouse** dan **Locator** tujuan.
9. Klik **Save**.
10. Klik **Complete** pada dokumen.

Saat RDO di-complete, sistem otomatis membuat **Inventory Move Delivery** dengan mekanisme intransit — warehouse dan locator tujuan dari pengiriman adalah **intransit**.

Karena distribusi dilakukan berdasarkan kategori Sub Brand, user menginput produk satu per satu melalui **scan barcode**. Ikuti langkah berikut:

1. Buka menu **Inventory Move**.
2. Tentukan dokumen **Inventory Move** yang ter-create dari RDO.
3. Pada field **Product Value**, lakukan scan barcode atau input manual kode produk.
4. Tentukan **Qty Barcode**.
5. Klik **Enter**.

Setelah Enter diklik, sistem otomatis membuat **Move Line** dengan ketentuan berikut:

- **Locator asal dan tujuan** — sesuai konfigurasi header (_intransit_).
- **Quantity** — sesuai Qty Barcode yang diinput.

6. Verifikasi **produk** dan **quantity** yang diproses.
7. Klik **Save**.
8. Klik **Complete** pada dokumen.

> **Catatan:** Quantity yang diproses tidak boleh melebihi quantity yang dikonfigurasi di RDO Line. Jika melebihi, Inventory Move Delivery tidak dapat di-complete.

### Langkah Inventory Move Receipt (Penerimaan) Manual — RDO Sub Brand

Setelah Inventory Move Delivery selesai diproses, lakukan penerimaan secara manual:

1. Buka menu **Inventory Move**.
2. Klik **New**.
3. Tentukan **Document Type**.
4. Input dokumen **Inventory Move Delivery** sebelumnya pada field **Movement Source/Target**.
5. Informasi RDO otomatis tersalin ke Inventory Move Receipt.
6. Field **Warehouse From** terisi otomatis sesuai warehouse tujuan dari Inventory Move Delivery.
7. Field **Warehouse To** terisi otomatis sesuai warehouse saat user login.
8. Klik **Generated Movement Line**.
9. Klik **OK**.

Sistem otomatis menyalin Move Line dari Inventory Move Delivery, dengan **Locator tujuan** sesuai RDO Line.

10. Verifikasi **produk**, **quantity**, serta **Locator** asal dan tujuan.
11. Klik **Save**.
12. Klik **Complete** pada dokumen.

> **Catatan:** Jika penerimaan RDO dilakukan sebagian, sistem akan mengurangi Qty Delivered dengan jumlah yang telah diterima sebelumnya saat user melakukan penerimaan berikutnya.

## Penerimaan dengan Mempertimbangkan Kapasitas Locator

Setiap locator memiliki kapasitas untuk menampung product. User dapat mengatur kapasitas dan allowance (batas tambahan kapasitas) pada masing-masing locator melalui menu **SIS Subbrand Capacity** yang dijelaskan pada bab Routing.

Konfigurasi kapasitas dan allowance membantu user mengontrol penerimaan barang agar tidak melebihi kapasitas locator.

### Konfigurasi Check SubBrand Capacity

Setelah menentukan kapasitas dan allowance, user perlu melakukan konfigurasi pada **Document Type Inventory Move Receipt** melalui field **Check SubBrand Capacity**.

- **Check SubBrand Capacity = Yes** — Sistem memeriksa kapasitas locator tujuan sebelum memproses Inventory Move Receipt. Jika kapasitas masih mencukupi, sistem mengizinkan transaksi diproses. Jika kapasitas terlampaui, sistem menolak transaksi dan menampilkan error **Over Capacity**.
- **Check SubBrand Capacity = No** — Sistem tidak memeriksa kapasitas locator tujuan saat memproses Inventory Move Receipt.

Konfigurasi kapasitas ini hanya berlaku untuk product yang memiliki **Subbrand**. Product yang tidak menggunakan Subbrand tidak mengikuti pemeriksaan kapasitas berdasarkan konfigurasi tersebut.

## Tipe RDO

Mekanisme RDO dibedakan menjadi dua tipe: **RDO Pusat** dan **RDO Outlet**. Perbedaan utamanya terletak pada fungsi warehouse di header:

- **RDO Pusat** — Warehouse di header berfungsi sebagai **Warehouse From** (asal).
- **RDO Outlet** — Warehouse di header berfungsi sebagai **Warehouse To** (tujuan).

Tipe RDO dikonfigurasi di Document Type RDO.
### Konfigurasi Document Type RDO

1. Buka menu **Document Type**.
2. Pada field **Document Base Type**, pilih **SIS RDO**.
3. Pada field **RDO. Document Type Delivery**, tentukan document type Delivery.
4. Pada field **RDO. Document Type Receipt**, tentukan document type Receipt.
5. Tentukan **RDO Type**.

![rdo](../tipe_rdo.png "RDO Type") {#Figure380}

6. Klik **Save**.
### RDO Pusat

RDO Pusat memiliki dua mekanisme: **multi warehouse tujuan** dan **satu warehouse tujuan**.
#### Konfigurasi Multi Warehouse Tujuan

1. Buka menu **Document Type**.
2. Pada field **Document Base Type**, pilih **SIS RDO**.
3. Pada field **RDO. Document Type Delivery**, tentukan document type Delivery.
4. Pada field **RDO. Document Type Receipt**, tentukan document type Receipt.
5. Tentukan **RDO Type**.
6. Pada field **Multi Warehouse To**:
- **Dicentang** — Warehouse To dapat ditentukan lebih dari satu.
- **Tidak dicentang** — Warehouse To ditentukan di header pada field **Warehouse To**.

![rdo](../multi_wh_to.png "Konfigurasi Multi Warehouse Tujuan") {#Figure381}

7. Klik **Save**.

#### Proses RDO Pusat dengan Multi Warehouse Tujuan

Pada mekanisme ini, user menentukan warehouse tujuan di RDO Line untuk masing-masing produk.

1. Buka menu **SIS RDO**.
2. Tentukan **Document Type** — pastikan RDO Type adalah **Pusat**.
3. Tentukan **Warehouse** dan **Locator** asal.
4. Klik **Generate RDO Line**.
5. Tentukan **produk** dan **quantity** yang akan diproses.
6. Klik **SIS Generate RDO Line**.
7. Masuk ke tab **Line**.
8. Tentukan **Warehouse** dan **Locator** tujuan untuk produk yang akan diproses.

![rdo](../rdo_wh_multi.png "RDO Pusat dengan Multi Warehouse Tujuan") {#Figure382}

9. Klik **Save**.
10. Ulangi langkah 8–9 untuk produk lainnya.
11. Klik **Complete**.

Saat RDO di-complete, sistem otomatis membuat dokumen **Inventory Move Delivery** dan **Inventory Move Receipt** (jika dikonfigurasi auto receipt).
#### Proses Inventory Move Delivery

1. Buka menu **SIS RDO**.
2. Tentukan RDO yang sudah diproses sebelumnya.
3. Masuk ke tab **Delivery**.
4. Klik **Inventory Move** yang ter-create.
5. Pada menu Inventory Move, verifikasi informasi di header.
6. Masuk ke **Move Line**.
7. Verifikasi dan tentukan **quantity** produk yang akan diproses.
8. Klik **Save**.
9. Klik **Complete** pada dokumen.

#### Proses Inventory Move Receipt Manual

Setelah Delivery selesai, lakukan penerimaan ke warehouse tujuan:

1. Buka menu **Inventory Move**.
2. Klik **New**.
3. Tentukan **Document Type**.
4. Input dokumen **Inventory Move Delivery** sebelumnya pada field **Movement Source/Target**.
5. Informasi RDO otomatis tersalin ke Inventory Move Receipt.
6. Field **Warehouse From** terisi otomatis sesuai warehouse tujuan dari Inventory Move Delivery.
7. Field **Warehouse To** terisi otomatis sesuai warehouse tujuan.
8. Klik **Generated Movement Line**.
9. Klik **OK**.

Sistem otomatis menyalin Move Line dari Inventory Move Delivery, dengan **Locator tujuan** sesuai RDO Line.

10. Verifikasi **produk**, **quantity**, serta **Locator** asal dan tujuan.
11. Klik **Save**.
12. Klik **Complete** pada dokumen.

#### Proses RDO Pusat dengan Satu Warehouse Tujuan

1. Buka menu **SIS RDO**.
2. Tentukan **Document Type** — pastikan RDO Type adalah **Pusat**.
3. Tentukan **Warehouse** dan **Locator** asal.
4. Tentukan **Warehouse To** dan **Locator To**.

![rdo](../rdo_wh_1.png "RDO Pusat dengan Satu Warehouse Tujuan") {#Figure383}

5. Klik **Generate RDO Line**.
6. Tentukan **produk** dan **quantity** yang akan diproses.
7. Klik **SIS Generate RDO Line**.
8. Masuk ke tab **Line**.
9. Verifikasi **produk** dan **quantity** yang akan diproses.
10. Klik **Save**.
11. Klik **Complete** pada dokumen.

Proses Inventory Move Delivery dan Receipt sama seperti sebelumnya. Inventory Move Receipt dapat dibuat otomatis atau manual sesuai konfigurasi di Document Type RDO.

### RDO Outlet

Pada RDO Outlet, Warehouse From dapat multi, sedangkan Warehouse To hanya satu. Artinya, beberapa gudang bahan dapat mengirimkan produk ke satu outlet atau showroom. Karena warehouse asal dapat berbeda untuk setiap produk, lakukan konfigurasi rute pada setiap produk — sistem mengambil informasi Warehouse From dari rute tersebut.
#### Konfigurasi Master Rute

1. Buka menu **SIS Route**.
2. Klik **New**.
3. Isi **Search Key** dan **Name** untuk rute.
4. Tentukan **Warehouse Asal**.

![rute](../rute_head.png "Rute") {#Figure328}

5. Masuk ke tab **Route Line**.
6. Tentukan **Warehouse Tujuan**.

![rute](../rute_line.png "Rute") {#Figure329}

7. Klik **Save**.

#### Konfigurasi Rute pada Product

1. Buka menu **Product**.
2. Tentukan **product** yang akan dikonfigurasi.
3. Masuk ke tab **Product Route**.
4. Tentukan **rute** untuk product tersebut.

![rdo](../rute_product.png "Konfigurasi Rute di Product") {#Figure384}

5. Klik **Save**.

#### Proses RDO Outlet

1. Buka menu **SIS RDO**.
2. Tentukan **Document Type** — pastikan RDO Type adalah **Outlet**.
3. Tentukan **Warehouse** dan **Locator** tujuan.

![rdo](../rdo_outlet.png "Warehouse Tujuan RDO Outlet") {#Figure385}

4. Klik **Generate RDO Line**.
5. Tentukan **produk** dan **quantity** yang akan diproses.
6. Klik **SIS Generate RDO Line**.
7. Masuk ke tab **Line**.
8. Verifikasi **produk** dan **quantity** yang akan diproses.
9. **Warehouse** dan **Locator From** terisi otomatis sesuai warehouse asal pada rute.
10. **Warehouse** dan **Locator To** terisi otomatis sesuai warehouse tujuan di header.

![rdo](../rdo_ot_2.png "RDO Line atas RDO Outlet") {#Figure386}

11. Klik **Save**.
12. Klik **Complete** pada dokumen.

Saat RDO di-complete, sistem otomatis membuat dokumen **Inventory Move Delivery** dan **Inventory Move Receipt** (jika dikonfigurasi auto receipt). Proses Inventory Move Delivery dan Receipt sama seperti sebelumnya, dan Receipt dapat dibuat otomatis atau manual sesuai konfigurasi di Document Type RDO.


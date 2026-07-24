# Report

Terdapat tiga kelompok report utama: **Purchase Order (PO)**, **Material Receipt (MR)**, dan **BG/DP Vendor**. Setiap report memiliki template cetak (_print format_) tersendiri yang disesuaikan dengan kebutuhan proses bisnis masing-masing tim.

Pengelompokan report ini bertujuan agar dokumen yang dihasilkan sesuai dengan format dan informasi yang relevan per tim, sekaligus mempermudah proses approval, pencetakan, dan pengarsipan dokumen.
## Report Purchase Order (PO)

Report PO digunakan untuk mencetak dokumen Purchase Order yang telah dibuat di sistem. Report ini dibedakan menjadi dua template sesuai tim pengguna — **tim SCI** dan **tim PPG** — karena kedua tim memiliki jenis kebutuhan pembelian dan format dokumen yang berbeda.
### Purchase Order (PO) tim SCI

#### PO ATK

Pembelian Alat Tulis Kantor untuk kebutuhan administrasi dan operasional kantor.

![po atk](../po_atk_sci.png "PO ATK SCI") {#Figure136}
#### PO Bahan Mentah

Pembelian bahan baku yang digunakan sebagai input proses produksi.

![PO Bahan mentah](../po_bahan_mentah_sci.png "PO Bahan Mentah") {#Figure136}
#### PO Barang Jadi

Pembelian barang jadi dari vendor/pihak ketiga, baik untuk dijual kembali maupun melengkapi kebutuhan produk akhir.

![barang jadi](../po_barang_jadi_sci.png "PO Barang Jadi") {#Figure137}
#### PO Belanja Outlet

Pembelian kebutuhan operasional outlet/toko, misalnya perlengkapan display dan kebutuhan harian outlet.

![belanja outlet](../po_belanja_outlet_sci.png "PO Belanja Outlet") {#Figure138}
#### PO Biaya

Pembelian yang bersifat jasa atau biaya non-barang, misalnya jasa service, sewa, dan biaya operasional lainnya.

![biaya](../po_biaya_sci.png "PO Biaya") {#Figure139}
#### PO Inventaris

Pembelian aset atau inventaris kantor/pabrik seperti peralatan kerja dan perlengkapan tetap.

![inventaris](../po_inventaris_sci.png "PO Inventaris") {#Figure140}
#### PO Barang Kemas

Pembelian bahan/material kemasan (_packaging_) untuk pengemasan produk.

![kemas](../po_kemas_sci.png "PO Kemas") {#Figure141}
#### PO Perlengkapan

Pembelian perlengkapan penunjang operasional di luar kategori ATK dan inventaris.

![perlengkapan](../po_perlengkapan_sci.png "PO Perlengkapan") {#Figure142}
### Purchase Order (PO) tim PPG

#### PO ATK

Pembelian Alat Tulis Kantor untuk kebutuhan administrasi tim PPG.

![atk ppg](../po_atk_ppg.png "PO ATK PPG") {#Figure143}
#### PO Aksesoris

Pembelian aksesoris produksi garment seperti kancing, resleting, label, dan material pelengkap lainnya.

![aksesoris](../po_aksesoris_ppg.png "PO Aksesoris") {#Figure144}
#### PO Inventaris

Pembelian aset atau inventaris yang digunakan pada area produksi PPG.

![inventaris](../po_inventaris_ppg.png "PO Inventaris") {#Figure145}
#### PO Kendaraan

Pembelian yang berkaitan dengan kendaraan operasional, misalnya suku cadang, bahan bakar, dan perawatan kendaraan.

![kendaraan](../po_kendaraan_ppg.png "PO Kendaraan") {#Figure145}
#### PO Knitting

Pembelian bahan baku, benang, atau suku cadang mesin untuk kebutuhan proses knitting.

![knit](../po_knit_ppg.png "PO Knitting") {#Figure146}
#### PO Umum

Pembelian kebutuhan umum PPG yang tidak termasuk dalam kategori khusus lainnya.

![umum](../po_umum_ppg.png "PO Umum") {#Figure146}
#### PO Woven

Pembelian bahan baku atau material untuk kebutuhan proses woven. 

![woven](../po_woven_ppg.png "PO Woven") {#Figure147}
## Report Material Receipt (MR/BPB)

Report MR digunakan untuk mencetak dokumen permintaan material yang diajukan secara internal oleh divisi produksi ke bagian gudang/persediaan. Permintaan ini diproses lebih lanjut menjadi Purchase Order jika stok tidak mencukupi, atau dipenuhi langsung dari stok gudang. Klasifikasi report MR adalah sebagai berikut:
### MR Aksesoris

Permintaan material aksesoris produksi seperti kancing, resleting, dan label.

![aksesoris](../mr_aksesoris.png "MR Aksesoris") {#Figure148}
### MR Knitting

Permintaan material/bahan baku untuk kebutuhan proses produksi knitting.

![knit](../mr_knit.png "MR Knitting") {#Figure149}
### MR Woven

Permintaan material/bahan baku untuk kebutuhan proses produksi woven. 

![woven](../mr_woven.png "MR Woven") {#Figure150}
### MR Sisa Cutting

Pencatatan penggunaan sisa hasil cutting (kain/material sisa potong) untuk dimanfaatkan kembali dalam proses produksi.

![sisa cutting](../mr_sisa_cut.png "MR Sisa Cutting") {#Figure151}
### MR FID

Permintaan material terkait proses/divisi FID sesuai klasifikasi internal perusahaan.

![FID](../mr_fid.png "MR FID") {#Figure151}
### MR FB

Permintaan material terkait proses/divisi FB sesuai klasifikasi internal perusahaan.

![FB](../mr_fb.png "MR FB") {#Figure152}
## Report BG (DP Vendor)

Report BG digunakan untuk mencetak dokumen uang muka (_Down Payment_/DP) yang diberikan kepada vendor sebagai bagian dari proses pembayaran atas Purchase Order. Report ini terdiri dari dua jenis template:
### DP Vendor BG

Digunakan untuk mencetak dokumen DP kepada satu vendor (Business Partner) dalam satu dokumen transaksi.

![satu vendor](../dp_bg.png "DP Vendor BG") {#Figure153}
### DP Vendor BG Multi BP

Digunakan untuk mencetak dokumen DP yang mencakup lebih dari satu vendor dalam satu dokumen transaksi, misalnya pada pembayaran DP gabungan.

![multi](../dp_multi_bg.png "DP Vendor BG Multi BP") {#Figure154}

## Report Print Journal Status

**Print Journal Status** adalah laporan yang menampilkan status pencatatan (_posting_) jurnal akuntansi dari seluruh dokumen transaksi. Report ini membantu tim Finance memantau apakah transaksi sudah berhasil diposting ke General Ledger (GL) atau masih terdapat dokumen yang gagal diposting.
### Fungsi Print Journal Status

- **Memantau status posting jurnal** — Mengetahui apakah dokumen sudah berhasil diposting (_Posted = Yes_) atau belum (_Posted = No_).
- **Mendeteksi kegagalan posting** — Mengidentifikasi dokumen yang gagal diposting akibat kesalahan konfigurasi, seperti akun belum tersedia, periode sudah tutup, atau costing belum terbentuk, sehingga dapat segera ditindaklanjuti.
- **Rekonsiliasi transaksi dengan General Ledger** — Memastikan seluruh transaksi operasional telah menghasilkan jurnal di GL dan membantu proses _closing_ bulanan agar tidak ada transaksi yang terlewat.
### Langkah Akses Report Print Journal Status

1. Buka menu **SIS Export Print Journal Status**.
2. Input parameter berikut sesuai kebutuhan:
- **Date Acct** — Tanggal akuntansi.
- **Posted** — Pilih jika ingin menampilkan jurnal yang sudah ter-posting.
- **Posting Error** — Pilih jika ingin menampilkan jurnal yang gagal diposting.
- **Processing** — Status proses dokumen.

![parameter](../parameter_print_jurnal.png "Parameter") {#Figure161}

3. Klik **Start**.

Sistem menampilkan pop-up hasil export dalam format **Excel**. Klik dokumen tersebut untuk mengunduhnya.

> Jika hanya **Date Acct** yang diisi, sistem menampilkan seluruh jurnal — baik yang sudah ter-posting maupun yang belum — pada hasil export.

#### Informasi yang Ditampilkan pada Hasil Export


![export](../export_jurnal.png "Hasil Export Format Excel") {#Figure162}

| Informasi         | Keterangan                                                       |
| ----------------- | ---------------------------------------------------------------- |
| **Document No**   | Nomor dokumen transaksi                                          |
| **Table**         | Tabel asal transaksi (Invoice, Order, Inventory, Movement, dll.) |
| **Date Account**  | Tanggal akuntansi                                                |
| **Posted**        | Status posting jurnal                                            |
| **Processing**    | Status proses dokumen                                            |
## Laporan Crosscheck Ayat Silang

Laporan Crosscheck Ayat Silang digunakan untuk memverifikasi keseimbangan jurnal akuntansi di iDempiere. Laporan ini memastikan setiap transaksi yang telah diposting ke **General Ledger (GL)** membentuk pasangan ayat jurnal (debet dan kredit) yang benar dan seimbang.

### Fungsi Laporan Kros Cek Ayat Silang

- Memastikan setiap jurnal memiliki total **debet = kredit**.
- Memverifikasi bahwa posting transaksi dari modul operasional (Purchase, Sales, Inventory, Asset, Production, Payment, dan lain-lain) telah menghasilkan jurnal sesuai konfigurasi accounting.
- Membantu proses rekonsiliasi sebelum penutupan periode (_Period Closing_).
- Memudahkan auditor atau tim Finance menelusuri asal jurnal jika ditemukan selisih atau ketidaksesuaian.

### Langkah Akses Laporan Cross Check Ayat Silang

1. Buka menu **SIS Laporan Kros Cek Ayat Silang**.
2. Input parameter berikut sesuai kebutuhan:
- **Process Detail Report** — Report yang akan diproses.
- **Tenant** — Tenant yang akan dilakukan pengecekan.
- **Account** — Akun yang akan dicek.
- **Transaction Date** — Tanggal transaksi.

![parameter](../parameter_ayat_silang.png "Parameter Laporan Cross Check Ayat Silang") {#Figure166}

3. Klik start

![report](../laporan_ayat_silang.png "Laporan Ayat Silang") {#Figure167}

Sistem menampilkan informasi berikut pada laporan:

- Tanggal transaksi
- Saldo awal
- Nomor dokumen
- Jenis dokumen
- Nilai debet
- Nilai kredit
- Organization

Laporan Crosscheck Ayat Silang adalah laporan kontrol akuntansi yang memverifikasi hubungan antar akun dalam jurnal, memastikan keseimbangan debet dan kredit, serta membantu analisis asal-usul transaksi sehingga proses rekonsiliasi dan audit dapat dilakukan lebih cepat dan akurat.
## Report Invoice Vendor

Report Invoice Vendor digunakan untuk menampilkan daftar dokumen Invoice Vendor (_Accounts Payable Invoice_) yang telah dibuat di iDempiere. Gunakan report ini untuk memantau transaksi tagihan dari vendor serta memudahkan proses rekonsiliasi dengan Purchase Order, Material Receipt, maupun pembayaran.

Report Invoice Vendor dibagi menjadi dua jenis berdasarkan tipe transaksi:
### Invoice Vendor Lain-Lain

Report ini menampilkan seluruh transaksi invoice pembelian dari vendor yang menambah nilai kewajiban perusahaan kepada vendor (_Accounts Payable_). Ikuti langkah berikut untuk mengaksesnya:

1. Buka menu **Purchase Invoice and Credit/Debit Note**.
2. Klik tombol **Setting (⚙)**.
3. Klik **Print Invoice Lain-Lain**.
4. Klik **OK**.

![vendor](../invoice_vendor_lain-lain.png "Invoice Vendor Lain-Lain") {#Figure167}
### Invoice Vendor Credit Note Lain-Lain

Report ini menampilkan transaksi Credit Note Vendor — dokumen yang digunakan untuk mengurangi nilai tagihan vendor akibat kondisi tertentu, seperti:

- Retur barang kepada vendor.
- Koreksi harga pembelian.
- Koreksi kuantitas.
- Pembatalan sebagian nilai invoice.
- Pemberian potongan (_allowance_) dari vendor.

Ikuti langkah berikut untuk mencetak Invoice Vendor Credit Note Lain-Lain:

1. Buka menu **Purchase Invoice and Credit/Debit Note**.
2. Klik tombol **Setting (⚙)**.
3. Klik **Print Invoice Credit Note**.
4. Klik **OK**.

## Report Invoice Buyer

Report Invoice Buyer digunakan untuk menampilkan seluruh transaksi Invoice Penjualan (_Accounts Receivable Invoice_) yang dibuat kepada buyer atau pelanggan. Gunakan report ini untuk memantau transaksi penjualan yang telah ditagihkan, baik berupa invoice penjualan maupun credit note.

Report Invoice Buyer dibagi menjadi dua jenis:
### Invoice Buyer Lain-Lain

Report ini digunakan untuk mencatat tagihan atas transaksi non-reguler, seperti penjualan jasa, biaya administrasi, penggantian biaya (_reimbursement_), atau transaksi lain yang memerlukan penagihan kepada buyer tanpa melalui proses Sales Order.

Ikuti langkah berikut untuk mengaksesnya:

1. Buka menu **Purchase Invoice and Credit/Debit Note**.
2. Klik tombol **Setting (⚙)**.
3. Klik **SIS Printout Invoice Buyer Lain-Lain**.
4. Klik **OK**.

### Invoice Buyer Credit Note

Report ini menampilkan transaksi Credit Note yang diterbitkan kepada buyer — dokumen yang digunakan untuk mengurangi nilai piutang kepada buyer akibat adanya koreksi transaksi.

Ikuti langkah berikut untuk mencetak Invoice Buyer Credit Note:

1. Buka menu **Purchase Invoice and Credit/Debit Note**.
2. Klik tombol **Setting (⚙)**.
3. Klik **SIS Printout Invoice Credit Note Buyer Lain-Lain**.
4. Klik **OK**.

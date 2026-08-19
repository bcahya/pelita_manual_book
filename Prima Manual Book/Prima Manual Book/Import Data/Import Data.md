# Import Data

Import Data adalah proses memasukkan data dari sumber eksternal seperti file CSV atau Excel ke dalam sistem iDempiere. Tujuan utama import data meliputi:
- Migrasi data — memindahkan data dari sistem lama ke iDempiere
- Input massal — memasukkan ratusan/ribuan record sekaligus tanpa input manual satu per satu
- Efisiensi — menghemat waktu dibandingkan proses entry manual

## FileZilla

FileZilla adalah aplikasi transfer file open source yang digunakan untuk memindahkan file antara komputer lokal dan server melalui jaringan internet atau jaringan lokal. Dalam konteks iDempiere, FileZilla digunakan untuk mengupload file Excel atau CSV dari PC ke folder di server iDempiere.

### Langkah Instalasi & Koneksi FileZilla:

**Langkah 1: Install FileZilla**

1. Download dari [https://filezilla-project.org/](https://filezilla-project.org/)
2. Install Filezilla dan buka aplikasi

**Langkah 2: Menghubungkan ke server FTP**

1. Klik menu Manajemen Situs
2. Klik New Site dan beri nama contoh “Prima-Dev”
3. Input konfigurasi koneksi sebagai berikut:
  - Protocol : SFTP – SSH File Transfer Protocol
  - Host : 76.13.18.16
  - Port : (sesuai kebijakan)
  - Logon : Normal
  - User : (sesuai kebijakan)
  - Password : (sesuai kebijakan)

![Setup FileZilla](../Setup_Filezilla.png "Setup FileZilla") {#Figure81}

4. Klik Connect untuk menghubungkan ke server.

## Import Data MT940

MT940 adalah format standar SWIFT (Society for Worldwide Interbank Financial Telecommunication) untuk rekening koran elektronik (_electronic bank statement_). File MT940 memuat informasi transaksi perbankan — mencakup saldo awal, daftar debit/kredit, dan saldo akhir — yang dikirimkan bank kepada nasabah korporat. Di iDempiere, MT940 digunakan dalam modul **Bank Statement**.

Format MT940 umumnya menggunakan encoding **UTF-8**. Namun, sistem iDempiere saat ini juga mendukung format MT940 dengan encoding **ISO-8859-1**. Berikut contoh format file yang digunakan untuk import data Bank Statement.

    
   ![Format Bank Statement](../Format_MT940.png "Format MT940") {#Figure91}

Langkah Import File MT940:
1. Siapkan file MT940 dari bank. File MT940 menggunakan format **TXT**.
2. Konfigurasi Bank Account di iDempiere:
  - Masuk ke Bank/Cash → Account → Account No

  ![Bank Account](../Account_No.png "Account Number") {#Figure82}

  - Pastikan nomor rekening **cocok** dengan field :**25**: di file MT940
  - Set Currency sesuai (IDR untuk rupiah)

3. Import melalui FileZilla
  - Navigasi ke /home/dev-idempiere/MT940 → Import Bank Statement
  - Pilih file MT940 yang akan diimport

![Import Data MT940](../Import_MT940.png "Import Data MT940") {#Figure83}

4. Jika import berhasil, file otomatis berpindah ke folder **done**

![Done Import Data MT940](../Import_Bank_Done.png "Done Import Data MT940") {#Figure87}

5. Dokumen **Bank Statement** akan menampilkan bank tersebut sebagai pilihan pada field **Bank Account**.

![Bank Statement](../Deliver_Bank.png "Bank Statement") {#Figure88}

## Import Data PO Kecil

Sebelum melakukan import, pastikan nama file sesuai format yang ditentukan, yaitu: organisasi, value product/search key pada product, dan tahun bulan transaksi. Berikut contoh format file yang digunakan untuk import data PO Kecil.

   ![Format PO](../Format-POKecil.png "Format PO Kecil") {#Figure90}


Langkah Import File PO Kecil:
1. Siapkan file PO Kecil dalam format csv
2. Import melalui FileZilla
  - Navigasi ke /home/dev-idempiere/po_import → Import PO Kecil
  - Pilih file PO Kecil yang akan diimport

![Import Data PO Kecil](../Import_PO.png "Import Data PO Kecil") {#Figure84}

4. Jika import berhasil, file otomatis berpindah ke folder **done**

![Done Import PO](../PO_Done.png "Done Import PO") {#Figure89}

5. Sistem iDempiere akan membuat dokumen PO dengan status Draft atau In Progress, yang selanjutnya dapat di-confirm sesuai kebutuhan operasional.

![Purchase Order](../Hasil_Import_PO.png "Hasil Import Purchase Order") {#Figure90}

Jika file PO Kecil yang diimport tidak sesuai format, sistem tidak akan memproses file tersebut ke iDempiere. Contoh ketidaksesuaian format yang umum terjadi antara lain penggunaan delimiter **;** atau penggunaan **Product ID** pada nama file yang seharusnya menggunakan **Product Value**.

Saat import gagal, file tidak berpindah ke folder **done**. Sistem otomatis membuat folder **error** pada direktori PO Import, yang berisi file txt dengan informasi detail penyebab kegagalan import.

![Error](../Error.png "Log Error File Import") {#Figure91}

Jika file pertama belum diperbaiki dan file kedua yang diimport juga tidak sesuai format, sistem menampilkan pesan error yang sama. File akan tetap berada di folder PO Import dan tidak akan berpindah hingga kesalahan pada file diperbaiki.

## Report PO Kecil

Report PO Kecil digunakan untuk menampilkan informasi Purchase Order dengan format PO Kecil sesuai kebutuhan operasional. Report ini mengambil data dari transaksi Purchase Order beserta informasi pendukung yang telah dikonfigurasi. Report PO Kecil memuat informasi **Regional** dan **Area** yang digunakan untuk mengelompokkan PO berdasarkan lokasi atau wilayah outlet/warehouse tujuan.

### Mekanisme Konfigurasi Regional dan Area

Informasi Regional dan Area pada Report PO Kecil mengikuti konfigurasi **SIS Regional** dan **Sales Region**. SIS Regional menentukan struktur wilayah yang digunakan perusahaan, sedangkan Sales Region berfungsi sebagai pengelompokan wilayah yang ditampilkan pada report.

#### Konfigurasi Regional

1. Buka menu **SIS Regional**.
2. Tentukan Regional yang digunakan, misalnya:
- Jakarta
- Jawa Barat

![region](../sis_regional.png "Regional") {#Figure255}

3. Masuk ke tab **Sales Region**.
4. Tentukan **Search Key** dan **Name** dari region, contoh: Jakarta Pusat, Jakarta Utara, dan sebagainya.

![sr](../sales_region.png "Sales Region") {#Figure256}

5. Klik **Save**.

#### Konfigurasi Sales Region pada Warehouse

1. Buka menu **Warehouse and Locators**.
2. Tentukan warehouse yang akan dikonfigurasi.
3. Pada field **Sales Region**, tentukan Sales Region untuk masing-masing Warehouse/Outlet.

![wh](../wh_sales_region.png "Konfigurasi Sales Region di Warehouse") {#Figure257}

4. Klik **Save**.

Setiap Warehouse/Outlet akan terhubung dengan Regional melalui Sales Region yang telah dikonfigurasi. Saat PO Kecil dibuat dengan Warehouse/Outlet tujuan tertentu, sistem mengambil Sales Region dari master Warehouse tersebut untuk menentukan **Regional** dan **Area** yang ditampilkan pada Report PO Kecil.
### Langkah Proses Report PO Kecil

1. Buka menu **Print Report PO Kecil**.
2. Tentukan **periode** yang akan diproses.
3. Klik **OK**.

![po kecil](../print_report_po_kecil.png "Report Rekapitulasi PO Kecil") {#Figure258}
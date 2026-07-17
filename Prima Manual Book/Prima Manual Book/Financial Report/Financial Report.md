# Financial Report

**Financial Report** digunakan untuk menghasilkan laporan keuangan berdasarkan transaksi akuntansi yang telah diposting (posted). Laporan yang dapat dihasilkan antara lain:

- **Balance Sheet (Neraca)**, untuk menampilkan posisi aset, kewajiban, dan ekuitas.
- **Profit & Loss (Laba Rugi)**, untuk menampilkan pendapatan, beban, serta laba atau rugi pada periode tertentu.

## Konfigurasi Financial Report

Sebelum membuat laporan keuangan, lakukan konfigurasi pada parameter berikut:

|Parameter|Keterangan|
|---|---|
|**Accounting Schema**|Pilih skema akuntansi yang digunakan sebagai dasar penyusunan laporan.|
|**Calendar**|Pilih kalender akuntansi sesuai tenant.|
|**Report Line Set**|Menentukan struktur baris laporan beserta sumber data yang digunakan.|
|**Report Column Set**|Menentukan informasi dan periode yang ditampilkan pada setiap kolom laporan.|
|**Exclude Adjustment Period**|Centang jika transaksi pada periode penyesuaian tidak ingin disertakan dalam laporan.|
|**List Sources**|Centang untuk menampilkan rincian akun (Chart of Accounts) yang menjadi sumber setiap baris laporan.|

## Konfigurasi Report Line Set

**Report Line Set** digunakan untuk menyusun struktur laporan dan menentukan sumber data pada setiap baris.
### Line Type

Pilih jenis baris sesuai kebutuhan:

|Line Type|Fungsi|
|---|---|
|**Segment Value**|Mengambil nilai langsung dari akun pada Chart of Accounts.|
|**Calculation**|Menghasilkan nilai berdasarkan perhitungan dari baris lain dalam laporan.|

### Calculation Type

Jika menggunakan **Calculation**, pilih metode perhitungan berikut:

|Calculation|Fungsi|
|---|---|
|**Add**|Menjumlahkan nilai dari beberapa baris.|
|**Add Range**|Menjumlahkan nilai dalam rentang baris tertentu.|
|**Subtract**|Mengurangi nilai antarbaris.|
|**Percentage**|Menghitung persentase berdasarkan operand yang ditentukan.|

### Parameter Lain

|Parameter|Keterangan|
|---|---|
|**Posting Type**|Pilih **Actual** untuk mengambil transaksi yang telah diposting.|
|**Amount Type**|Pilih **Balance (Expected Sign)** agar saldo ditampilkan sesuai karakteristik akun (debit atau kredit).|
|**Report Source**|Tentukan akun yang digunakan sebagai sumber data. Jika baris hanya berfungsi sebagai judul atau heading, parameter ini dapat dikosongkan.|

## Konfigurasi Report Column Set

**Report Column Set** digunakan untuk menentukan informasi dan periode yang ditampilkan pada kolom laporan.

### Relative Period

Digunakan untuk mengambil data berdasarkan periode relatif terhadap periode laporan yang dipilih.

### Period Type

Pilih jenis periode sesuai kebutuhan pelaporan.

|Period Type|Keterangan|
|---|---|
|**Natural**|Menampilkan data sejak awal tahun fiskal hingga periode laporan.|
|**Period**|Menampilkan data hanya pada periode yang dipilih.|
|**Total**|Menampilkan akumulasi seluruh data hingga periode laporan.|
|**Year**|Menampilkan data dalam satu tahun fiskal.|

## Laporan Gabungan Outlet

Financial Report dapat menampilkan data gabungan dari beberapa outlet menggunakan struktur organisasi (**Tree**).

Langkah konfigurasi:

1. Buka menu **Tree Management**.
2. Buat **Cost Center** yang akan digunakan sebagai kelompok outlet.
3. Aktifkan opsi **Summary** pada Cost Center tersebut.
4. Tambahkan seluruh outlet yang akan digabungkan sebagai **child** dari Cost Center tersebut.

Setelah konfigurasi selesai, pilih Cost Center tersebut sebagai organisasi saat menjalankan Financial Report.
## Membuat Financial Report

Setelah seluruh konfigurasi selesai, buat laporan keuangan dengan langkah berikut:

1. Buka menu **Create Financial Report**.
2. Pilih **Accounting Schema**.
3. Pilih **Calendar** dan **Periode** laporan.
4. Pilih **Report Line Set**.
5. Pilih **Report Column Set**.
6. Tentukan **Organization** yang akan ditampilkan.
7. Atur parameter tambahan sesuai kebutuhan, seperti **Exclude Adjustment Period** atau **List Sources**.
8. Klik ok.

Sistem akan menghasilkan Financial Report sesuai konfigurasi yang telah ditentukan. Laporan yang dihasilkan dapat berupa **Balance Sheet (Neraca)** atau **Profit & Loss (Laba Rugi)**, bergantung pada **Report Line Set** yang dipilih.
# Asset Management

## Asset Movement

Asset Movement adalah proses perpindahan aset dari satu lokasi ke lokasi tujuan untuk aktivasi aset. Setelah aset dipindahkan ke locator tujuan, status aset berubah menjadi aktif. Perpindahan aset ditentukan berdasarkan **ASI (Attribute Set Instance)**.

Sebelum melakukan perpindahan aset, konfigurasi warehouse tujuan terlebih dahulu dengan menetapkannya sebagai warehouse untuk depresiasi. Ikuti langkah berikut:

1. Buka menu **Warehouse & Locator**.
2. Centang field **Depreciate**.
3. Klik **Save**.

Setelah field Depreciate dicentang, aset akan otomatis aktif saat dipindahkan ke warehouse tersebut.

Ikuti langkah berikut untuk melakukan perpindahan aset:
1. Buka menu **Inventory Move**
2. Tentukan **warehouse** asal dan **warehouse** tujuan
3. Masuk ke tab **Move Line**
4. Tentukan **locator** asal dan **locator** tujuan
5. Masuk ke tab **Attribute**
6. Tentukan **Attribute Set Instance** (ASI) atas aset yang akan dipindahkan
7. Klik **save**
8. Klik **complete** pada dokumen movement

Di belakang layar, saat movement di-complete, sistem otomatis meng-complete dokumen aset atas ASI tersebut. Depresiasi dimulai H+1 bulan dari penerimaan aset dan berjalan secara otomatis sesuai scheduler yang telah dikonfigurasi. Locator pada dokumen aset juga terisi otomatis sesuai locator Movement, dan dokumen aset teraktivasi secara otomatis.
## Asset Addition

Asset Addition adalah proses penambahan nilai pada aset yang telah ada, akibat investasi lanjutan, peningkatan kapasitas, perbaikan mayor (major overhaul), renovasi, revaluasi, atau kapitalisasi biaya.

Ikuti langkah berikut untuk melakukan Asset Addition:
1. Buka menu **SIS Asset Addition**.
2. Klik **New**.
3. Input field-field pada header.
4. Pada field **Asset Addition Type**, pilih **Addition**.
5. Masuk ke tab **Line**.
6. Input **nomor dokumen aset** yang akan diproses.
7. Input **Addition Amount** yang akan diproses.
8. Klik **Save**.
9. Klik **Complete** pada dokumen.

Setelah dokumen Asset Addition di-complete, sistem otomatis mengkalkulasi ulang **Gross Value** dan **Residual Value** aset dengan menambahkan Addition Amount. Nilai depresiasi juga ikut menyesuaikan dengan Gross Value yang baru.
## Asset Transfer

Asset Transfer adalah proses pengalihan nilai antar aset. Fitur ini digunakan untuk menggabungkan beberapa aset yang sebelumnya dicatat secara terpisah menjadi satu **aset induk (parent asset)**, guna memudahkan pengelolaan.

Ikuti langkah berikut untuk melakukan Asset Transfer:

1. Buka menu **SIS Asset Addition**.
2. Klik **New**.
3. Input field-field pada header.
4. Pada field **Asset Addition Type**, pilih **Transfer**.
5. Masuk ke tab **Line**.
6. Pada field **Asset From**, input nomor dokumen aset asal (aset yang akan digabungkan).
7. Pada field **Asset To**, input nomor dokumen aset tujuan (aset induk).
8. Field **Addition Amount** terisi otomatis dengan nilai sisa (_Residual Value_) dari aset asal.
9. Klik **Save**.
10. Klik **Complete** pada dokumen.

Setelah dokumen Asset Transfer di-complete, **Residual Value** aset tujuan terkalkulasi dengan nilai dari aset asal, sedangkan **Residual Value** aset asal menjadi 0 karena nilainya telah digabungkan ke aset tujuan. Depresiasi dilanjutkan sesuai masa manfaat ekonomi pada aset tujuan.
## Asset Depreciation

Asset Depreciation adalah proses pencatatan penurunan nilai ekonomis aset tetap secara sistematis selama masa manfaatnya, sesuai kebijakan akuntansi perusahaan dan standar pelaporan keuangan yang berlaku. Periode atau masa manfaat aset dikonfigurasi di **Asset Type**.

Saat aset dipindahkan ke warehouse atau outlet tujuan, dokumen aset otomatis di-complete dan proses depresiasi langsung berjalan. Jurnal untuk periode pertama depresiasi juga ter-complete secara otomatis. Sistem menggunakan **tanggal penerimaan barang** saat dokumen penerimaan di-complete sebagai _start date_ depresiasi.

Konfigurasi **auto complete aset** dan **auto complete jurnal** dapat dilakukan di **Asset Type**. Jika keduanya dikonfigurasi, depresiasi langsung berjalan tanpa perlu tindakan manual.

Ikuti langkah berikut untuk mengecek depresiasi aset:
1. Buka menu **SIS Asset**
2. Pilih asset yang akan diproses
3. Pada tab **Line**, periksa **Depreciation Date** dan nilai depresiasi aset selama masa manfaatnya.

Depresiasi berjalan secara otomatis sesuai scheduler yang telah dikonfigurasi.
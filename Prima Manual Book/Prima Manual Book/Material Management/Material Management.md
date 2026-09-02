# Material Management
## Stock Opname

Stock Opname — atau dikenal sebagai **Physical Inventory** di iDempiere — adalah fitur untuk merekonsiliasi stok fisik di gudang dengan stok yang tercatat di sistem. Jika terdapat selisih antara quantity fisik dan quantity di sistem (_book_), selisih tersebut diproses sebagai penyesuaian.
### Langkah Proses Stock Opname

1. Buka menu **Physical Inventory**.
2. Klik **New**.
3. Input field pada header:
- **Warehouse** — Lokasi inventory yang akan diproses.
- **Movement Date** — Tanggal dilakukan perhitungan stok. 
- **Cost Center** — Dimensi tambahan untuk financial report.
4. Klik **Create Inventory Count List** — Sistem otomatis men-generate line dari daftar inventory di warehouse yang dipilih, dengan filter berikut:
- Locator — Lokasi dari warehouse yang diproses.
- Product Category — Kategori produk yang akan diproses.
- Inventory Qty — **Not 0** = hanya produk yang memiliki stok di locator
5. Klik **SIS Generate Inventory Charge Amount** — Menghitung biaya charging jika terdapat selisih minus.
6. Masuk ke **Inventory Count Line**, kemudian input field berikut:
- **Locator** — Lokasi dari warehouse yang diproses.
- **Product** — Produk yang akan diproses.
- **Qty Count** — Jumlah quantity fisik hasil perhitungan aktual.
- **Inventory Type** — Tipe charging untuk biaya yang dicatat.
- **Attribute** — ASI pada produk _(jika ada)_.
- **Charge** — Menentukan biaya yang akan dicatat atas selisih (plus atau minus).
7. Klik **Complete** pada dokumen Physical Inventory.

> **Catatan:** Jika ASI tidak diinput saat memproses Physical Inventory, sistem mengkalkulasi quantity berdasarkan artikel tanpa spesifikasi ke ASI atau batch/lot.

### Konfigurasi Sistem

SIS_INVENTORY_EXT_URL dan SIS_INVENTORY_CHARGE5_URL merupakan konfigurasi URL yang digunakan untuk menghubungkan iDempiere dengan tools atau informasi yang tersedia pada server klien. Konfigurasi ini digunakan untuk mendukung proses Stock Opname, khususnya dalam mengakses informasi atau fungsi tambahan yang diperlukan selama transaksi Stock Opname.

- SIS_INVENTORY_EXT_URL adalah URL untuk mengakses tools atau informasi eksternal yang digunakan dalam proses Stock Opname.
- SIS_INVENTORY_CHARGE5_URL adalah URL untuk mengakses tools atau informasi yang digunakan pada proses Stock Opname dengan Charge Type 5.
## Adjustment Plus dan Minus

Untuk mencatat penggunaan persediaan atau melakukan adjustment plus/minus tanpa melalui proses penjualan, gunakan fitur **Inventory Decrease/Increase**.
### Konfigurasi Document Type

Penentuan adjustment plus atau minus dikonfigurasi di level **Document Type**, sehingga adjustment plus dan minus menggunakan document type yang berbeda.

1. Buka menu **Document Type**.
2. Cari dokumen **Inventory Decrease/Increase**.
3. Pada field **Adjustment Type**, tentukan jenis adjustment yang digunakan untuk dokumen tersebut:
- - **Adjustment Negatif** — Dokumen khusus untuk adjustment negatif. Saat diproses, Internal Use Qty bernilai positif dan sistem **menambah** stok.
- **Adjustment Positif** — Dokumen khusus untuk adjustment positif. Saat diproses, Internal Use Qty bernilai negatif dan sistem **mengurangi** stok.

![adjustment](../iu_adj_charge.png "Adjustment Type") {#Figure161}

4. Pada field **Charge**, input charge atas transaksi jika charge sudah ditentukan. Jika tidak, user dapat memilih charge secara manual saat transaksi.
5. Klik **Save**.
### Langkah Proses Inventory Decrease/Increase

1. Buka menu **Inventory Decrease/Increase**.
2. Input field pada header:
- **Warehouse** — Tentukan warehouse inventory yang akan diproses.
- **Movement Date** — Tanggal adjustment dilakukan.
- **Document Type** — Tipe dokumen yang digunakan.
- **Cost Center** — Dimensi tambahan untuk financial report.
3. Masuk ke **Internal Use Line**, kemudian input field berikut:
- **Locator** — Lokasi inventory yang akan diproses.
- **Product** — Artikel yang akan diproses.
- **Qty** — Quantity produk yang akan di-adjust.
- **Attribute Set Instance** — Nomor ASI yang akan diproses _(jika ada)_.
4. Klik **Save**.
5. Klik **Complete** pada dokumen Inventory Decrease/Increase.

### Ketentuan Adjustment

- **Adjustment Positif** — Menunjukkan adanya kelebihan stok yang harus dikurangi dari sistem. Sistem otomatis **mengurangi** stok produk.
- **Adjustment Negatif** — Menunjukkan adanya kekurangan stok yang harus ditambahkan ke sistem. Sistem otomatis **menambah** stok produk.

Setelah dokumen di-complete, sistem otomatis mengkalkulasi ulang quantity produk sesuai konfigurasi dan membentuk jurnal atas penyesuaian tersebut. Nilai jurnal mengikuti cost pada artikel.
## Report Internal Use

Ikuti langkah berikut untuk mengakses report Internal Use (_Inventory Decrease/Increase_):

1. Buka menu **Inventory Decrease/Increase**.
2. Klik tombol **Setting (⚙)**.
3. Klik **Print Document Internal Use**.
4. Klik **OK**.

![inv](../IU_Inventory.png "Internal Use Inventory"){#Figure268}

![scrap](../IU_Scarp.png "Internal Use Scrap Pabrik") {#Figure269}

## Product Auto Internal Use

Beberapa product yang dipindahkan ke warehouse atau gudang tertentu akan otomatis membentuk **Internal Use**. Karena jumlah product yang memerlukan konfigurasi ini bisa sangat banyak, konfigurasi Auto Internal Use dapat dilakukan di level **Product Category** untuk efisiensi.

Jika Auto Internal Use sudah dikonfigurasi di Product Category, seluruh product baru maupun product _existing_ yang menggunakan Product Category tersebut otomatis ter-update menjadi Auto Internal Use. Setelah konfigurasi tersalin ke product, user perlu melakukan konfigurasi **Charge Internal Use** untuk setiap product secara individual.

![pc](../auto_iu_pc.png "Konfigurasi di Product Category") {#Figure278}

![product](../auto_iu_p_baru.png "Tercopy di Product Baru dan Existing") {#Figure279}

Dengan mekanisme ini, user tidak perlu mengkonfigurasi Auto Internal Use satu per satu pada setiap product.
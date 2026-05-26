Request Distribution Order (RDO) adalah instrumen pengendalian distribusi yang digunakan untuk memonitor, mengalokasikan, dan mendistribusikan barang **non-produksi** ke warehouse tujuan secara terstruktur dan dapat ditelusuri.

#### Konfigurasi Request Distribution Order (RDO)

Sebelum proses RDO dijalankan, pastikan konfigurasi berikut sudah diselesaikan:
1. Warehouse dan Locator tujuan sudah didefinisikan dengan jelas.
2. Document Type untuk delivery dan receipt sudah dikonfigurasi agar sistem dapat mencatat pergerakan barang secara akurat.
3. Produk yang akan didistribusikan sudah diinput melalui menu **Product Access** menggunakan fitur **Generate Product**.
4. Field **Organization** wajib diisi pada seluruh transaksi operasional untuk menjaga integritas data. 

#### Konfigurasi Document Type RDO

Pada konfigurasi Document Type RDO, terdapat beberapa field utama yang wajib diisi:

| Field                  | Keterangan                                                         |
| ---------------------- | ------------------------------------------------------------------ |
| Document type delivery | Digunakan untuk mencatat barang keluar dari warehouse asal         |
| Document type receipt  | Digunakan untuk mencatat penerimaan barang di warehouse tujuan     |
| Warehouse intransit    | Warehouse transit selama proses distribusi                         |
| Locator Tujuan         | Lokasi penerimaan barang                                           |
| Product Access         | **Wajib dicentang** agar filter produk berjalan sesuai konfigurasi |

#### Alur Proses Request Distribution Order di Sistem

1. Lakukan assign produk melalui fitur **Generate Product** pada menu **Product Access**.
2. Buka menu Request Distribution Order (**RDO**).
	![[Pasted image 20260526141955.png]]
	
3. Jalankan proses **Generate RDO Line** untuk menampilkan daftar produk yang sudah dikonfigurasi.
4. Pilih produk yang akan didistribusikan sesuai kebutuhan.
	![[Pasted image 20260526142032.png]]
	
5. Validasi quantity distribusi.
6. Klik **Complete Document** untuk menyelesaikan proses RDO.
Setelah dokumen di-complete, sistem akan otomatis membuat dokumen:

- Inventory Move Delivery
- Inventory Move Receipt

Kedua dokumen tersebut akan terbentuk dalam status **Draft** dan perlu diproses lebih lanjut sesuai alur operasional.

#### Back Order Pada RDO

Jika quantity distribusi yang diproses lebih kecil dari quantity permintaan, sistem akan otomatis membuat Back Order untuk sisa quantity yang belum terpenuhi.

Dengan mekanisme ini, proses distribusi tetap dapat dilanjutkan tanpa harus membuat dokumen baru secara manual.
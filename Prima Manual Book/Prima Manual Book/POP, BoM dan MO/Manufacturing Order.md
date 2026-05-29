# Manufacturing Order

Manufacturing Order adalah dokumen proses produksi untuk menghasilkan barang jadi maupun barang setengah jadi. Manufacturing Order merupakan bagian dari proses Production Order Planning (POP).

Urutan Manufacturing Order mengikuti struktur Semi Finished Goods terkecil berdasarkan hierarki BoM.
## Tab pada Manufacturing Order

1. Manufacturing Order Line
	Berisi daftar kebutuhan bahan baku yang digunakan dalam produksi.
2. Movement/Inventory Move
	Dokumen perpindahan material sebagai permintaan bahan produksi. Dokumen ini bukan surat jalan.
3. Requisition
	Dokumen permohonan pembelian material. Requisition hanya muncul jika stok material tidak mencukupi.
	Jika stok tersedia, proses dapat langsung dilanjutkan ke tahap movement.
4. Production
	Digunakan untuk menjalankan proses produksi artikel.
5. Childs
	Berisi Child Manufacturing Order yang terbentuk dari komponen Semi Finished Goods.
6. Production Report Quantity
	Digunakan untuk mencatat hasil produksi, baik produk baik maupun produk defect.
## Child Manufacturing Order

Satu Manufacturing Order dapat memiliki beberapa Child MO apabila dalam BoM terdapat komponen Semi Finished Goods.

Proses produksi tidak dapat dilanjutkan jika material pada Child Manufacturing Order belum tersedia.
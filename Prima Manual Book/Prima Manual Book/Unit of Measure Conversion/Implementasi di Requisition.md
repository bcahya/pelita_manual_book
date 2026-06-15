## Implementasi di Requisition
### Requisition

Di tahap requisition, user mengajukan kebutuhan barang. Fitur UoM Conversion memungkinkan user memasukkan permintaan dalam satuan yang lebih familiar, seperti karton atau pack. Sistem lalu otomatis mengonversi jumlah tersebut ke Base UoM (misalnya Pcs) untuk keperluan pengecekan stok dan perencanaan pengadaan.
#### Requisition Line

![Requisition Line](../UoM_Requisition.png "UoM di Requisition") {#Figure10}

UoM pada requisition line terbentuk dari konversi Base UoM. Berikut field quantity dan harga yang perlu dipahami:

1. Quantity — Menampilkan jumlah produk dalam satuan Base UoM.
2. Quantity Entered — Menampilkan jumlah produk dalam satuan UoM Conversion.
	Contoh: Base UoM adalah each dan UoM Conversion adalah pack, di mana 1 pack = 10 each. Maka Quantity Entered mencerminkan jumlah dalam satuan pack.
### Generate PO From Requisition

Setelah requisition diconfirm (complete), langkah berikutnya adalah **Generate PO From Requisition.** Proses ini menyalin data dari requisition — termasuk UoM dan quantity — ke dalam Purchase Order. Sistem kemudian menggunakan UoM yang telah dikonversi sebelumnya.

UoM yang digunakan di requisition dan purchase order sebenarnya bisa berbeda, namun  disarankan untuk **menyamakannya** demi konsistensi data. Contoh: jika requisition menggunakan satuan pack, maka purchase order sebaiknya juga menggunakan pack.

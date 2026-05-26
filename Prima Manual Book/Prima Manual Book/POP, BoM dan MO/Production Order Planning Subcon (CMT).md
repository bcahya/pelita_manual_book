Subcon atau CMT adalah ketika salah satu komponen Finished Goods diproduksi di luar perusahaan oleh vendor.

Dalam proses ini:
- Perusahaan mengirim material ke vendor
- Vendor memproduksi barang setengah jadi atau barang jadi
- Perusahaan melakukan proses pembelian hasil produksi vendor melalui:
	- Requisition
	- Purchase Order
	- Material Receipt
### Mekanisme POP Subcon

Jika Finished Goods memiliki komponen subcon, maka Manufacturing Order yang terbentuk hanya satu, yaitu untuk Finished Goods.

Namun, ketika Purchase Order untuk produk subcon selesai diproses, sistem dapat otomatis membuat POP baru untuk Semi Finished Goods yang masih diproduksi secara inhouse.

Setelah produksi Semi Finished Goods selesai dan stok tersedia di warehouse, proses produksi Finished Goods dapat dilanjutkan.

### Langkah POP Subcon di Sistem

1. Buka menu **SIS Production Order Planning**
2. Masuk ke Tab **Line**
3. Input:
	- Produk yang akan diproduksi
	- Quantity produksi
	- BoM yang digunakan
4. Jalankan proses **SIS Generate POP BoM**
	![[Pasted image 20260525161924.png]]
5. Klik **SIS Generate MO**
	![[Pasted image 20260525161938.png]]
6. Masuk ke menu **Manufacturing Order**. Setelah proses Generate MO selesai, sistem otomatis membuat dokumen berikut:
	- Back Order
	- Movement
	- Requisition
	- Production
	- Child
	- Production Report Quantity
7. Lakukan proses **Requisition** untuk material subcon. Alur proses:
	- Requisition Complete
	- Purchase Order Complete
	- Material Receipt
	Sistem akan membuat POP baru untuk Semi Finished Goods yang diproduksi secara inhouse.
	![[Pasted image 20260525162052.png]]
8. Jalankan proses produksi Semi Finished Goods hingga selesai
9. Setelah Semi Finished Goods tersedia di Warehouse, lakukan **Movement** sesuai urutan proses
10. Klik tab **Movement** dan lakukan movement sesuai urutan
11. Setelah stok tersedia, jalankan proses produksi pada tab **Production Report Quantity**:

	- Isi quantity produksi
	- Isi quantity defect, **jika ada**
	- Centang field **Defect** untuk produk defect
	
	Produk defect akan diproses movement manual ke locator sesuai konfigurasi BoM.
12. Setelah quantity ditentukan, lakukan **Complete Document MO**. Sistem akan menjalankan proses production secara otomatis dan mengkonsumsi:

	- Raw Material
	- Semi Finished Goods
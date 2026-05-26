### Manajemen Penyusutan dan Disposal Aset

Penyusutan aset adalah proses mengalokasikan biaya aset secara sistematis selama masa manfaatnya. Setiap periode, sistem mencatat beban penyusutan dan mengurangi nilai buku aset.

Sebelum melakukan penyusutan, pastikan konfigurasi berikut telah selesai:
1. Product Category — Gunakan costing method **Average PO** dan costing level **Batch/Lot**.

	![[Pasted image 20260526133825.png]]
	
2. Attribute Set — Pilih **Lot Control** dengan pengaturan berikut:
	a.	Mandatory Type: **Always**
	b.	Attribute Set Type: Material Management System
	c.	Exclude:
	-	C_OrderLine – Sales Order Line
	-	M_InOutLine – Shipment/Receipt Line
	d.	Un-check field **Sales Transaction**

	![[Pasted image 20260526133959.png]]

3. Master Data Asset Type — Tentukan klasifikasi aset, metode penyusutan, dan GL Document Type.
4. Set Product — Atur Product Type ke **Item**.
5. Attribute Set — Sesuaikan dengan kategori aset.
6. Asset Type — Sesuaikan dengan kategori aset.

#### Proses Pengadaan Aset

Pengadaan aset dilakukan melalui tahapan berikut:
1.	Purchase order
2.	Material receipt
3.	Invoice
4.	Matching invoice

Setelah proses penerimaan selesai, sistem otomatis membentuk data aset berdasarkan ASI (Attribute Set Instance). Data aset tersebut dapat diakses melalui menu SIS Aset.

#### Proses Manajemen Penyusutan Asset

Lakukan penyusutan aset melalui langkah-langkah berikut:
1. Akses menu **SIS Asset**.
	
	![[Pasted image 20260526134248.png]]
	
2. Generate aset — Data awal akan berstatus Draft.
3. Evaluasi aset — Lakukan evaluasi terhadap aset yang berstatus Draft.
4. Konfirmasi aset — Validasi aset sebelum digunakan.
5. Sistem menampilkan:
	a.	Daftar aset berdasarkan ASI
	b.	Proposal depresiasi sesuai masa manfaat aset
6. Penyusutan berjalan sesuai konfigurasi Asset Type.

Jurnal penyusutan di-generate secara otomatis, berdasarkan permintaan user atau jadwal automation scheduler yang berjalan setiap bulan.

#### Mekanisme Penyusutan Asset

Penyusutan aset bekerja dengan ketentuan berikut:
1. Dasar penyusutan menggunakan harga perolehan (harga beli).
2. Penentuan batch/lot dilakukan saat penerimaan barang.
3. Setiap penerimaan dicatat berdasarkan batch/lot dan mereferensikan dokumen pembelian terkait.
4. Penyusutan mengikuti harga Purchase Order, sedangkan nilai disposal dapat disesuaikan dengan kebutuhan bisnis.

### Disposal Aset

Disposal adalah proses penghapusan aset dari catatan perusahaan secara permanen. Disposal dilakukan ketika aset sudah tidak layak pakai, dijual, dihibahkan, atau dihancurkan. 

Disposal aset dapat dilakukan melalui dua mekanisme:

1. Sales order
	a.	Buka menu **Sales Order,** pastikan Document Type menggunakan **Standard Order**.
	b.	Pilih aset berdasarkan **ASI** yang sesuai.
		![[Pasted image 20260526134647.png]]
		
	c.	Proses Shipment, lalu buat Invoice Customer (AR).
2. Physical Inventory (Internal Use)
	a.	Buka menu **Inventory Decrease/Increase**.
	b.	Pilih Document Type **Internal Use Inventory**.
	c.	Masuk ke **Internal Use Line**.
	d.	Pilih aset yang akan didisposal berdasarkan **ASI**.
		![[Pasted image 20260526134840.png]]
		
	e.	Tentukan **Charge** sebagai beban disposal

Setelah proses disposal selesai — baik melalui Sales Order maupun Internal Use — sistem otomatis memperbarui status disposal pada data aset dan men-generate jurnal disposal.

#### Pergerakan dan Pengelolaan aset
- Perpindahan aset antar lokasi memengaruhi pencatatan penyusutan
- Penyusutan dapat disesuaikan berdasarkan lokasi atau outlet tempat aset berada.
- Aset yang belum digunakan (misalnya masih di gudang) tidak langsung disusutkan. Penyusutan baru dimulai saat aset mulai digunakan di outlet.

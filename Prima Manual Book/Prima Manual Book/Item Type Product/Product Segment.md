### Definisi Product Segment

Product Segment adalah kode identifikasi produk yang otomatis digunakan pada setiap produk baru di sistem iDempiere. Kode ini biasanya terdiri dari 2–3 karakter dan dikombinasikan dengan nomor urut produk.

**Contoh Product Segment**

| Kode Segment | Keterangan          |
| ------------ | ------------------- |
| 10           | Barang Jadi Kemeja  |
| 20           | Bahan Baku Knitting |
| 21           | Bahan Baku Woven    |

Tanpa Product Segment, sistem hanya menghasilkan nomor urut seperti 0001 atau 0002 yang tidak memberikan informasi mengenai jenis produk. Dengan Product Segment, user dapat langsung mengenali kategori produk hanya dari kode artikel yang ditampilkan.

### Manfaat Product Segment

1. Mempermudah Identifikasi Produk
	Saat jumlah produk mencapai ratusan atau ribuan item, Product Segment membantu user mengenali produk dengan cepat. User cukup melihat awalan kode untuk mengetahui apakah produk tersebut bahan baku, barang setengah jadi, atau barang jadi.
2. Menghindari Duplikasi Kode Antar Kategori
	Tanpa segment, produk dari kategori berbeda dapat memiliki nomor urut yang sama, misalnya 0001 untuk bahan baku dan 0001 untuk barang jadi. Dengan segment, setiap kode menjadi unik, seperti:

	- RM-0001
	- FG-0001
	
	Kedua kode tersebut berbeda dan tidak saling bertabrakan.
3. Mendukung Konsistensi Data
	Segment yang ditentukan sejak awal implementasi membantu seluruh tim menggunakan pola penamaan yang sama. Dengan begitu, proses pencarian data dan pembuatan laporan menjadi lebih terstruktur dan konsisten.

Dalam satu segment, sistem dapat menampung beberapa tipe sekaligus. Jika perusahaan membutuhkan pengelompokan segment berdasarkan kategori tertentu, seperti jenis artikel bahan jadi, bahan baku, gramasi, benang, brand, dan kategori lainnya, lakukan pengaturan pada Menu **Product Segment Type**.

Sistem akan mengelompokkan kode artikel sesuai kategori yang ditentukan sehingga penyusunan kode artikel menjadi lebih rapi, konsisten, dan mudah dikelola.
### Langkah Pengaturan Product Segment Type

1. Buka menu **SIS Product Segment Type**
2. Klik **New**
3. Isi Field
	- **Search Key**
	- **Name** -> Nama Segment Type
	
	![[Pasted image 20260523120403.png]]

1. Klik **Save**

Setelah pengelompokan segment berdasarkan kategori selesai dilakukan, lanjutkan konfigurasi pada menu **Product Segment**.
### Langkah Pengaturan Product Segment di Sistem

1. Buka Menu **SIS Product Segment**
2. Klik **New**
3. Isi field
	- **Search Key** -> Kode Segment
	- **Name** -> Nama Segment
	
	Contoh 10 untuk Barang Jadi dan 59 untuk Brand Polo ![[Pasted image 20260522135201.png]]
4. Klik **Save**

Setelah Product Segment selesai dikonfigurasi, langkah berikutnya adalah mengatur **Item Type**. Item Type berfungsi untuk menyusun kode artikel berdasarkan segment yang sudah dibuat.



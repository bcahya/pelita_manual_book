# Konfigurasi Sebelum Menentukan Product Varian
Sebelum membuat produk varian, lakukan tiga konfigurasi berikut:
## Master Varian Attribute

Buat Master Varian Attribute terlebih dahulu sebelum menentukan produk varian. Berikut langkah-langkah untuk membuat Varian Attribute:

1. Klik menu **SIS Varian Attribute**
2. Isi field **Name** dengan nama varian yang akan digunakan.

	![Attribute](../SIS_Varian.png "Varian Attribute") {#Figure53}


3. Buka tab **Value**, lalu masukkan nama varian dan value sesuai kebutuhan. Contoh: Size S menggunakan prefiks 01. Penentuan varian pada produk disesuaikan dengan kebutuhan operasional perusahaan.

	![Value](../Value_Varian.png "Value Varian Attribute") {#Figure54}
	
## Product Type

Setelah Master Varian Attribute selesai, konfigurasikan Product Type dengan langkah berikut:
1. Pada field **Product Type**, pilih **SIS Template** sebagai product template

	![Template](../Product_SIS_Template.png "Konfigurasi Product Type") {#Figure55}

2. Buat product template secara berurutan, mulai dari artikel terkecil: Raw Material → Semi Finished Goods → Finished Goods. Pembuatan product template tidak boleh dimulai dari Finished Goods.
3. Setelah product template selesai, tambahkan **Varian Attribute** pada product template untuk membentuk kombinasi varian. Satu produk dapat memiliki lebih dari satu Varian Attribute

	![Varian Attribute2](../Varian_Product.png "Konfigurasi Varian Attribute di Product") {#Figure56}
		
## Konfigurasi Sistem

Sistem menyediakan parameter **SIS_VARIAN_ALLOW_UPDATE** di **System Configurator** untuk menentukan data mana saja yang akan diperbarui saat Regenerate dijalankan. Berikut parameter yang perlu dikonfigurasi:

| Parameter                             | Keterangan       |
| ------------------------------------- | ---------------- |
| SIS_VARIAN_ALLOW_UPDATE_BOM           | Bill of Material |
| SIS_VARIAN_ALLOW_UPDATE_PURCHASING    | Purchasing       |
| SIS_VARIAN_ALLOW_UPDATE_REPLENISH     | Replenish        |
| SIS_VARIAN_ALLOW_UPDATE_REPLENISHRDO  | Replenish RDO    |
| SIS_VARIAN_ALLOW_UPDATE_ROUTING       | Routing          |
| SIS_VARIAN_ALLOW_UPDATE_UOMCONVERSION | UoM Conversion   |
	"System Configurator"{#Tabel4}

**Salah satu contoh Konfigurasi**

![Configurator](../SIS_Config.png "Konfigurasi Sistem") {#Figure57}

Untuk **Configured Value**, pilih salah satu:
1. Y → Data akan diperbarui secara otomatis saat proses Regenerate Product Variant dijalankan.
2. N → Data tidak akan diperbarui saat proses Regenerate dijalankan.
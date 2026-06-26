# Format Report

Satu document type dapat memiliki beberapa pilihan sub document type pada dropdown. Contoh: document type Purchase Order dapat memiliki pilihan PO General, PO Bahan Baku, PO Inventaris, PO Barang Kemas, PO Perlengkapan, dan sebagainya. Konfigurasi serupa juga dapat diterapkan pada document type lain, seperti Invoice dengan pilihan _Credit Note_, _Invoice Vendor Lain-lain, dan sebagainya.

Untuk mengatur dropdown tersebut, lakukan konfigurasi pada setiap document type yang membutuhkan.

Konfigurasi ini bertujuan untuk:

- Memisahkan penomoran dokumen.
- Menerapkan Print Format berbeda — setiap document type dapat menggunakan Print Format PDF dengan kolom, layout, atau logo yang berbeda.
- Menerapkan workflow approval berbeda — misalnya, PO Inventaris memerlukan approval lebih tinggi dibanding PO Bahan Baku.
- Memudahkan filter dan pelaporan per kategori pembelian.
## Konfigurasi Document Type

Setiap document type dapat menghasilkan report dengan pilihan yang berbeda. Oleh karena itu, tim IT harus menyiapkan file **Jasper** untuk masing-masing report. Contoh: document type **Purchase Order** dapat memiliki report **PO General** dan **PO Bahan Baku Woven**.

Untuk referensi print Jasper pada dokumen PO, gunakan dua parameter berikut:

- **Process** — Menggunakan default logic berdasarkan **AD_Process_UU**. Contoh logic yang digunakan:  `@SQL=select ad_process_id from ad_process where ad_process_uu='019e267d-2690-7322-a4a2-122489db370d'`

![Process](../Process_1.png "Parameter Process") {#Figure99}

- **Process Detail Report** — Menggunakan Dynamic Validation **SIS_ProcessDetailReport by Process DT Target Access**.

![Process Detail](../Process_Detail.png "Process Detail Report") {#Figure100}

Pastikan field **Report** pada menu **Report & Access** sudah dicentang agar report tersebut muncul di tenant dan sistem.

Ikuti langkah berikut untuk melakukan konfigurasi report print pada masing-masing document type:

1. Buka menu **Document Type** yang akan dikonfigurasi, contoh: **Purchase Order**.
2. Masuk ke tab **Report Detail Access**.
3. Klik **New**.
4. Pada field **Process**, pilih proses sesuai kebutuhan perusahaan.
5. Pada field **Process Detail Report**, input report sesuai kebutuhan perusahaan.

![Report Detail Access](../Report_Access.png "Report Detail Access") {#Figure101}

6. Klik **save**.

![Report PO](../Print_PO.png "Report PO") {#Figure102}

Ulangi langkah di atas untuk document type lain yang memerlukan konfigurasi serupa. Setelah konfigurasi selesai, sistem akan menampilkan pilihan format report tersebut saat user melakukan report pada document yang bersangkutan.
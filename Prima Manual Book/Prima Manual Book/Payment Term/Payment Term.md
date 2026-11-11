# Payment Term

**Payment Term** adalah konfigurasi yang menentukan ketentuan pembayaran antara perusahaan dan Business Partner (Customer maupun Vendor). Konfigurasi ini mengatur kapan invoice harus dibayar, lama jatuh tempo, serta kemungkinan diskon jika pembayaran dilakukan lebih awal.

Payment Term dapat digunakan pada transaksi berikut:

- **Purchase Order (PO)** — Menentukan ketentuan pembayaran kepada Vendor.
- **Sales Order (SO)** — Menentukan ketentuan pembayaran dari Customer.
- **AP Invoice** — Menentukan tanggal jatuh tempo pembayaran kepada Vendor.
- **AR Invoice** — Menentukan tanggal jatuh tempo pembayaran dari Customer.

## Membuat Master Payment Term

1. Buka menu **Payment Term**.
2. Tentukan **Search Key** dan **Name**.
3. Field **Next Business Day** — Jika dicentang, jatuh tempo yang jatuh pada hari non-kerja akan dimajukan ke hari kerja berikutnya.
4. Tentukan **Net Days**.
5. Tentukan **Discount Days** _(jika ada)_.
6. Tentukan **Discount Days 2** _(jika ada)_.
7. Tentukan **Discount %** _(jika ada)_.
8. Tentukan **Discount 2 %** _(jika ada)_.
9. Pada field **Payment Term Usage**, pilih penggunaan Payment Term: **Purchase**, **Sales**, atau **Both**.
10. Klik **Save**.

## Konfigurasi Payment Term Pada Business Partner

Setelah Payment Term dibuat, hubungkan ke Business Partner:

1. Buka menu **Business Partner**.
2. Pilih **Customer** atau **Vendor** yang akan dikonfigurasi.
3. Masuk ke tab **Customer** atau **Vendor Information**.
4. Isi field **Payment Term** sesuai ketentuan pembayaran yang disepakati.
5. Klik **Save**.

Saat membuat transaksi SO/PO atau AR/AP Invoice, Payment Term terisi otomatis berdasarkan konfigurasi Business Partner. Nilainya tetap dapat disesuaikan pada transaksi sesuai kebutuhan dan hak akses.
# Kontra Bon

Fitur Kontra Bon digunakan untuk mengelola proses pengumpulan dan verifikasi tagihan vendor/customer sebelum dilakukan pembayaran atau penagihan. Kontra Bon adalah dokumen yang membuktikan bahwa sejumlah dokumen tagihan telah diserahkan dan diverifikasi untuk diproses ke tahap pembayaran.

Kontra Bon bukan transaksi pembayaran — fungsinya adalah mengelompokkan dan mengontrol invoice yang akan dibayarkan.
## Mekanisme Kontra Bon

### Kontra Bon dengan Purchase Order

1. Buat **Purchase Order** seperti biasa.
2. Proses **Material Receipt** dari PO yang telah dibuat.
3. Proses **Invoice** dari Material Receipt yang telah diproses.
4. Buka menu **SIS Kontra Bon**.
5. Tentukan **Document Type** — pilih **Kontra Bon PO Lengkap**.
6. Tentukan **Document Date**.
7. Input nomor **PO** yang akan diproses.
8. Masuk ke tab **Line**.
9. Input nomor **MR/BPB**.
10. Tentukan **tanggal faktur pajak**.
11. Input **nomor invoice supplier**.
12. Input **nomor faktur pajak**.
13. Input **Amount Debit Note** — isi jika terdapat pengurangan nilai pada tagihan.
14. Tentukan **Charge** atas Amount Debit Note.
15. Centang field **Confirm Qty**.
16. Centang field **Confirm Total**.

![line](../kontra_line_po.png "SIS Kontra Line") {#Figure223}

17. Klik **Save**.
18. Klik **Complete** pada dokumen.

Saat dokumen Kontra Bon di-complete, sistem otomatis menyalin informasi **nomor invoice supplier** dan **nomor faktur pajak** ke invoice. Sistem juga menghitung dan menampilkan **tanggal jatuh tempo** pada invoice berdasarkan tanggal invoice dan **Term of Payment (TOP)** dari Business Partner.

![info](../invoice_awal.png "Copy Informasi") {#Figure224}

Jika terdapat debit note, sistem otomatis membentuk **Invoice Debit Note** atau **AP Invoice Credit Memo** saat dokumen Kontra Bon di-complete, dan melakukan alokasi pada invoice tersebut secara otomatis.

![cn](../ap_cn_kontra.png "AP Invoice Credit Memo") {#Figure225}

![allo](../invc_cn.png "Allocation AP Invoice Credit Memo") {#Figure226}

Berikut contoh jurnal alokasi atas Invoice Credit Memo tersebut:

![jurnal](../jurnal_all.png "Jurnal Allocation AP Invoice Credit Memo") {#Figure227}
### Kontra Bon tanpa Purchase Order

1. Buka menu **Purchase Invoice and Credit/Debit Note**.
2. Tentukan **Target Document Type**.
3. Tentukan **Business Partner**.
4. Tentukan **Price List** yang digunakan.
5. Tentukan **Payment Rule**.
6. Masuk ke **Invoice Line**.
7. Tentukan **Charge** atau biaya yang akan diproses.
8. Tentukan **Qty**.
9. Tentukan **Price** untuk tagihan tersebut.
10. Klik **Save**.
11. Klik **Complete**.
12. Buka menu **SIS Kontra Bon**.
13. Tentukan **Document Type** — pilih **Kontra Bon Non PO** atau **PO Invoice**.
14. Tentukan **Document Date**.
15. Tentukan **Business Partner**.
16. Masuk ke tab **Line**.
17. Input nomor **AP Invoice**.
18. Tentukan **tanggal faktur pajak**.
19. Input **nomor invoice supplier**.
20. Input **nomor faktur pajak**.
21. Centang field **Confirm Qty**.
22. Centang field **Confirm Total**.

![invoice](../kontra_inv.png "Kontra Bon Tanpa PO") {#Figure228}

23. Klik **Save**.
24. Klik **Complete** pada dokumen.

Saat dokumen Kontra Bon di-complete, sistem otomatis menyalin informasi **nomor invoice supplier** dan **nomor faktur pajak** ke invoice. Sistem juga menghitung dan menampilkan **tanggal jatuh tempo** pada invoice berdasarkan tanggal invoice dan **Term of Payment (TOP)** dari Business Partner.
## Pembayaran Kontra Bon

1. Buka menu **Payment and Receipt**.
2. Tentukan **Document Type**.
3. Pilih **Bank Account** yang digunakan untuk pembayaran.
4. Tentukan **Transaction Date**.
5. Pilih **Business Partner** sebagai pihak yang melakukan atau menerima pembayaran.
6. Klik tombol **Setting (⚙)**.
7. Klik **Generate Allocate Kontra Bon**.
8. Pilih **AP Invoice** yang akan diproses.

![pay](../payment_kontra.png "Payment Kontra Bon") {#Figure229}

9. Klik **Complete**.

Status invoice yang diproses berubah menjadi **Paid** dan sistem membentuk alokasi atas invoice tersebut sebesar amount yang diproses. Berikut contoh jurnal yang terbentuk atas pembayaran invoice Kontra Bon:

![jurnal](../jurnal_pay.png "Jurnal Pembayaran") {#Figure230}
# Document Type

Document Type adalah konfigurasi yang mendefinisikan perilaku sebuah dokumen transaksi — seperti Purchase Order, Sales Invoice, Payment, dan lain-lain. Setiap dokumen di iDempiere memiliki tipe, dan tipe tersebut mengontrol:

- Nomor dokumen (sequence/auto-numbering)
- Alur persetujuan (DocAction)
- Jurnal akuntansi yang dihasilkan

Di iDempiere, ada dua lapisan yang berbeda namun saling terkait erat. Document Base Type adalah lapisan **sistem** iDempiere, tidak bisa ditambah atau diubah pengguna. Document Type adalah lapisan **konfigurasi** — dibuat dan dikustomisasi oleh admin per organisasi, dan selalu "menempel" pada salah satu Document Base Type.

Berikut adalah **Document Base Type** yang sudah terdefinisi di sistem iDempiere:

| Name                        | Value |
| --------------------------- | ----- |
| AP Credit Memo              | APC   |
| AP Invoice                  | API   |
| AP Payment                  | APP   |
| AR Credit Memo              | ARC   |
| AR Invoice                  | ARI   |
| AR Pro Forma Invoice        | ARF   |
| AR Receipt                  | ARR   |
| Bank Statement              | CMB   |
| GL Document                 | GLD   |
| GL Journal                  | GLJ   |
| ICPL                        | ICP   |
| ICPL Update                 | ICU   |
| Match Invoice               | MXI   |
| Match PO                    | MXP   |
| Material Delivery           | MMS   |
| Material Movement           | MMM   |
| Material Physical Inventory | MMI   |
| Material Production         | MMP   |
| Material Receipt            | MMR   |
| Payment Allocation          | CMA   |
| Production Order Planning   | POP   |
| Project Issue               | PJI   |
| Purchase Order              | POO   |
| Purchase Requisition        | POR   |
| Sales Order                 | SOO   |
| SIS Asset                   | AST   |
| SIS Asset Addition          | AAD   |
| SIS Contract Management     | CBT   |
| SIS MPS                     | MPS   |
| SIS Price Contract          | SPC   |
| SIS RDO                     | RDO   |

## Konfigurasi Document  Type di Sistem

1. Buka menu Window, Tab and Field
2. Search Document Type yang akan dikonfigurasi
3. Masuk ke Tab
4. Masuk ke Field, kemudian search Document Base Type atau Target Document Type
5. Klik tab Column
6. Klik Dynamic Validation. Pada validation code akan tertera document base yang menempel di document type tersebut

![Konfigurasi](../Doc_System.png "Konfigurasi") {#Figure110}

7. Klik save

Ketika user membuat Document Type baru dan memilih Base Type, sistem langsung "mewarisi" sejumlah perilaku yang tidak bisa diubah dari level Document Type. Satu Base Type dapat memiliki banyak Document Type, namun satu Document Type hanya boleh memiliki satu Base Type.
## Header Document Type

Masing-masing document type memiliki header yang berbeda-beda, namun ada beberapa field yang mana field tersebut ada di semua header document type. Berikut adalah penjelasan setiap field yang terdapat pada tab header form Document Type:

1. Name — Nama Document Type yang muncul di dropdown saat user membuat dokumen transaksi. Contoh: Purchase Order, Material Movement.
2. Document Base Type — Tipe dasar dokumen yang dipilih. Wajib diisi. Menentukan logika akuntansi, alur DocAction, dan form yang digunakan. Tidak dapat diubah setelah record disimpan.
3. Sales Transaction — Menandakan jika ini transaksi ke customer (sisi AR/Sales). Biarkan unchecked untuk transaksi ke vendor (sisi AP/Purchase).
4. Default — Menjadikan Document Type ini sebagai default untuk Base Type-nya. Hanya satu yang boleh dicentang per kategori per organisasi.
5. Document Sequence — Sequence (urutan penomoran) yang digunakan untuk menghasilkan nomor dokumen otomatis. Dikonfigurasi di menu Sequence.
6. Definite Sequence — Sequence kedua yang digunakan saat dokumen berstatus Completed. Berguna jika nomor draft berbeda dengan nomor dokumen final/definitif.
7. GL Category — Kategori General Ledger yang menentukan pengelompokan jurnal di laporan GL. Harus diisi untuk Base Type yang menghasilkan posting akuntansi.
8. Document Number Controlled — Jika dicentang, nomor dokumen dikontrol penuh oleh system sequence dan tidak bisa diedit manual oleh pengguna.
9. Overwrite Sequence on Complete — Menentukan apakah nomor antrean atau nomor urut (sequence) akan dihapus/ditimpa ulang saat siklus atau batch data tersebut dinyatakan selesai
10. Overwrite Date on Complete — Mengizinkan sistem untuk mengubah tanggal awal menjadi tanggal penyelesaian yang baru secara otomatis saat statusnya berubah menjadi Complete
11. Create Counter Document — Untuk dokumen antar-organisasi (intercompany). Jika dicentang, ketika dokumen dibuat di satu organisasi, sistem otomatis membuat dokumen balasan di organisasi lain.
12. Counter Document Type — Pasangan dari field di atas, menentukan tipe dokumen yang di-generate di org lawan.
13. Document Copies — Jumlah salinan yang dicetak secara default saat dokumen ini dicetak.
14. Print Format — Format cetak default yang digunakan saat mencetak dokumen dengan tipe ini.
15. Product Access — Membatasi produk secara spesifik yang dapat diproses dalam suatu transaksi
16. Product Category Access — Membatasi produk yang dapat diproses dalam suatu transaksi berdasarkan kategori produk yang telah dikonfigurasi di level Product Category.

Pada header setiap document type juga terdapat field auto back order. Field ini berfungsi untuk memisahkan pesanan yang belum terpenuhi akibat stok kosong menjadi dokumen baru secara otomatis. Fitur ini memastikan sisa pesanan tetap tercatat dalam sistem agar dapat diproses segera setelah stok tersedia
## Setup Auto Sequence Number (Penomoran Otomatis)

Penomoran otomatis dokumen di iDempiere dikelola melalui mekanisme Sequence yang terhubung ke Document Type. Berikut langkah-langkah konfigurasinya: 
1. Buka Document Type yang akan diproses
2. Klik field Document Sequence
3. Isi field-field berikut:
  - Name — Nama sequence
  - Prefix — Awalan nomor dokumen yang muncul sebelum angka
  - Suffix — Akhiran nomor
  - Increment — Penambahan angka setiap kali nomor baru digenerate
  - Start No — Angka awal sequence. Akan increment setiap dokumen baru
  - Decimal Pattern — Format padding angka, contoh 000 akan menghasilkan 000, 001, dan seterusnya.
  - Restart sequence every year — merestart penomoran setiap tahun.
  - Restart sequence every month — merestart penomoran setiap bulan.
  - Restart sequence every day — merestart penomoran setiap hari.
  - Date Column — Input DateOrdered

![Sequence](../Sequence_Doc.png "Document Sequence") {#Figure111}

4. Field Auto Numbering dicheck
5. Klik save
## Setup Auto Generate Material Receipt

Material Receipt (MR) adalah dokumen yang mencatat penerimaan barang fisik dari vendor. MR dapat digenerate langsung dari Purchase Order yang sudah berstatus Completed. Ikuti langkah berikut untuk mengkonfigurasi auto generate material receipt saat dokumen purchase order sudah complete:

1. Buka document type Purchase Order
2. Centang field Generate MR, nanti akan muncul Document Type for MR
3. Pilih Document Type for MR sesuai kebutuhan perusahaan

![Generate](../Generate_MR.png "Generate Material Receipt") {#Figure112}

4. Klik save

Saat purchase order dicomplete maka sistem akan otomatis mengenerate material receipt yang mana dokumen tersebut nantinya akan berstatus draft. Dokumen tersebut bisa diverifikasi complete jika sudah sesuai.

## Setup Auto Invoice dari Material Receipt

Fitur Auto Invoice memungkinkan sistem membuat AP Invoice (Vendor Invoice) secara otomatis ketika Material Receipt (MR) di-Complete, tanpa memerlukan input manual dari pengguna. Berikut konfigurasi yang diperlukan:
1. Buka menu Document Type Material Receipt
2. Centang field Auto Invoice AP, field ini untuk mengontrol auto-generation invoice.
3. Kemudian akan muncul field Document Type Invoice AP, pilih document type untuk invoice tersebut
4. Pada field Document Action Invoice AP, pilih document action jika invoice tergenerate apakah dalam status draft atau complete

![Auto](../Auto_Inv.png "Auto Invoice") {#Figure113}

5. Klik save
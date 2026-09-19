# Konfigurasi Document Type

Document Type digunakan untuk mengatur bagaimana suatu transaksi diproses — termasuk penomoran dokumen, jenis transaksi, status dokumen, dan proses lanjutan yang dapat dilakukan. Setiap document type memiliki informasi header yang sama, namun beberapa field tambahan hanya muncul pada document type tertentu.
## Informasi Header di Document Type

Berikut field utama yang perlu dikonfigurasi pada Document Type:

1. **Name** — Nama Document Type yang muncul di dropdown saat user membuat dokumen transaksi.
2. **Document Base Type** — Tipe dasar dokumen. Wajib diisi. Menentukan logika akuntansi, alur DocAction, dan form yang digunakan.
3. **Sales Transaction** — Menandakan transaksi ke customer (sisi AR/Sales). Biarkan _unchecked_ untuk transaksi ke vendor (sisi AP/Purchase).
4. **Default** — Menjadikan Document Type ini sebagai default untuk Base Type-nya. Hanya satu yang boleh dicentang per kategori per organisasi.
5. **GL Category** — Kategori General Ledger untuk pengelompokan jurnal di laporan GL. Konfigurasi ini tidak mempengaruhi transaksi maupun jurnal atas transaksi yang menggunakan document type tersebut.
6. **Document Sequence** — Sequence penomoran untuk menghasilkan nomor dokumen otomatis. Dikonfigurasi di menu Document Sequence.
7. **Definite Sequence** — Sequence kedua yang digunakan saat dokumen berstatus _Completed_. Berguna jika nomor draft berbeda dengan nomor dokumen final.
8. **Document Number Controlled** — Jika dicentang, nomor dokumen dikontrol penuh oleh system sequence dan tidak dapat diedit manual.
9. **Overwrite Sequence on Complete** — Menentukan apakah sequence akan ditimpa ulang saat dokumen dinyatakan selesai.
10. **Overwrite Date on Complete** — Mengizinkan sistem mengubah tanggal transaksi menjadi tanggal penyelesaian secara otomatis saat status berubah menjadi _Complete_.
11. **Create Counter Document** — Untuk dokumen antar-organisasi (_intercompany_). Jika dicentang, sistem otomatis membuat dokumen balasan di organisasi lain.
12. **Counter Document Type** — Menentukan tipe dokumen yang di-generate di organisasi lawan.
13. **Document Copies** — Jumlah salinan yang dicetak secara default saat dokumen dicetak.
14. **Print Format** — Format cetak default yang digunakan saat mencetak dokumen.
15. **Product Access** — Membatasi produk secara spesifik yang dapat diproses dalam suatu transaksi.
16. **Product Category Access** — Membatasi produk yang dapat diproses berdasarkan kategori produk yang dikonfigurasi di level Product Category.
17. **Manual** — Menentukan apakah dokumen dapat dibuat atau diproses secara manual oleh user.
## Document Type Purchase Order

Field yang perlu dikonfigurasi:

1. **Allow Product Without Price List** — Jika dicentang, document type mengizinkan transaksi dengan produk yang tidak memiliki price list.
2. **PO Expense** — Menandakan document type digunakan untuk PO dengan product type _Expense_. Hanya produk bertipe Expense yang dapat diproses.
3. **PO/SO. Generate MR/Shipment** — Saat PO di-complete, sistem otomatis men-generate MR/BPB.
4. **PO/SO. Document Type for MR/Shipment** — Menentukan document type MR/BPB hasil generate.
5. **PO/SO. Document Action For MR/Shipment** — Menentukan status dokumen atas MR/BPB yang di-generate.
6. **Document Type Adjustment SC** — Menentukan document type atas Cost Adjustment untuk PO hasil CMT yang saat MR/BPB akan auto Internal Use.
7. **Tax Rate Access** — Membatasi tax rate yang muncul di transaksi Purchase Order sesuai konfigurasi.

## Document Type Material Receipt

Field yang perlu dikonfigurasi:

1. **MR/Shipment. Auto Invoice AP/AR** — Saat MR di-complete, sistem otomatis men-generate AP Invoice.
2. **MR/Shipment. Document Type Invoice AP/AR** — Menentukan document type AP Invoice hasil generate.
3. **MR/Shipment. Document Action Invoice AP/AR** — Menentukan status dokumen atas AP Invoice yang di-generate.
4. **Allow Future Doc** — Jika dicentang, transaksi diizinkan diproses dengan _future date_.
5. **Manual ASI Setup** — Jika dicentang, ASI diinput secara manual oleh user, tidak dibuat otomatis oleh sistem.
6. **Max MR Back Dated Days** — Mengatur berapa hari transaksi diperbolehkan menggunakan tanggal mundur (_backdate_).

## Document Type AP Invoice

Field yang perlu dikonfigurasi:

1. **Auto Payment** — Jika dicentang, saat AP Invoice di-complete sistem otomatis membuat AP Payment (berlaku untuk invoice dari transaksi Kartu Fleet).
2. **Fleet Payment Document Type** — Menentukan document type AP Payment hasil generate.
3. **Fleet Payment Document Action** — Menentukan status dokumen atas AP Payment yang di-generate.
4. **Auto Bank Statement** — Jika dicentang, saat AP Invoice di-complete sistem otomatis membuat Bank/Cash Statement (berlaku untuk invoice dari transaksi Kartu Fleet).
5. **Fleet Bank Statement Document Type** — Menentukan document type Bank Statement hasil generate.
6. **Fleet Bank Statement Document Action** — Menentukan status dokumen atas Bank Statement yang di-generate.
## Document Type AP Payment

Field yang perlu dikonfigurasi:

1. **Payment Multi BP** — Mengizinkan payment dilakukan dengan multi vendor — mengakomodasi kondisi di mana BP Payment dan BP Invoice berbeda.
2. **Bank Account Access** — Membatasi bank account yang dapat diproses di transaksi payment sesuai konfigurasi.
3. **Auto Bank Statement** — Jika dicentang, saat payment di-complete sistem otomatis membuat Bank/Cash Statement. Jangan aktifkan untuk payment Kartu Fleet.
4. **Auto Bank Statement Doc Action** — Menentukan status dokumen atas Bank Statement yang di-generate.
5. **Prepayment** — Jika dicentang, document type berlaku untuk transaksi Prepayment (_Down Payment_).
## Document Type AR Receipt

Field yang perlu dikonfigurasi:

1. **Bank Account Access** — Membatasi bank account yang dapat diproses di transaksi payment sesuai konfigurasi.
2. **Auto Bank Statement** — Jika dicentang, saat payment di-complete sistem otomatis membuat Bank/Cash Statement. Jangan aktifkan untuk payment Kartu Fleet.
3. **Auto Bank Statement Doc Action** — Menentukan status dokumen atas Bank Statement yang di-generate.

## Document Type Bank/Cash Statement

Field yang perlu dikonfigurasi:

1. **Bank Account Access** — Membatasi bank account yang dapat diproses di transaksi sesuai konfigurasi.
## Document Type Bank/Cash Transfer

Field yang perlu dikonfigurasi:

1. **Charge Bank Transfer** — Menentukan charge atas transaksi Bank atau Cash Transfer.
2. **BT. Document Type AP Payment** — Menentukan document type AP Payment yang ter-create otomatis saat Bank/Cash Transfer di-complete.
3. **BT. Document Type AR Receipt** — Menentukan document type AR Receipt yang ter-create otomatis saat Bank/Cash Transfer di-complete.

## Document Type SIS RDO

Field yang perlu dikonfigurasi:

1. **RDO. Document Type Delivery** — Menentukan document type Inventory Move Delivery yang ter-create saat RDO di-complete.
2. **RDO. IM. Document Type Receipt** — Menentukan document type Inventory Move Receipt yang ter-create saat RDO di-complete.
3. **RDO Cancel Delivery Document Type** — Menentukan document type atas Inventory Move yang dibatalkan pengirimannya.
4. **RDO. IM. Warehouse Intransit** — Menentukan warehouse intransit saat Inventory Move dari warehouse asal.
5. **RDO. IM. Locator Intransit** — Menentukan locator intransit saat Inventory Move dari warehouse asal.
6. **Auto Create Back Order** — Jika dicentang, sistem otomatis membuat dokumen baru untuk sisa pesanan yang belum terpenuhi.
## Document Type Inventory Move

Field yang perlu dikonfigurasi:

1. **RDO. IM. Warehouse Intransit** — Menentukan warehouse intransit saat Inventory Move dari warehouse asal.
2. **RDO. IM. Locator Intransit** — Menentukan locator intransit saat Inventory Move dari warehouse asal.
3. **RDO. IM. Document Type Receipt** — Menentukan document type Inventory Move Receipt yang ter-create saat RDO di-complete.
4. **Document Type Cancel Delivery** — Menentukan document type atas Inventory Move yang dibatalkan pengirimannya.
## Document Type SIS Expedition

Tidak ada konfigurasi khusus yang diperlukan. Isi field-field pada header sesuai kebutuhan operasional.
## Document Type SIS Kontra Bon

Field yang perlu dikonfigurasi:

1. **AP Credit Memo Doctype** — Menentukan document type AP Credit Memo jika terdapat credit note (debit note) pada Kontra Bon.
2. **Kontra Bon Type** — Menentukan tipe Kontra Bon yang diproses: _PO Lengkap_, _Non PO_, atau _PO Invoice_. Jika _PO Lengkap_, user harus menginput nomor PO. Jika _Non PO_ atau _PO Invoice_, cukup menginput nomor AP Invoice.
## Document Type SIS ICPL dan SIS ICPL Update

Tidak ada konfigurasi khusus yang diperlukan. Isi field-field pada header sesuai kebutuhan operasional.
## Document Type SIS Asset Split

Field yang perlu dikonfigurasi:

1. **ASP. Document Type Internal Use** — Menentukan document type Inventory Decrease/Increase saat Asset Split dilakukan.
2. **ASP. Document Type Physical Inventory** — Menentukan document type Physical Inventory saat Asset Split dilakukan.
3. **ASP. Document Type GL Journal** — Menentukan document type GL Journal yang ter-create saat Asset Split dilakukan.
4. **ASP. Document Type Cost Adjustment** — Menentukan document type Cost Adjustment yang ter-create saat Asset Split dilakukan.
5. **ASP. Charge** — Menentukan charge atas aset yang dilakukan split.
## Document Type SIS Asset Addition

Tidak ada konfigurasi khusus yang diperlukan. Isi field-field pada header sesuai kebutuhan operasional.

## Document Type Sales Order

Field yang perlu dikonfigurasi:

1. **SO Sub Type** — Memberikan klasifikasi lebih spesifik terhadap Sales Order.
2. **SO. ICPL Type 1** — Menentukan tipe ICPL yang digunakan pada Sales Order.
3. **PO/SO. Generate MR/Shipment** — Saat SO di-complete, sistem otomatis men-generate Shipment.
4. **PO/SO. Document Type for MR/Shipment** — Menentukan document type Shipment hasil generate.
5. **PO/SO. Document Action For MR/Shipment** — Menentukan status dokumen atas Shipment yang di-generate.

## Document Type Shipment

Field yang perlu dikonfigurasi:

1. **MR/Shipment. Auto Invoice AP/AR** — Saat Shipment di-complete, sistem otomatis men-generate AR Invoice.
2. **MR/Shipment. Document Type Invoice AP/AR** — Menentukan document type AR Invoice hasil generate.
3. **MR/Shipment. Document Action Invoice AP/AR** — Menentukan status dokumen atas AR Invoice yang di-generate.
## Document Type AR Invoice, AP dan AR Credit Memo

Tidak ada konfigurasi khusus yang diperlukan. Isi field-field pada header sesuai kebutuhan operasional.
## Document Type Vendor dan Customer RMA

Field yang perlu dikonfigurasi:

1. **SO Sub Type** — Pilih **Return Material** untuk klasifikasi dokumen RMA.
2. **Auto Return Material** — Saat RMA di-complete, sistem otomatis men-generate Customer atau Vendor Return.
3. **Document Type Return** — Menentukan document type Customer atau Vendor Return hasil generate.
4. **Document Action Return** — Menentukan status dokumen atas Customer atau Vendor Return yang di-generate.

## Document Type Vendor dan Customer Return

Field yang perlu dikonfigurasi:

1. **MR/Shipment. Auto Invoice AP/AR** — Saat Vendor atau Customer Return di-complete, sistem otomatis men-generate AR atau AP Credit Memo.
2. **MR/Shipment. Document Type Invoice AP/AR** — Menentukan document type AR atau AP Credit Memo hasil generate.
3. **MR/Shipment. Document Action Invoice AP/AR** — Menentukan status dokumen atas AR atau AP Credit Memo yang di-generate.

## Document Type Inventory Decrease/Increase (Internal Use)

Field yang perlu dikonfigurasi adalah **Inv Sub Type** — pilih **Internal Use Inventory** untuk memberikan klasifikasi yang lebih spesifik terhadap transaksi Inventory.

## Document Type Adjustment Positif dan Negatif

Field yang perlu dikonfigurasi:

1. **Inv Sub Type** — Pilih **Internal Use Inventory**.
2. **Adjustment Type** — Menentukan tipe adjustment (_positif_ atau _negatif_) yang berpengaruh pada quantity produk yang diproses.
3. **Adjustment Charge** — Menentukan charge atas adjustment sehingga user tidak perlu memilih charge secara manual saat transaksi.

## Document Type Cost Adjustment

Field yang perlu dikonfigurasi adalah **Inv Sub Type** — pilih **Cost Adjustment**.

## Document Type Physical Inventory

Field yang perlu dikonfigurasi adalah **Inv Sub Type** — pilih **Physical Inventory**.

## Document Type Production Order Planning

Field yang perlu dikonfigurasi:

1. **POP. Document Type Movement** — Menentukan document type Inventory Move Delivery yang ter-generate saat MO di-generate.
2. **POP. Document Type Movement 2** — Menentukan document type Inventory Move Receipt yang ter-generate saat MO di-generate.
3. **POP. Document Type for PR** — Menentukan document type Requisition yang ter-generate saat MO di-generate.
4. **POP. Document Type Manufacturing Order** — Menentukan document type Manufacturing Order saat MO di-generate.
5. **POP. Document Type Production** — Menentukan document type Production saat Generate Production From MO atau saat MO di-complete.
6. **POP Consolidate Movement** — Jika dicentang, movement akan dikonsolidasi. Jika tidak, setiap movement dibuat secara terpisah.

## Document Type Manufacturing Order

Field yang perlu dikonfigurasi:

1. **Auto Create Back Order** — Jika dicentang, sistem otomatis membuat dokumen MO berstatus _Draft_ dengan quantity sisa yang belum diproduksi saat produksi dilakukan secara parsial.
2. **POP. Document Type Movement Defect** — Menentukan document type jika terdapat artikel yang diproduksi dengan status _defect_.
3. **POP. Movement Allowance** — Batas toleransi perpindahan artikel.
4. **POP. Production Allowance** — Batas toleransi produksi atas artikel, sehingga quantity yang diproduksi tidak boleh melebihi nilai allowance.
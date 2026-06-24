# Tools
## Bank Statement
### Complete

Jika perlu meng-complete dokumen Bank Statement dalam jumlah banyak — puluhan bahkan ratusan — gunakan tools **SIS Complete Bank Statement**. Ikuti langkah berikut:

1. Buka menu **SIS Complete Bank Statement**
2. Input **date statement**
3. Pilih **Document Type** "Bank Statement"
4. Pilih **Bank Account** yang akan diproses

![SIS Complete Bank Statement](../SIS_Complete_Bank.png "SIS Complete Bank Statement") {#Figure100}

5. Klik **ok**

![Complete](../Complete_Bank_Stat.png "Complete Bank Statement") {#Figure102}

Sistem otomatis meng-complete seluruh dokumen dalam rentang waktu yang dikonfigurasi.
### Delete

Jika perlu menghapus dokumen Bank Statement yang tidak diperlukan atau merupakan duplikat, gunakan tools **SIS Delete Bank Statement**. Ikuti langkah berikut:

1. Buka menu **SIS Delete Bank Statement**
2. Input **date statement**
3. Pilih **Document Type** "Bank Statement"
4. Pilih **Bank Account** yang akan diproses

![SIS Delete Bank Statement](../SIS_Delete_Bank.png "SIS Delete Bank Statement") {#Figure101}

5. Klik **ok**

![Delete](../Success_Delete_Bank.png "Delete Bank Statement") {#Figure103}

Sistem otomatis menghapus seluruh dokumen dalam rentang waktu yang dikonfigurasi.

>**Catatan:** Proses Delete hanya dapat dilakukan pada dokumen Bank/Cash Statement berstatus **Draft**.

## Movement
### Complete

Jika perlu meng-complete dokumen Inventory Move dalam jumlah banyak gunakan tools **SIS Complete Inventory Move**. Ikuti langkah berikut:

1. Buka menu **SIS Complete Inventory Move**
2. Input **Movement Date**
3. Pilih **Document Type**

![Complete Movement](../SIS_Complete_Move.png "Complete Movement") {#Figure103}

4. Klik ok

![Berhasil Complete](../Move_Complete.png "Complete Inventory Move") {#Figure104}

Sistem otomatis meng-complete seluruh dokumen dalam rentang waktu yang dikonfigurasi.
### Delete

Jika perlu menghapus dokumen Inventory Move yang tidak diperlukan atau merupakan duplikat, gunakan tools **SIS Delete Inventory Move**. Ikuti langkah berikut:

1. Buka menu **SIS Delete Inventory Move**
2. Input **Movement Date**
3. Pilih **Document Type**

![Complete Movement](../SIS_Delete_Move.png "Complete Movement") {#Figure105}

4. Klik ok

![Berhasil Delete](../Succes_Delete_Move.png "Delete Inventory Move") {#Figure106}

Sistem otomatis menghapus seluruh dokumen dalam rentang waktu yang dikonfigurasi.

>**Catatan:** Proses Delete hanya dapat dilakukan pada dokumen Inventory Move berstatus **Draft**.
## Physical Inventory
### Complete
Jika perlu meng-complete dokumen Physical Inventory dalam jumlah banyak gunakan tools **SIS Complete Physical Inventory**. Ikuti langkah berikut:

1. Buka menu **SIS Complete Physical Inventory**
2. Input **Movement Date**
3. Pilih **Document Type**

![SIS Complete](../SIS_Complete_PhysInven.png "SIS Complete Physical Inventory"){#Figure107}

4. Klik ok

![Complete](../Complete_Phys_Inven.png "Berhasil Complete") {#Figure108}

Sistem otomatis meng-complete seluruh dokumen dalam rentang waktu yang dikonfigurasi.
### Delete

Jika perlu menghapus dokumen Physical Inventory yang tidak diperlukan atau merupakan duplikat, gunakan tools **SIS Delete Physical Inventory**. Ikuti langkah berikut:

1. Buka menu **SIS Delete Physical Inventory**
2. Input **Movement Date**
3. Pilih **Document Type**

![SIS Delete](../SIS_Del_PhysInven.png "SIS Delete Physical Inventory") {#Figure109}

4. Klik **ok**

![Delete|406](../Delete_PhysInven.png "Berhasil Delete Physical Inventory") {#Figure110}

Sistem otomatis menghapus seluruh dokumen dalam rentang waktu yang dikonfigurasi.

>**Catatan:** Proses Delete hanya dapat dilakukan pada dokumen Physical Inventory yang berstatus **Draft**.

## Invoice
### Complete

Complete dokumen invoice adalah langkah final yang mengeksekusi logika bisnis, memperbarui stok, dan menghasilkan jurnal akuntansi otomatis. Fitur ini digunakan jika perusahaan memerlukan confirm banyak dokumen invoice yang bahkan mencapai puIuhan. Ikuti langkah berikut untuk melakukan complete dokumen invoice:

1. Buka menu **SIS Complete Invoice**
2. Input **Date Invoice**
3. Pilih **Document Type**
4. Pilih **Business Partner**
5. Klik ok

Sistem otomatis meng-complete seluruh dokumen dalam rentang waktu yang dikonfigurasi. Saat dokumen sudah dicomplete maka nominal di invoice tidak bisa diubah dan Invoice resmi masuk ke dalam daftar piutang/utang bisnis dan siap ditarik ke jendela _Payment / Receipt_.

>**Catatan:** Proses Complete hanya dapat dilakukan pada dokumen Invoice yang berstatus **Draft**.
### Delete

Fitur ini bertujuan untuk **menghapus baris atau seluruh dokumen** yang masih berstatus **Draft (DR)** atau **In Progress (IP)**. Ikuti langkah berikut untuk melakukan delete dokumen invoice:

1. Buka menu **SIS Delete Invoice**
2. Input **Date Invoice**
3. Pilih **Document Type**
4. Pilih **Business Partner**
5. Klik ok

Sistem otomatis menghapus seluruh dokumen dalam rentang waktu yang dikonfigurasi. Saat dokumen dihapus itu artinya sistem menghapus draf tagihan yang salah input atau salah nominal sebelum terjurnal. Menghapus _antrean_ dokumen dari modul piutang (_Accounts Receivable_) atau utang (_Accounts Payable_)

>**Catatan:** Proses Delete hanya dapat dilakukan pada dokumen Invoice yang berstatus **Draft**.

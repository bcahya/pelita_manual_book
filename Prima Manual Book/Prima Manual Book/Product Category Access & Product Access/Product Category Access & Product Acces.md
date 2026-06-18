## Product Category dan Product Access

Product category access adalah produk yang masuk dalam category produk yang sebelumnya sudah dikonfigurasi di level Product Category, dimana produk-produk tersebut nantinya yang akan didistribusikan dalam transaksi tersebut. Dalam hal ini pengelompokkan produk berdasarkan kategori. Apabila produk yang masuk dalam category tersebut dikonfigurasi di document type tersebut, maka saat akan dilakukan transaksi, hanya produk-produk yang masuk dalam kategory tersebut yang bisa diproses. Produk diluar kategori tersebut tidak bisa diproses. 

Sama halnya dengan product category access, untuk product access adalah produk yang akan diatur yang akan diproses. Dalam hal ini user menginput produk apa saja yang akan diproses. Diluar produk tersebut maka sistem tidak bisa memproses transaksinya. Konfigurasi product category access dan product acces dilakukan di level document type. Terdapat beberapa document type yang dapat dilakukan konfigurasi tersebut, diantaranya:
- Order Line
- Movement Line
- Invoice Line
- RDO Line
- ICPL Line

## Konfigurasi Product Category dan Product Access

Product category dan product access bisa dikonfigurasi di beberapa dokumen, maka dari itu user harus melakukan konfigurasi per document type. Berikut langkah-langkah untuk melakukan konfigurasi product category dan product access:
1. Buka Document Type Purchase Order
2. Pada header terdapat field Product Access. Untuk memilah produk yang akan diproses maka field tersebut harus dicentang
3. Untuk menginput produk apa saja yang akan diproses klik Generate Product
4. Input produk-produk apa saja yang akan diproses, kemudian klik SIS Generate Product Access
5. Pada sheet Product Access akan muncul produk-produk yang telah dikonfigurasi tersebut

Untuk konfigurasi product category access dapat dilakukan dengan langkah berikut:
1. Buka Document Type Purchase Order
2. Pada header terdapat field Product Category Access. Untuk memilah produk kategori yang akan diproses maka field tersebut harus dicentang
3. Klik Generate Product Category, input produk kategori yang akan diproses
4. Kemudian klik SIS Generate Product Category Access
5. Pada sheet Product Category Access akan muncul produk kategori yang telah dikonfigurasi tersebut
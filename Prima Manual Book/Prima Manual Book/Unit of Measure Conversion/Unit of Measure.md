# Unit of Measure (UoM)

Unit of Measure (UoM) adalah satuan pengukuran yang digunakan untuk menentukan kuantitas produk dalam setiap transaksi di iDempiere.

Dalam iDempiere, setiap produk memiliki satu Base UoM, yaitu satuan dasar dan terkecil yang menjadi acuan utama sistem untuk:

- Menyimpan saldo stok di database
- Menghitung harga pokok (costing)
- Menjadi referensi seluruh proses konversi satuan

UoM juga menentukan jumlah produk yang terlibat dalam transaksi. Ketika transaksi menggunakan satuan yang berbeda dari satuan dasar produk, sistem akan melakukan perhitungan berdasarkan konversi UoM yang telah ditentukan.
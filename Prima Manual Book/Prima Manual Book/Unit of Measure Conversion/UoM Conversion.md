# UoM Conversion

Unit of Measure (UoM) Conversion adalah mekanisme yang digunakan untuk mengonversi satu satuan pengukuran ke satuan lain untuk produk yang sama. Contohnya, produk dibeli dalam satuan karton (10 pcs), disimpan dalam satuan pcs, dan dikeluarkan juga dalam satuan pcs. Dalam kondisi ini, sistem harus memahami hubungan antar satuan tersebut.

UoM Conversion terdiri dari beberapa komponen utama:

- Base UoM, yaitu satuan dasar yang menjadi acuan utama, biasanya satuan terkecil seperti pcs, kg, atau meter.
- Alternate UoM, yaitu satuan lain yang digunakan dalam transaksi, seperti karton, lusin, atau dus.
- Conversion Factor, yaitu nilai pengali antar satuan. Contoh: 1 karton = 10 pcs, sehingga faktor konversinya adalah 10.

Setiap produk memiliki Base UoM sebagai referensi utama seluruh konversi. Sistem mendefinisikan konversi menggunakan multiply rate dan divide rate. Karena itu, Base UoM harus menjadi satuan terkecil dari seluruh skema konversi yang digunakan, dan nilai divide rate harus lebih besar atau sama dengan 1.

![Konfigurasi](../Multiply_Rate.png "Konfigurasi Multiply Rate dan Divide Rate") {#Figure9}

UoM Conversion diterapkan di Requisition, Purchase Order, dan Movement. Karena itu, pastikan konfigurasi UoM di level Product sudah selesai sebelum memulai transaksi di ketiga modul tersebut.


> [Tim PSI merekomendasikan untuk menetapkan standarisasi UoM pada proses Movement, Requisition dan Purchasing dengan tujuan untuk meminimalkan potensi kesalahan input UoM serta memastikan akurasi dalam penentuan harga] Catatan


## Ketentuan UoM Conversion

Dalam proses transaksi, satu vendor dapat menggunakan satuan yang berbeda dengan vendor lainnya untuk produk yang sama. Oleh karena itu, sistem perlu mendukung **lebih dari satu UoM Conversion** pada satu product sesuai dengan kebutuhan transaksi masing-masing vendor.
### Konfigurasi UoM Conversion di Level Product

Lakukan konfigurasi UoM Conversion pada menu **Product** dengan langkah berikut:

1. Buka menu **Product**.
2. Masuk ke tab **UoM Conversion**.
3. Tentukan **UoM From** dan **UoM To**.
4. Tentukan jenis transaksi yang menggunakan konfigurasi tersebut melalui flag:
- **Movement**
- **Purchasing**
- **Requisition**

![uom1](../po1.png "UoM Conversion 1") {#Figure248}


![po2](../po2.png "UoM Conversion 2") {#Figure249}

5. Klik **Save** untuk menyimpan konfigurasi.

Meskipun flag **Movement, Requisition, dan Purchasing** dapat diaktifkan secara bersamaan atau lebih dari satu, sistem tetap menggunakan **satu UoM Conversion sebagai default** untuk masing-masing transaksi **Requisition, Purchasing, dan Movement pada POP**.

### Contoh Implementasi

Berikut contoh implementasi **multi UoM Conversion** untuk transaksi **Purchasing**, ketika satu product memiliki satuan pembelian yang berbeda sesuai dengan kebutuhan vendor:

![po](../uom__po.png "Implementasi Purchase Order") {#Figure250}
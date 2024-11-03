Brainstorming: 

1. *Mengapa ERD penting dalam perancangan basis data ?*
ERD (Entity Relationship Diagram) penting dalam perancangan basis data karena dapat membantu kita memvisualisasikan dan memahami struktur data yang akan disimpan dalam basis data. ERD memungkinkan kita untuk mengidentifikasi entitas, atribut, dan relasi antara entitas sehingga dapat merancang basis data yang efisien dan efektif.

2. *Di dalam perancangan ERD, apa saja elemen dan simbol yang mesti ada?*
   simbol 
- Entitas (berbentuk persegi panjang)
- Relasi (berbentuk belah ketupat)
- Atribut (berbentuk elips)
- Garis

- Elemen lingkungan dri sebuah perusahaan atau toko yang mencakup customer, supplier, dsb
- Elemen sumber daya yang mencakup suatu produk dari perusahaan dan suatu penjual
- Elemen arus informasi yang mencakup seperti informasi tentang suatu penjualan produk dan pemesanan 
- Atau elemen objek seperti dalam sebuah universitas yang mencakup mahasiswa, anggota, buku

3. *Apa yang dimaksud entitas dan apa saja contoh entitas yang ada di sekitar kalian?*
Entitas adalah objek atau benda yang dapat diidentifikasi secara unik dalam basis data. Contoh entitas di sekitar kita antara lain mahasiswa, dosen, mata kuliah, jurusan, transaksi penjualan, dan lain-lain.

Contoh Entitas disekitar kita:
1. Mahasiswa
   - Contoh entitas mahasiswa dapat memiliki atribut seperti NIM, nama, program studi, IPK, dan lain-lain.
2. Buku
   - Contoh entitas buku dapat memiliki atribut seperti judul, penulis, penerbit, tahun terbit, dan lain-lain.
3. Kendaraan
- Contoh entitas kendaraan dapat memiliki atribut seperti nomor plat, merk, model, tahun pembuatan, dan lain-lain.
4. Pelatihan
- Contoh entitas pelatihan dapat memiliki atribut seperti nama pelatihan, tanggal, instruktur, biaya, dan lain-lain.
5. Dokumen
- Contoh entitas dokumen dapat memiliki atribut seperti nomor dokumen, judul, tanggal, penulis, dan lain-lain.
6. Acara
- Contoh entitas acara dapat memiliki atribut seperti nama acara, tanggal, lokasi, kategori, dan lain-lain.

4. *Apa itu relasi dalam ERD dan seperti apa contohnya?*
Relasi dalam Entity-Relationship Diagram (ERD) merujuk pada hubungan antara entitas di dalam sistem yang sedang dianalisis. Relasi ini menggambarkan bagaimana satu entitas berinteraksi dengan entitas lainnya. Setiap relasi biasanya ditandai dengan garis yang menghubungkan entitas, dan dapat memiliki berbagai jenis kardinalitas, seperti One the One (1:1), One the Many (1:N), atau Many to Many (M:N).

Contoh Relasi dalam ERD
1. Entitas: Mahasiswa dan Mata Kuliah
   Relasi: 
   Mahasiswa mendaftar pada Mata Kuliah.
   Tipe Relasi: 
   Banyak ke Banyak (M:N), karena satu mahasiswa bisa mendaftar di banyak mata kuliah, dan satu mata kuliah bisa diambil oleh banyak mahasiswa.
2. Entitas: Karyawan dan Departemen
   Relasi:
   Karyawan bekerja di Departemen.
   Tipe Relasi: 
   Banyak ke Satu (N:1), karena banyak karyawan bisa berada di satu departemen, tetapi setiap karyawan hanya bekerja di satu departemen.
3. Entitas: Buku dan Penulis
   Relasi:
   Buku ditulis oleh Penulis.
   Tipe Relasi:
   Banyak ke Banyak (M:N), karena satu buku bisa ditulis oleh beberapa penulis, dan satu penulis bisa menulis banyak buku.
4. Entitas: Pelanggan dan Pesanan
   Relasi:
   Pelanggan membuat Pesanan.
   Tipe Relasi:
   Satu ke Banyak (1:N)
   Penjelasan: Setiap pelanggan dapat membuat banyak pesanan, tetapi setiap pesanan hanya dapat dibuat oleh satu pelanggan.
5. Entitas: Produk dan Kategori
   Relasi:
   Produk termasuk dalam Kategori.
   Tipe Relasi:
   Banyak ke Satu (N:1)
   Penjelasan: Banyak produk dapat termasuk dalam satu kategori, tetapi setiap produk hanya dapat berada dalam satu kategori.

5. *Setiap entitas dapat berhubungan satu sama lain dalam bentuk kardinalitas. Apa-apa saja kardinal-itas dalam ERD?*
   Kardinalitas dalam ERD menggambarkan jumlah maksimum entitas yang dapat terlibat dalam suatu relasi. Beberapa kardinalitas umum adalah:
- One-to-one (1:1)
- One-to-many (1:M)
- Many-to-many (M:N)
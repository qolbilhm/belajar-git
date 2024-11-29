
---

# Soal 1
### *1. Membuat Database*

```mysql
CREATE DATABASE SistemSekolah;
USE SistemSekolah;
```

Hasil :
![[ujian1.jpg]]

*Penjelasan saat mencoba*:  
Kami memulai dengan membuat database bernama SistemSekolah. Perintah CREATE DATABASE digunakan untuk mendefinisikan database baru, dan kami menggunakan USE SistemSekolah untuk memastikan semua operasi berikutnya dilakukan dalam konteks database ini.

*Analisis*:

- **Database SistemSekolah** menjadi wadah utama untuk semua tabel yang terkait, membantu dalam pengorganisasian data secara terintegrasi.
- Tidak ada masalah teknis di tahap ini, tetapi penting untuk memastikan nama database deskriptif agar sesuai dengan fungsinya.

---

### *2. Membuat Tabel Barang*

```mysql
CREATE TABLE Barang (
    id_barang INT AUTO_INCREMENT PRIMARY KEY,
    nama_barang VARCHAR(100) NOT NULL,
    tipe_barang VARCHAR(50),
    jumlah_barang INT NOT NULL,
    id_peminjam INT
);
```

Hasil :
![[ujian2.jpg]]

*Penjelasan saat mencoba*:  
Kami membuat tabel Barang dengan id_barang sebagai primary key untuk memastikan setiap barang memiliki identitas unik. Selain itu, kami menambahkan kolom-kolom untuk menyimpan informasi tentang barang seperti nama, tipe, jumlah, dan id_peminjam yang nantinya dapat digunakan untuk menghubungkan peminjam (guru atau siswa).

*Analisis*:

- **Kolom id_barang** berfungsi sebagai primary key yang menjamin setiap barang memiliki identifikasi unik, dengan nilai yang otomatis bertambah (AUTO_INCREMENT).
- **Kolom id_peminjam** dapat digunakan untuk menghubungkan barang dengan peminjam dari tabel Guru atau Siswa. Namun, saat ini belum ada relasi langsung yang ditentukan.
- **Kolom jumlah_barang** memastikan jumlah barang yang tersedia tercatat, wajib diisi (NOT NULL), sehingga tidak ada data barang yang tidak memiliki informasi stok.

---

### *3. Membuat Tabel Ruang*

```mysql
CREATE TABLE Ruang (
    id_ruang INT AUTO_INCREMENT PRIMARY KEY,
    nama_ruang VARCHAR(100) NOT NULL,
    kapasitas_ruang INT NOT NULL
);
```

*Hasil :*
![[ujian3.jpg]]

*Penjelasan saat mencoba*:  
Kami merancang tabel Ruang untuk mencatat data tentang ruang-ruang di sekolah. Kolom id_ruang berfungsi sebagai identitas unik, sedangkan nama_ruang dan kapasitas_ruang digunakan untuk menyimpan informasi detail.

*Analisis*:

- **Kolom id_ruang** adalah primary key yang unik untuk setiap ruang, dengan nilai yang otomatis bertambah.
- **Kolom kapasitas_ruang** mencatat jumlah maksimum kapasitas ruang, wajib diisi untuk memastikan data ruang lengkap dan akurat.
- *Struktur tabel* dirancang sederhana tanpa relasi ke tabel lain. Jika diperlukan, relasi ke tabel kegiatan atau penggunaan ruang dapat ditambahkan.

---

### *4. Membuat Tabel Guru*

```mysql
CREATE TABLE Guru (
    id_guru INT AUTO_INCREMENT PRIMARY KEY,
    nama_guru VARCHAR(100) NOT NULL,
    mata_pelajaran VARCHAR(100) NOT NULL
);
```

*Hasil :*
![[ujian4.jpg]]

*Penjelasan saat mencoba*:  
Kami membuat tabel Guru untuk menyimpan informasi tentang guru. Kolom id_guru adalah primary key, sedangkan nama_guru dan mata_pelajaran mencatat informasi penting tentang setiap guru.

*Analisis*:

- **Kolom id_guru** berfungsi sebagai primary key untuk memastikan setiap guru memiliki identifikasi unik.
- **Kolom mata_pelajaran** menyimpan informasi tentang mata pelajaran yang diajarkan oleh guru. Hal ini memungkinkan pencarian atau pengelompokan berdasarkan mata pelajaran.
- *Relasi dengan tabel lain* belum diatur. Namun, tabel ini dapat dihubungkan ke tabel lain seperti Jadwal untuk mencatat pengajaran guru.

---

### *5. Membuat Tabel Siswa*

```sql
CREATE TABLE Siswa (
    id_siswa INT AUTO_INCREMENT PRIMARY KEY,
    nama_siswa VARCHAR(100) NOT NULL,
    kelas_siswa VARCHAR(50) NOT NULL
);
```

*Hasil :*
![[ujian5.jpg]]

*Penjelasan saat mencoba*:  
Kami membuat tabel Siswa untuk mencatat informasi tentang siswa. Kami menggunakan id_siswa sebagai primary key, sedangkan nama_siswa dan kelas_siswa digunakan untuk informasi personal siswa.

*Analisis*:

- **Kolom id_siswa** adalah primary key untuk menjamin bahwa setiap siswa memiliki identifikasi unik.
- **Kolom kelas_siswa** mencatat kelas tempat siswa belajar, yang dapat digunakan untuk pengelompokan atau penjadwalan lebih lanjut.
- *Potensi pengembangan*: Tabel ini dapat dihubungkan ke tabel Peminjaman untuk mencatat barang yang dipinjam siswa, atau tabel Jadwal untuk mengatur relasi antara siswa, guru, dan kelas.

---

### *Analisis Keseluruhan*

- *Primary Key* di setiap tabel memastikan setiap data memiliki identifikasi unik dan tidak duplikat.
- *Relasi antar tabel* belum ditentukan secara eksplisit. Untuk penggunaan lebih kompleks, tabel seperti Peminjaman atau Jadwal perlu ditambahkan untuk menghubungkan entitas seperti barang, guru, siswa, dan ruang.
- *Rekomendasi penggunaan constraint*: Tambahkan FOREIGN KEY dengan ON DELETE CASCADE atau ON DELETE SET NULL untuk menjaga konsistensi data, terutama pada kolom seperti id_peminjam.

---

### *Kesimpulan*

- Database ini sudah mencakup struktur dasar yang cukup baik, tetapi akan lebih optimal jika relasi antar entitas ditambahkan. Dengan perbaikan lebih lanjut, database ini dapat digunakan untuk sistem sekolah yang lebih kompleks.


# Soal 2

---

### **Contoh 1
Query ini menampilkan total barang yang dipinjam oleh setiap jenis peminjam (Guru dan Siswa), hanya menampilkan data dengan jumlah barang yang lebih dari 5.

```sql
SELECT 
    CASE 
        WHEN g.id_guru IS NOT NULL THEN 'Guru'
        WHEN s.id_siswa IS NOT NULL THEN 'Siswa'
    END AS peminjam,
    COUNT(b.id_barang) AS jumlah_barang_dipinjam
FROM 
    Barang b
LEFT JOIN Guru g ON b.id_peminjam = g.id_guru
LEFT JOIN Siswa s ON b.id_peminjam = s.id_siswa
GROUP BY 
    CASE 
        WHEN g.id_guru IS NOT NULL THEN 'Guru'
        WHEN s.id_siswa IS NOT NULL THEN 'Siswa'
    END
HAVING 
    COUNT(b.id_barang) > 0;
```

Hasil : 
![[ujian6.jpg]] 

*Penjelasan*:

- *Relasi*: Tabel Barang direlasikan dengan tabel Guru dan Siswa menggunakan LEFT JOIN pada kolom id_peminjam.
- *GROUP BY*: Data dikelompokkan berdasarkan jenis peminjam (Guru atau Siswa).
- *HAVING*: Hanya menampilkan kelompok peminjam dengan total barang dipinjam lebih dari 0.

---

### **Contoh 2

Query ini menampilkan total kapasitas ruang yang digunakan oleh guru, dikelompokkan berdasarkan mata pelajaran, hanya jika kapasitas total ruang yang digunakan lebih dari 30.

```sql
SELECT 
    g.mata_pelajaran,
    SUM(r.kapasitas_ruang) AS total_kapasitas_ruang
FROM 
    Ruang r
INNER JOIN Guru g ON r.id_ruang = g.id_guru
GROUP BY 
    g.mata_pelajaran
HAVING 
    SUM(r.kapasitas_ruang) > 30;
```

Hasil : 
![[ujian7.jpg]] 

*Penjelasan*:

- *Relasi*: Tabel Ruang direlasikan dengan tabel Guru menggunakan INNER JOIN.
- *GROUP BY*: Data dikelompokkan berdasarkan mata_pelajaran dari tabel Guru.
- *HAVING*: Hanya menampilkan mata pelajaran dengan total kapasitas ruang lebih dari 30.

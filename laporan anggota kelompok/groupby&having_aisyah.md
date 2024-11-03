# DESC
**Penjelasan** : Dalam MySQL, `DESC` adalah singkatan dari "DESCRIBE". Perintah `DESCRIBE` digunakan untuk menampilkan struktur dari tabel yang ada dalam database. Dengan menggunakan `DESCRIBE`, Anda bisa mendapatkan informasi mengenai kolom-kolom dalam tabel, termasuk nama kolom, tipe data, apakah kolom tersebut dapat bernilai `NULL` atau tidak, dan atribut lainnya seperti kunci primer (primary key) atau default value.

**Contoh Program :
~~~sql
desc Pegawai;
~~~
**Hasilnya :

![](aset/d.jpg)

**Analisisnya :**
**NIP INT PRIMARY KEY :
- `NIP`: Ini biasanya merujuk pada nama kolom dalam tabel basis data. Dalam konteks basis data, NIP sering digunakan sebagai singkatan untuk "Nomor Induk Pegawai," yang merupakan identifikasi unik untuk pegawai dalam sistem.
- `INT`: Ini adalah tipe data dalam SQL yang berarti "integer" atau bilangan bulat. Tipe data ini digunakan untuk menyimpan angka tanpa pecahan desimal.
- `PRIMARY KEY`: Ini adalah sebuah constraint (kekangan) dalam SQL yang menandakan bahwa kolom tersebut adalah kunci utama. Tidak ada dua baris yang boleh memiliki nilai yang sama pada kolom kunci utama, dan kolom ini tidak boleh berisi nilai NULL.
**NDep VARCHAR(255) NOT NULL :
-  `NDep` : Ini adalah nama kolom dalam tabel basis data.
- `VARCHAR`: Singkatan dari "Variable Character," adalah tipe data yang digunakan untuk menyimpan teks dengan panjang variabel.
- `(255)`: dapat menyimpan hingga 255 karakter.
- `NOT NULL`: Ini adalah constraint (kekangan) yang menunjukkan bahwa kolom ini tidak boleh mengandung nilai NULL.
**NBlk VARCHAR(255)** :
- `NBlk` : Kolom ini menyimpan Nama Belakang pegawai bertipe data string dengan panjang maksimum 255 karakter
- `VARCHAR(255))` : Kolom ini tidak memiliki batasan NOT NULL, sehingga nilai kosong (NULL) diizinkan.
**JK ENUM('L', 'P') NOT NULL**:
- `JK` : Kolom ini menyimpan Jenis Kelamin pegawai dengan tipe data ENUM. Hanya dua nilai yang diperbolehkan: 'L' (Laki-laki) atau 'P' (Perempuan).
- `ENUM` :Anda memastikan bahwa hanya nilai-nilai tertentu yang bisa dimasukkan ke dalam kolom. Misalnya, untuk kolom `JenisKelamin`, Anda hanya mengizinkan 'Laki-laki' atau 'Perempuan'. Ini membantu menjaga konsistensi data.
- `NOT NULL` : Menandakan bahwa kolom ini tidak boleh kosong; artinya, setiap baris harus memiliki nilai untuk kolom ini.
**Alamat TEXT NOT NULL**:
- `Alamat` : Kolom ini menyimpan alamat pegawai dengan tipe data TEXT.
- `TEXT` : dapat menyimpan data teks dengan panjang hingga 65.535 karakter (untuk `TEXT` standar), yang biasanya cukup untuk alamat yang panjang.
- `NOT NULL` Menandakan bahwa kolom ini harus diisi dengan nilai; nilai kosong (NULL) tidak diperbolehkan.
**Telp VARCHAR(255) NOT NULL**:
- `Telp` : Kolom ini menyimpan nomor telepon pegawai dengan tipe data string dan panjang maksimum 255 karakter (VARCHAR(255)).
- `NOT NULL` : Menandakan bahwa kolom ini harus diisi; nilai kosong (NULL) tidak diperbolehkan.
**Jabatan ENUM('Manager', 'Supervisor', 'Staff')** :
- `Jabatan` : Kolom ini menyimpan jabatan pegawai dengan tipe data ENUM. Nilai yang diperbolehkan adalah 'Manager', 'Supervisor', atau 'Staff'.
- Kolom ini tidak memiliki batasan NOT NULL, sehingga nilai kosong (NULL) diizinkan.

**Gaji BIGINT NOT NULL** :
- `Gaji` : Kolom ini menyimpan gaji pegawai dengan tipe data BIGINT, yang dapat menampung bilangan bulat yang sangat besar.
- `BIGINT` adalah tipe data dalam SQL yang digunakan untuk menyimpan bilangan bulat (integer) dengan rentang yang lebih besar dibandingkan dengan tipe data `INT`.
- `NOT NULL`: Menandakan bahwa kolom ini harus diisi; nilai kosong (NULL) tidak diperbolehkan.

- **NoCab VARCHAR(255) NOT NULL**:
- `NoCab` : Kolom ini menyimpan nomor cabang pegawai dengan tipe data string dan panjang maksimum 255 karakter (VARCHAR(255)).
- `NOT NULL`: Menandakan bahwa kolom ini harus diisi; nilai kosong (NULL) tidak diperbolehkan.

**Kesimpulan :**
Secara keseluruhan, tabel `pegawai` dirancang dengan kolom `id` sebagai identifikasi unik yang bertambah otomatis, sementara kolom `nama` adalah wajib diisi, dan kolom `jabatan` serta `tanggal_lahir` bersifat opsional. Ini mencerminkan struktur dasar dari tabel yang mungkin digunakan untuk menyimpan data pegawai dengan informasi kunci seperti nama, jabatan, dan tanggal lahir.

# SELECT
**Penjelasan :** Perintah `SELECT` dalam MySQL digunakan untuk mengambil data dari tabel dalam database. Ini adalah perintah dasar dan paling sering digunakan dalam SQL untuk menampilkan data. Anda bisa menggunakan `SELECT` untuk memilih kolom tertentu, menggabungkan tabel, melakukan filter data, dan banyak lagi.

**Contoh Program :**
~~~sql
select * from pegawai;
~~~

**Hasil :**
![](aset/s.jpg)

**Analisisnya:**
1. **SELECT**: Ini adalah perintah SQL yang digunakan untuk memilih data dari database. Dalam hal ini, `SELECT` digunakan untuk mengambil data dari tabel.

2. **;** Simbol ini adalah wildcard yang berarti "semua kolom". Jadi, `SELECT *` akan memilih semua kolom yang ada dalam tabel.

3. **FROM pegawai**: Bagian ini menunjukkan tabel dari mana data akan diambil. Dalam hal ini, tabelnya adalah `pegawai`.
**Kesimpulan :**
Perintah `SELECT * FROM pegawai;` berguna untuk melihat seluruh data dalam tabel `pegawai` tanpa batasan atau filter. Ini adalah cara cepat untuk mendapatkan gambaran lengkap tentang data yang ada di tabel, tetapi untuk analisis yang lebih spesifik atau untuk meningkatkan performa query, sebaiknya Anda memilih kolom tertentu dan menerapkan kondisi yang sesuai.

# GROUP BY & HAVING
### contoh 1
**Contoh Program** :
~~~sql
SELECT COUNT(NIP) AS JumlahPegawai, COUNT(Jabatan) AS JumlahJabatan FROM pegawai;
~~~
**Hasilnya :**
![](aset/basdat1.jpg)

**Analisisnya :**
**`SELECT`**:Digunakan untuk memilih data dari tabel.
**`COUNT(NIP)` AS `JumlahPegawai`**: Fungsi `COUNT(NIP)` menghitung jumlah baris di tabel `pegawai` di mana kolom `NIP` tidak bernilai NULL.`JumlahPegawai` digunakan untuk memberikan nama hasil kolom ini pada output query.
**`COUNT(Jabatan)` AS `JumlahJabatan`**: Fungsi `COUNT(Jabatan)` menghitung jumlah baris di tabel `pegawai` di mana kolom `Jabatan` tidak bernilai NULL. `JumlahJabatan` digunakan untuk memberikan nama hasil kolom ini pada output query.
**`FROM pegawai`**:Menunjukkan bahwa data diambil dari tabel `pegawai`.

**Kesimpulannya:**
Query ini memberikan informasi tentang kelengkapan data di dua kolom penting (`NIP` dan `Jabatan`) dalam tabel `pegawai`. Ini berguna untuk melakukan analisis terhadap kualitas data, memastikan bahwa kolom-kolom penting diisi dengan informasi yang diperlukan, dan membantu dalam perencanaan lebih lanjut atau pemeliharaan data.

### contoh 2
**Contoh Program :**
~~~sql
SELECT COUNT(NIP) AS JumlahPegawai 
-> FROM pegawai 
-> WHERE NoCab = 'C102';
~~~
**Hasilnya :**
![](aset/basdat2.jpg)

**Analisisnya :**
 `SELECT` :untuk memilih kolom mana saja yang ingin dihitung.
`COUNT(NIP)`: untuk mengitung jumlah barisan data yang mempunyai data dari kolom yang dipilih. "NIP" adalah nama kolom yang dipilih untuk dihitung
`AS`: untuk mengubah nama dari suatu kolom untuk sementara.
`Jumlah_Pegawai` : nama sementara dari kolom hasil `COUNT(NIP)`.
`FROM pegawai`: untuk memilih dari tabel mana yang data kolommnya ingin digunakan , `pegawai` adalah nama tabel yang diplih untuk digunakan.
`WHERE`: merupakan kondisi yang harus dipenuhi agar datanya dapat dengan query count(NIP).
`NoCab = C102`= adalah kondisi dari where yang harus dipenuhi, jadi hanya barisan data yang memliki `C102` dikolom  "NoCab"  yang bisa dihitung.


**Kesimpulannya :**
Query ini memberikan informasi spesifik tentang jumlah pegawai yang terdaftar di cabang dengan kode 'C102' dan yang memiliki nilai pada kolom `NIP`. Ini membantu dalam memantau atau menganalisis distribusi pegawai berdasarkan lokasi atau cabang tertentu.

### contoh 3
**Contoh Program :**
~~~sql
SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai 
    -> FROM pegawai
	-> GROUP BY NoCab;
~~~
**Hasilnya :**
![](aset/basdat3.jpg)

**Analisisnya :**
`SELECT` :untuk memilih kolom mana saja yang ingin dihitung atau ditampilkan
`NoCab`: merupakan nama kolom  yang kolom yang ingin ditampilkan.
`COUNT(NIP)`: untuk mengitung jumlah barisan data yang mempunyai data dari kolom yang dipilih. "NIP" adalah nama kolom yang dipilih untuk dihitung.
`AS`: untuk mengubah nama dari suatu kolom untuk sementara.
`FROM pegawai`: untuk memilih dari tabel mana yang data kolommnya ingin digunakan , `pegawai` adalah nama tabel yang diplih untuk digunakan.
 `GROUP BY`: untuk mengelmpokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
 `NoCab`: nama kolom yang dipilih untuk datanya dikelompokkan.

**Kesimpulannya:**
Query ini memberikan ringkasan jumlah pegawai di setiap cabang atau lokasi yang ditunjukkan oleh kolom `NoCab`. Dengan mengelompokkan data berdasarkan `NoCab` dan menghitung jumlah pegawai dalam setiap kelompok, query ini membantu dalam analisis distribusi pegawai dan perencanaan sumber daya di berbagai cabang atau lokasi.

### contoh 4
**Contoh Program :**
~~~sql
SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai
	-> FROM pegawai
	-> GROUP BY NoCab HAVING COUN(NIP) >= 3;
~~~
**Hasilnya :**
![](aset/basdat4.jpg)

**Analisisnya :**
`select`: untuk memilih kolom mana saja yang ingin dihitung atau ditampilkan.
`NoCab`: merupakan nama kolom yang ingin ditampilkan
`COUNT(NIP)`: untuk mengitung jumlah barisan data yang mempunyai data dari kolom yang dipilih. "NIP" adalah nama kolom yang dipilih untuk dihitung.
`AS`: untuk mengubah nama dari suatu kolom untuk sementara.
`Jumlah_Pegawai` : nama sementara dari kolom hasil `COUNT(NIP)`.
`FROM pegawai`: untuk memilih dari tabel mana yang data kolommnya ingin digunakan , `pegawai` adalah nama tabel yang diplih untuk digunakan.
 `GROUP BY`: untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
`NoCab`: nama kolom yang dipilih untuk datanya dikelompokkan.
`HAVING`: untuk menentukan kondisi (yang harus dipenuhi) oleh suatu kelompok data agar bisa ditampilkan .
`(COUNT(NIP) > =3)`: merupakan kondisi yang harus dipenuhi oleh suatu kelompok data.
  Jadi hanya kelompok data yang hasil hitungannya lebih atau sama dengan 3.

**Kesimpulannya :**
Query ini menghasilkan daftar cabang yang memiliki lebih dari 3 pegawai. Dengan menggunakan `GROUP BY` dan `HAVING`, query ini memfokuskan pada cabang-cabang dengan jumlah pegawai yang cukup besar, yang bisa digunakan untuk analisis lebih lanjut mengenai distribusi pegawai dan kebutuhan sumber daya di cabang-cabang tersebut.


### contoh 5
**Contoh Program :**
~~~sql
SELECT SUM(Gaji) AS Total_Gaji
  -> FROM pegawai;
~~~
**Hasilnya :**
![](aset/basdat5.jpg)

**Analisisnya :**`
`SELECT`: untuk memilih kolom mana saja yang dipilih untuk dijumlahkan.
`SUM(Gaji)`: untuk menghitung jumlah data(khusus angka) pada kolm yang dipilih , Gaji merupakan nama kolom yang dipilih untuk dihitung jumlah isi datanya.
`AS`: untuk mengganti nama dari klm hasil `SUM`(Gaji) untuk sementara.
`Total_Gaji`:merupakan nama sementara dari peritah AS.
`FORM pegawai`: untuk memilih dari tabel mana yang kolom datanya akan digunakan pegawai adalah nama dari tabel yang dipilih.

**Kesimpulannya:**
Query ini menghitung total jumlah gaji dari semua pegawai yang terdaftar di tabel pegawai,Hasilnya adalah satu nilai yang menunjukkan jumlah total gaji seluruh pegawai, dan kolom hasil tersebut dinamakan `Total_Gaji`.
Berguna untuk analisis keuangan atau perhitungan total biaya gaji dalam laporan atau aplikasi yang memerlukan informasi total gaji, Dengan kata lain, query ini memberikan total keseluruhan gaji yang harus dibayarkan kepada semua pegawai berdasarkan data di tabel `pegawai`.


### contoh 6
**Contoh Program :**
~~~sql
 SELECT SUM(Gaji) AS Gaji_Manajer
 	-> FROM pegawai
 	-> WHERE Jabatan = 'Manajer';
~~~
**Hasilnya :**
![](aset/basdat6.jpg)

**Analisisnya :**
`SELECT`: untuk memilih kolom mana saja yang dipilih untuk dijumlahkan.
`SUM(Gaji)`: untuk menghitung jumlah data(khusus angka) pada kolm yang dipilih , Gaji merupakan nama kolom yang dipilih untuk dihitung jumlah isi datanya.
`AS`: untuk mengganti nama dari kolom hasil `SUM`(Gaji) untuk sementara.
`Gaji_Manajer`: merupakan nama sementara dari perintah AS.
`FORM pegawai`: untuk memilih dari tabel mana yang kolom datanya yang akan digunakan pegawai adalah nama dari tabel yang dipilih .
`WHERE`: kondisi yang harus dipenuhi oleh suatu kolom agar datanya bisa dijumlah .
`(Jabatan = "Manajer)`: merupakan kondisi dari where , hanya barisan data yang kolom jabatannya berisi manajer yang kolom gajinya bisa dijumlahkan.
 
**Kesimpulannya  :**
Query ini digunakan untuk mendapatkan jumlah total gaji yang dibayarkan kepada semua pegawai dengan jabatan `'Manajer'` di tabel `pegawai`. Hasilnya menunjukkan total keseluruhan gaji dari pegawai yang menjabat sebagai manajer.


### contoh 7
**Contoh Program :**
~~~sql
SELECT NoCab, SUM(Gaji) AS TotalGaji
-> FROM pegawai
-> GROUP BY NoCab;
~~~
**Hasilnya :**
![](aset/basdat7.jpg)

**Analisisnya :**
`SELECT`: untuk memilih kolom mana saja yang dipilih untuk dijumlahkan.
`NoCab`: adalah nama kolom yang ingin ditampilkan.
`SUM(Gaji)`: untuk menghitung jumlah data(khusus angka) pada kolm yang dipilih , Gaji merupakan nama kolom yang dipilih untuk dihitung jumlah isi datanya.
`AS`: untuk mengganti nama dari kolom hasil `SUM`(Gaji) untuk sementara.
`TotalGaji`: merupakan nama sementara dari perintah AS.
`FORM pegawai`: untuk memilih dari tabel mana yang kolom datanya yang akan digunakan pegawai adalah nama dari tabel yang dipilih .
 `GROUP BY`: untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
 `NoCab`: nama kolom yang dipilih untuk datanya dikelompokkan.

**Kesimpulannya :**
Dengan menggunakan fungsi agregat `SUM` dan klausa `GROUP BY`, query ini mengelompokkan data berdasarkan kolom `NoCab` (nomor cabang) dan menjumlahkan gaji (`Gaji`) untuk setiap kelompok tersebut. Hasilnya adalah daftar nomor cabang berserta total gaji yang dibayarkan di masing-masing cabang. Ini membantu dalam analisis biaya gaji per unit dalam organisasi.


### contoh 8
**Contoh Program :**
~~~sql
SELECT NoCab, SUM(Gaji) AS Total_Gaji
    -> FROM pegawai
	-> GROUP BY NoCab HAVING SUM(Gaji) >= 8000000;
~~~
**Hasilnya :**
![](aset/basdat8.jpg)

**Analisisnya :**
`SELECT`: untuk memilih kolom mana saja yang dipilih untuk dijumlahkan.
`NoCab`: adalah nama kolom yang ingin ditampilkan.
`SUM(Gaji)`: untuk menghitung jumlah data(khusus angka) pada kolom yang dipilih , Gaji merupakan nama kolom yang dipilih untuk dihitung jumlah isi datanya.
`AS`: untuk mengganti nama dari kolom hasil `SUM`(Gaji) untuk sementara.
`TotalGaji`: merupakan nama sementara dari perintah AS.
`FORM pegawai`: untuk memilih dari tabel mana yang kolom datanya yang akan digunakan pegawai adalah nama dari tabel yang dipilih .
 `GROUP BY`: untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
 `NoCab`: nama kolom yang dipilih untuk datanya dikelompokkan.
  `HAVING`: untuk menentukan kondisi (yang harus dipenuhi) oleh suatu kelompok data agar bisa ditampilkan .
  `(SUM (Gaji) >= 8000000)`: kondisi dari `HAVING`, Hasil dari penjumlahan Gaji yang hanya bisa ditampilkan adalah hasil yang lebih dari atau sama dengan (8000000).
  
**Kesimpulannya :**
Query ini efektif untuk memfilter dan menampilkan hanya cabang-cabang yang memiliki total gaji pegawai yang melebihi batas tertentu (8.000.000 dalam hal ini). Ini membantu dalam fokus analisis pada cabang-cabang dengan biaya gaji tinggi.


### contoh 9
**Contoh Program :**
~~~sql
SELECT AVG(Gaji) AS Rata_rata
-> FROM pegawai;
~~~
**Hasilnya :**
![](aset/basdat9.jpg)
**Analisisnya :**
 `SELECT`: untuk memilih kolom mana saja yang dipilih untuk dijumlahkan.
`AVG(Gaji)`: untuk menghitung rata-rata dari data yang ada pada kolom yang dipilih. Gaji adalah nama kolom dipilih untuk dihitung rata-ratanya.
`AS`: untuk mengganti nama dari kolom hasil `AVG`(Gaji) untuk sementara.
`Rata-rata`: nama sementara dari perintah `AS`
`FORM pegawai`: untuk memilih dari tabel mana yang kolom datanya yang akan digunakan , pegawai adalah nama dari tabel yang dipilih .

**Kesimpulannya :**
Query ini memberikan informasi tentang rata-rata gaji pegawai di tabel `pegawai`. Ini berguna untuk analisis kompensasi, seperti memahami seberapa besar gaji rata-rata yang dibayar kepada pegawai dalam organisasi. 

### contoh 10
**Contoh Program :**
~~~sql
SELECT AVG(Gaji) AS GajiRataMgr
-> FROOM pegawai
-> WHERE Jabatan = 'Manajer' ;
~~~

**Hasilnya :**
![](aset/basdat10.jpg)

**Analisisnya:**
 `SELECT`: untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
 `AVG(Gaji)`: untuk menghitung rata-rata dari data yang ada pada kolom yang dipilih. Gaji adalah nama kolom dipilih untuk dihitung rata-ratanya.
 `AS`: untuk mengganti nama dari kolom hasil `AVG`(Gaji) untuk sementara.
 `GajiRataMgr`:nama sementara dari perintah `AS`
 `FORM pegawai`: untuk memilih dari tabel mana yang kolom datanya yang akan digunakan , pegawai adalah nama dari tabel yang dipilih .
 `WHERE`: kondisi yang harus dipenuhi oleh suatu kolom agar datanya bisa dihitung rata-ratanya 
 `(Jabatan = "Manajer)`:  kondisi dari `WHERE`. Barisan data yang kolom jabatannya Manajer akan dihitung rata-rata kolom Gajinya.
 
**Kesimpuannya :**
Kesimpulan dari query SQL ini adalah bahwa query digunakan untuk menghitung dan menampilkan rata-rata gaji dari semua pegawai yang memiliki jabatan 'Manajer'. Dengan menyaring data berdasarkan jabatan dan menggunakan fungsi agregat `AVG`, query ini menghasilkan satu nilai yang menunjukkan nilai rata-rata gaji dalam kelompok jabatan tersebut, memberikan wawasan tentang kompensasi rata-rata untuk manajer di organisasi.


### contoh 11
**Contoh Program :**
~~~sql
SELECT NoCab, AVG(Gaji) AS RataGaji
	-> FROM pegawai
	-> GROUP BY NoCab;
~~~
**Hasilnya:**
![](aset/basdat11.jpg)

**Analisisnya:**
`SELECT`: untuk memilih kolom mana saja yang dipilih untuk ditampilkan, dihitung.
`NoCab`: adalah nama kolom yang ingin ditampilkan.
`AVG(Gaji)`: untuk menghitung rata-rata dari data yang ada pada kolom yang dipilih. Gaji adalah nama kolom dipilih untuk dihitung rata-ratanya.
`AS`: untuk mengganti nama dari kolom hasil `AVG`(Gaji) untuk sementara.
`RataGaji`:nama sementara dari perintah `AS`.
`FORM pegawai`: untuk memilih dari tabel mana yang kolom datanya yang akan digunakan , pegawai adalah nama dari tabel yang dipilih .
 `GROUP BY`: untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
  `NoCab`: nama kolom yang dipilih untuk datanya dikelompokkan.
  
**Kesimpulannya :**
Query ini menghitung rata-rata gaji pegawai untuk setiap cabang yang ada, memungkinkan analisis gaji berdasarkan lokasi atau cabang tertentu. Hasilnya memberikan wawasan tentang kompensasi rata-rata di masing-masing cabang organisasi.

### contoh 12
**Contoh Program :**
~~~sql
	SELECT NoCab, AVG(Gaji) AS RataGaji
	-> FROM pegawai
	-> GROUP BY NoCab HAVING NoCab = 'C101' OR NoCab = 'C102';
~~~
**Hasilnya :**
![](aset/basdat12.jpg)

**Analisisnya :**
`SELECT`: untuk memilih kolom mana saja yang dipilih untuk ditampilkan, dihitung.
`NoCab`: kolom yang dipilih untuk ditampilkan.
`AVG(Gaji)`: untuk menghitung rata-rata dari data yang ada pada kolom yang dipilih. Gaji adalah nama kolom dipilih untuk dihitung rata-ratanya.
`AS`: untuk mengganti nama dari kolom hasil `AVG`(Gaji) untuk sementara.  
`RataGaji`:nama sementara dari perintah `AS`.
`FORM pegawai`: untuk memilih dari tabel mana yang kolom data kolomnya yang ingin digunakan , pegawai adalah nama dari tabel yang dipilih .
`GROUP BY`: untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
`NoCab`: nama kolom yang dipilih untuk datanya dikelompokkan.
`HAVING`: kondisi yang harus dipenuhi oleh suatu kelompok data.
`NoCab = 'C101' OR NoCab = 'C102`: merupakan kondisi dari `HAVING`.

**Kesimpulannya :**
Query ini menghitung dan menampilkan rata-rata gaji untuk pegawai di cabang-cabang tertentu ('C101' dan 'C102'). Hasilnya menunjukkan rata-rata gaji hanya untuk cabang yang sesuai dengan kondisi yang ditentukan.

### contoh 13
**Contoh Program :**
~~~sql
SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
	-> FROM pegawai;
~~~

**Hasilnya :**
![](aset/basdat13.jpg)

**Analisisnya :**
`SELECT`: untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
`MAX(Gaji)`: untuk menampilkan nilai maksimum atau terbesar/tertinggi dari suatu data dalam kolom yang dipilih, Gaji adalah nama kolom dipilih.
`AS GajiTerbesar`: untuk mengganti nama dari kolom hasil `MAX(Gaji)`menjadi nama sementara yaitu GajiTerbesar.
`MIN(Gaji`: untuk menampilkan nilai minuman atau terkecil/terendah dari suatu data kolom yang dipilih. `Gaji`adalah nama kolom yang dipilih .
`AS GajiTerkecil`: untuk mengganti nama dari kolom hasil `MIN(Gaji` menjadi gaji terkecil untuk sementara.
`FORM pegawai`: untuk memilih dari tabel mana yang kolom data kolomnya yang ingin ditampikan.

**Kesimpulannya :**
Query ini memberikan informasi tentang gaji tertinggi dan terendah di tabel `pegawai`. Hasilnya memudahkan pemahaman tentang rentang gaji dalam dataset yang ada.


### contoh 14
**Contoh Program :**
~~~sql
SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
	-> FROM pegawai;
	-> WHERE Jabatan = 'Manajer';
~~~
**Hasilnya :**
![](aset/basdat14.jpg)

**Analisisnya :**
Penjelasan ; 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
- `MAX(Gaji)` = untuk menampilkan nilai terbesar dari suatu data dalam kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiTerbesar` = untuk mengganti nama dari kolom hasil MAX(Gaji) menjadi GajiTerbesar untuk sementara.
- `MIN(Gaji)` =  untuk menampilkan nilai terkecil dari suatu data dalam kolom yang dipilih. Sedangkan gaji adalah nama kolom yang dipilih.
- `AS GajiTerkecil` = untuk mengganti nama dari kolom hasil MIN(Gaji) menjadi GajiTerkecil untuk sementara.
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnya ingin ditampilkan.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `(Jabatan = 'Manajer')` = kondisi dari WHERE yang harus dipenuhi. Barisan data yang kolom Jabatannya berisi manajeeer akan ditampilkan kolom Gajinya.

Kesimpulan : 
Jabatan Manajer yang memiliki nilai maksimum adalah 6250000 kolom hasil MAX nya diubah jadi GajiTerbesar. sedangkan nilai minimumnya adalah 5250000 kolom hasil MIN nya diubah menjadi GajiTerkecil.


### contoh 15
**Contoh Program :**
~~~sql
SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
	-> FROM pegawai
	-> GROUP BY NoCab;
~~~
**Hasilnya :**
![](aset/basdat15.jpg)

**Analisisnya :**
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
- `NoCab` = nama kolom yang ingin ditampilkan.
- `MAX(Gaji)` = untuk menampilkan nilai terbesar dari suatu data dalam kolom yang dipilih. Sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiTerbesar` = untuk mengganti nama kolom hasil MAX(Gaji) menjadi GajiTerbesar untuk sementara.
- `MIN(Gaji)` = untuk menampilkan nilai terkecil dari suatu data dalam kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiTerkecil` = untuk mengganti nama kolom hasil MIN(Gaji) menjadi GajiTerkecil untuk sementara.
- `FROM pegawai` = untuk memilih dari tabel mamna yang data kolomnya ingin ditampilkan. sedangkan pegawai adalah nama tabel yang dipilih untuk ditampilkan.
- `GROUP BY` = untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
- `NoCab` = nama kolom yang ingin dikelompokkan.

Kesimpulan : 
Masing-masing NoCab dicari nilai maksimum dan minimumnya. mulai dari "C101", "C102", "C103" dan "C104" dan nama hasil kolomnya diubah jadi GajiTerbesar dan GajiTerkecil.


### contoh 16
~~~sql
SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
	-> FROM pegawai
	-> GROUP BY NoCab HAVING COUNT(NIP) >= 3;
~~~
**Hasilnya :**
![](aset/basdat16.jpg)

**Analisisnya :**
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
- `NoCab` = nama kolom yang ingin ditampilkan.
- `MAX(Gaji)` = untuk menampilkan nilai terbesar dari suatu data dalam kolom yang dipilih. Sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiTerbesar` = untuk mengganti nama kolom hasil MAX(Gaji) menjadi GajiTerbesar untuk sementara.
- `MIN(Gaji)` = untuk menampilkan nilai terkecil dari suatu data dalam kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiTerkecil` = untuk mengganti nama kolom hasil MIN(Gaji) menjadi GajiTerkecil untuk sementara.
- `FROM pegawai` = untuk memilih dari tabel mamna yang data kolomnya ingin ditampilkan. sedangkan pegawai adalah nama tabel yang dipilih untuk ditampilkan.            nmmmmmmnm m                                                                     nnnnn       
- `GROUP BY` = untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
- `NoCab` = nama kolom yang ingin dikelompokkan.
- `HAVING` = kondisi yang harus dipenuhi oleh suatu kelompok data.
- `(COUNT(NIP) >= 3)` = kondisi dari HAVING. hanya hasil hitung kolom NIP yang lebih dari atau sama dengan 3 yang muncul.

Kesimpulan : 
seperti contoh 4 yang mempunyai hasil hitung lebih dari atau sama dengan 3 adalah NoCab "C102". jadi hanya itu yang dicari nilai maksimum dan minimumnya pada kolom Gaji.

### contoh 17
**Contoh Program :**
~~~sql
SELECT COUNT(NIP) AS JumlahPegawai, SUM(Gaji) AS TotalGaji,
	-> AVG(Gaji) AS RataGaji, MAX(Gaji) AS GajiMaks, MIN(Gaji) AS GajiMin
	-> FROM pegawai ;
~~~
**Hasilnya :**
![](aset/basdat17.jpg)

**Analisisnya :**
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
- `COUNT(NIP)` = untuk menghitung jumlah barisan data yang ada pada kolom yang dipilih.
- `AS JumlahPegawai` = untuk mengganti nama kolom hasil COUNT(NIP) menjadi JumlahPegawai.
- `SUM(Gaji)` = untuk menjumlah data yang ada pada kolom yang dipilih. sedangkan gaji adalah nama kolom yang dipilih.
- `AS TotalGaji` = untuk mengganti nama kolom hasil SUM(Gaji) menjadi TotalGaji.
- `AVG(Gaji)` = untuk menghitung rata-ratanya suatu data dalaml kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih untuk dihitung.
- `AS RataGaji` = untuk mengganti nama kolom hasil AVG(Gaji) menjadi RataGaji.
- `MAX(Gaji)` = untuk menampilkan nilai terbesar dari suatu data dalam kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiMaks` = untuk mengganti nama dari kolom hasil MAX(Gaji) menjadi GajiMaks untuk sementara.
- `MIN(Gaji)` = untuk menampilkan nilai terkecil dari suatu kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiMin` = untuk mengganti nama dari kolom hasil MIN(Gaji) menjadi GajiMin untuk sementara.
- `FROM pegawai` = untuk memilih tabel mana yang dipilih untuk ditampilkan. sedangkan pegawai adalah nama tabel yang dipilih.

Kesimpulan : 
Dihitung berapa NIP, dijiumlahkan semua data pada kolom Gaji, dihitung Rata-rata dari kolom Gaji, ditampilkan nilai terbesar pada kolom Gaji dan nilai terkecil dalam kolom Gaji.

### contoh 18 
**Contoh Program :**
~~~sql
SELECT COUNT(NIP) AS JumlahPegawai, SUM(Gaji) AS TotalGaji,
	-> AVG(Gaji) AS RataGaji, MAX(Gaji) AS GajiMaks, MIN(Gaji) AS GajiMin
	-> FROM pegawai
	-> WHERE Jabatan = 'Staf' OR jabatan = 'Sales'
	-> GROUP BY Nocab HAVING SUM(Gaji) <= 2600000;
~~~
**Hasilnya :**
![](aset/basdat18.jpg)

**Analisisnya :**
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
- `COUNT(NIP)` = untuk menghitung jumlah barisan data yang ada pada kolom yang dipilih.
- `AS JumlahPegawai` = untuk mengganti nama kolom hasil COUNT(NIP) menjadi JumlahPegawai.
- `SUM(Gaji)` = untuk menjumlah data yang ada pada kolom yang dipilih. sedangkan gaji adalah nama kolom yang dipilih.
- `AS TotalGaji` = untuk mengganti nama kolom hasil SUM(Gaji) menjadi TotalGaji.
- `AVG(Gaji)` = untuk menghitung rata-ratanya suatu data dalaml kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih untuk dihitung.
- `AS RataGaji` = untuk mengganti nama kolom hasil AVG(Gaji) menjadi RataGaji.
- `MAX(Gaji)` = untuk menampilkan nilai terbesar dari suatu data dalam kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiMaks` = untuk mengganti nama dari kolom hasil MAX(Gaji) menjadi GajiMaks untuk sementara.
- `MIN(Gaji)` = untuk menampilkan nilai terkecil dari suatu kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiMin` = untuk mengganti nama dari kolom hasil MIN(Gaji) menjadi GajiMin untuk sementara.
- `FROM pegawai` = untuk memilih tabel mana yang dipilih untuk ditampilkan. sedangkan pegawai adalah nama tabel yang dipilih.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu kolom.
- `(Jabatan = 'Staf' OR Jabatan = 'Sales')` = kondisi  dari WHERE. jadi hanya Jabatan staf atau Jabatan sales, hanya salah satunya saja yang harus dipenuhi agar bisa tampil. OR (hanya salah satu kondisi yang harus dipenuhi).
- `GROUP BY` = untuk mengelompokkan data sesuai dengan kolom yang ingin dipilih.
- `NoCab` = nama kolom yang dipilih untuk dikelompokkan.
- `HAVING` = kondisi yang harus dipenuhi oleh suatu kelompok data agar bisa ditampilkan.
- `(SUM(Gaji) <= 2600000)` = kondisi dari having. hanya data yang hasil jumlahan gajinya kurang dari atau sama dengan 2600000 yang bisa tampil.

Kesimpulan : 
Ada 2 barisan data yang memenuhi kondisi `<= 2600000`. Adapun kondisi WHERE yang juga dipenuhi oleh barisan dta tersebut. masing-masing nama nya diubah sesuai perintah AS.
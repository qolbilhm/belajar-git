---
undefined: ""
File: Basis_Data_XII/Agregasi dengan GROUP BY & HAVING.md
---
## membuat database baru di mysql
1. Buka apk XAMPP.
2. Klik **Start** pada MySQL.
3. Klik **Shell.**
4. Lalu akan muncul cmd dan masuk melalui akun administrator. Ketik **mysql -u root -p** lalu klik enter.
```SQL
mysql -u root -p
```
5. Ketika kita ingin membuat database dengan nama `company_namakita` maka kita ketikkan di mysql seperti contoh di bawah
Contoh kode : 
```SQL
mysql > CREATE DATABASE company_nurfadila
```

![DATABASE_NURFADILA|450](assets/database_tugas1.png)
Penjelasan : 
- `CREATE` : perintah `CREATE` digunakan untuk membuat berbagai objek dalam basis data.
- `DATABASE` : adalah koleksi data yang sistematis dan sistematis yang disimpan secara elektronik
- `company_nurfadila` : adalah nama database yang ingin kita buat.
Kesimpulan : 
Jadi ketika kita ingin membuatt database baru kita bisa mengetikkan kode sql `CREATE DATABASE` lalu klik enter maka database kita berhasil di buat.

## membuat tabel dalam database

Ketentuan tabel: tipe data dan constraintnya
- NIP: int & primary key
- NDep: varchar & NOT NULL
- NBlk: varchar
- JK: enum, NOT NULL
- Alamat: text, NOT NULL
- Telp: varchar, NOT NULL
- Jabatan: enum
- Gaji: BIGINT, NOT NULL
- NoCab: Varchar, NOT NULL
Kode : 
```SQL
CREATE TABLE pegawai (
nama_kolom1 tipe data(ukuran) [tipe_constraint],
nama_kolom2 tipe data(ukuran) [tipe_constraint],
nama_kolom3 tipe data(ukuran) [tipe_constraint]
);
```

![STRUKTUR_TABEL_PEGAWAI|390](assets/database_tugas3.png)

![STRUKTUR_TABEL_PEGAWAI|580](assets/database_tugas4.png)

Penjelasan : 
- `CREATE TABLE` : perintah `CREATE TABLE` adalah kode yang digunakan untuk membuat table dalam mysql.
- `pegawai` : adalah nama table yang kita buat
- `NIP` : NIP, atau **Nomor Induk Pegawai**, adalah sebuah kode identifikasi unik yang diberikan kepada pegawai negeri sipil (PNS) di Indonesia
- `int(3)` : adalah tipe data yang digunakan untuk bilangan bulat. sedangkan angka 2 adalalh nilai maximal yang hanya boleh diisi sampai 2 digit.
- `primary key` : digunakan pada kolom pertama sebagai penanda dalam tabel dan memiliki nilai unik yang tidak sama dengan data yang lain
- `NDep` : NDep adalah singkatan dari Nama depan pegawai.
- `varchar(50)` : adalah tipe data yang digunakan untuk menyimpan karakter alfanumerik. sedangkan angka 50 adalah angka maximal yang nilai nya hanya bisa di isi sampai 50 angka.
- `NOT NULL` : adalah kolom yang tidak boleh kosong, artinya pada kolom 
- `NBlk` : adalah singkatan dari Nama belakang pegawai.
- `varchar(50)` : adalah tipe data yang digunakan untuk menyimpan karakter alfanumerik. sedangkan angka 50 adalah angka maximal yang nilai nya hanya bisa di isi sampai 50 angka.
- `jenis_kelamin` : adalah salah satu struktur data yang berisi dua pilihan yaitu, laki-laki dan perempuan
- `enum(laki-laki, perempuan)` : digunakan untuk mendefinisikan kolom yang hanya dapat berisi nilai-nilai yang telah ditentukan sebelumnya. sedangkan (laki-laki, perempuan) adalah nilai pilihan dari tipe data enum.
- `NOT NULL` : adalah kolom yang tidak boleh kosong, artinya pada kolom pertama atau kolom `id` menandakan bahwa pada kolom tersebut tidak boleh kosong.
- `alamat` : adalah struktur yang menyimpan semua alamat dalam pegawai table
- `text(50)` : digunakan untuk menyimpan data teks yang panjang. sedangkan angka 50 adalah nilai maximal yang membatasi nilai isinya
- `NOT NULL` : adalah kolom yang tidak boleh kosong, artinya pada kolom pertama atau kolom `id` menandakan bahwa pada kolom tersebut tidak boleh kosong.
- `Telp` : adalah struktur yang menyimpan nomor telepon dari table pegawai.
- `varchar(50)` : adalah tipe data yang digunakan untuk menyimpan karakter alfanumerik. sedangkan angka 50 adalah angka maximal yang nilai nya hanya bisa di isi sampai 50 angka.
- `NOT NULL` : adalah kolom yang tidak boleh kosong, artinya pada kolom pertama atau kolom `id` menandakan bahwa pada kolom tersebut tidak boleh kosong.
- `jabatan` : adalah salah satu struktur table yang menyimpan apa saja jabatan dari setiap pegawai yang ada pada table pegawai.
- `enum(manajer, staf, sales)` : digunakan untuk menyimpan satu nilai dari sekumpulan pilihan yang telah ditentukan sebelumnya, sedangkan (manajer, staf, sales) adalah nilai valid yang memastikan bahwa hanya salah satu dari ketiga nilai ini yang dapat di pilih.
- `Gaji` : adalah salah satu struktur table yang menyimpan jumlah gaji setiap pegawai yang ada dalam table pegawai.
- `BIGINT` : digunakan untuk menyimpan nilai angka yang sangat besar di banding dengan int.
- `NOT NULL` : adalah kolom yang tidak boleh kosong, artinya pada kolom pertama atau kolom `id` menandakan bahwa pada kolom tersebut tidak boleh kosong.
- `NoCab` : digunakan untuk menyimpan informasi tentang cabang atau lokasi spesifik di mana seorang pegawai terdaftar atau ditempatkan.
- `varchar(50)` : adalah tipe data yang digunakan untuk menyimpan karakter alfanumerik. sedangkan angka 50 adalah angka maximal yang nilai nya hanya bisa di isi sampai 50 angka.
- `NOT NULL` : adalah kolom yang tidak boleh kosong, artinya pada kolom pertama atau kolom `id` menandakan bahwa pada kolom tersebut tidak boleh kosong.

Kesimpulan : 
- Tabel `pegawai` dirancang untuk menyimpan berbagai informasi tentang pegawai, termasuk ID unik, departemen, blok, jenis kelamin, alamat, nomor telepon, jabatan, gaji, dan cabang.
- Tipe data dan constraint yang digunakan dalam tabel memastikan integritas data, validasi input, dan penyimpanan data yang sesuai dengan kebutuhan aplikasi.
- Penggunaan `ENUM` dan `BIGINT` membantu dalam menyimpan data dengan nilai yang terbatas dan nilai numerik besar, masing-masing, sementara `VARCHAR` dan `TEXT` digunakan untuk menyimpan teks dengan panjang variabel.

## memasukkan isi data dalam tabel pegawai
Kode : 
```SQL
 INSERT INTO nama_tabel
	-> VALUES (nilai1, nilai2, nilai3, nilai4),
	-> (nilai1, nilai2, nilai3, nilai4),
	-> (nilai1, nilai2, nilai3, nilai4);
```

![DATA_TABLE_PEGAWAI](assets/database_tugas5.png)

### Penjelasan : 
#### kolom 1
- `INSERT INTO` : kode ini berfungsi untuk memasukka  data atau suatu nilai ke dalam table
- `pegawai` : tempat di mana data pegawai akan dimasukkan.
- `10107` : adalah Nomor Induk Pegawai dalam table pegawai kolom 1
- `Emya` : adalah Nama depan pegawai.
- `Salsalina` : adalah Nama belakang pegawai.
- `Perempuan`  : adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `jl.Suci 78 Bandung` : adalah alamat tempat tinggal pegawai.
- `022-555768` : adalah Nomor telepon pegawai.
- `Manajer` : adalah Jabatan pegawai, yang menggunakan tipe data ENUM ('manajer', 'staf', 'sales').
- `5250000` : adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C101` : adalah Nomor cabang tempat pegawai bekerja.
#### kolom 2
- `10176`: adalah NIP dari pegawai.
- `Diah`: adalah Nama depan pegawai.
- `Wahyuni`: adalah Nama belakang pegawai.
- `Perempuan` : adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `Jl.Maluku 56 Bandung` : adalah alamat tempat tinggal pegawai.
- `022-555934` : adalah Nomor telepon pegawai.
- `Sales` : adalah Jabatan pegawai, yang menggunakan tipe data ENUM ('manajer', 'staf', 'sales').
- `2500000` : adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C101` : adalah Nomor cabang tempat pegawai bekerja.
#### kolom 3
- `10246` : adalah NIP dari pegawai.
- `Dian` : adalah Nama depan pegawai.
- `Anggraini` : adalah Nama belakang pegawai.
- `Perempuan` : adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `Jl.Mawar 5 Semarang` : adalah alamat tempat tinggal pegawai.
- `024-555102` : adalah Nomor telepon pegawai.
- `Sales` : adalah Jabatan pegawai, yang menggunakan tipe data ENUM ('manajer', 'staf', 'sales').
- `2750000` : adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C103` : adalah Nomor cabang tempat pegawai bekerja.
#### kolom 4
- `10252` : adalah NIP dari pegawai.
- `Antoni` : adalah Nama depan pegawai.
- `Irawan` : adalah Nama belakang pegawai.
- `Laki-laki` : adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `Jl.A.Yani 15 Jakarta` : adalah alamat tempat tinggal pegawai.
- `021-555888` :  adalah Nomor telepon pegawai.
- `Manajer` : adalah Jabatan pegawai, yang menggunakan tipe data ENUM ('manajer', 'staf', 'sales').
- `5750000` : adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C102` : adalah Nomor cabang tempat pegawai bekerja.
#### kolom 5
- `10307` : adalah NIP dari pegawai.
- `Erik` :  adalah Nama depan pegawai.
- `Andrian` : adalah Nama belakang pegawai.
- `Laki-laki` :  adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `Jl.Manggis 5 Semarang` : adalah alamat tempat tinggal pegawai.
- `024-555236` :  adalah Nomor telepon pegawai.
- `Manajer` : adalah Jabatan pegawai, yang menggunakan tipe data ENUM ('manajer', 'staf', 'sales').
- `2650000` : adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C103` : adalah Nomor cabang tempat pegawai bekerja.
#### kolom 6
- `10314` : adalah NIP dari pegawai.
- `Ayu` :  adalah Nama depan pegawai.
- `Rahmadani` : adalah Nama belakang pegawai.
- `Perempuan` : adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `Jl.Malaka 342 Jakarta` : adalah alamat tempat tinggal pegawai.
- `022-555098` : adalah Nomor telepon pegawai.
- `Sales` : adalah Jabatan pegawai, yang menggunakan tipe data ENUM ('manajer', 'staf', 'sales').
- `1950000` : adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C102` : adalah Nomor cabang tempat pegawai bekerja.
#### kolom 7
- `10324` : adalah NIP dari pegawai.
- `Martin` : adalah Nama depan pegawai.
- `Susanto` :  adalah Nama belakang pegawai.
- `Laki-laki` : adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `Jl.Bima 51 Jakarta` : adalah alamat tempat tinggal pegawai.
- `021-555785` : adalah Nomor telepon pegawai.
- `Staf` : adalah Jabatan pegawai, yang menggunakan tipe data ENUM ('manajer', 'staf', 'sales').
- `1750000` : adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C102` : adalah Nomor cabang tempat pegawai bekerja.
#### kolom 8
- `10407` : adalah NIP dari pegawai.
- `Rio` : adalah Nama depan pegawai.
- `Gunawan` : adalah Nama belakang pegawai.
- `Laki-laki` : adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `Jl.Melati 356 Surabaya` :  adalah alamat tempat tinggal pegawai.
- `031-555231` : adalah Nomor telepon pegawai.
- `Staf` : adalah Jabatan pegawai, yang menggunakan tipe data ENUM ('manajer', 'staf', 'sales').
- `17250000` :  adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C104` : adalah Nomor cabang tempat pegawai bekerja.
#### kolom 9
- `10415` : adalah NIP dari pegawai.
- `Susan` : adalah Nama depan pegawai.
- `Sumantri` : adalah Nama belakang pegawai.
- `Perempuan` : adalah Jenis kelamin pegawai, yang menggunakan tipe data ENUM ('laki-laki', 'perempuan').
- `Jl.Pahlawan 24 Surabaya` : adalah alamat tempat tinggal pegawai.
- `031-555120` : adalah Nomor telepon pegawai.
- `2650000` : adalah Gaji pegawai, yang menggunakan tipe data `BIGINT`.
- `C104` : adalah Nomor cabang tempat pegawai bekerja.

### Kesimpulan : 
Insert into digunakan untuk memasukkan data ke dalam table pegawai dan dalam pegawai tersebut harus diisi berdasarkan struktur table yang telah kita buat sebelumnya. Pada setiap kolom datanya berisi NIP pegawai, Nama depan pegawai, Nama belakang pegawai, jenis kelamin pegawai, alamat pegawai, nomor telepon pegawai, jabatan pegawai, gaji pegawai, dan juga nomor cabang pegawai. dan pada NIP pegawai atau nomor induk pegawai di tandai dengan primary key agar mempermudah jika kita ingin mencari data pegawai.

## menampilkan tabel pegawai
Kode : 
```SQL
SELECT * FROM nama_table;
```

![DATA_TABLE_PEGAWAI](assets/database_tugas6.png)

Penjelasan : 
- `SELECT` : adalah untuk mengambil data dari tabel di database.
- `*` : digunakan untuk menyatakan bahwa semua kolom atau data dari tabel pegawai ingin di tampilkan.
- `FROM` : berfungsi untuk menunjukkan bahwa tabel yang mana yang ingin kita tampilkan keseluruhan datanya.
- `pegawai` : adalah nama tabel yang ingin kita tunjukkan atau tampilkan kolom beserta data di dalamnya.

kesimpulan : 
Perintah SQL `SELECT * FROM pegawai` digunakan untuk mengambil dan menampilkan semua kolom dan baris dari tabel `pegawai`. Hasilnya akan berupa tabel dengan semua kolom yang ada di tabel , seperti NIP,  NDep,  NBlk,  Jenis Kelamin,  Alamat,  Telp,  Jabatan,  Gaji, dan NoCab, serta semua baris data yang tersimpan dalam tabel tersebut.

## Agregasi dan Having BY
### contoh 1
kode : 
```SQL
SELECT COUNT(NIP) AS JumlahPegawai, COUNT(Jabatan) AS JumlahJabatan FROM pegawai;
```

![contoh_1](assets/contoh1.png)
 Penjelasan : 
- `SELECT` = untuk memilih kolom apa saja yang ingin dipilih (untuk dihitung)
- `COUNT(NIP)` = untuk menghitung jumlah barisan data yang mempunyai isi data dari kolom yang dipilih. sedangkan `(NIP)` adalah nama kolom yang dipilih untuk dihitung.
- `AS` = untuk mengubah nama dari suatu kolom untuk sementara.
- `JumlahPegawai` =merupakan nama ubahan dari perintah AS yang digunakan. sedangkan `pegawai` merupakan nama sementara dari perintah `COUNT(NIP)`. 
- `COUNT(Jabatan)` = untuk menghitung jumlah barisan data yang mempunyai isi data dari kolom yang dipilih. sedangkan `Jabatan` adalah nama kolom yang dipilih untuk dihitung.
- `AS` = untuk mengubah nama dari suatu kolom untuk sementara.
- `JumlahJabatan` = merupakan nama sementara dari perintah `COUNT(Jabatan)`.
- `FROM pegawai` = merupakan dari tabel mana datanya ingin digunakan. sedangkan pegawai adalah nama tabel yang datanya ingin digunakan.

Kesimpulan : 
Karena ada 9 barisan data yang ingin dihitung  adalah kolom NIP, jumlah dari kolom NIP (isi datanya) ada 9, ditampilkan sebagai `JumlahPegawai`. Kolom jabatan juga dihitung, akan tetapi ada satu data yang berisi NULL (kosong), oleh karena itu hanya ada 8 data ditampilkan sebagai `JumlahJabatan`. 

### contoh 2
kode : 
```SQL
SELECT COUNT(NIP) AS JumlahPegawai
    -> FROM pegawai
    -> WHERE NoCab = 'C102';
```

![contoh_2](assets/contoh2.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin dipilih untuk dihitung.
- `COUNT(NIP)` = untuk menghitung jumlah barisan data yang mempunyai data dari kolom yang dipilih. sedangkan `NIP` adalah nama kolom yang dipilih untuk dihitung.
- `AS` = untuk mengubah dari suatu kolom untuk sementara.
- `JumlahPegawai` = nama sementara yang dipilih untuk kolom `COUNT(NIP)`.
- `FROM pegawai` = dari tabel mana datanya akan digunakan. sedangkan pegawai adalah nama tabel yang dipilih untuk digunakan.
- `WHERE` = merupakan kondisi yang harus dipenuhi agar datanya dapat dihitung dengan query `COUNT(NIP)`.
- `(NoCab = C102` = adalah kondisi dari WHERE yang harus dipenuhi, jadi hanya barisan data yang memiliki "C102" di kolom "NoCab" yang bisa dihitung.

Kesimpulan : 
Di 9 barisan data yang ada pada tabel pegawai, kita ingin menghitung jumlah barisan data yang memiliki nilai "C102" pada kolom "NoCab" nya dengan menggunakan COUNT. Jadi yang muncul adalah 3 barisan data . Kita juga ingin mengubah nama dari kolom hasil perintah COUNT secara sementara dengan perintah AS, namanya adalah JumlahPegawai.

### contoh 3
kode : 
```SQL
SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai
    -> FROM pegawai
    -> GROUP BY NoCab;
```

![contoh_3|490](assets/contoh3.png)
Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin dihitung atau ditampilkan.
- `NoCab` = merupakan nama kolom yang ingin ditampilkan.
- `COUNT(NIP)` = untuk menghitung jumlah barisan data yang mempunyai isi data dari kolom yang dipilih. sedangkan NIP adalah nama kolom yang dipilih untuk dihitung.
- `AS` =  untuk mengubah nama dari suatu kolom untuk sementara.
- `Jumlah_Pegawai` = merupakan nama sementara dari kolom hasil `COUNT(NIP)`.
- `FROM pegawai` = dari tabel mana yang data kolomnya ingin digunakan. sedangkan pegawai adalah nama tabel yang dipilih untuk digunakan.
- `GROUP BY` = untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
- `NoCab` = nama kolom yang dipilih untuk datanya di kelompokkan.

Kesimpulan : 
Berdasarkan 9 barisan data, masing-masing nilai dalam kolom NoCab dikelompokkan berdasarkan nilainya sendiri. Jadi NoCab "C101" bersama NoCab yang nilainya sama yaitu "C101". Jadi NoCab yang memiliki "C101" ada 2, "C102" ada 3, "C103" ada 2, "C104" ada 2. Total semuanya 9 sesuai dengan jumlah barisan data yang ada. Adapun nama dari kolom hasil yaitu `Jumlah_Pegawai` dari perintah `AS`.

### contoh 4
kode : 
```SQL
SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai
    -> FROM pegawai
    -> GROUP BY NoCab HAVING COUNT(NIP) >= 3;
```

![contoh_4|570](assets/contoh4.png)
Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin dihitung atau ditampilkan.
- `NoCab` = merupakan nama kolom yang ingin ditampilkan.
- `COUNT(NIP)` = untuk menghitung jumlah barisan data yang mempunyai isi data dari kolom yang dipilih. sedangkan NIP adalah nama kolom yang dipilih untuk dihitung.
- `AS` = untuk mengubah nama dari suatu kolom untuk sementara.
- `Jumlah_Pegawai` = nama sementara dari kolom hasil `COUNT(NIP)`. 
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnnya ingin digunakan. sedangkan pegawai adalah nama tabel yang dipilih untuk digunakan.
- `GROUP BY` = untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
- `NoCab` = nama kolom yang dipilih untuk dikelompokkan datanya.
- `HAVING` = untuk menentukan kondisi (yang harus dipenuhi) oleh suatu kelompok data agar bisa ditampilkan.
- `(COUNT(NIP) >= 3)` = merupakan kondisi yang harus dipenuhi oleh suatu kelompok data. Jadi hanya kelompok data yang hasil hitungannya lebih atau sama dengan 3.

Kesimpulan : 
seperti sebelumnya, ada 9 barisan data dibagi sesuai NoCab nya masing-masing. Namun yang ingin ditampilkan adalah hasil hitungan yang lebih dari atau sama dengan 3. Yaitu NoCab "C102" yang ada 3. yang lain "C101" ada 2, "C103" ada 2, "C104" ada 2.

### contoh 5
kode : 
```SQL
SELECT SUM(Gaji) AS Total_Gaji
    -> FROM pegawai;
```

![contoh_5|500](assets/contoh5.png)
Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk dijumlahkan.
- `SUM(Gaji)` = untuk menghitung jumlah data (khusus angka) pada kolom yang dipilih. sedangkan gaji merupakan nama kolom yang dipilih untuk dihitung jumlah isi datanya.
- `AS` = untuk mengganti nama kolom hasil dari SUM(Gaji) untuk sementara.
- `Total_Gaji` = merupakan nama sementara dari perintah AS.
- `FROM pegawai` = untuk memilih dari tabel mana yang kolom datanya akan digunakan. sedangkan pegawai adalah nama dari tabel yang dipilih.

Kesimpulan : 
kolom Gaji yang isi datanya berupa angka-angka, semuanya di jumlahkan menjadi satu seperti di totalkank (sama seperti matematika pada umumnya). Dan hasilnya adalah 30575000. Adapun nama kolom dari hasil jumlah tersebut diubah dari SUM(Gaji) menjadi Total_Gaji.

### contoh 6
kode : 
```SQL
SELECT SUM(Gaji) AS Gaji_Manajer
    -> FROM pegawai
    -> WHERE Jabatan = 'Manajer';
```

![contoh_6|480](assets/contoh6.png)
Penjelasan : 
- `SELECT` : untuk memilih kolom mana saja yang dipilih untuk dijumlahkan.
- `SUM(Gaji)` = untuk menghitung jumlah isi data (khusus angka) pada kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilh untuk dijumlahkan isi datanya.
- `AS` = untuk mengganti nama dari kolom hasil s\SUM(Gaji) secara semnetara.
- `Gaji_Manajer` = merupakan nama sementara dari perintah AS.
- `FROM pegawai` = untuk memilih dari tabel mana yang kolom datanya akan digunakan. sedangkan pegawai adalah nama dari tabel yang dipilih.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu kolm agar datanya bisa dijumlah.
- `Jabatan = "manajer"` = merupakan kondisi dari WHERE. hanya barisan data yang kolom jabatannya berisi manajer yang kolom gajinya bisa dijumlahkan.

Kesimpulan : 
barisan data yang kolom jabatannya berisi manajer akan dijumlahkan kolom gajinya menrjadi 17250000. Jadi, hanya beberapa kolom saja yang dijumlahkan

### contoh 7
kode : 
```SQL
SELECT NoCab, SUM(Gaji) AS TotalGaji
    -> FROM pegawai
    -> GROUP BY NoCab;
```

![contoh_7|480](contoh7.png)
Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan/dijumlahkan
- `NoCab` = adalah nama kolom yang ingin ditampilkan.
- `SUM(Gaji)` = untuk menghitung jumlah data (khusus angka) pada kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih untuk dijumlahkan isi datanya.
- `AS` = untuk mengganti nama dari kolom hasil SUM(Gaji) untuk sementara.
- `TotalGaji` =  merupakan nama sementara dari perintah AS.
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnya akan digunakan. sedangkan pegawai adalah nama tabel yang dipilih.
- `GROUP BY` = untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
- `NoCab` = nama kolom yang datanya dipilih untuk dikelompokkan.

Kesimpulan : 
Jadi, berdasarkan kolom NoCab, barisan data yang kolom NoCab nya berisi "C102" maka kolom Gaji dari barisan data itu dijumlahkan bersama barisan data yang memiliki NoCab "C101" juga. Maka kolom Gaji dijumlahkan sesuai dengan kolom NoCab nya masing-masing, mulai dari "C101" memiliki 2 kolom Gaji yang bisa dijumlahkan. sama dengan "C103" dan "C104". Adapun "C102" memiliki 3 kolom Gaji yang dapat dijumlahkan. TotalGaji merupakan hasil perintah dari `AS` untuk mengubah nama kolom hasil SUM(Gaji).

### contoh 8
kode : 
```SQL
SELECT NoCab, SUM(Gaji) AS Total_Gaji
    -> FROM pegawai
    -> GROUP BY NoCab HAVING SUM(Gaji) >= 8000000;
```

![contoh_8|490](assets/contoh8.png)
Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan/dijumlahkan.
- `NoCab` = nama kolom yang dipilih untuk ditampilkan.
- `SUM(Gaji)` = untuk menghitung jumlah data (khusus data) pada kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih untuk dijumlahkan isi datanya.
- `AS` = untuk mengganti nama dari kolom hasil SUM(Gaji) untuk sementara.
- `Total_Gaji` = nama sementara  dari perintah AS.
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnya ingin digunakan. sedangkan pegawai adalah nama dari tabel yang dipilih.
- `GROUP BY` = untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
- `NoCab` =  nama kolom yang dipilih untuk datanya dikelompokkan. 
- `HAVING` = kondisi yang harus dipenuhi oleh suatu kelompok data agar bisa ditampilkan.
- `(SUM(Gaji) >= 8000000)` = kondisi dari HAVING, hasil dari penjumlahan Gaji yang hanya bisa ditampilkan adalah hasil yang lebih dari atau sama dengan 8000000.

Kesimpulan : 
Sama seperti sebelumnya, tetapi NoCab yang memenuhi kondisi tersebut hanyalah  "C102" dan "C103" karena hasil jumlah kolom Gaji nya lebih dari atau sama dengan  8000000. Adapun hasil kolom SUM(Gaji) di ganti jadi Total_Gaji.

### contoh 9
kode : 
```SQL
SELECT AVG(Gaji) AS Rata_rata
    -> FROM pegawai;
```

![contoh_9|450](assets/contoh9.png)
Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan
- `AVG(Gaji)` = untuk menghitung rata-rata dari data yang ada pada kolom yang dipilih. Sedangkan Gaji adalah nama kolom yang dipilih untuk dihitung rata-ratanya.
- `AS` = untuk mengganti nama dari kolom hasil AVG(Gaji) untuk sementara.
- `Rata-rata` = nama sementara dari perintah AS.
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnya ingin digunakan. sedangkan pegawai adalah nama dari tabel yang dipilih.

Kesimpulan : 
3397222.222 merupakan hasil rata-rata dari semua 9 barisan data pada kolom Gaji. Adapun nama kolom hasil dari AVG(Gaji) yaitu Rata-rata.

### contoh 10
kode : 
```SQL
SELECT AVG(Gaji) AS GajiRataMgr
    -> FROM pegawai
    -> WHERE Jabatan = 'Manager';
```

![contoh_10|450](assets/contoh10.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
- `AVG(Gaji)` = untuk menghitung rata-rata dari data yang ada pada kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipililh untuk dihitung  rata-ratanya.
- `AS` = untuk mengganti nama dari kolom hasil `AVG(Gaji)` untuk sementara.
- `GajiRataMgr` = nama sememntara dari perintah AS.
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnya ingin digunakan. sedangkan pegawai adalah nama dari tabel yang dipilih.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu kolom agar datanya bisa dihitung rata-ratanya.
- `(Jabatan = 'manajer')` = kondisi dari WHERE. Barisan data yang kolom jabatannya Manajer akan dihitung rata-rata kolom Gaji nya.

Kesimpulan : 
5750000.0000 merupakan hasil hitung rata-rata dari barisan data yang memiliki manajer di kolom Gaji nya dihitung.


### contoh 11
kode : 
```SQL
SELECT NoCab, AVG(Gaji) AS RataGaji
    -> FROM pegawai
    -> GROUP BY NoCab;
```

![contoh_11|450](assets/contoh11.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan, dihitung.
- `NoCab` =  kolom yang dipilih untuk ditampilkan.
- `AVG(Gaji)` = untuk menghitung rata-rata dari data yang ada pada kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih untuk dihitung rata-ratanya.
- `AS` = untuk mengganti nama dari kolom hasil AVG(Gaji) untuk sementara.
- `RataGaji` = adalah nama sementara dari perintah AS.
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnya ingin digunakan. sedangkan pegawai adalah nama dari tabel yang dipilih.
- `GROUP BY` = untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan.
- `NoCab` = nama kolom yang dipilih untuk datanya dikelompokkan.

Kesimpulan : 
Hampir sama seperti contoh 7, masing-masing kolom NoCab dihtung rata-ratanya sesuai dengan isi NoCab, jadi yang "C101" dihitung dengan "C101" yang lainnya juga (yang sama). Adapun RataGaji merupakan nama sementara dari kolom hasil AVG(Gaji).


### contoh 12
kode : 
```SQL
SELECT NoCab, AVG(Gaji) AS RataGaji
    -> FROM pegawai
    -> GROUP BY NoCab HAVING NoCab = 'C101' OR NoCab = 'C102';
```

![contoh_12|450](assets/contoh12.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan, dihitung.
- `NoCab` = kolom yang dipilih untuk ditampilkan.
- `AVG(Gaji)` = untuk menghitung rata-rata dari data yang ada pada kolom yang dipilih. sedangkan Gaji adalah kolom yang dipilih untuk dihitung rata-ratanya.
- `AS` = untuk mengganti nama dari kolom hasil AVG(Gaji) untuk sementara.
- `RataGaji` = nama sementara dari perintah AS.
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnya ingin digunakan. sedangkan pegawai adalah nama dari tabel yang dipilih.
- `GROUP BY` = untuk mengelompokkan data berdasarkan nilai data yang telah ditentukan pada kolom yang dipilih.
- `NoCab` = nama kolom yang dipilih untuk datanya dikelompokkan.
- `HAVING` = kondisi yang harus dipenuhi oleh suatu kelompok data.
- `(NoCab = 'C101' OR NoCab = 'C102'` = merupakan kondisi dari having. Jadi kolom NoCab yang memiliki "C101" atau "C102" yang hanya akan ditampilkan. sedangkan OR adalah kondisi yang hanya salah satu dataya harus dipenuhi.

Kesimpulan : 
Jadi pada NoCab akan dihitung rata-rata gaji nya. Rata-rata gaji nya yang dihitung adalah pada NoCab "C101" dan "C102" dan rata-rata gaji yang ada pada "C101" adalah 3875000.0000 dan rata-rata gaji yang ada pada NoCab "C102" adalah 3150000.0000.
### contoh 13
kode : 
```SQL
SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
    -> FROM pegawai;
```

![contoh_13|600](assets/contoh13.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang dipilih untuk ditampilkan.
- `MAX(Gaji)` = untuk menampilkan nilai maksimum atau terbesar/tertinggi dari suatu data dalam kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiTerbesar` = untuk mengganti nama dari kolom hasil MAX(Gaji) menjadi nama sementaranya yaitu GajiTerbesar.
- `MIN(Gaji)` = untuk menampilkan nilai minimum atau terkecil/terendah dari suatu data kolom yang dipilih. sedangkan Gaji adalah nama kolom yang dipilih.
- `AS GajiTerkecil` = untuk  mengganti nama dari kolom hasil MIN(Gaji) menjadi GajiTerkecil untuk sementara.
- `FROM pegawai` = untuk memilih dari tabel mana yang data kolomnya ingin ditampilkan. sedangkan pegawai adalah nama tabel yang dipilih.

Kesimpulan : 
Jadi daari 9 nilai yang ada dikolom Gaji, Gaji maksimumnya adalah 6250000 dan namanya diubah menjadi GajiTerbesar. Gaji minimumnya adalah 1725000 dan namanya diubah menjadi GajiTerkecil.

### contoh 14
kode : 
```SQL
SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
    -> FROM pegawai
    -> WHERE Jabatan = 'Manajer';
```

![contoh-14|590](assets/contoh14.png)

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
kode : 
```SQL
SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
    -> FROM pegawai
    -> GROUP BY NoCab;
```

![contoh-15|650](assets/contoh15.png)

Penjelasan : 
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
Kode : 
```SQL
SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
    -> FROM pegawai
    -> GROUP BY NoCab HAVING COUNT(NIP) >= 3;
```

![contoh-16|690](assets/contoh16.png)

Penjelasan : 
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
Kode : 
```SQL 
SELECT COUNT(NIP) AS JumlahPegawai, SUM(Gaji) AS TotalGaji,
    -> AVG(Gaji) AS RataGaji, MAX(Gaji) AS GajiMaks, MIN(Gaji) AS GajiMin
    -> FROM pegawai;
```

![contoh-17|600](assets/contoh17.png)

Penjelasan : 
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
Kode : 
```SQL
SELECT COUNT(NIP) AS JumlahPegawai, SUM(Gaji) AS TotalGaji,
    -> AVG(Gaji) AS RataGaji, MAX(Gaji) AS GajiMaks, MIN(Gaji) AS GajiMin
    -> FROM pegawai
    -> WHERE Jabatan = 'Staf' OR Jabatan = 'Sales'
    -> GROUP BY NoCab HAVING SUM(Gaji) <= 2600000;
```

![contoh-18|590](assets/contoh18.png)

Penjelasan : 
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

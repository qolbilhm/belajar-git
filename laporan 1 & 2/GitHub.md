---
sticker: emoji//1f90d
---
 # 1. Instalasi Git Bush
1. Jika ingin mendownload github search Git SCM, gambarnya seperti di bawah ini
![belajar-git](assetrelasi/19.jpg)

setelah muncul seperti diatas klik download
![belajar-git](assetrelasi/21.jpg)

pilih lah download untuk windows dan download Git For Windows versi 64-bit (sesuikan dengan penyimpanan laptop)
![belajar-git](assetrelasi/20.jpg)
setelah download git scm search git-hub dan login atau buat akun jika belum punya akun


# 2. Login/Buat Akun GitHub
1. Buka browser dan ketik github dan klik paling atas yaitu github.com
![\300x300](assetrelasi/20.jpg)

2. Klik Sign in jika belum punya akun dan Sign Up jika telah mempunyai akun
![\300x150](assetrelasi/22.jpg)

3. Login buat akun menggunakan akun google
![](assetrelasi/23.jpg)

4. dan isi keselurahan persyaratan membuat akun
![\400x400](asset/25.jpg)
# 3. Buat Repository di Github
1. Jika telah membuat akun github, klik tambah di bagian kanan pada dasbor akun github anda (klik buat repository baru)
![\2x250](assetrelasi/1.jpg)

2. Jika telah klik repositori baru buatlah  nama repositori yang di inginkan seperti di bawah ini dan jangan lupa untuk di publik agar user lain bisa melihat isi repositori kita
![](assetrelasi/2.jpg)

3. Jika telah seperti di bawah scrool ke bawah lalu klik buat repositori 
![](assetrelasi/3.jpg)

4. jika telah buat repositori baru klik profil, maka akan muncul repositori yang telah di buat
![](assetrelasi/26.JPG)

# 4. Konfigurasi Awal di Git Bash
1. Jika telah sampai buat repositori baru, buka git bush dan ketikkan 
 `git config --list`
![](assetrelasi/34.jpg)

2. Jika telah muncul seperti diatas kita akan mengkonfigurasi email dan username kita yang sama di akun github dengan menggunakan kode seperti ini : 
`git config --global user.name  "username-qolbilhm"` (untuk username dan username di sesuikan dengan username akun github)
`git config --global user.email "email@nqolby29.com"` (untuk email dan email disesuikan dengan email akun github)

![](assetrelasi/8.jpg)

3. Jika telah seperti yang diatas ketikkan kembali 
`git config --list` 
![](assetrelasi/9.jpg)
jika barisan paling bawah username dan email telah muncul maka berarti konfigurasi email dan username telah berhasil

# 5. Akses Folder Proyek di Git Bush
1. mengakses folder proyek di git bush dengan menggunakan kode di bawah ini : 
`cd c:` (klik enter lalu ketik ls)
`ls` (klik enter maka akan muncul semua file-file yang ada pada data C)
![](assetrelasi/10.jpg)

2. Lalu buka file obsidian dengan cara ketik 
`cd obsidian` (lalu klik enter dan ketikkan lagi ls)
`ls` (maka akan muncul semua isi file-file yang ada dalam folder obsidian)
![](assetrelasi/11.jpg)
pada gambar diatas kita bisa lihat di dalam folder obsidian kita telah mempunyai file belajar-git yang telah di buat di repositori

3. Selanjutnya kita akan melihat isi folder proyek dari belajar-git dengan mengetikkan : 
`cd belajar-git` (nama folder proyek)
`ls` (menampilkan isi semua file dalam folder)
![](assetrelasi/12.jpg)
pada gambar diatas kita telah melihat folder proyek yang telah dibuat telah diisi file 'Belajar Git.md'

# 6. Hubungkan Folder Proyek Lokal ke Github
1. Inisialisasi repository, dengan ini kita mengecek repositori kita apakah tersambung atau tidak dengan menggunakan kode di bawah ini : 
`git init` (lalu klik enter)
![](assetrelasi/13.jpg)
jika tampilannya seperti diatas maka telah berhasil terhubung

2. Hubungkan ke repository github, disini kita akan manambahkan atau menghubungkan repositori github dengan menggunakan kode di bawah ini : 
`git remote add origin https://(link yang ada pada repositori github yang telah di buat)` lalu klik enter
![](assetrelasi/28.jpg)

3. Menampilakn status commit / koneksi file ke github apakah status telah terpenuhi atau belum dengan menggunakan kode di bawah ini : 
`git status` (lalu klik enter)
![](assetrelasi/29.jpg)

4. Menambahkan semua file-file baru dengan menggunakan kode di bawah ini :
`git add .` (lalu klik enter)
![](assetrelasi/30.jpg)

5. Menampilakn status commit / koneksi file ke github apakah status telah terpenuhi atau belum dengan menggunakan kode di bawah ini : 
`git status` (lalu klik enter)
![](assetrelasi/29.jpg)

6. Menambahkan pesan dengan  menggunakan kode di bawah ini : 
`git commit -m "pesan yang ingin di tambahkan`
![](assetrelasi/31.jpg)
jika telah seperti diatas maka 1 file telah berhasil di tambahkan 

7.  Menampilkan seluruh perubahan menggunakan kode di bawah ini : 
![](assetrelasi/32.jpg)

8. Login ke akun Github atau menghubungkan Obsidian ke Github 
![](assetrelasi/15.jpg)
klik (Sign in with your browser)

![](assetrelasi/16.jpg)
lalu klik (authorize git-ecosystem)

![](assetrelasi/17.jpg)
lalu masukkan password akun github

![](assetrelasi/18.jpg)
jika telah tampil ini maka autentukasi telah sukses

![](assetrelasi/33.jpg)
masuk kembali ke repositori dan refresh, jika telah tampil seperti di atas ini maka obsidian dan github telah berhasil di hubungkan
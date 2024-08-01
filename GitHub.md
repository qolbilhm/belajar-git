# 1. Instalasi Git Bush
1. Jika ingin mendownload github search Git SCM, gambarnya seperti di bawah ini
![github](asset/19.JPG)

setelah muncul seperti diatas klik download
![](asset/21.JPG)

pilih lah download untuk windows dan download Git For Windows versi 64-bit (sesuikan dengan penyimpanan laptop)
![github](asset/20.JPG)
setelah download git scm search git-hub dan login atau buat akun jika belum punya akun


# 2. Login/Buat Akun GitHub
1. Buka browser dan ketik github dan klik paling atas yaitu github.com
![github\300x300](asset/20.JPG)

2. Klik Sign in jika belum punya akun dan Sign Up jika telah mempunyai akun
![github\300x150](asset/22.JPG)

3. Login buat akun menggunakan akun google
![github](asset/23.JPG)

4. dan isi keselurahan persyaratan membuat akun
![github\400x400](asset/25.JPG)
# 3. Buat Repository di Github
1. Jika telah membuat akun github, klik tambah di bagian kanan pada dasbor akun github anda (klik buat repository baru)
![github\2x250](asset/1.JPG)

2. Jika telah klik repositori baru buatlah  nama repositori yang di inginkan seperti di bawah ini dan jangan lupa untuk di publik agar user lain bisa melihat isi repositori kita
![github](asset/2.JPG)

3. Jika telah seperti di bawah scrool ke bawah lalu klik buat repositori 
![github](asset/3.JPG)

4. jika telah buat repositori baru klik profil, maka akan muncul repositori yang telah di buat
![github](asset/26.JPG)

# 4. Konfigurasi Awal di Git Bash
1. Jika telah sampai buat repositori baru, buka git bush dan ketikkan 
 `git config --list`
![github](asset/27.JPG)

2. Jika telah muncul seperti diatas kita akan mengkonfigurasi email dan username kita yang sama di akun github dengan menggunakan kode seperti ini : 
`git config --global user.name  "username-qolbilhm"` (untuk username dan username di sesuikan dengan username akun github)
`git config --global user.email "email@nqolby29.com"` (untuk email dan email disesuikan dengan email akun github)

![github](asset/8.JPG)

3. Jika telah seperti yang diatas ketikkan kembali 
`git config --list` 
![github](asset/9.JPG)
jika barisan paling bawah username dan email telah muncul maka berarti konfigurasi email dan username telah berhasil

# 5. Akses Folder Proyek di Git Bush
1. mengakses folder proyek di git bush dengan menggunakan kode di bawah ini : 
`cd c:` (klik enter lalu ketik ls)
`ls` (klik enter maka akan muncul semua file-file yang ada pada data C)
![github](asset/10.JPG)

2. Lalu buka file obsidian dengan cara ketik 
`cd obsidian` (lalu klik enter dan ketikkan lagi ls)
`ls` (maka akan muncul semua isi file-file yang ada dalam folder obsidian)
![github](asset/11.JPG)
pada gambar diatas kita bisa lihat di dalam folder obsidian kita telah mempunyai file belajar-git yang telah di buat di repositori

3. Selanjutnya kita akan melihat isi folder proyek dari belajar-git dengan mengetikkan : 
`cd belajar-git` (nama folder proyek)
`ls` (menampilkan isi semua file dalam folder)
![github](asset/12.JPG)
pada gambar diatas kita telah melihat folder proyek yang telah dibuat telah diisi file 'Belajar Git.md'

# 6. Hubungkan Folder Proyek Lokal ke Github
1. Inisialisasi repository, dengan ini kita mengecek repositori kita apakah tersambung atau tidak dengan menggunakan kode di bawah ini : 
`git init` (lalu klik enter)
![github](asset/13.JPG)
jika tampilannya seperti diatas maka telah berhasil terhubung

2. Hubungkan ke repository github, disini kita akan manambahkan atau menghubungkan repositori github dengan menggunakan kode di bawah ini : 
`git remote add origin https://(link yang ada pada repositori github yang telah di buat)` lalu klik enter
![github](asset/28.JPG)

3. Menampilakn status commit / koneksi file ke github apakah status telah terpenuhi atau belum dengan menggunakan kode di bawah ini : 
`git status` (lalu klik enter)
![github](asset/29.JPG)

4. Menambahkan semua file-file baru dengan menggunakan kode di bawah ini :
`git add .` (lalu klik enter)
![github](asset/30.JPG)

5. Menampilakn status commit / koneksi file ke github apakah status telah terpenuhi atau belum dengan menggunakan kode di bawah ini : 
`git status` (lalu klik enter)
![github](asset/29.JPG)

6. Menambahkan pesan dengan  menggunakan kode di bawah ini : 
`git commit -m "pesan yang ingin di tambahkan`
![github](asset/31.JPG)
jika telah seperti diatas maka 1 file telah berhasil di tambahkan 

7.  Menampilkan seluruh perubahan menggunakan kode di bawah ini : 
![github](asset/32.JPG)

8. Login ke akun Github atau menghubungkan Obsidian ke Github 
![github](asset/15.JPG)
klik (Sign in with your browser)

![github](asset/16.JPG)
lalu klik (authorize git-ecosystem)

![github](asset/17.JPG)
lalu masukkan password akun github

![github](asset/18.JPG)
jika telah tampil ini maka autentukasi telah sukses

![github](asset/33.JPG)
masuk kembali ke repositori dan refresh, jika telah tampil seperti di atas ini maka obsidian dan github telah berhasil di hubungkan
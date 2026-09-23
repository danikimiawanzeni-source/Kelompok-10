🏟️ SewaLapang

Sistem Reservasi Lapangan Futsal & Badminton Berbasis Web

SewaLapang adalah aplikasi berbasis web yang digunakan untuk membantu proses reservasi lapangan futsal dan badminton secara online.

Aplikasi ini dibuat untuk mempermudah pelanggan dalam melihat informasi lapangan, mengecek jadwal, melakukan reservasi, dan mengunggah bukti pembayaran. Admin dapat mengelola data lapangan, reservasi, pembayaran, pengguna, serta laporan.

Project ini dikembangkan sebagai tugas/proyek menggunakan PHP, MySQL, dan XAMPP, dengan Visual Studio Code sebagai code editor.

---

📌 Fitur

👤 Pelanggan

- Registrasi akun
- Login dan logout
- Melihat daftar lapangan
- Melihat detail lapangan
- Mengecek jadwal lapangan
- Melakukan reservasi
- Validasi bentrok jadwal
- Melihat total harga reservasi
- Mengunggah bukti pembayaran
- Melihat status pembayaran
- Melihat riwayat reservasi

👨‍💼 Admin

- Login sebagai admin
- Dashboard admin
- Mengelola data lapangan
- Menambah lapangan
- Mengedit lapangan
- Menghapus lapangan
- Melihat data reservasi
- Mengelola pembayaran
- Memvalidasi pembayaran
- Mengelola data pengguna
- Melihat laporan reservasi
- Melihat laporan pendapatan

---

🛠️ Teknologi

Project ini menggunakan:

Teknologi| Kegunaan
PHP| Backend
MySQL| Database
HTML| Struktur halaman
CSS| Tampilan website
JavaScript| Interaksi halaman
XAMPP| Web server dan database
Apache| Web server
phpMyAdmin| Pengelolaan database
Visual Studio Code| Code editor

---

💻 Persyaratan Sistem

Sebelum menjalankan project, pastikan sudah terinstall:

- Windows 10/11
- XAMPP
- PHP
- MySQL
- Visual Studio Code
- Web Browser seperti Google Chrome, Microsoft Edge, atau Mozilla Firefox

---

📂 Struktur Folder

sewalapang/
│
├── admin/
│   ├── dashboard.php
│   ├── lapangan.php
│   ├── lapangan_tambah.php
│   ├── lapangan_edit.php
│   ├── lapangan_hapus.php
│   ├── reservasi.php
│   ├── pembayaran.php
│   ├── laporan.php
│   └── pengguna.php
│
├── pelanggan/
│   ├── dashboard.php
│   ├── lapangan.php
│   ├── jadwal.php
│   ├── reservasi.php
│   ├── pembayaran.php
│   └── riwayat.php
│
├── auth/
│   ├── login.php
│   ├── register.php
│   └── logout.php
│
├── config/
│   └── database.php
│
├── assets/
│   ├── css/
│   │   └── style.css
│   │
│   ├── js/
│   │   └── script.js
│   │
│   └── img/
│
├── uploads/
│   └── bukti_pembayaran/
│
├── index.php
└── README.md

---

🗄️ Database

Nama database:

sewalapang

Database menggunakan MySQL.

Tabel

Database terdiri dari beberapa tabel utama:

users
lapangan
reservasi
pembayaran

Relasi

users
  │
  │ 1
  │
  │ N
reservasi
  │
  │ N
  │
  │ 1
lapangan

reservasi
  │
  │ 1
  │
  │ 1
pembayaran

---

⚙️ Cara Instalasi

1. Clone Repository

Clone repository menggunakan Git:

git clone https://github.com/USERNAME/sewalapang.git

Ganti "USERNAME" dengan username GitHub kamu.

Contoh:

git clone https://github.com/satrio/sewalapang.git

---

2. Masukkan Project ke XAMPP

Setelah repository selesai di-clone, pindahkan folder project ke:

C:\xampp\htdocs\

Sehingga:

C:\xampp\htdocs\sewalapang

---

3. Jalankan XAMPP

Buka XAMPP Control Panel.

Aktifkan:

Apache  → Start
MySQL   → Start

Pastikan keduanya berwarna hijau/running.

---

🗄️ 4. Membuat Database

Buka:

http://localhost/phpmyadmin

Kemudian buat database:

sewalapang

Setelah itu import file SQL project jika tersedia:

database/sewalapang.sql

Jika file SQL belum tersedia, database dapat dibuat menggunakan struktur tabel pada dokumentasi project.

---

🔌 5. Konfigurasi Database

Buka:

config/database.php

Sesuaikan konfigurasi:

<?php

$host = "localhost";
$user = "root";
$password = "";
$database = "sewalapang";

$conn = mysqli_connect(
    $host,
    $user,
    $password,
    $database
);

if (!$conn) {
    die("Koneksi database gagal: " . mysqli_connect_error());
}

?>

Konfigurasi default XAMPP biasanya:

Host     : localhost
Username : root
Password : kosong
Database : sewalapang

---

🌐 6. Menjalankan Website

Buka browser dan akses:

http://localhost/sewalapang/

Halaman login:

http://localhost/sewalapang/auth/login.php

Halaman registrasi:

http://localhost/sewalapang/auth/register.php

---

🔐 Sistem Role

SewaLapang menggunakan dua role:

admin
pelanggan

Admin

Setelah login:

admin/dashboard.php

Pelanggan

Setelah login:

pelanggan/dashboard.php

Sistem menggunakan PHP Session untuk mempertahankan status login.

---

🔑 Akun Testing

Untuk testing awal dapat digunakan akun yang telah dibuat di database.

Admin

Email    : admin@sewalapang.com
Password : password
Role     : admin

Pelanggan

Email    : pelanggan@sewalapang.com
Password : password
Role     : pelanggan

«Untuk penggunaan sebenarnya, password akun testing sebaiknya diganti.»

---

🔒 Keamanan

Beberapa mekanisme keamanan yang digunakan:

- Password disimpan menggunakan "password_hash()".
- Password diverifikasi menggunakan "password_verify()".
- Sistem menggunakan session untuk login.
- Hak akses dibedakan berdasarkan role.
- Pengguna pelanggan tidak dapat membuka halaman admin.
- Email pengguna harus unik.
- Input form dilakukan validasi.
- Query tertentu menggunakan prepared statement.

---

📅 Alur Reservasi

Alur utama sistem:

Pelanggan
    ↓
Login / Registrasi
    ↓
Melihat Lapangan
    ↓
Memilih Lapangan
    ↓
Memilih Tanggal
    ↓
Memilih Jam
    ↓
Cek Ketersediaan
    ↓
Validasi Bentrok
    ↓
Reservasi
    ↓
Pembayaran
    ↓
Upload Bukti Pembayaran
    ↓
Validasi Admin
    ↓
Reservasi Dikonfirmasi

---

💰 Status Pembayaran

Sistem menggunakan beberapa status pembayaran:

Belum Bayar
Menunggu Validasi
Lunas
Ditolak

---

📋 Status Reservasi

Status reservasi:

Menunggu Pembayaran
Menunggu Validasi
Dikonfirmasi
Ditolak
Selesai
Dibatalkan

---

🧪 Pengujian

Pengujian sistem menggunakan metode Black Box Testing.

Contoh pengujian:

Fitur| Pengujian| Hasil
Login| Email dan password benar| Berhasil
Login| Password salah| Menampilkan error
Registrasi| Data lengkap| Berhasil
Registrasi| Email sudah digunakan| Ditolak
Reservasi| Jadwal tersedia| Berhasil
Reservasi| Jadwal bentrok| Ditolak
Pembayaran| Upload bukti| Berhasil
Validasi| Admin menerima pembayaran| Status Lunas
Logout| Klik logout| Session dihapus

---

🚧 Status Project

Project saat ini masih dalam tahap pengembangan.

Progress:

- [x] Perancangan SRS
- [x] Struktur folder
- [x] Database MySQL
- [x] Koneksi database
- [x] Login Admin
- [x] Login Pelanggan
- [x] Session & Role
- [x] Registrasi Pelanggan
- [ ] Dashboard Admin
- [ ] CRUD Data Lapangan
- [ ] Cek Jadwal
- [ ] Reservasi
- [ ] Validasi Bentrok
- [ ] Pembayaran
- [ ] Validasi Pembayaran
- [ ] Riwayat Reservasi
- [ ] Laporan
- [ ] Pengujian Akhir

---

👨‍💻 Pengembang

Nama: Satrio
Project: SewaLapang
Jenis: Sistem Informasi Berbasis Web
Platform: Web
Bahasa: PHP

---

📄 Lisensi

Project ini dibuat untuk keperluan pembelajaran dan tugas akademik.

---

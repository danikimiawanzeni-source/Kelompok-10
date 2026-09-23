# 🏟️ SewaLapang

## Sistem Reservasi Lapangan Futsal & Badminton Berbasis Web

SewaLapang adalah aplikasi berbasis web yang digunakan untuk membantu proses reservasi lapangan futsal dan badminton secara online.

Aplikasi ini dibuat untuk mempermudah pelanggan dalam melihat informasi lapangan, mengecek jadwal, melakukan reservasi, dan mengunggah bukti pembayaran.

Admin dapat mengelola data lapangan, reservasi, pembayaran, pengguna, serta laporan.

Project ini dikembangkan menggunakan PHP, MySQL, XAMPP, HTML, CSS, JavaScript, dan Visual Studio Code.

---

## 📌 Fitur Sistem

### 👤 Pelanggan

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

### 👨‍💼 Admin

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

## 🛠️ Teknologi

| Teknologi | Kegunaan |
|---|---|
| PHP | Backend |
| MySQL | Database |
| HTML | Struktur halaman |
| CSS | Tampilan website |
| JavaScript | Interaksi halaman |
| XAMPP | Web server dan database |
| Apache | Web server |
| phpMyAdmin | Pengelolaan database |
| Visual Studio Code | Code editor |

---

## 💻 Persyaratan Sistem

Sebelum menjalankan project, pastikan sudah terinstall:

- Windows 10/11
- XAMPP
- PHP
- MySQL
- Visual Studio Code
- Google Chrome / Microsoft Edge / Mozilla Firefox

---

## 📂 Struktur Folder

```text
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
│   ├── js/
│   │   └── script.js
│   └── img/
│
├── uploads/
│   └── bukti_pembayaran/
│
├── index.php
└── README.md
```

---

## 🗄️ Database

Nama database:

```text
sewalapang
```

Database dibuat menggunakan **MySQL** melalui **phpMyAdmin** pada XAMPP.

### Tabel Database

Project SewaLapang menggunakan 4 tabel utama:

```text
users
lapangan
reservasi
pembayaran
```

### Fungsi Tabel

| Tabel | Fungsi |
|---|---|
| `users` | Menyimpan data admin dan pelanggan |
| `lapangan` | Menyimpan data lapangan futsal dan badminton |
| `reservasi` | Menyimpan data pemesanan lapangan |
| `pembayaran` | Menyimpan data pembayaran dan bukti pembayaran |

### Relasi Database

```text
users
  │
  └── reservasi
          │
          ├── lapangan
          │
          └── pembayaran
```

---

## ⚙️ Cara Instalasi

### 1. Clone Repository

Gunakan Git untuk melakukan clone repository:

```bash
git clone https://github.com/USERNAME/sewalapang.git
```

Ganti `USERNAME` dengan username GitHub pemilik repository.

Contoh:

```bash
git clone https://github.com/satrio/sewalapang.git
```

---

### 2. Masukkan Project ke XAMPP

Pastikan folder project berada di:

```text
C:\xampp\htdocs\sewalapang
```

---

### 3. Jalankan XAMPP

Buka **XAMPP Control Panel**.

Aktifkan:

```text
Apache
MySQL
```

Pastikan keduanya sudah berstatus **Running**.

---

### 4. Membuat Database

Buka:

```text
http://localhost/phpmyadmin
```

Buat database dengan nama:

```text
sewalapang
```

Kemudian buat tabel sesuai struktur database project.

---

### 5. Konfigurasi Database

Buka file:

```text
config/database.php
```

Gunakan konfigurasi berikut:

```php
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
```

Konfigurasi default XAMPP:

| Pengaturan | Nilai |
|---|---|
| Host | `localhost` |
| Username | `root` |
| Password | Kosong |
| Database | `sewalapang` |

---

### 6. Menjalankan Website

Buka browser:

```text
http://localhost/sewalapang/
```

Halaman login:

```text
http://localhost/sewalapang/auth/login.php
```

Halaman registrasi:

```text
http://localhost/sewalapang/auth/register.php
```

---

## 🔐 Sistem Role

SewaLapang memiliki dua jenis pengguna:

```text
admin
pelanggan
```

### Admin

Admin diarahkan ke:

```text
admin/dashboard.php
```

Admin dapat mengelola data lapangan, reservasi, pembayaran, pengguna, dan laporan.

### Pelanggan

Pelanggan diarahkan ke:

```text
pelanggan/dashboard.php
```

Pelanggan dapat melihat lapangan, mengecek jadwal, melakukan reservasi, melakukan pembayaran, dan melihat riwayat reservasi.

Sistem menggunakan **PHP Session** untuk mengatur status login dan hak akses berdasarkan role.

---

## 🔑 Akun Testing

### Admin

```text
Email    : admin@sewalapang.com
Password : password
Role     : admin
```

### Pelanggan

```text
Email    : pelanggan@sewalapang.com
Password : password
Role     : pelanggan
```

> Akun di atas hanya digunakan untuk kebutuhan testing selama pengembangan.

---

## 🔒 Keamanan

Sistem menggunakan beberapa mekanisme keamanan:

- Password disimpan menggunakan `password_hash()`.
- Password diverifikasi menggunakan `password_verify()`.
- Sistem menggunakan PHP Session.
- Hak akses dibedakan berdasarkan role.
- Pelanggan tidak dapat mengakses halaman admin.
- Email pengguna harus unik.
- Input form dilakukan validasi.
- Query registrasi menggunakan prepared statement.

---

## 📅 Alur Reservasi

```text
Pelanggan
    ↓
Login / Registrasi
    ↓
Melihat Lapangan
    ↓
Memilih Lapangan
    ↓
Memilih Tanggal dan Jam
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
```

---

## 💰 Status Pembayaran

| Status | Keterangan |
|---|---|
| Belum Bayar | Pelanggan belum melakukan pembayaran |
| Menunggu Validasi | Bukti pembayaran sudah dikirim |
| Lunas | Pembayaran telah diterima admin |
| Ditolak | Bukti pembayaran ditolak |

---

## 📋 Status Reservasi

| Status | Keterangan |
|---|---|
| Menunggu Pembayaran | Reservasi dibuat tetapi belum dibayar |
| Menunggu Validasi | Bukti pembayaran menunggu pemeriksaan |
| Dikonfirmasi | Reservasi telah disetujui |
| Ditolak | Reservasi atau pembayaran ditolak |
| Selesai | Waktu penggunaan lapangan telah selesai |
| Dibatalkan | Reservasi dibatalkan |

---

## 🧪 Pengujian

Pengujian sistem menggunakan metode **Black Box Testing**.

| No | Fitur | Skenario | Hasil yang Diharapkan |
|---:|---|---|---|
| 1 | Login | Email dan password benar | Masuk ke dashboard |
| 2 | Login | Password salah | Menampilkan pesan error |
| 3 | Registrasi | Data lengkap | Akun berhasil dibuat |
| 4 | Registrasi | Email sudah digunakan | Registrasi ditolak |
| 5 | Reservasi | Jadwal tersedia | Reservasi berhasil |
| 6 | Reservasi | Jadwal bentrok | Reservasi ditolak |
| 7 | Pembayaran | Upload bukti | Bukti tersimpan |
| 8 | Validasi | Admin menerima pembayaran | Status menjadi Lunas |
| 9 | Logout | Klik logout | Session dihapus |

---

## 🚧 Status Project

Project masih dalam tahap pengembangan.

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

## 👨‍💻 Pengembang

**Nama:** Dani Kurniawan, Muhammad Raflly , Satrio Dewo

**Project:** SewaLapang

**Jenis:** Sistem Informasi Berbasis Web

**Teknologi:** PHP, MySQL, HTML, CSS, JavaScript, XAMPP

---

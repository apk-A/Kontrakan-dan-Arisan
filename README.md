# 🏠 Kontrakan & Arisan

Aplikasi web untuk membantu pengelolaan data kontrakan dan arisan secara sederhana, responsif, dan mudah digunakan melalui komputer maupun smartphone.

## ✨ Fitur

### 🏢 Manajemen Kontrakan

* Data kontrakan pria
* Data kontrakan wanita
* Data penghuni
* Data kamar
* Status pembayaran
* Tanggal jatuh tempo
* Pengaturan pengingat jatuh tempo

### ⏰ Sistem Pengingat

Aplikasi memberikan tanda pengingat berdasarkan tanggal:

* 🔴 **Hari Ini** — jatuh tempo atau jadwal terjadi hari ini
* 🟠 **Besok** — jatuh tempo atau jadwal terjadi besok
* 🟢 **Terjadwal** — jadwal masih akan datang

Notifikasi otomatis akan muncul ketika aplikasi dibuka apabila terdapat jadwal penting pada hari tersebut.

### 🎯 Manajemen Arisan

* Data peserta arisan
* Jumlah iuran
* Status peserta
* Pengundian menggunakan roulette
* Riwayat pemenang
* Penggantian pemenang
* Pengaturan tanggal pengingat arisan

### 🎨 Dashboard

* Ringkasan jumlah penghuni
* Status pembayaran
* Kamar tersedia
* Jadwal jatuh tempo
* Jadwal arisan
* Ringkasan arisan
* Profil pemilik dashboard
* Pilihan tema tampilan

## 🌐 Teknologi

Aplikasi menggunakan:

* **Google Apps Script** sebagai backend dan aplikasi utama
* **Google Spreadsheet** sebagai penyimpanan data
* **HTML, CSS, dan JavaScript** untuk antarmuka
* **GitHub Pages** sebagai halaman domain/custom domain

## 🔗 Arsitektur

```text
Custom Domain
     │
     ▼
GitHub Pages
     │
     ▼
index.html
     │
     ▼
Google Apps Script Web App
     │
     ├── Code.gs
     │
     └── Index.html
          │
          ▼
   Google Spreadsheet
```

## 🚀 Cara Menggunakan

Repository GitHub digunakan sebagai halaman depan aplikasi.

File utama:

```text
index.html
CNAME
README.md
```

`index.html` akan meneruskan tampilan aplikasi ke Google Apps Script Web App.

Google Apps Script menjadi mesin utama aplikasi, sedangkan Google Spreadsheet digunakan untuk menyimpan data.

## ⚙️ Konfigurasi

URL Google Apps Script Web App:

```text
https://script.google.com/macros/s/AKfycbzf2P0erQwKB7R9AmmJpDJgI4otFEAEO5r7A0h2c6HASa2h1pR21sN4jc03BLJUwy1m/exec
```

URL tersebut digunakan oleh `index.html` GitHub Pages sebagai sumber aplikasi.

## 📱 Responsif

Aplikasi dirancang agar dapat digunakan pada:

* Komputer / laptop
* Tablet
* Smartphone

## 👨‍💻 Pengembang

**Kontrakan & Arisan**

Dikembangkan untuk membantu pengelolaan kontrakan dan arisan secara lebih praktis.

---

© 2026 Kontrakan & Arisan

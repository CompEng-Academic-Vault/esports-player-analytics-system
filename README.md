# 🎮 Sistem Analisis Player Esports Multi-Node 3-Tier

## 📖 Deskripsi Singkat

**Sistem Analisis Player Esports Multi-Node 3-Tier** adalah aplikasi berbasis web yang dirancang untuk membantu manajemen tim esports dalam mengambil keputusan kontrak player secara lebih objektif dan berbasis data.

Sistem mengolah data performa hasil pertandingan seperti kills, assists, deaths, KDA, gold, dan statistik tim untuk menghasilkan **skor performance** yang dapat digunakan sebagai indikator evaluasi pemain.

Melalui dashboard interaktif, pelatih dan manajemen tim dapat:

* Menginput data player dan pertandingan.
* Menghitung skor performa secara otomatis.
* Melihat statistik performa pemain.
* Membandingkan performa antar player atau antar match.
* Mendukung proses evaluasi kontrak berdasarkan data historis.

---

# 🏗️ Arsitektur Sistem Berbasis 3 VM

Sistem diimplementasikan menggunakan arsitektur **3-Tier Architecture** yang dipisahkan ke dalam tiga Virtual Machine (VM).

```text
┌─────────────────────┐
│      Frontend VM    │
│     Web Dashboard   │
└──────────┬──────────┘
           │ HTTP/API
           ▼
┌─────────────────────┐
│      Backend VM     │
│ Business Logic API  │
└──────────┬──────────┘
           │ SQL Query
           ▼
┌─────────────────────┐
│     Database VM     │
│   MySQL Database    │
└─────────────────────┘
```

### Alur Kerja Sistem

1. Pengguna membuka dashboard melalui browser.
2. Frontend menerima input data player dan data pertandingan.
3. Frontend mengirim data ke Backend melalui API.
4. Backend melakukan validasi data.
5. Backend menghitung nilai performance.
6. Backend menyimpan data ke Database.
7. Backend mengirim hasil pengolahan ke Frontend.
8. Frontend menampilkan statistik dan tabel performa player.

---

# 🖥️ Pembagian Fungsi Virtual Machine

## 1. Database VM

### Fungsi

Bertanggung jawab menyimpan seluruh data aplikasi.

### Data yang Disimpan

* Data identitas player
* Data pertandingan
* Hasil perhitungan performance
* Riwayat evaluasi player

### Tugas Utama

* Menyediakan layanan database
* Menyimpan data secara persisten
* Menangani query dari Backend
* Menjaga integritas data

---

## 2. Backend VM

### Fungsi

Menjalankan seluruh logika bisnis aplikasi.

### Tugas Utama

* Menerima request dari Frontend
* Memvalidasi input data
* Menghitung skor performance
* Mengelola API
* Mengakses Database
* Mengirim response ke Frontend

### Logika Perhitungan Performance

Skor performance dihitung menggunakan beberapa parameter seperti:

* KDA Score
* Kill Participation
* Kontribusi Kill dan Assist terhadap Team Kill
* Death Control
* Gold Per Minute

---

## 3. Frontend VM

### Fungsi

Menyediakan antarmuka pengguna berbasis web.

### Tugas Utama

* Menampilkan dashboard
* Menampilkan statistik player
* Menampilkan tabel performa
* Menyediakan form input player
* Menyediakan form input data pertandingan
* Menampilkan hasil analisis performance

---

# 🛠️ Tools dan Teknologi yang Digunakan

## Infrastruktur

* VirtualBox
* Vagrant
* Ansible

## Frontend

* HTML5
* CSS3
* JavaScript

## Backend

* Python Flask

## Database

* MySQL

## Version Control

* Git
* GitHub

## Sistem Operasi VM

* Ubuntu Server

---

# 📊 Fitur Aplikasi

## Dashboard Statistik

Menampilkan:

* Total player
* Rata-rata performance
* Performance tertinggi
* Jumlah player yang direkomendasikan lanjut kontrak

## Form Input Player

Input data:

* Nama Player
* Role
* Tim
* Match ID

## Form Input Pertandingan

Input data:

* Kills
* Assists
* Deaths
* KDA
* Gold
* Team Kills
* Team Deaths
* Menit
* Detik

## Tabel Performa Player

Menampilkan:

* Data player
* Statistik pertandingan
* Nilai performance
* Hasil evaluasi

---

# 🚀 Cara Instalasi dan Menjalankan Aplikasi

## Prasyarat

Pastikan perangkat telah terinstal:

* VirtualBox
* Vagrant
* Git

---

## 1. Clone Repository

```bash
git clone https://github.com/username/esports-player-analysis.git
cd esports-player-analysis
```

---

## 2. Menjalankan Infrastruktur VM

Membangun seluruh Virtual Machine menggunakan Vagrant:

```bash
vagrant up
```

Memastikan seluruh VM aktif:

```bash
vagrant status
```

---

## 3. Konfigurasi Otomatis Menggunakan Ansible

Masuk ke VM Controller atau jalankan provisioning:

```bash
vagrant provision
```

Ansible akan:

* Menginstal MySQL pada Database VM
* Menginstal Flask pada Backend VM
* Menginstal Web Server pada Frontend VM
* Mengatur konektivitas antar VM

---

## 4. Menjalankan Backend

Masuk ke Backend VM:

```bash
vagrant ssh backend
```

Aktifkan aplikasi Flask:

```bash
python app.py
```

Backend akan berjalan pada:

```text
http://<backend-ip>:5000
```

---

## 5. Menjalankan Frontend

Masuk ke Frontend VM:

```bash
vagrant ssh frontend
```

Jalankan web server atau akses halaman yang telah dideploy.

Frontend dapat diakses melalui:

```text
http://<frontend-ip>
```

---

## 6. Verifikasi Sistem

Lakukan pengujian:

1. Buka dashboard.
2. Input data player.
3. Input data pertandingan.
4. Simpan data.
5. Pastikan skor performance muncul.
6. Pastikan data tersimpan ke database.
7. Pastikan statistik dashboard berubah sesuai data terbaru.

---

# 📂 Struktur Proyek

```text
project-root/
│
├── frontend/
│   ├── index.html
│   ├── css/
│   └── js/
│
├── backend/
│   ├── app.py
│   ├── routes/
│   └── models/
│
├── database/
│   └── schema.sql
│
├── automation/
│   ├── Vagrantfile
│   └── playbook.yml
│
└── README.md
```

---

# 🎯 Tujuan Proyek

Membangun sistem analisis performa player esports berbasis cloud yang mampu membantu manajemen tim dalam mengambil keputusan kontrak pemain secara lebih objektif, terukur, dan berbasis data historis pertandingan.

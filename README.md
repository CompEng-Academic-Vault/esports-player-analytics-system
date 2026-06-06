# 🎮 Sistem Analisis Player Esports Multi-Node 3-Tier

![3-Tier](https://img.shields.io/badge/Architecture-3--Tier-blue?style=for-the-badge)
![Infrastructure](https://img.shields.io/badge/Infrastructure-Vagrant%20%7C%20Ansible-orange?style=for-the-badge)
![Backend](https://img.shields.io/badge/Backend-Python%20Flask-green?style=for-the-badge)
![Database](https://img.shields.io/badge/Database-MySQL-blue?style=for-the-badge)

## 📖 Deskripsi Singkat

**Sistem Analisis Player Esports Multi-Node 3-Tier** adalah aplikasi berbasis web yang dirancang untuk membantu manajemen tim esports dalam mengambil keputusan kontrak player secara lebih objektif dan berbasis data.

Sistem mengolah data performa hasil pertandingan seperti *kills, assists, deaths, KDA, gold*, dan statistik tim untuk menghasilkan **skor performance** yang dapat digunakan sebagai indikator evaluasi pemain.

> 💡 **Core Capabilities Dashboard Interaktif**
>
> - Menginput data player dan pertandingan.
> - Menghitung skor performa secara otomatis.
> - Melihat statistik performa pemain.
> - Membandingkan performa antar player atau antar match.
> - Mendukung proses evaluasi kontrak berdasarkan data historis.

---

# 🏗️ Arsitektur Sistem Berbasis 3 VM

Sistem diimplementasikan menggunakan arsitektur **3-Tier Architecture** yang diisolasi secara mandiri ke dalam tiga Virtual Machine (VM) terpisah.

```text
┌─────────────────────┐
│      Frontend VM    │
│     Web Dashboard   │
└──────────┬──────────┘
           │ HTTP/API (Port 80)
           ▼
┌─────────────────────┐
│      Backend VM     │
│ Business Logic API  │
└──────────┬──────────┘
           │ SQL Query (Port 3306)
           ▼
┌─────────────────────┐
│     Database VM     │
│    MySQL Database   │
└─────────────────────┘
```

## ⚙️ Alur Kerja Sistem (Data Pipeline Flow)

1. **Access:** Pengguna membuka dashboard melalui browser.
2. **Input:** Frontend menerima input data player dan data pertandingan.
3. **Transmission:** Frontend mengirim data ke Backend melalui API.
4. **Validation:** Backend melakukan validasi data.
5. **Computation:** Backend menghitung nilai performance.
6. **Persistence:** Backend menyimpan data ke Database.
7. **Response:** Backend mengirim hasil pengolahan ke Frontend.
8. **Visualization:** Frontend menampilkan statistik dan tabel performa player.

---

# 🖥️ Pembagian Fungsi Virtual Machine (Node Breakdown)

## 1. 🗄️ Database VM

### Fungsi

Bertanggung jawab menyimpan seluruh data aplikasi.

### Data yang Disimpan

- Data identitas player
- Data pertandingan
- Hasil perhitungan performance
- Riwayat evaluasi player

### Tugas Utama

- Menyediakan layanan database
- Menyimpan data secara persisten
- Menangani query dari Backend
- Menjaga integritas data

---

## 2. ⚙️ Backend VM

### Fungsi

Menjalankan seluruh logika bisnis aplikasi.

### Tugas Utama

- Menerima request dari Frontend
- Memvalidasi input data
- Menghitung skor performance
- Mengelola API
- Mengakses Database
- Mengirim response ke Frontend

### 📊 Logika Perhitungan Performance

Skor performance dihitung menggunakan beberapa parameter mutlak seperti:

- KDA Score
- Kill Participation
- Kontribusi Kill dan Assist terhadap Team Kill
- Death Control
- Gold Per Minute

---

## 3. 💻 Frontend VM

### Fungsi

Menyediakan antarmuka pengguna berbasis web.

### Tugas Utama

- Menampilkan dashboard
- Menampilkan statistik player
- Menampilkan tabel performa
- Menyediakan form input player
- Menyediakan form input data pertandingan
- Menampilkan hasil analisis performance

---

# 🛠️ Tools dan Teknologi yang Digunakan

| Kategori | Teknologi | Deskripsi / Fungsi |
|-----------|------------|--------------------|
| **Infrastruktur** | `VirtualBox` | Provider virtualisasi komponen lokal |
| | `Vagrant` | Automasi manajemen siklus hidup VM |
| | `Ansible` | Configuration Management & automasi deployment |
| **Frontend** | `HTML5`, `CSS3`, `JavaScript` | Penyusun antarmuka dashboard interaktif |
| **Backend** | `Python Flask` | Penyedia layanan RESTful API dan mesin logika bisnis |
| **Database** | `MySQL` | Penyimpanan relasional data entitas |
| **Version Control** | `Git`, `GitHub` | Manajemen kontrol versi repositori kode |
| **Sistem Operasi** | `Ubuntu Server` | Basis lingkungan OS pada ketiga Node VM |

---

# 📊 Fitur Aplikasi

## 📈 Dashboard Statistik

Menampilkan metrik agregat utama:

- Total player
- Rata-rata performance
- Performance tertinggi
- Jumlah player yang direkomendasikan lanjut kontrak

## 📥 Form Input Player

Pengisian entitas awal:

- Nama Player
- Role
- Tim
- Match ID

## ⚔️ Form Input Pertandingan

Metrik gameplay terperinci:

- Kills
- Assists
- Deaths
- KDA
- Gold
- Team Kills
- Team Deaths
- Durasi Waktu (Menit & Detik)

## 📋 Tabel Performa Player

- Menampilkan ringkasan data player.
- Menampilkan statistik pertandingan.
- Menampilkan nilai performance.
- Menampilkan rekomendasi keputusan evaluasi akhir.

---

# 🚀 Cara Instalasi dan Menjalankan Aplikasi

## 📋 Prasyarat

Pastikan perangkat lokal telah terinstal:

- VirtualBox
- Vagrant
- Git

---

## 1. Clone Repository

```bash
git clone https://github.com/username/esports-player-analysis.git
cd esports-player-analysis
```

## 2. Menjalankan Infrastruktur VM

Membangun seluruh cluster Virtual Machine menggunakan Vagrant:

```bash
vagrant up
```

Memastikan seluruh node berjalan:

```bash
vagrant status
```

## 3. Konfigurasi Otomatis Menggunakan Ansible

Menjalankan provisioning:

```bash
vagrant provision
```

> 🤖 **Alur Otomatisasi Ansible**
>
> - Menginstal dan mengonfigurasi MySQL pada Database VM.
> - Menginstal pustaka Flask pada Backend VM.
> - Menginstal konfigurasi Web Server pada Frontend VM.
> - Mengatur konektivitas jaringan antar VM.

## 4. Menjalankan Backend

Masuk ke Backend VM:

```bash
vagrant ssh backend
```

Menjalankan Flask:

```bash
python app.py
```

Backend akan berjalan pada:

```text
http://<backend-ip>:5000
```

## 5. Menjalankan Frontend

Masuk ke Frontend VM:

```bash
vagrant ssh frontend
```

Frontend dapat diakses melalui:

```text
http://<frontend-ip>
```

## 6. Verifikasi Sistem

1. Buka dashboard pada browser.
2. Masukkan data identitas player baru.
3. Input statistik pertandingan.
4. Klik tombol simpan.
5. Pastikan skor performance muncul otomatis.
6. Verifikasi data tersimpan pada MySQL.
7. Pastikan dashboard memperbarui statistik secara dinamis.

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

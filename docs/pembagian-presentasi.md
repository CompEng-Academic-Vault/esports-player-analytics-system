# 🎤 Struktur Estafet Presentasi Tim

## BAGIAN 1: LATAR BELAKANG (Konseptual & Masalah)

**Goal:** Meyakinkan dosen bahwa proyek ini memiliki urgensi tinggi dan landasan teori cloud yang kuat.

### 👤 Pembicara 1: Alya
**Topik:** Masalah Real-World & Solusi Cloud

**Materi:**
- Menjelaskan tren industri esports saat ini.
- Menjelaskan pentingnya analisis data performa player secara objektif untuk mendukung pengambilan keputusan manajemen.
- Mengidentifikasi masalah pada infrastruktur tradisional:
  - Rentan mengalami crash.
  - Risiko kehilangan data.
  - Data dapat tercampur atau tidak konsisten.
- Memperkenalkan sistem yang dikembangkan sebagai solusi berbasis cloud.

**Kata Kunci:**
- Esports Analytics
- Data-Driven Decisions
- Cloud Mitigation

---

### 👤 Pembicara 2: Rizqul
**Topik:** Arsitektur 3-Tier & Keamanan

**Materi:**
- Menjelaskan alasan pemilihan arsitektur **3-Tier Multi-Node**:
  - Frontend Layer
  - Backend Layer
  - Database Layer
- Menjelaskan konsep **Separation of Concerns** melalui pemisahan fungsi tiap server.
- Menekankan aspek keamanan dengan mengisolasi database agar tidak dapat diakses langsung dari luar jaringan.

**Kata Kunci:**
- Separation of Concerns
- Network Isolation
- Database Security

---

### 👤 Pembicara 3: Algina
**Topik:** Metodologi Automasi (Infrastructure as Code)

**Materi:**
- Menjelaskan tantangan deployment manual yang rentan terhadap human error.
- Menjelaskan penerapan **Infrastructure as Code (IaC)** menggunakan:
  - Vagrant
  - Ansible
- Menunjukkan bagaimana proses pembuatan server dapat berjalan otomatis dan konsisten.

**Kata Kunci:**
- Infrastructure as Code (IaC)
- Automation Efficiency
- Idempotency

---

# 🏗️ BAGIAN 2: ARSITEKTUR VM (Teknis & Spesifikasi)

**Goal:** Membedah infrastruktur server yang telah dibangun.

### 👤 Pembicara 1: Rizqul
**Topik:** Sisi Penyimpanan – VM Database

**Materi:**
- Menjelaskan spesifikasi **vm-database** (`192.168.56.10`).
- Menjelaskan penggunaan **MySQL** sebagai sistem manajemen basis data.
- Menjelaskan konsep **Persistent Storage** untuk menjaga data statistik pemain tetap aman meskipun VM dimatikan atau direstart.

**Kata Kunci:**
- MySQL
- Persistent Storage
- IP `192.168.56.10`

---

### 👤 Pembicara 2: Algina
**Topik:** Sisi Logika & API – VM Backend

**Materi:**
- Menjelaskan spesifikasi **vm-backend** (`192.168.56.20`).
- Menjelaskan lingkungan eksekusi:
  - PHP 8.1
  - Composer
- Menjelaskan fungsi backend sebagai pusat pemrosesan logika sistem.
- Menjelaskan proses pengolahan statistik esports seperti:
  - Win Rate
  - KDA (Kill, Death, Assist)
- Menjelaskan penyediaan data melalui RESTful API.

**Kata Kunci:**
- Core Logic Processing
- RESTful API
- IP `192.168.56.20`

---

### 👤 Pembicara 3: Alya
**Topik:** Sisi Antarmuka – VM Frontend

**Materi:**
- Menjelaskan spesifikasi **vm-frontend** (`192.168.56.30`).
- Menjelaskan penggunaan **Nginx Web Server**.
- Menjelaskan bagaimana dashboard visual disajikan kepada pengguna.
- Menjelaskan manfaat dashboard bagi manajer tim esports dalam membaca hasil analisis performa pemain.

**Kata Kunci:**
- Nginx Web Server
- User Dashboard
- IP `192.168.56.30`

---

# 🚀 BAGIAN 3: DEMO ALAT & VALIDASI (Eksekusi Real-Time)

**Goal:** Membuktikan secara langsung bahwa sistem bekerja otomatis dan terintegrasi.

### 👤 Pembicara 1: Algina
**Topik:** Demo Otomatisasi Jaringan & Server

**Materi:**
- Menampilkan terminal saat menjalankan:
  ```bash
  vagrant up
  ```

- Menampilkan proses provisioning menggunakan:
  ```bash
  ansible-playbook
  ```

- Menjelaskan bahwa instalasi:
  - Nginx
  - PHP
  - MySQL

  pada seluruh VM dilakukan secara otomatis menggunakan satu blueprint konfigurasi tanpa instalasi manual.

**Kata Kunci:**
- Live Provisioning
- Configuration Management
- Automated Deployment

---

### 👤 Pembicara 2: Alya
**Topik:** Demo Integrasi Dashboard Aplikasi

**Materi:**
- Membuka browser dan mengakses:
  ```
  http://192.168.56.30
  ```
- Menampilkan dashboard analisis esports.
- Mendemonstrasikan bagaimana data pemain diambil secara dinamis dari backend dan database secara real-time.
- Menunjukkan alur komunikasi antar server dalam sistem.

**Kata Kunci:**
- End-to-End Integration
- Data Visualization
- User Experience

---

### 👤 Pembicara 3: Rizqul
**Topik:** Validasi Keamanan & Penutup

**Materi:**
- Melakukan pembuktian isolasi jaringan, misalnya dengan:
  - Menunjukkan konfigurasi `bind-address` pada database.
  - Mencoba melakukan koneksi langsung dari frontend ke database yang berakhir gagal atau diblokir.
- Menjelaskan bagaimana pendekatan tersebut meningkatkan keamanan sistem.
- Menyampaikan kesimpulan akhir proyek.

**Kata Kunci:**
- Network Hardening
- Structural Resilience
- Project Conclusion

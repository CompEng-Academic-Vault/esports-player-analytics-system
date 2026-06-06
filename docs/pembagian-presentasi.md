# BAGIAN 1: LATAR BELAKANG (Slide 3–6)

## Alya (Slide 3 & 4: Pengantar & Urgensi Ekonomi Esports)

### Poin Penjelasan

* Membuka presentasi pada bagian latar belakang.
* Menjelaskan pertumbuhan industri esports berdasarkan data ekonomi global dan nasional.
* Membahas nilai ekonomi esports global sebesar **$1.86 miliar** dan esports Indonesia sebesar **$11.1 juta**.
* Menunjukkan bahwa besarnya investasi dan perputaran ekonomi dalam industri ini menuntut pengelolaan tim yang terukur, profesional, dan berbasis data.
* Menekankan bahwa keputusan manajerial tidak lagi dapat dilakukan secara subjektif atau berdasarkan intuisi semata.

### Keyword

* Economic Growth
* Data-Driven Management

---

## Rizqul (Slide 5: Masalah & Tantangan Manajerial)

### Poin Penjelasan

* Menjelaskan permasalahan utama yang dihadapi manajemen tim esports.
* Membahas inkonsistensi performa atlet antar pertandingan yang menyulitkan proses evaluasi.
* Menjelaskan risiko bias subjektivitas dalam pengambilan keputusan, seperti faktor kedekatan personal atau popularitas pemain.
* Menunjukkan bahwa tanpa data historis yang terstruktur, proses perpanjangan kontrak maupun evaluasi pemain berpotensi tidak objektif.

### Keyword

* Performance Inconsistency
* Subjective Bias

---

## Algina (Slide 6: Solusi Sistem Analisis & Teori Cloud)

### Poin Penjelasan

* Memperkenalkan solusi yang dikembangkan oleh tim.
* Menjelaskan bahwa dashboard analisis dirancang untuk menghasilkan penilaian yang transparan dan objektif.
* Menampilkan penggunaan parameter performa seperti:

  * KDA (Kill, Death, Assist)
  * Gold
  * Kontribusi terhadap tim
* Menjelaskan bagaimana sistem membantu pelatih dan manajemen dalam mengambil keputusan secara cepat dan berbasis data.

### Keyword

* Objective Analysis
* Transparent Parameters

---

# BAGIAN 2: DEMO ALAT (Slide 7–9)

> **Catatan:** Sesuai struktur PPT terbaru, sesi Demo Alat ditempatkan sebelum pembahasan infrastruktur agar audiens dapat memahami bentuk sistem terlebih dahulu.

## Algina (Slide 7 & 8: Arsitektur & Antarmuka Dashboard)

### Poin Penjelasan

* Membuka sesi demonstrasi sistem.
* Menjelaskan konsep dashboard berbasis **Single-Page Application (SPA)**.
* Menguraikan tiga komponen utama dashboard:

  1. Ringkasan statistik performa pada bagian atas.
  2. Form input data pertandingan pada bagian tengah.
  3. Tabel komparasi data historis pada bagian bawah.
* Menunjukkan bagaimana seluruh fitur terintegrasi dalam satu halaman untuk meningkatkan efisiensi penggunaan.

### Keyword

* Dashboard Layout
* Unified Interface

---

## Alya (Slide 9: Logika Perhitungan & Rumus Metrik)

### Poin Penjelasan

* Menjelaskan grafik tren performa yang ditampilkan pada dashboard.
* Menguraikan logika perhitungan yang digunakan sistem untuk menghasilkan skor performa pemain.
* Menjelaskan parameter yang digunakan dalam proses pembobotan, meliputi:

  * KDA
  * Kill Participation
  * Death Control
  * Gold Per Minute (GPM)
* Menjelaskan bagaimana backend dan AI menggabungkan berbagai metrik tersebut menjadi skor akhir yang dapat digunakan untuk evaluasi pemain.

### Keyword

* Performance Score Formula
* Weighted Metrics

---

## Rizqul (Transisi Menuju Validasi Sistem)

### Poin Penjelasan

* Menjelaskan alur perpindahan data dari frontend menuju backend.
* Menguraikan proses:

  1. Input data melalui dashboard.
  2. Pengiriman data ke backend server.
  3. Perhitungan rumus performa.
  4. Penyimpanan hasil ke database.
* Menjadikan penjelasan ini sebagai jembatan menuju pembahasan arsitektur cloud dan infrastruktur sistem.

### Keyword

* Data Flow
* Functional Integration

---

# BAGIAN 3: ARSITEKTUR VM (Slide 10–12)

## Rizqul (Slide 10 & 11: Lapisan Database – Node Terdalam)

### Poin Penjelasan

* Memperkenalkan arsitektur **3-Tier Multi-Node**.
* Menjelaskan fungsi **Database Tier** menggunakan MySQL/MariaDB.
* Menjelaskan alasan database ditempatkan pada server terpisah dan terisolasi.
* Menekankan manfaat isolasi jaringan untuk meningkatkan keamanan sistem.
* Menjelaskan bahwa database bertugas menyimpan seluruh data pertandingan dan hasil analisis secara permanen.

### Keyword

* Database Tier
* Network Isolation
* Persistent Storage

---

## Algina (Slide 11: Lapisan Backend – Otak Logika)

### Poin Penjelasan

* Menjelaskan fungsi **Backend Tier** sebagai pusat pemrosesan aplikasi.
* Menjelaskan bagaimana backend menerima request dari frontend melalui API.
* Menjelaskan proses:

  * Validasi data
  * Perhitungan skor performa
  * Perhitungan win-rate
  * Komunikasi dengan database
* Menunjukkan bahwa backend menjadi penghubung utama antara antarmuka pengguna dan penyimpanan data.

### Keyword

* Application Logic Tier
* RESTful API Processing

---

## Alya (Slide 11 & 12: Lapisan Frontend & Penutup Sesi)

### Poin Penjelasan

* Menjelaskan fungsi **Frontend Tier** yang menggunakan Nginx sebagai web server.
* Menjelaskan peran frontend dalam menyajikan antarmuka dashboard kepada pengguna.
* Menunjukkan bagaimana pengguna dapat mengakses data dan visualisasi performa melalui browser.
* Menyampaikan kesimpulan proyek bahwa:

  * Otomatisasi deployment berhasil dijalankan.
  * Network hardening berhasil diterapkan.
  * Arsitektur cloud berjalan sesuai tujuan sistem.
* Menutup presentasi dan mengarahkan audiens ke sesi tanya jawab pada Slide 12.

### Keyword

* Web Server Tier
* Structural Resilience
* Closing Statement

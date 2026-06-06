# 🎤 Skrip Presentasi Tugas Besar

## Sistem Analisis Player Esports Multi-Node 3-Tier
> link PPT: https://docs.google.com/presentation/d/14nmcAfRe2DmXE0lx4APRz__PBioFe1bAl02Iy7Bi_aE/edit?usp=sharing 

---

# BAGIAN 1: LATAR BELAKANG

## Alya (Slide 3 & 4: Pengantar & Urgensi Ekonomi Esports)

### Slide 3 — Section Title: Latar Belakang

> Selamat pagi/siang Pak Budhi dan rekan-rekan sekalian. Saya Alya, mewakili kelompok kami, akan membuka presentasi Tugas Besar Komputasi Awan kami yang berjudul **"Sistem Analisis Player Esports untuk Optimasi Keputusan Manajemen Tim Berbasis Data."**

### Slide 4 — Pertumbuhan Ekonomi Esports

> Mari kita mulai dengan melihat urgensi dari industri ini. Seperti yang tertera pada slide, pertumbuhan ekonomi esports global diproyeksikan menembus angka **4,5 miliar dolar** pada tahun 2025, sementara di pasar domestik Indonesia sendiri valuasinya telah mencapai **30,7 juta dolar**.

> Angka investasi yang sangat besar ini menjadi bukti bahwa esports bukan lagi sekadar hobi, melainkan industri bernilai tinggi. Konsekuensinya, manajemen klub esports dituntut untuk menerapkan **data-driven management** atau manajemen berbasis data.

> Kita tidak dapat lagi mengelola tim hanya berdasarkan intuisi ketika melakukan rekrutmen maupun investasi pemain. Mengenai tantangan riil yang terjadi di lapangan akan dibahas lebih lanjut oleh rekan saya, Rizqul.

---

## Rizqul (Slide 5: Masalah & Tantangan Manajerial)

### Slide 5 — Tantangan Manajerial

> Terima kasih, Alya. Saya Rizqul akan melanjutkan pembahasan mengenai tantangan manajerial di internal tim esports.

> Ada dua masalah utama yang sering kami temui di lapangan.

### 1. Inkonsistensi Performa

> Performa seorang atlet esports sering kali mengalami fluktuasi yang drastis antar pertandingan akibat faktor teknis maupun psikologis.

### 2. Bias Subjektivitas

> Tanpa adanya rekam jejak digital yang valid, manajemen atau pelatih sering kali mengambil keputusan perpanjangan kontrak pemain hanya berdasarkan popularitas, kedekatan personal, atau sekadar ingatan sesaat tanpa dukungan data historis yang objektif.

> Solusi atas masalah ini akan dipaparkan oleh Algina.

---

## Algina (Slide 6: Solusi Sistem Analisis & Teori Cloud)

### Slide 6 — Solusi: Analisis Objektif

> Terima kasih, Rizqul. Saya Algina.

> Untuk memitigasi bias keputusan yang telah dijelaskan tadi, kelompok kami merancang sistem dashboard analisis objektif ini.

> Melalui pendekatan yang transparan, sistem kami mengolah variabel-variabel mentah hasil pertandingan seperti **KDA**, **perolehan Gold**, dan **kontribusi tim** menjadi metrik yang terukur secara nyata.

> Dengan tersedianya data yang terstruktur, manajemen dapat melakukan evaluasi performa secara adil sekaligus membantu pelatih dalam mengambil keputusan taktis secara cepat dan akurat.

> Untuk melihat bagaimana sistem ini beroperasi, mari kita masuk ke Bagian Kedua, yaitu **Demo Alat**.

---

# BAGIAN 2: DEMO ALAT

## Algina (Slide 7 & 8: Arsitektur & Antarmuka Dashboard)

### Slide 7 — Section Title: Demo Alat

### Slide 8 — Arsitektur Dashboard

> Memasuki bagian demonstrasi alat, kami mengimplementasikan sistem antarmuka berbasis **Single-Page Application (SPA)** untuk memastikan pengalaman pengguna yang efisien.

> Dashboard visualisasi ini kami bagi menjadi tiga area fungsional utama.

### Ringkasan Statistik Performa

> Pada bagian atas, terdapat ringkasan statistik performa yang menampilkan metrik agregat seperti rata-rata skor dan nilai tertinggi sebagai indikator utama.

### Form Input Data Variabel

> Di bagian tengah, kami menyediakan form input data variabel yang digunakan admin atau analis tim untuk memasukkan data hasil pertandingan secara langsung.

### Tabel Hasil Komparasi Data Historis

> Pada bagian bawah, sistem menyajikan tabel hasil komparasi data historis guna melacak perkembangan performa pemain dari waktu ke waktu.

> Selanjutnya, detail perhitungan metrik ini akan dijelaskan oleh Alya.

---

## Alya (Slide 9: Logika Perhitungan & Rumus Metrik)

### Slide 9 — Logika Skor Performa

> Terima kasih, Algina.

> Saya Alya akan menjelaskan logika di balik kurva tren yang tampak pada slide saat ini.

> Skor performa atlet yang dihasilkan oleh sistem kami tidak diperoleh melalui kalkulasi sederhana, melainkan menggunakan pendekatan **weighted metrics** atau pembobotan metrik.

> Sistem kami memproses fungsi matematika yang mengombinasikan empat komponen utama:

- Pembobotan aspek **KDA**
- Persentase keterlibatan eliminasi (**Kill Participation**)
- Tingkat kontrol kematian (**Death Control**)
- Efisiensi ekonomi pemain melalui **Gold Per Minute (GPM)**

> Parameter-parameter tersebut diproses di latar belakang sistem untuk menghasilkan satu skor akhir yang objektif.

> Lalu, bagaimana data dari antarmuka ini dialirkan secara aman? Rizqul akan mengantarkan kita menuju arsitektur jaringannya.

---

## Rizqul (Transisi Menuju Validasi Sistem)

### Slide 9 → Menuju Slide 10

> Terima kasih, Alya.

> Sebagai jembatan menuju infrastruktur teknis, penting bagi kita untuk memahami bagaimana **data flow** atau aliran data ini bekerja.

> Saat pengguna menekan tombol **Submit** pada form input di lapisan frontend, data akan dikirimkan dalam bentuk payload digital menuju server backend.

> Pada server backend inilah seluruh rumus matematika yang dijelaskan sebelumnya dieksekusi secara real-time.

> Setelah skor akhir diperoleh, hasil tersebut diteruskan ke node terdalam untuk disimpan secara aman di dalam database.

> Integrasi fungsional inilah yang membawa kita untuk membedah arsitektur penyusunnya pada Bagian Ketiga.

---

# BAGIAN 3: ARSITEKTUR VM

## Rizqul (Slide 10 & 11: Lapisan Database — Node Terdalam)

### Slide 10 — Section Title: Arsitektur VM

### Slide 11 — Detail Infrastruktur Cloud

> Memasuki bagian akhir mengenai infrastruktur, saya Rizqul akan menjelaskan lapisan terdalam dari arsitektur **3-Tier Multi-Node** kami, yaitu **Database Tier** yang menggunakan MySQL/MariaDB.

> Dalam implementasi cloud ini, database ditempatkan pada Virtual Machine yang terisolasi penuh dari jaringan luar guna mencegah potensi serangan siber secara langsung.

> Node database ini bertanggung jawab terhadap **persistent storage**, yaitu memastikan seluruh data historis performa atlet esports tersimpan secara aman dan permanen pada media penyimpanan virtual.

> Dengan demikian, data tidak akan hilang meskipun komponen server lainnya mengalami pemeliharaan atau gangguan operasional.

> Selanjutnya, lapisan backend akan dijelaskan oleh Algina.

---

## Algina (Slide 11: Lapisan Backend — Otak Logika)

### Slide 11 — Fokus pada Backend Tier

> Terima kasih, Rizqul.

> Saya Algina akan menjelaskan lapisan tengah, yaitu **Backend Tier**.

> Jika database merupakan tempat penyimpanan memori, maka backend dapat diibaratkan sebagai otak logika dari sistem kami.

> Node ini berfungsi sebagai lingkungan eksekusi yang melayani **RESTful API request** dari aplikasi frontend.

> Backend bertugas untuk:

- Memvalidasi data masukan
- Menjalankan proses kalkulasi skor performa
- Melakukan komunikasi dengan database tier melalui jalur IP privat internal

> Dengan pemisahan beban kerja seperti ini, proses komputasi yang berat tidak akan mengganggu performa visual aplikasi pada sisi pengguna.

> Terakhir, lapisan terluar akan dijelaskan oleh Alya.

---

## Alya (Slide 11 & 12: Lapisan Frontend & Penutup)

### Slide 11 — Fokus pada Frontend Tier

> Terima kasih, Algina.

> Lapisan terluar dari sistem komputasi awan kami adalah **Frontend Tier**.

> Pada lapisan ini, kami mengonfigurasi **Nginx Web Server** berkinerja tinggi untuk melayani pengiriman aset visual dashboard kepada pengguna akhir.

> Melalui otomatisasi deployment menggunakan **Vagrant** dan **Ansible**, serta penerapan **network hardening** atau pengerasan jaringan, kami memastikan seluruh komponen infrastruktur memiliki **structural resilience** atau ketahanan struktural yang tinggi dan siap beroperasi pada lingkungan produksi.

---

### Slide 12 — Terima Kasih & Sesi Tanya Jawab

> Sebagai kesimpulan, dengan menggabungkan kekuatan arsitektur **3-Tier Cloud** dan analisis data objektif, sistem ini mampu membantu manajemen tim esports dalam mengambil keputusan yang lebih modern, terukur, dan akurat.

> Demikian presentasi dari kelompok kami.

> Kami sangat terbuka untuk menerima pertanyaan, tanggapan, maupun masukan dari Pak Budhi pada sesi tanya jawab ini.

> **Terima kasih.**

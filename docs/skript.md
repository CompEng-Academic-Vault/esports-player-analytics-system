SKRIP PRESENTASI TUGAS BESAR

Sistem Analisis Player Esports Multi-Node 3-Tier
BAGIAN 1: LATAR BELAKANG
Alya (Slide 3 & 4: Pengantar & Urgensi Ekonomi Esports)

    [Slide 3: Section Title - Latar Belakang]

    "Selamat pagi/siang Pak Budhi dan rekan-rekan sekalian. Saya Alya, mewakili kelompok kami, akan membuka presentasi Tugas Besar Komputasi Awan kami yang berjudul 'Sistem Analisis Player Esports untuk Optimasi Keputusan Manajemen Tim Berbasis Data'.

    [Slide 4: Pertumbuhan Ekonomi Esports]

    Mari kita mulai dengan melihat urgensi dari industri ini. Seperti yang tertera pada slide, pertumbuhan ekonomi esports global diproyeksikan menembus angka 1.86 Miliar Dolar pada tahun 2025, sementara di pasar domestik Indonesia sendiri valuasinya telah mencapai 11.1 Juta Dolar.

    Angka investasi yang raksasa ini menjadi bukti bahwa esports bukan lagi sekadar hobi, melainkan industri bernilai tinggi. Konsekuensinya, manajemen klub esports dituntut untuk menerapkan data-driven management [manajemen berbasis data]. Kita tidak boleh lagi mengelola tim secara asal-asalan atau mengandalkan intuisi semata ketika melakukan rekrutmen maupun investasi pemain. Mengenai tantangan riil di lapangan akan dibedah lebih lanjut oleh rekan saya, Rizqul."

Rizqul (Slide 5: Masalah & Tantangan Manajerial)

    [Slide 5: Tantangan Manajerial]

    "Terima kasih, Alya. Saya Rizqul akan melanjutkan pembahasan mengenai tantangan manajerial di internal tim esports. Ada dua masalah utama yang sering kami temui di lapangan.

    Yang pertama adalah Inkonsistensi Performa. Performa seorang atlet esports sering kali mengalami fluktuasi yang drastis antar-pertandingan akibat faktor teknis maupun psikologis. Masalah kedua, yang menjadi titik paling krusial, adalah adanya Bias Subjektivitas. Tanpa adanya rekam jejak digital yang valid, manajemen atau pelatih sering kali mengambil keputusan perpanjangan kontrak pemain hanya berdasarkan popularitas, kedekatan personal, atau sekadar ingatan sekilas tanpa dukungan data historis yang objektif. Solusi atas masalah ini akan dipaparkan oleh Algina."

Algina (Slide 6: Solusi Sistem Analisis & Teori Cloud)

    [Slide 6: Solusi: Analisis Objektif]

    "Terima kasih, Rizqul. Saya Algina. Untuk memitigasi bias keputusan yang dijelaskan tadi, kelompok kami merancang sistem dashboard analisis objektif ini.

    Melalui pendekatan yang transparan, sistem kami meramu variabel-variabel mentah hasil pertandingan seperti KDA, perolehan Gold, dan kontribusi tim menjadi metrik yang terukur secara riil. Dengan ketersediaan data yang terstruktur ini, manajemen dapat melakukan evaluasi performa secara adil, sekaligus membantu pelatih dalam mengambil keputusan taktis secara cepat dan akurat. Untuk melihat bagaimana sistem ini beroperasi, mari kita langsung masuk ke Bagian Kedua, yaitu Demo Alat."

BAGIAN 2: DEMO ALAT
Algina (Slide 7 & 8: Arsitektur & Antarmuka Dashboard)

    [Slide 7: Section Title - Demo Alat]

    "Memasuki bagian demonstrasi alat, [Slide 8: Arsitektur Dashboard], kami mengimplementasikan sistem antarmuka berbasis Single-Page Application untuk memastikan pengalaman pengguna yang efisien. Dashboard visualisasi ini kami bagi menjadi tiga area fungsional utama.

    Pada bagian atas, terdapat Ringkasan Statistik Performa yang langsung memunculkan metrik agregat seperti rata-rata skor dan nilai tertinggi sebagai indikator utama. Di bagian tengah, kami menyediakan Form Input Data Variabel tempat admin atau analis tim memasukkan angka hasil match secara instan. Dan di bagian bawah, sistem menyajikan Tabel Hasil Komparasi Data Historis untuk melacak perkembangan performa pemain dari waktu ke waktu. Selanjutnya, detail perhitungan metrik ini akan dibedah oleh Alya."

Alya (Slide 9: Logika Perhitungan & Rumus Metrik)

    [Slide 9: Logika Skor Performa]

    "Terima kasih, Algina. Saya Alya akan menjelaskan logika di balik kurva tren yang tampak pada slide saat ini. Skor performa atlet yang dihasilkan oleh sistem kami tidak didapatkan dari kalkulasi sederhana, melainkan melalui pembobotan metrik (weighted metrics).

    Sistem kami memproses rumus fungsi matematika yang mengombinasikan empat komponen utama: pembobotan aspek KDA, persentase keterlibatan eliminasi atau Kill Participation, tingkat kontrol kematian atau Death Control, hingga efisiensi ekonomi pemain lewat Gold Per Minute (GPM). Parameter-parameter inilah yang diolah di latar belakang sistem untuk menghasilkan satu skor akhir yang objektif. Lalu, bagaimana data dari antarmuka ini dialirkan secara aman? Rizqul akan mengantarkan kita menuju arsitektur jaringannya."

Rizqul (Transisi Menuju Validasi Sistem)

    [Masih di Slide 9 / Bersiap Pindah ke Slide 10]

    "Terima kasih, Alya. Sebagai jembatan menuju infrastruktur teknis, penting untuk kita ketahui bersama bagaimana data flow [aliran data] ini bekerja.

    Saat pengguna menekan tombol submit pada form input di lapisan frontend, data tersebut dikirimkan dalam bentuk payload digital menuju server backend. Di server backend inilah seluruh rumus matematika yang dijelaskan Alya tadi dieksekusi secara real-time. Setelah skor akhir didapatkan, hasilnya akan diteruskan ke node terdalam untuk disimpan secara aman di dalam database. Integrasi fungsional inilah yang membawa kita untuk membedah arsitektur penyusunnya di Bagian Ketiga."

BAGIAN 3: ARSITEKTUR VM
Rizqul (Slide 10 & 11: Lapisan Database - Node Terdalam)

    [Slide 10: Section Title - Arsitektur VM]

    "Memasuki bagian akhir mengenai infrastruktur, [Slide 11: Detail Infrastruktur Cloud], saya Rizqul akan menjelaskan lapisan terdalam dari arsitektur 3-Tier Multi-node kami, yaitu Database Tier menggunakan MySQL/MariaDB.

    Dalam implementasi cloud ini, kami menempatkan database pada Virtual Machine yang terisolasi penuh dari jaringan luar guna mencegah potensi serangan siber langsung. Node database ini mengemban tanggung jawab untuk mengelola Persistent Storage. Artinya, seluruh data historis performa atlet esports tim akan terkunci dan tersimpan dengan aman di dalam penyimpanan harddisk/SSD virtual, sehingga data tidak akan hilang atau rusak walaupun komponen server lainnya mengalami pemeliharaan berkala. Selanjutnya, lapisan backend akan dibedah oleh Algina."

Algina (Slide 11: Lapisan Backend - Otak Logika)

    [Slide 11: Fokus pada baris Backend]

    "Terima kasih, Rizqul. Saya Algina akan menjelaskan lapisan tengah, yaitu Backend Tier. Jika database adalah tempat penyimpanan memori, maka backend adalah otak logika dari sistem kami.

    Node ini berfungsi sebagai lingkungan eksekusi yang bertugas melayani RESTful API request yang dikirimkan oleh aplikasi frontend. Backend akan memeriksa validitas data, menjalankan skrip kalkulasi skor, dan melakukan query komunikasi ke database tier secara aman melalui jalur privat IP internal. Dengan pemisahan beban kerja ini, pemrosesan data yang berat tidak akan mengganggu kinerja visual aplikasi pada sisi pengguna. Terakhir, lapisan terluar akan ditutup oleh Alya."

Alya (Slide 11 & 12: Lapisan Frontend & Penutup Sesi)

    [Slide 11: Fokus pada baris Frontend]

    "Terima kasih, Algina. Lapisan pamungkas dari sistem komputasi awan kami adalah Frontend Tier. Di sini kami mengonfigurasi Nginx Web Server berkinerja tinggi untuk melayani pengiriman aset visual dashboard kepada end-user.

    Melalui otomatisasi deployment menggunakan Vagrant dan Ansible, serta penerapan network hardening [pengerasan jaringan], kami berhasil memastikan bahwa seluruh komponen infrastruktur ini memiliki structural resilience [ketahanan struktural] yang tinggi dan siap beroperasi di lingkungan produksi.

    [Slide 12: Terima Kasih / Q&A]

    Kesimpulannya, dengan menyatukan kekuatan arsitektur 3-tier cloud dan analisis data objektif, sistem ini siap membawa manajemen tim esports menuju era pengambilan keputusan yang modern dan akurat. Demikian presentasi dari kelompok kami. Kami sangat terbuka untuk menerima pertanyaan, tanggapan, maupun masukan dari Pak Budhi pada sesi tanya jawab ini. Terima kasih."

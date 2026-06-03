# 1. Bagian Infrastruktur (`automation/`) ➡️ Gunakan Blueprint

Untuk file **Vagrantfile** dan **Ansible Playbook** (`playbook.yml`), kamu bisa menggunakan file contoh **Pencatatan Kas RW** yang sudah kamu miliki sebagai **cetak biru (blueprint)**.

> Kamu tidak perlu menulis ulang struktur logika Ansible dari nol.

### Langkah yang dapat dilakukan:

- Salin (*copy-paste*) file `playbook.yml` ke folder proyek Tubes yang baru.
- Sesuaikan isinya dengan kebutuhan analisis esports.
- Ubah nama variabel database, misalnya:
  - `kasrw_db` → `esports_db`
- Ganti nama pengguna (*user*) database sesuai kebutuhan.
- Sesuaikan paket atau layanan yang perlu diinstal.

---

# 2. Bagian Database (`database/`) ➡️ Modifikasi Struktur Tabel

Kamu tidak perlu memikirkan sistem database dari awal.

> Gunakan struktur perintah SQL standar seperti `CREATE TABLE` dari materi kuliah atau contoh skrip yang pernah digunakan sebelumnya.

### Fokus utama tim:

Mendesain tabel yang relevan dengan tema **esports**, misalnya:

#### Tabel `players`
Menyimpan data pemain esports:

| Kolom | Deskripsi |
|---------|---------|
| id | ID pemain |
| nama_player | Nama pemain |
| role_game | Role atau posisi dalam game |

#### Tabel `teams`
Menyimpan data tim esports:

| Kolom | Deskripsi |
|---------|---------|
| id | ID tim |
| nama_tim | Nama tim |
| region | Wilayah atau liga |

#### Tabel `match_statistics`
Menyimpan statistik pertandingan:

| Kolom | Deskripsi |
|---------|---------|
| id | ID statistik |
| player_id | Referensi pemain |
| win_rate | Persentase kemenangan |
| kda | Kill-Death-Assist |
| match_played | Jumlah pertandingan |

---

# 3. Bagian Aplikasi (`frontend/` & `backend/`) ➡️ Manfaatkan GitHub Copilot

Inilah salah satu alasan utama mengapa proyek ini cocok diikutsertakan ke lomba **GitHub Finish-Up-A-Thon**.

> GitHub Copilot hadir untuk membantu proses pengembangan sehingga kamu tidak perlu mengoding semuanya dari nol.

## Frontend

Gunakan kerangka halaman HTML/CSS sederhana, lalu manfaatkan Copilot untuk menghasilkan komponen antarmuka.

Contoh prompt:

```html
<!-- Buatkan tabel responsif untuk menampilkan peringkat performa player esports -->

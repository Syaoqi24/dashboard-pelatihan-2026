# 📊 Dashboard Realisasi Pelatihan 2026
**BBPVP Bekasi** — Sistem pemantauan realisasi peserta pelatihan berbasis web, terhubung langsung ke Google Sheets secara *live*.

🔗 **Live Demo:** [Klik di sini untuk membuka Dashboard](https://syaoqi24.github.io/dashboard-pelatihan-2026/)

---

## 📋 Deskripsi

Dashboard ini merupakan antarmuka web interaktif untuk memantau realisasi program pelatihan tahun 2026 di BBPVP Bekasi. Data diambil secara langsung (*real-time*) dari Google Sheets tanpa perlu backend atau database tambahan.

---

## ✨ Fitur Utama

- **KPI Cards** — Menampilkan total program, target peserta, realisasi, dan tingkat penyerapan secara ringkas
- **Filter Interaktif** — Menyaring data berdasarkan jenis pelatihan: Semua, Non APBN, APBN PBK, APBN PBL, APBN TMT
- **Bar Chart** — Visualisasi tingkat penyerapan per jenis pelatihan
- **Donut Chart** — Distribusi peserta per kejuruan menggunakan Chart.js
- **Tabel Detail** — Rincian lengkap setiap program dengan status penyerapan (Terpenuhi / Sebagian / Rendah)
- **Live Data** — Data diperbarui otomatis dari Google Sheets setiap kali halaman dibuka
- **Responsif** — Tampilan menyesuaikan layar desktop maupun perangkat mobile

---

## ⚙️ Konfigurasi

### Langkah 1 — Publish Google Sheets ke Publik

Agar dashboard dapat membaca data, Google Sheets **wajib** dipublikasikan:

1. Buka Google Sheets yang berisi data pelatihan
2. Klik **File → Share → Publish to web**
3. Pilih sheet yang sesuai → klik **Publish**
4. Konfirmasi dengan klik **OK**

> ⚠️ Tanpa langkah ini, dashboard akan menampilkan pesan error saat dimuat.

### Langkah 2 — Ganti Sheet ID dan Nama Sheet

Buka file `index.html`, temukan bagian konfigurasi berikut dan sesuaikan:

```javascript
/* ─────────────────────────────────────────
   KONFIGURASI — hanya ubah bagian ini
───────────────────────────────────────── */
const SHEET_ID   = 'GANTI_DENGAN_ID_SPREADSHEET_ANDA';
const SHEET_NAME = 'GANTI_DENGAN_NAMA_SHEET_ANDA';
```

**Cara mendapatkan Sheet ID:**
URL spreadsheet: `https://docs.google.com/spreadsheets/d/`**`1lBqh_cs3Fi75G...`**`/edit`
Bagian yang dicetak tebal di atas itulah Sheet ID-nya.

### Langkah 3 — Sesuaikan Nama Kolom

Dashboard membaca kolom dengan nama header berikut (baris pertama sheet):

| Nama Kolom di Sheet | Keterangan |
|---|---|
| `Nama Program` | Nama lengkap program pelatihan |
| `Kejuruan` | Nama kejuruan / bidang keahlian |
| `JP` | Jumlah jam pelajaran |
| `Target Orang` | Target jumlah peserta |
| `Realisasi Orang` | Jumlah peserta yang telah terealisasi |
| `Jenis Pelatihan` | Jenis: `NON APBN`, `APBN PBK`, `APBN PBL`, atau `APBN TMT` |

---

## 🚀 Cara Menjalankan

### Secara Lokal
1. Clone atau unduh repositori ini
2. Buka file `index.html` langsung di browser

```bash
git clone https://github.com/Syaoqi24/dashboar-pelatihan-2026.git
cd dashboar-pelatihan-2026
# Buka index.html di browser
```

### Via GitHub Pages (Online)
1. Buka **Settings** repositori ini
2. Navigasi ke **Pages**
3. Pada *Source*, pilih **Branch: main** → folder **/ (root)**
4. Klik **Save**
5. Dashboard akan dapat diakses di: `https://syaoqi24.github.io/dashboar-pelatihan-2026/`

---

## 📁 Struktur Repositori

```
dashboar-pelatihan-2026/
├── index.html     # Seluruh aplikasi dashboard (HTML + CSS + JS)
└── README.md      # Dokumentasi repositori ini
```

---

## 🛠️ Teknologi yang Digunakan

| Teknologi | Kegunaan |
|---|---|
| HTML5 / CSS3 | Struktur dan tampilan antarmuka |
| Vanilla JavaScript (ES6+) | Logika aplikasi dan pengolahan data |
| [Chart.js v4.4.1](https://www.chartjs.org/) | Visualisasi grafik (Donut Chart) |
| Google Sheets API (gviz) | Sumber data *real-time* |
| Google Fonts (DM Sans) | Tipografi antarmuka |

---

## 🖼️ Tampilan Dashboard

> *(Tambahkan screenshot dashboard di sini setelah GitHub Pages aktif)*
>
> Contoh cara menambahkan: simpan gambar di folder `assets/` lalu gunakan:
> `![Preview Dashboard](assets/preview.png)`

---

## ⚠️ Catatan Penting

- Sheet ID yang tercantum di `index.html` bersifat publik di repositori ini. Pastikan data di Google Sheets tidak mengandung informasi sensitif yang tidak boleh diakses publik.
- Dashboard bersifat *read-only* — tidak ada data yang dikirim atau dimodifikasi ke Google Sheets.
- Jika data tidak muncul, periksa kembali apakah Google Sheets sudah di-publish dan nama kolom sudah sesuai.

---

## 👤 Pengembang

**Mohammad Syaoqi Ramadhan**
BBPVP Bekasi — Program Uji Coba INTALA 2026

---

## 📄 Lisensi

Repositori ini bersifat terbuka untuk keperluan internal BBPVP Bekasi.

---

![HTML](https://img.shields.io/badge/HTML-100%25-orange?style=flat-square&logo=html5)
![Status](https://img.shields.io/badge/Status-Aktif-brightgreen?style=flat-square)
![Data](https://img.shields.io/badge/Data-Google%20Sheets-34a853?style=flat-square&logo=googlesheets)

# ZUMA Dashboard - Sistem Manajemen Gudang

Sistem dashboard manajemen gudang untuk **ZUMA Sandal** yang terintegrasi dengan Google Sheets untuk monitoring stok, pengiriman, dan operasional gudang secara real-time.

## Fitur Utama

### 1. Dashboard Utama (`index.html`)
Dashboard monitoring stok multi-entitas dengan fitur:
- **Monitoring Stok Real-time** - Tracking stok untuk 3 entitas (DDD, LJBB, MBB)
- **Kartu Ringkasan** - Total box, utilisasi gudang, total pairs, dan total artikel
- **Peringatan Stok Rendah** - Notifikasi otomatis untuk stok ≤ 10 box
- **Visualisasi Data**:
  - Grafik distribusi stok per entitas
  - Grafik distribusi stok per tier
  - Trend transaksi harian (Masuk/Keluar)
- **Tabel Transaksi** - Riwayat barang masuk dan keluar

### 2. Cycle Count (`cyclecount.html`)
Sistem stock opname dengan fitur:
- **Generate Artikel Otomatis** berdasarkan kategori:
  - Slow Moving (20%)
  - Fast Moving (40%)
  - Turnover Tinggi (25%)
  - Random Pick (15%)
- **Input Stok Fisik** - Perbandingan sistem vs fisik untuk setiap entitas
- **Kalkulasi Akurasi** - Global dan per entitas
- **Grafik Distribusi Selisih**
- **Export** - Simpan ke Google Sheets atau export Excel

### 3. Schedule Pengiriman (`delivery.html`)
Manajemen jadwal pengiriman dengan fitur:
- **Tracking Pengiriman** - Plan date, actual date, arrival date
- **Status Tracking** - Pending, In Transit, Delivered, Cancelled
- **Metrik Performa**:
  - On-time rate vs Late rate
  - Status DNPB (OK/Error)
  - Rata-rata SLA
- **Filter & Pencarian** - Berdasarkan periode, tujuan, status
- **Visualisasi** - Grafik distribusi status dan rasio on-time
- **CRUD** - Tambah dan edit data pengiriman

### 4. Monitoring IG & Raw Material (`igrm.html`)
Monitoring intermediate goods dan raw material:
- **Tracking Material** - Kode artikel, deskripsi, quantity
- **Tracking Tanggal**:
  - Tanggal masuk dari supplier
  - Tanggal kirim ke gudang HJS
  - Tanggal masuk ke warehouse
- **Status** - Done, Packing, Outstanding
- **Filter Jenis** - Sandal, Insole, dll
- **Kartu Ringkasan** - Total item, done, packing, outstanding

## Teknologi

| Teknologi | Keterangan |
|-----------|------------|
| HTML5 | Struktur halaman |
| TailwindCSS | Styling (via CDN) |
| Chart.js | Visualisasi grafik |
| Google Sheets API | Database backend |
| Google Apps Script | API untuk CRUD |

## Warna Brand ZUMA

| Warna | Kode Hex | Penggunaan |
|-------|----------|------------|
| ZUMA Dark | `#002A3A` | Header, tombol utama |
| ZUMA Green | `#00E273` | Aksen, status sukses |

## Struktur Folder

```
zuma-dashboard-main/
├── index.html        # Dashboard utama monitoring stok
├── cyclecount.html   # Sistem stock opname/cycle count
├── delivery.html     # Manajemen jadwal pengiriman
├── igrm.html         # Monitoring IG & raw material
└── README.md         # Dokumentasi project
```

## Koneksi Google Sheets

Setiap modul terhubung ke Google Spreadsheet terpisah:

| Modul | Fungsi |
|-------|--------|
| Dashboard | Data stok dan transaksi multi-entitas |
| Cycle Count | Rekapan box dan transaksi per entitas |
| Delivery | Data jadwal pengiriman |
| IGRM | Data intermediate goods dan raw material |

## Cara Penggunaan

1. Buka `index.html` sebagai halaman utama
2. Navigasi ke modul lain melalui tombol di header:
   - **Cycle Count** - Untuk stock opname
   - **IGRM** - Untuk monitoring material
   - **Delivery** - Untuk jadwal pengiriman
3. Data otomatis dimuat dari Google Sheets
4. Klik tombol **Refresh** untuk memperbarui data

## Fitur Umum

- Loading overlay saat memuat data
- Responsive design (mobile & desktop)
- Filter dan pencarian data
- Pagination untuk tabel besar
- Modal form untuk input/edit data
- Timestamp update terakhir

---

**ZUMA Dashboard** v1.0
© 2026 ZUMA Sandal. All rights reserved.

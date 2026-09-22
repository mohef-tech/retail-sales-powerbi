# Retail Sales Analytics Dashboard V1 — Progress & Planning

> File ini dipakai untuk tracking progress harian. Taruh di root folder project (`D:\project\powerbi\PROGRESS.md`).
> Referensi utama: PRD_Retail_Sales_Analytics_Dashboard_V1_AI_Ready.md — bagian 18.7 (Project Progress Tracking).

---

## 1. Status Checklist

Status hanya boleh dicentang jika hasilnya **sudah dikerjakan dan divalidasi**, bukan sekadar dibahas (PRD Rule 18.7).

- [x] Environment Setup
- [x] Power BI Basic Orientation
- [x] Dataset Preparation
- [x] Data Cleaning
- [x] Data Modeling
- [x] DAX Measures
- [ ] Sales Overview
- [ ] Sales Analysis
- [ ] Product & Category Analysis
- [ ] Branch Analysis
- [ ] Validation
- [ ] Business Insights
- [ ] Documentation
- [ ] GitHub Portfolio
- [ ] Final Review

---

## 2. Decision Log

Catat keputusan penting yang mempengaruhi arah project (bukan sekadar suggestion AI yang belum disetujui).

| Tanggal | Keputusan | Alasan |
|---|---|---|
| 2026-09-22 | Development Power BI tetap di Windows (bukan MacBook/VM/Power BI Service) | Power BI Desktop tidak punya versi native macOS; laptop Windows sudah memenuhi syarat teknis |

---

## 3. Session Notes / Checkpoints

Tambahkan entri baru setiap sesi kerja. Format bebas, minimal: apa yang dikerjakan, apa yang selesai, apa langkah berikutnya.

### 2026-09-22 — Checkpoint 1: Environment → DAX Measures → GitHub

**Dikerjakan:**
- Review PRD, konfirmasi pemahaman scope V1.
- Cek spesifikasi laptop Windows (Windows 11 Home 64-bit, RAM 20GB, storage cukup) → memenuhi syarat.
- Install Power BI Desktop via Microsoft Store, orientasi tampilan awal (Report/Data/Model view).
- Dataset Preparation: generate data simulasi via Mockaroo — `dim_branch` (5 cabang Jawa Timur), `dim_product` (25 produk, 5 kategori), `fact_sales` (4 batch @1000 baris, Jan-Jun 2026).
- Import 6 file CSV ke Power BI via Get Data.
- Data Cleaning (Power Query):
  - Perbaiki header `dim_branch` (Use First Row as Headers).
  - Gabungkan 4 batch `fact_sales` jadi 1 tabel `fact_sales` (Append Queries).
  - Perbaiki TransactionID yang duplikat (replace dengan Index Column).
  - Ubah kolom Discount dari angka bulat (0-20) jadi desimal (0-0.2).
  - Validasi tipe data tiap kolom (Date, Text, Whole Number).
  - Nonaktifkan Enable Load untuk 4 tabel batch mentah (biar tidak numpuk di data model).
- Data Modeling: relationship `dim_branch` ↔ `fact_sales` dan `dim_product` ↔ `fact_sales` (1:*, cross-filter Single) — terbentuk otomatis, tervalidasi manual.
- DAX Measures (6 measure, semua tervalidasi angkanya masuk akal):
  - Total Sales, Total Transaction, Total Quantity, Average Transaction Value, Gross Profit, Gross Margin.
- Setup Git & GitHub:
  - Install Git for Windows.
  - Buat repo `retail-sales-powerbi` (public) di GitHub.
  - Struktur folder lokal: `data/`, `documentation/` (berisi PRD & PROGRESS.md), README.md awal.
  - Checkpoint 1 berhasil di-commit & push ke GitHub.

**Belum selesai / in progress:**
- Format tampilan angka measure (Currency untuk Total Sales/Gross Profit, Percentage untuk Gross Margin) — opsional, belum wajib.
- Dashboard belum dibangun sama sekali (Sales Overview, Sales Analysis, Product & Category, Branch Analysis).
- File `.pbix` belum disimpan/ditambahkan ke folder `powerbi/` maupun ke GitHub.
- `screenshots/` masih kosong.

**Next step:**
- Simpan file `.pbix` ke `D:\project\powerbi\powerbi\`.
- Bangun **Dashboard 1 — Sales Overview** sesuai PRD bagian 10.
- Checkpoint berikutnya: push lagi setelah Dashboard 1 selesai & tervalidasi.

---

## 4. Cara Update File Ini

1. Setiap step di checklist selesai **dan tervalidasi** → ubah `[ ]` jadi `[x]`.
2. Setiap sesi kerja baru → tambah entri baru di bagian **Session Notes** (jangan timpa entri lama).
3. Kalau ada keputusan besar yang mengubah scope/pendekatan → catat di **Decision Log**.

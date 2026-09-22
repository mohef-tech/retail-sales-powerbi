# PRD — Retail Sales Analytics Dashboard V1

## 1. Product Overview

**Nama:** Retail Sales Analytics Dashboard
**Versi:** V1
**Jenis:** Personal Portfolio Project
**Platform:** Microsoft Power BI
**Data Source:** Dataset simulasi retail / penjualan

### Deskripsi

Retail Sales Analytics Dashboard adalah dashboard interaktif untuk membantu pengguna memahami kondisi penjualan berdasarkan periode, produk, kategori, cabang, dan performa penjualan.

Dashboard dirancang untuk **Manager sebagai pengguna utama**, namun tetap dapat digunakan oleh Owner, Supervisor, Admin, maupun pihak lain yang membutuhkan informasi penjualan.

Dashboard bukan hanya menampilkan angka, tetapi membantu pengguna menjawab pertanyaan bisnis dari data penjualan.

---

# 2. Tujuan Proyek

Membangun dashboard Power BI yang mampu:

* Menampilkan kondisi penjualan secara ringkas.
* Menganalisis perkembangan penjualan berdasarkan waktu.
* Membandingkan performa antar cabang.
* Mengidentifikasi produk dan kategori dengan performa tinggi/rendah.
* Membantu pengguna menemukan pola atau masalah dalam penjualan.
* Mengurangi ketergantungan terhadap laporan Excel manual.
* Menjadi portfolio project yang menunjukkan kemampuan **Data Analysis, Business Intelligence, dan Power BI**.

---

# 3. Problem Bisnis

Dalam proses retail, data transaksi biasanya tersedia tetapi belum tentu mudah digunakan untuk pengambilan keputusan.

Contoh kondisi:

* Data penjualan tersimpan dalam Excel.
* Laporan membutuhkan proses rekap manual.
* Sulit melihat trend penjualan dengan cepat.
* Sulit membandingkan performa antar cabang.
* Produk dengan penjualan rendah sulit diidentifikasi.
* Management membutuhkan informasi ringkas tanpa membaca ribuan transaksi.

### Masalah utama

> Bagaimana mengubah data transaksi penjualan menjadi informasi yang mudah dipahami dan dapat digunakan untuk analisis bisnis?

---

# 4. Target User

### Primary User

**Manager**

Membutuhkan gambaran umum mengenai kondisi dan performa penjualan.

### Secondary User

Dashboard tetap dapat digunakan oleh:

* Owner
* Supervisor
* Admin
* Staff terkait
* Pihak lain yang membutuhkan analisis penjualan

### Prinsip

Dashboard **tidak dikunci berdasarkan jabatan**.

Role hanya digunakan sebagai contoh kebutuhan pengguna, bukan sebagai pembatas akses pada V1.

---

# 5. Scope

## In Scope

### Data

Dashboard menggunakan data simulasi yang mencakup:

* Transaksi penjualan
* Tanggal transaksi
* Produk
* Kategori produk
* Cabang
* Jumlah barang
* Harga
* Total penjualan
* Diskon
* Metode pembayaran

### Analisis

Dashboard mencakup:

* Total Sales
* Total Transaction
* Total Quantity Sold
* Average Transaction Value
* Sales Trend
* Sales by Branch
* Sales by Category
* Sales by Product
* Sales by Payment Method
* Perbandingan performa berdasarkan periode
* Filter dan interaksi antar visual

### Dashboard

V1 minimal memiliki:

1. **Executive / Sales Overview**
2. **Sales Analysis**
3. **Product & Category Analysis**
4. **Branch Analysis**

---

# 6. Out of Scope

Fitur berikut tidak menjadi fokus V1:

* Sistem kasir/POS
* Sistem inventory real-time
* Sistem accounting
* Forecasting menggunakan machine learning
* Prediksi penjualan
* Customer loyalty system
* CRM
* Integrasi API perusahaan nyata
* Mobile application
* User management kompleks
* Real-time streaming data

Fitur tersebut dapat dipertimbangkan pada versi berikutnya.

---

# 7. Rancangan Data Simulasi

Dataset akan dibuat menyerupai transaksi retail nyata.

### Tabel utama

**Sales**

| Field         | Deskripsi         |
| ------------- | ----------------- |
| TransactionID | ID transaksi      |
| Date          | Tanggal transaksi |
| ProductID     | ID produk         |
| BranchID      | ID cabang         |
| Quantity      | Jumlah produk     |
| UnitPrice     | Harga satuan      |
| Discount      | Diskon            |
| PaymentMethod | Metode pembayaran |

### Master Product

| Field       | Deskripsi   |
| ----------- | ----------- |
| ProductID   | ID produk   |
| ProductName | Nama produk |
| Category    | Kategori    |
| UnitCost    | Harga modal |
| UnitPrice   | Harga jual  |

### Master Branch

| Field      | Deskripsi   |
| ---------- | ----------- |
| BranchID   | ID cabang   |
| BranchName | Nama cabang |
| City       | Kota        |
| Region     | Wilayah     |

### Date

Digunakan untuk analisis waktu:

* Date
* Day
* Month
* Month Name
* Quarter
* Year

---

# 8. Perhitungan Utama

Beberapa KPI yang akan digunakan:

### Total Sales

Total nilai penjualan setelah memperhitungkan diskon.

### Total Transaction

Jumlah transaksi penjualan.

### Total Quantity

Total unit produk yang terjual.

### Average Transaction Value

Rata-rata nilai transaksi.

### Gross Profit

Jika data harga modal digunakan:

**Gross Profit = Sales - Cost**

### Gross Margin

**Gross Margin = Gross Profit / Sales**

KPI dapat dikembangkan sesuai kebutuhan dataset.

---

# 9. Business Questions

Dashboard harus mampu membantu pengguna menjawab pertanyaan seperti:

### Sales

* Berapa total penjualan?
* Bagaimana perkembangan penjualan dari waktu ke waktu?
* Apakah penjualan meningkat atau menurun dibanding periode sebelumnya?
* Berapa rata-rata nilai transaksi?

### Product

* Produk apa yang paling banyak terjual?
* Produk apa yang menghasilkan penjualan terbesar?
* Kategori apa yang memiliki kontribusi terbesar?
* Produk mana yang memiliki performa rendah?

### Branch

* Cabang mana yang memiliki penjualan terbesar?
* Bagaimana perbandingan performa antar cabang?
* Cabang mana yang mengalami penurunan penjualan?

### Payment

* Metode pembayaran apa yang paling banyak digunakan?
* Bagaimana distribusi transaksi berdasarkan metode pembayaran?

---

# 10. Rancangan Dashboard

## Dashboard 1 — Sales Overview

Tujuan:

Memberikan gambaran cepat mengenai kondisi penjualan.

Komponen:

* Total Sales
* Total Transaction
* Total Quantity
* Average Transaction Value
* Sales Trend
* Sales by Branch
* Sales by Category
* Sales vs Previous Period

Filter:

* Date
* Year
* Month
* Branch
* Category

---

## Dashboard 2 — Sales Analysis

Tujuan:

Melakukan analisis lebih mendalam terhadap perkembangan penjualan.

Komponen:

* Sales Trend
* Monthly Sales
* Daily Sales
* Sales Growth
* Sales by Branch
* Sales by Region
* Transaction Trend

---

## Dashboard 3 — Product & Category Analysis

Tujuan:

Memahami performa produk.

Komponen:

* Top Products
* Bottom Products
* Sales by Category
* Quantity by Product
* Revenue Contribution
* Gross Profit
* Gross Margin

---

## Dashboard 4 — Branch Analysis

Tujuan:

Menganalisis performa setiap cabang.

Komponen:

* Sales by Branch
* Transaction by Branch
* Quantity by Branch
* Average Transaction Value
* Branch Sales Trend
* Branch Comparison

---

# 11. User Interaction

Dashboard harus bersifat interaktif.

Pengguna dapat:

* Memilih periode.
* Memilih cabang.
* Memilih kategori.
* Memilih produk.
* Melakukan cross-filter antar visual.
* Melakukan drill-down.
* Melakukan drill-through jika diperlukan.

Contoh:

> User memilih **Cabang Mojokerto** → seluruh visual dashboard otomatis menampilkan data Cabang Mojokerto.

---

# 12. Data Model

V1 menggunakan pendekatan **relational data model / star schema**.

Konsep awal:

```text
              DimDate
                 |
                 |
DimProduct — FactSales — DimBranch
```

Fact table:

```text
FactSales
```

Dimension:

```text
DimDate
DimProduct
DimBranch
```

Model dapat dikembangkan apabila kebutuhan analisis bertambah.

---

# 13. Technology Stack

### Core

* Microsoft Power BI Desktop
* Power Query
* DAX

### Data

* Excel / CSV
* Simulated Retail Dataset

### Documentation

* GitHub
* README.md

### Optional

* SQL / MySQL untuk pengembangan data source pada versi berikutnya.

---

# 14. Target Portfolio GitHub

Repository harus menunjukkan bahwa proyek bukan sekadar screenshot dashboard.

Struktur dokumentasi minimal:

```text
retail-sales-powerbi/
│
├── README.md
├── data/
│   └── retail_sales.csv
│
├── powerbi/
│   └── retail_sales_dashboard.pbix
│
├── documentation/
│   ├── business-requirements.md
│   ├── data-dictionary.md
│   └── dashboard-overview.md
│
└── screenshots/
    ├── overview.png
    ├── sales-analysis.png
    ├── product-analysis.png
    └── branch-analysis.png
```

README menjelaskan:

* Project overview
* Business problem
* Objectives
* Dataset
* Data model
* KPI
* Business questions
* Dashboard
* Insights
* Technology
* Cara menjalankan project

---

# 15. Success Criteria

Project dianggap berhasil apabila:

### Technical

* Data berhasil di-load ke Power BI.
* Data berhasil dibersihkan menggunakan Power Query.
* Data model memiliki relationship yang benar.
* DAX measure dapat digunakan untuk KPI.
* Dashboard memiliki filter dan interaksi.
* Tidak terdapat error pada visualisasi.

### Business

Dashboard mampu menjawab business questions yang telah ditentukan.

### Portfolio

Repository GitHub:

* Memiliki README yang jelas.
* Memiliki dataset.
* Memiliki dokumentasi.
* Menampilkan screenshot dashboard.
* Menjelaskan business problem dan solusi.

### User Experience

Pengguna dapat memahami kondisi penjualan tanpa harus membaca data transaksi satu per satu.

---

# 16. Batasan Perubahan Scope

Selama V1 development:

### Boleh

* Menambahkan KPI yang masih berhubungan dengan sales.
* Memperbaiki visualisasi.
* Mengubah layout dashboard.
* Menambahkan business question yang relevan.
* Memperbaiki data model.
* Menambahkan DAX measure yang diperlukan.

### Tidak boleh tanpa evaluasi ulang scope

* Mengubah project menjadi sistem POS.
* Menambahkan inventory management.
* Menambahkan CRM.
* Menambahkan machine learning.
* Mengubah project menjadi aplikasi web.
* Menambahkan real-time analytics.
* Mengubah study case utama dari retail sales.

Perubahan besar akan masuk ke **V2 / future development**.

---

# 17. Definition of Done

Retail Sales Analytics Dashboard V1 dinyatakan selesai apabila:

1. Dataset simulasi tersedia.
2. Data berhasil masuk ke Power BI.
3. Data berhasil dibersihkan.
4. Data model selesai.
5. DAX KPI utama selesai.
6. Dashboard Overview selesai.
7. Dashboard Sales Analysis selesai.
8. Dashboard Product & Category selesai.
9. Dashboard Branch selesai.
10. Business questions dapat dijawab.
11. Dokumentasi selesai.
12. README GitHub selesai.
13. Project dapat digunakan sebagai portfolio.


---

# 18. Execution & AI Working Contract

## 18.1 Project Starting Condition

Project diasumsikan dimulai dari kondisi:

- User belum pernah menggunakan Power BI secara praktik.
- Laptop Windows belum memiliki environment Power BI.
- Dataset belum tersedia.
- Project belum memiliki data nyata.
- User membutuhkan pembelajaran sekaligus pembangunan portfolio.
- Development Power BI dilakukan di Windows.
- Coding / development pendukung dapat dilakukan di MacBook apabila pada tahap berikutnya memang dibutuhkan.

## 18.2 Development Environment

### Primary Environment

**Windows**

Digunakan untuk:

- Microsoft Power BI Desktop
- Power Query
- DAX
- Pembuatan dan pengujian dashboard

### Secondary Environment

**MacBook**

Dapat digunakan untuk:

- Coding
- Data preparation yang membutuhkan scripting
- Dokumentasi
- Git/GitHub
- Tool development lain yang kompatibel

Power BI Desktop tidak menjadi dependency untuk coding di MacBook. Pekerjaan Power BI tetap berpusat pada environment Windows.

---

## 18.3 Learning-While-Building Principle

Project ini bukan hanya project pembuatan dashboard.

Project memiliki dua tujuan yang berjalan bersamaan:

1. Menghasilkan Retail Sales Analytics Dashboard V1.
2. Membuat user memahami konsep Power BI yang benar melalui project nyata.

AI harus membantu user memahami alasan di balik setiap pekerjaan, bukan hanya memberikan hasil jadi.

Contoh:

Jika AI memberikan DAX measure, AI harus menjelaskan secara singkat:

- Apa fungsi measure tersebut.
- Data apa yang digunakan.
- Kenapa rumus tersebut diperlukan.
- Hasil bisnis apa yang dihasilkan.

Penjelasan tidak perlu panjang kecuali user meminta lebih detail.

---

# 18.4 AI Collaboration Rules

AI yang digunakan dalam project harus mengikuti pola kerja berikut.

### Rule 1 — Follow the PRD

PRD adalah source of truth utama project.

AI tidak boleh:

- Mengubah tujuan project secara sepihak.
- Mengganti study case.
- Menambahkan fitur besar tanpa alasan.
- Memperluas scope hanya karena fitur tersebut memungkinkan.
- Menghapus requirement tanpa persetujuan user.

Jika ada konflik antara ide baru dan PRD, AI harus menunjukkan konflik tersebut dan meminta keputusan user.

---

### Rule 2 — Do Not Guess

Jika informasi yang dibutuhkan belum tersedia:

- Jangan mengarang.
- Jangan berasumsi.
- Jangan menentukan keputusan bisnis sendiri.

AI harus:

1. Menyebutkan informasi yang belum tersedia.
2. Menjelaskan secara singkat kenapa informasi tersebut diperlukan.
3. Bertanya kepada user atau menawarkan opsi yang jelas.

---

### Rule 3 — One Step at a Time

User ingin project dikerjakan secara bertahap.

AI tidak boleh memberikan sepuluh langkah sekaligus ketika satu langkah sudah cukup untuk melanjutkan pekerjaan.

Format kerja:

```text
Current Step
↓
Action
↓
User Confirmation
↓
Next Step
```

AI hanya melanjutkan ke langkah berikutnya setelah user memberikan konfirmasi, kecuali user secara eksplisit meminta beberapa langkah sekaligus.

---

### Rule 4 — Beginner-Friendly

User dianggap mulai dari nol untuk Power BI.

AI harus:

- Menggunakan istilah sederhana terlebih dahulu.
- Menjelaskan istilah teknis ketika pertama kali digunakan.
- Memberikan instruksi yang dapat langsung diikuti.
- Tidak menganggap user sudah memahami Power Query, DAX, data modeling, atau konsep BI.

Namun AI tidak perlu menjelaskan hal yang sudah jelas atau mengulang penjelasan yang sudah pernah diberikan.

---

### Rule 5 — Practical First

Prioritas project:

```text
Pahami konsep → Praktik → Validasi → Dokumentasikan
```

Bukan:

```text
Teori panjang → Teori panjang → Baru praktik
```

Setiap konsep sebaiknya dikaitkan dengan project Retail Sales Analytics Dashboard.

---

### Rule 6 — Preserve User's Working Style

AI harus menyesuaikan pola kerja user:

- Langsung ke inti.
- Tidak bertele-tele.
- Tidak membuat brainstorming panjang tanpa diminta.
- Tidak membuat langkah tambahan yang belum diperlukan.
- Jika membutuhkan keputusan user, tanyakan hanya keputusan yang memang diperlukan.
- Jika sebuah keputusan belum diperlukan, jangan tanyakan.

---

### Rule 7 — Validate Before Moving Forward

Sebelum berpindah ke tahap berikutnya, AI harus memastikan hasil tahap saat ini benar.

Contoh:

Jika membuat data model:

```text
Model dibuat
↓
Relationship diperiksa
↓
Hasil divalidasi
↓
Baru lanjut ke DAX
```

Jika terdapat error, fokus terlebih dahulu pada error tersebut sebelum melanjutkan.

---

### Rule 8 — Business Context Over Decoration

Dashboard tidak dibuat hanya agar terlihat bagus.

Setiap visual harus memiliki alasan bisnis.

Untuk setiap visual penting, AI harus dapat menjawab:

> "Pertanyaan bisnis apa yang dijawab visual ini?"

Jika tidak ada alasan bisnis yang jelas, visual tersebut harus dipertimbangkan kembali.

---

### Rule 9 — AI Must Distinguish Facts, Decisions, and Suggestions

AI harus membedakan:

**Requirement**
→ berasal dari PRD atau keputusan user.

**Fact**
→ informasi yang dapat diverifikasi.

**Suggestion**
→ rekomendasi AI yang belum menjadi requirement.

**Decision**
→ keputusan yang harus dibuat atau telah dibuat oleh user.

AI tidak boleh menyampaikan suggestion seolah-olah sudah menjadi keputusan project.

---

### Rule 10 — Scope Control

Jika muncul ide baru seperti:

- Forecasting
- Customer segmentation
- Inventory
- Machine learning
- Real-time dashboard
- API integration
- Web application

AI harus mengecek apakah ide tersebut masuk scope V1.

Jika tidak:

> Tandai sebagai kandidat V2 / Future Development.

Jangan langsung mengimplementasikannya.

---

# 18.5 AI Output Format

Ketika membantu pengerjaan project, AI sebaiknya menggunakan format:

### Context

Apa yang sedang dikerjakan.

### Current Step

Satu langkah yang sedang dilakukan.

### Action

Apa yang harus dilakukan user.

### Expected Result

Apa yang seharusnya terlihat jika berhasil.

### Confirmation

Tunggu konfirmasi user sebelum melanjutkan.

Untuk pertanyaan sederhana, AI tidak wajib menggunakan seluruh format tersebut.

---

# 18.6 AI Role

AI bertindak sebagai:

- Power BI mentor
- Business Analyst
- Data Analyst
- Technical assistant
- Project documentation assistant
- Reviewer

AI bukan sebagai pengambil keputusan project.

Keputusan final mengenai scope, arah project, perubahan requirement, dan prioritas tetap berada pada user.

---

# 18.7 Project Progress Tracking

AI harus mempertahankan status pekerjaan secara konseptual:

```text
[ ] Environment Setup
[ ] Power BI Basic Orientation
[ ] Dataset Preparation
[ ] Data Cleaning
[ ] Data Modeling
[ ] DAX Measures
[ ] Sales Overview
[ ] Sales Analysis
[ ] Product & Category Analysis
[ ] Branch Analysis
[ ] Validation
[ ] Business Insights
[ ] Documentation
[ ] GitHub Portfolio
[ ] Final Review
```

Status tidak boleh dianggap selesai hanya karena sudah dibahas. Status selesai ketika hasilnya benar-benar sudah dikerjakan dan divalidasi.

---

# 18.8 Change Control

Jika user ingin mengubah requirement:

1. Identifikasi bagian PRD yang terdampak.
2. Jelaskan dampak perubahan secara singkat.
3. Minta konfirmasi user.
4. Setelah disetujui, update requirement yang relevan.
5. Jangan mengubah bagian lain yang tidak terdampak.

---

# 18.9 Final Project Quality

Sebelum project dinyatakan selesai, AI harus membantu melakukan review terhadap:

- Akurasi data.
- Akurasi perhitungan.
- Relationship data model.
- DAX.
- Konsistensi KPI.
- Business questions.
- Dashboard usability.
- Visual hierarchy.
- Documentation.
- GitHub presentation.

Project final harus dapat dipertanggungjawabkan sebagai portfolio, bukan hanya sebagai latihan Power BI.

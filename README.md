# Analisis Pembatalan Pesanan E-Commerce Indonesia 2023–2025

## Repository Outline

```
1. description.md         - Dokumentasi dan deskripsi project ini
2. Data Analysis.ipynb  - Notebook Python berisi analisis data lengkap
3. all_months_clean_2.csv    - Dataset hasil data cleaning (siap digunakan)

```

## Problem Background

Platform e-commerce Indonesia menghadapi tantangan tingginya tingkat pembatalan pesanan (*order cancellation*) yang berada di angka **13,57%** selama periode Desember 2023 – November 2025. Tingginya angka pembatalan ini berdampak langsung pada penurunan pendapatan, pemborosan sumber daya logistik, serta menurunnya kepercayaan penjual dan pembeli terhadap platform.

Analisis ini bertujuan mengidentifikasi faktor-faktor utama penyebab pembatalan pesanan — mulai dari alasan pembatalan, metode pembayaran, hingga opsi pengiriman — guna memberikan rekomendasi yang tepat untuk menurunkan angka pembatalan menjadi **12,5% atau lebih rendah dalam 1 tahun ke depan**.

## Project Output

- **Python Notebook** — Analisis statistik deskriptif & inferensial lengkap beserta 4 visualisasi data
- **Tableau Dashboard** — Dashboard interaktif menampilkan visualisasi data dan hasil analisis statistik

## Data

| Keterangan | Detail |
|---|---|
| Sumber | [Kaggle — Indonesia E-Commerce Sales and Shipping 2023–2025](https://www.kaggle.com/datasets/bakitacos/indonesia-e-commerce-sales-and-shipping-20232025) |
| Jumlah Baris | 208.484 transaksi |
| Jumlah Kolom | 18 kolom |
| Periode | Desember 2023 – November 2025 |
| Missing Values | 18.018 nilai null pada kolom `Alasan Pembatalan` (ditangani dengan imputasi) |
| Tipe Data | 9 kolom numerik (int64), 9 kolom kategorikal (object) |

**Kolom utama yang dianalisis:**
- `Status Pesanan` — status akhir pesanan (Batal / Selesai)
- `Alasan Pembatalan` — alasan pembatalan yang diisi pembeli
- `Metode Pembayaran` — metode pembayaran yang digunakan
- `Opsi Pengiriman` — layanan pengiriman yang dipilih
- `Perkiraan Ongkos Kirim` — estimasi biaya pengiriman
- `Waktu Pesanan Dibuat` — timestamp pembuatan pesanan

## Method

### Data Cleaning
- Konversi kolom `Waktu Pesanan Dibuat` ke format datetime
- Imputasi nilai null pada `Alasan Pembatalan`:
  - Pesanan dengan status `Selesai` → diisi `"Tidak Dibatalkan"`
  - Pesanan dengan status `Batal` tanpa alasan → diisi `"Tidak Diketahui"`
- Drop kolom `source_file` yang tidak relevan
- File di `all_months_clean_2.csv`

### Analisis
1. **Frekuensi Alasan Pembatalan** — Top 10 alasan pesanan dibatalkan
2. **Persentase Pembatalan per Metode Pembayaran** — Identifikasi metode pembayaran dengan pembatalan tertinggi
3. **Persentase Pembatalan per Opsi Pengiriman** — Top 10 opsi pengiriman dengan pembatalan tertinggi
4. **Tren Pembatalan per Bulan** — Pola pembatalan dalam 24 bulan (Des 2023 – Nov 2025)
5. **Statistik Deskriptif** — Analisis distribusi ongkos kirim pesanan batal (mean, median, mode, std, skewness)
6. **Statistik Inferensial** — Mann-Whitney U Test untuk menguji perbedaan ongkir antara pesanan batal dan selesai

## Stacks

| Kategori | Tools / Library |
|---|---|
| Bahasa Pemrograman | Python 3 |
| Data Manipulation | `pandas` |
| Visualisasi | `matplotlib`, `seaborn` |
| Dashboard | Tableau Public |
| Environment | Jupyter Notebook |

## Reference

- Dataset: [Indonesia E-Commerce Sales and Shipping 2023–2025 — Kaggle](https://www.kaggle.com/datasets/bakitacos/indonesia-e-commerce-sales-and-shipping-20232025)
- Dashboard Tableau: [Dashboard Tableau](https://public.tableau.com/views/Book1_17726417772740/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

**Dibuat oleh:** Michael Richard L 

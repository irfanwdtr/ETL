# Trading Analytics Pipeline – Saham Grup Prajogo Pangestu

## 📌 Gambaran Proyek

Proyek ini merupakan **end-to-end trading analytics pipeline** yang bertujuan untuk mengambil, mengolah, menganalisis, dan memvisualisasikan data saham Indonesia.

Fokus analisis adalah **saham-saham Grup Prajogo Pangestu**, dengan menggunakan data historis harga saham untuk mengevaluasi **kinerja (performance)** dan **risiko (risk)** melalui metrik seperti **daily return, cumulative return, dan equity curve**.

Pipeline dimulai dari **pengambilan data menggunakan Python (yfinance)** dan diakhiri dengan **dashboard interaktif menggunakan Power BI**.

---

## 🎯 Tujuan Proyek

* Membangun pipeline analytics yang **realistis seperti di dunia kerja**
* Menganalisis performa historis saham dalam satu grup bisnis
* Menunjukkan pemahaman tentang **Python, financial metrics, data cleaning, dan BI dashboard**
* Membuat proyek **portfolio-ready** (bukan prediksi harga, bukan trading bot)

---

## 📊 Ruang Lingkup Analisis

* Pasar: **Indonesia Stock Exchange (IDX)**
* Grup Saham: **Grup Prajogo Pangestu**
* Sampel Saham:

  * BREN
  * CUAN
  * TPIA
  * PTRO
* Periode Data: **2024 – 2026**

---

## 🧱 Arsitektur Pipeline

```
yfinance (API)
   ↓
Python (Pandas, NumPy)
   ↓
Data Cleaning & Transformation
   ↓
Perhitungan Financial Metrics
   ↓
Export CSV / SQLite
   ↓
Power BI Dashboard
```

---

## 🧰 Tech Stack

* **Python** (data ingestion & processing)

  * pandas
  * numpy
  * yfinance
* **Data Storage**:

  * CSV (output final)
    
* **Visualization**:

  * Power BI

---

## 🔄 Data Ingestion

Data historis saham diambil menggunakan library **yfinance**.

Field data yang digunakan:

* date
* open
* high
* low
* close
* volume
* symbol

Data dari beberapa saham digabung dalam format **long table** (satu baris per tanggal per saham), yang merupakan format terbaik untuk analisis dan BI tools.

---

## 🧹 Data Cleaning & Preparation

Tahapan pembersihan data dilakukan di Python, meliputi:

* Konversi datetime menjadi format `YYYY-MM-DD`
* Penghapusan suffix ticker (contoh: `.JK`)
* Konversi kolom harga (`open`, `high`, `low`, `close`) menjadi integer
* Penanganan missing value pada hari pertama perdagangan
* Konsistensi struktur data untuk seluruh saham

---

## 📐 Financial Metrics

### 1️⃣ Daily Return

Mengukur perubahan harga harian berdasarkan harga penutupan:

```
Daily Return = (Close_today − Close_yesterday) / Close_yesterday
```

### 2️⃣ Cumulative Return

Mengukur total keuntungan atau kerugian sejak awal periode data:

```
Cumulative Return = (1 + r1) × (1 + r2) × ... − 1
```

Nilai ini mencerminkan performa **buy-and-hold** dari awal periode.

### 3️⃣ Equity Curve

Simulasi pertumbuhan modal dengan asumsi:

* Modal awal: **Rp 1.000.000**
* Full investment sejak hari pertama

```
Equity Curve = Initial Capital × (1 + Cumulative Return)
```

---

## 🗃️ Output Data

Dataset akhir yang dihasilkan:

### `fact_prices_clean.csv`

Berisi data time series per saham:

* date
* symbol
* open, high, low, close
* volume
* daily_return_pct
* cumulative_return_pct
* equity_curve


File ini **siap di-import ke RDBMS atau BI tools**.

---

## 📊 Power BI Dashboard

Dashboard Power BI menampilkan:

* Equity Curve per saham
* KPI Cumulative Return (%)
* Tren harga saham
* Filter interaktif berdasarkan symbol dan date

### Prinsip Desain Dashboard

* Menggunakan satu fact table (long format)
* Agregasi yang benar:

  * Equity curve menggunakan **MAX**, bukan SUM
  * Return ditampilkan berdasarkan nilai terakhir per periode
* Format mata uang menggunakan **Rupiah (Rp)**

---

## 🧠 Insight yang Dihasilkan

* Perbandingan performa saham dalam satu grup bisnis
* Identifikasi saham dengan drawdown terbesar dan volatilitas tertinggi
* Visualisasi pertumbuhan modal dan risiko secara historis

---

## 🚫 Di Luar Cakupan

* Prediksi harga saham
* Trading signal atau automation
* Machine learning model

Proyek ini fokus pada **descriptive dan diagnostic analytics**.

---

## 💼 Nilai Portfolio

Proyek ini menunjukkan kemampuan:

* Merancang pipeline data end-to-end
* Memahami data dan metrik finansial
* Melakukan data cleaning dan transformasi di Python
* Menyusun data untuk BI dan dashboard
* Menyajikan insight secara profesional

---


## 👤 Irfan Widiantoro

Proyek ini dibuat sebagai **proyek pembelajaran dan portfolio** di bidang Data Analytics dan Business Intelligence.

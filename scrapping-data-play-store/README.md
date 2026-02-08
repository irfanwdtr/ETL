Google Play Store Review Scraping (Python)
Deskripsi Proyek

Proyek ini bertujuan untuk melakukan web scraping review aplikasi Google Play Store menggunakan library google-play-scraper dengan bahasa Python. Data hasil scraping digunakan untuk analisis sentimen, evaluasi rating, dan eksplorasi opini pengguna.

Tools & Library

Python

google-play-scraper

pandas

numpy

Fitur Utama

Mengambil review aplikasi dari Google Play Store berdasarkan jumlah tertentu

Mendukung filter bahasa, negara, rating, dan metode sorting (relevan / terbaru)

Mengubah hasil scraping ke dalam bentuk DataFrame

Melakukan sorting review berdasarkan tanggal terbaru

Menyimpan data ke format CSV untuk analisis lanjutan

Data yang Dikumpulkan

Kolom utama yang dihasilkan:

userName : Nama pengguna

score : Rating (1–5)

at : Tanggal & waktu review

content : Isi ulasan

Output

File scrapped_data.csv yang berisi review aplikasi dan siap digunakan untuk:

Analisis sentimen

Visualisasi data

Machine Learning / NLP

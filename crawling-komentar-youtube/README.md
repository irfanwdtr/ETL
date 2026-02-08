YouTube Comment Scraper using YouTube Data API (Python)
Deskripsi Proyek

Proyek ini bertujuan untuk melakukan scraping komentar YouTube menggunakan YouTube Data API v3 dan bahasa Python. Script mampu mengambil komentar utama (top-level comments) beserta balasannya (replies) dari sebuah video YouTube, lalu menyimpannya dalam format CSV dan Excel untuk analisis lebih lanjut.

Tools & Library

Python

YouTube Data API v3

google-api-python-client

pandas

Fitur Utama

Mengambil komentar dari satu video YouTube berdasarkan Video ID

Mendukung pagination (mengambil komentar dalam jumlah besar secara otomatis)

Menyimpan:

komentar utama

balasan komentar (replies)

Setiap komentar & reply disimpan sebagai baris terpisah

Output data dalam format CSV dan Excel (.xlsx)

Siap digunakan untuk:

Analisis sentimen

Text mining / NLP

Social media analysis

Struktur Data

Kolom utama yang dihasilkan:

comment : Isi komentar / balasan

author : Nama penulis komentar

reply_to_author : Nama author komentar utama (kosong jika komentar utama)

likeCount : Jumlah likes komentar

publishedAt : Tanggal & waktu komentar dipublikasikan

Cara Kerja Singkat

Menghubungkan Python dengan YouTube Data API menggunakan API Key

Mengambil komentar menggunakan endpoint commentThreads

Mengolah data komentar dan replies ke dalam DataFrame

Menyimpan hasil scraping ke file CSV / Excel

Output

youtube_comments.csv

youtube_comments_split_rows.xlsx

File output siap digunakan untuk analisis lanjutan atau visualisasi data

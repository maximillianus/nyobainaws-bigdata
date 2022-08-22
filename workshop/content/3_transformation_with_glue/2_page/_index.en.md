+++
title = "Create Glue Crawler"
weight = 22
chapter = false
+++

### Membuat AWS Glue Crawlers

Dalam step ini kita masih akan ada di konsol AWS Glue untuk membuat Glue Crawler. Glue Crawler akan membaca data dan membuat skema dari data tersebut secara otomatis.

- Pergi ke konsol AWS Glue
- Di panel sebelah kiri, klik Crawlers > lalu klik Add Crawler
  - Informasi Crawler:
    - Crawler name: AnalyticsworkshopCrawler
  - Step ini opsional namun anda dapat menambahkan Tags seperti
      - Key: workshop
      - Value: AnalyticsOnAWS
  - Klik Data stores
  - Klik Next
  - Pilih sebuah Data Store:
    - Data store: s3
    - Crawl data in: Specified path in my account
    - Include path: s3://yourname-analytics-workshop-bucket/data/
    - Klik Next
    - Pada pilihan Add another data store, piih No.
    - Klik Next
- IAM Role
  - Pilih Choose and existing IAM role
  - Role name: AnalyticsworkshopGlueRole
  - Klik Next
- Schedule
  - Frequency: Run on demand
  - Klik Next
- Output
  - Klik Add database
  - Database name: analyticsworkshopdb
  - Klik Create
  - Klik Next
- Review semua step
  - Baca ulang semua konfigurasi dan pastikan konfigurasi tersebut sama seperti step di atas.
  - Klik Finish
- Anda harusnya dapat melihat message ini sesudah selesai "Crawler analyticsworkshopdb sudah dibuat untuk jalan on-demand"
  - Pilih checkbox crawler
  - Klik Run on demand untuk menjalankan crawler pada pertama kali nya.
  - Tunggu beberapa menit sampai crawler selesai.


### Membuat AWS Glue Crawlers

Mari kita validasi bahwa semua tabel sudah ada.
- Klik Click me
  - Klik analyticsworkshopdb
- Klik Tables in analyticsworkshopdb
  - Klik raw
  - Eksplorasi skema dari dataset anda.
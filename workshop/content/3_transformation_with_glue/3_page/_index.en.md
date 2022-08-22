+++
title = "View Data Catalog"
weight = 23
chapter = false
+++

### Melihat hasil Data Catalog

Glue Data Catalog adalah sebuah database katalog yang berisi metadata dari semua tabel-table yang dipindai oleh Glue Crawler. Apabila di step sebelumnya proses pemindaian berhasil maka kita dapat melihat hasil Data Catalog tersebut.

- Pergi ke konsol AWS Glue
  - Klik analyticsworkshopdb
- Klik Tables in analyticsworkshopdb
  - Klik raw
  - Eksplorasi skema dari dataset kita
    - Bisa dicoba untuk melihat `averageRecordSize`, `recordCount`, dan `compressionType`:
      - `averageRecordSize` : besar rata-rata dari sebuah data di tabel ini
      - `recordCount`: jumlah data di tabel ini
      - `compressionType` : jenis kompresi data

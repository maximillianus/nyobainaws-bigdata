+++
title = "Query with Athena"
weight = 31
chapter = false
+++

### Analisa data menggunakan Amazon Athena

Amazon Athena merupakan layanan kueri Serverless yang bisa membantu kita meng-kueri dan meng-analisa data baik di S3 maupun di database.

Mari kita coba kueri data mentah yang sudah di-katalog-kan oleh Glue:
- Pergi ke konsol Athena
- Setup lokasi hasil kueri ketika ditanya oleh prompt console:
  - Masukkan bucket `s3://yourname-analytics-workshop-bucket/query_results/`
  - Klik Save
- Di panel sebelah kiri, pilih `analyticsworkshopdb` > Pilih table `raw`
- Klik di lambang 3 titik > Pilih Preview Table
- Review kembali hasil outputnya
- Di editor kueri, masukkan query berikut. Query berikut menghitung jumlah data berdasarkan tipe aktivitas.
```
SELECT activity_type,
         count(activity_type)
FROM raw
GROUP BY  activity_type
ORDER BY  activity_type
```
- Klik Run Query
- Kita juga dapat memasukkan query lain contohnnya:
```
SELECT activity_type,
         count(activity_type)
FROM raw
GROUP BY  activity_type
ORDER BY  activity_type
```

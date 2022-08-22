+++
title = "Create IAM Role"
weight = 21
chapter = false
+++

### Membuat IAM Role

IAM Role diperlukan untuk memberikan akses tertentu terhadap layanan AWS Glue. Akses ini dibutuhkan AWS Glue agar layanan ini dapat meng-akses data yang tersimpan di S3 dan membuat Glue Data Catalog.

- Pergi ke konsol AWS Glue
- Klik Create role
  - Pilih layanan yang akan menggunakan role ini: Glue
  - Klik Next: Permissions
  - Cari kebijakan AmazonS3FullAccess
    - Lalu klik centang di checkbox
  - Cari kebijakan AWSGlueServiceRole
    - Lalu klik centang di checkbox
  - Klik Next: Tags
  - Step ini opsional namun anda dapat menambahkan Tags seperti
    - Key: workshop
    - Value: AnalyticsOnAWS
  - Klik Next: Review
  - Nama Role: AnalyticsworkshopGlueRole
  - Pastikan hanya ada 2 kebijakan yang tercantum di role ini **(AmazonS3FullAccess, AWSGlueServiceRole)**
  - Klik **Create role**

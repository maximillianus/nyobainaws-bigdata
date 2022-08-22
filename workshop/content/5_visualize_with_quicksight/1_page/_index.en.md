+++
title = "Setup Quicksight"
weight = 41
chapter = false
+++

### Setup Quicksight

Di step berikut kita akan memvisualisasikan data yang telah diproses menggunakan Quicksight
- Pergi ke konsol Quicksight
- Klik Sign up Quicksight
- Pastikan Enterprise dipilih lalu klik Continue
- Quicksight account name: yournameanalyticsworkshop
- Notification email address: you@youremail.com
- Pilih Amazon Athena - Ini memperbolehkan Quicksight untuk mengakses tabel di Athena
- Pilih Amazon S3:
  - Pilih yourname-analytics-workshop-bucket
  - Klik Finish
- Klik Finish
- Tunggu akun Quicksight selesai dibuat

### Tambahkan Dataset
- Pergi ke konsol Quicksight
- Di pilihan kanan atas, klik Manage Data
  - Klik New Data Set
  - Klik Athena
  - Sumber Data Athena baru:
    - Data source name: analyticsworkshop
    - Klik Validate connection
      - Ini akan mengecek apabila Quicksight dapat mengakses Athena
    - Klik Create data source
  - Pilih tabel:
    - Database: analyticsworkshopdb
    - Table: processed_data
    - Klik Select
  - Selesaikan pembuatan dataset:
    - Pilih Directly query your data
    - Klik Visualize

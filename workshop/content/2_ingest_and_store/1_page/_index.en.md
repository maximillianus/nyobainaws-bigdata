+++
title = "Create S3"
weight = 11
chapter = false
+++

### Membuat bucket S3

Di step ini kita akan pergi ke konsol S3 dan membuat bucket S3 yang akan digunakan sebagai tempat penampungan data di workshop ini.

- Login ke konsol AWS
- Pergi ke konsol S3
- Klik - Create Bucket
  - Bucket Name: yourname-analytics-workshop-bucket
  - Region: US EAST (N. Virginia)
  - Step ini opsional namun anda dapat menambahkan Tags seperti
    - Key: workshop
    - Value: AnalyticsOnAWS
  - Klik Create Bucket
- Menambahkan data referensi
  - Buka bucket yang baru saja dibuat yourname-analytics-workshop-bucket
    - Klik Create folder
      - Beri nama folder tersebut: data
      - Klik Save
  - Buka folder data
    - Klik Create folder di dalam folder data tersebut
      - Beri nama folder tersebut: reference_data
      - Klik Save
  - Buka folder reference_data
    - Unduh file ini di komputer anda: tracks_list.json
    - Di konsol S3, Klik Upload
      - Klik Add files dan unggah file tracks_list.json disini
      - Klik Upload di bagian kiri bawah

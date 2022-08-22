+++
title = "Create Kinesis Data Generator"
weight = 13
chapter = false
+++

### Membuat data sampel

Dalam step ini kita akan mengkonfigurasi sebuah aplikasi web untuk membuat dan mengirim data sampel. Aplikasi ini disebut Kinesis Data Generator. Kita akan mengirim data sampel ini ke Kinesis Data Firehose.

- Kita akan menggunakan skrip Cloudformation untuk mempermudah setup aplikasi web Kinesis Data Generator
  - Klik tautan berikut: https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=Kinesis-Data-Generator-Cognito-User&templateURL=https://aws-kdg-tools-us-east-1.s3.amazonaws.com/cognito-setup.json
  - Klik Next
  - Isi Detil:
    - Username: admin
    - Password: pilih password berupa huruf dan angka
    - Klik Next
  - Step ini opsional namun anda dapat menambahkan Tags seperti
    - Key: workshop
    - Value: AnalyticsOnAWS
  - Review:
    - Skrol ke bawah
    - Pada tulisan "I acknowledge that AWS Cloudformation might create IAM resources", centang box.
    - Klik Create stack
  - Tunggu sampai status stack berubah menjadi CREATE_COMPLETE
    - Anda dapat mengklik tombol Refresh untuk membantu meng-update status tack terbaru
  - Ketika status stack sudah berubah menjadi CREATE_COMPLETE:
    - Pilih stack Kinesis-Data-Generator-Cognito-User
    - Pergi ke tab Output dan klik tautan dengan nama KinesisDataGeneratorUrl. Ini akan membuka URL aplikasi web anda.
- Di halaman utama Amazon Kinesis Data Generator
  - Login dengan menggunakan username dan password di step sebelumnya
  - Region: us-east-1
  - Stream/delievry stream: analytics-workshop-stream
  - Records per second: 2000
  - Record template (Template 1): Di area textbox besar, masukkan template JSON berikut:
    ```
    {
      "uuid": "{{random.uuid}}",
      "device_ts": "{{date.utc("YYYY-MM-DD HH:mm:ss.SSS")}}",
      "device_id": {{random.number(50)}},
      "device_temp": {{random.weightedArrayElement(
        {"weights":[0.30, 0.30, 0.20, 0.20],"data":[32, 34, 28, 40]}
      )}},
      "track_id": {{random.number(30)}},
      "activity_type": {{random.weightedArrayElement(
            {
                "weights": [0.1, 0.2, 0.2, 0.3, 0.2],
                "data": ["\"Running\"", "\"Working\"", "\"Walking\"", "\"Traveling\"", "\"Sitting\""]
            }
        )}}
    }
    ```
  - Klik **Send Data**
  - Tunggu sejenak ketika aplikasi web ini sedang membuat dan mengirim data sampel. Ketika sudah terkirim 10 ribu data, Klik **Stop sending data to Kinesis**.

### Mem-validasi pengiriman data sukses
Kita dapat memastikan pengirim data sampel sukses dengan mengecek bucket S3
- Pergi ke konsol S3
- pergi ke bucket **yourname-analytics-workshop-bucket** lalu ke folder `data`
- Pastikan ada folder bernama `raw`.
- Apabila anda masuk ke dalam folder `raw` ini, anda akan lihat data sudah masuk dan sudah ada partisi sesuai dengan tanggal dalam bentuk `yyyy/mm/dd`.

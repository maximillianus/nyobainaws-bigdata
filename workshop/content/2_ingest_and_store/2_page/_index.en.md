+++
title = "Create Kinesis Firehose"
weight = 12
chapter = false
+++

### Membuat Kinesis Firehose

Di step berikut kita akan pergi ke konsol Kinesis dan membuat Kinesis Firehose delivery stream untuk memasukkan dan menyimpan data di S3.

- Pergi ke Kinesis Firehose konsol
- Klik **Create Delivery Stream**
  - Step 1: Pilih source dan destination
    - Source: Direct PUT or other sources
    - Destination: Amazon S3
  - Step 2: Nama Delivery Stream
    - Delivery Stream: analytics-workshop-stream
  - Step 3: Transformasi data
    - Data Transformation: Disabled
    - Record format conversion: Disabled
  - Step 4: Pengaturan Tujuan
    - S3 bucket: yourname-analytics-workshop-bucket
    - Dynamic partitioning: Disabled
    - S3 bucket prefix: data/raw
    - S3 bucket error output prefix: Leave Blank
    - Klik Buffer hints, compression and encryption
      - Buffer size: 1 MiB
      - Buffer interval: 60 seconds
      - Compression for data records: Disabled
      - Encryption for data records: Disabled
  - Step 5: Pengaturan lanjutan
    - Server-side encryption: unchecked
    - Amazon Cloudwatch error logging: Enabled
    - Permissions: Create or update IAM role KinesisFirehoseServiceRole-xxxx
    - Step ini opsional namun anda dapat menambahkan Tags seperti:
      - Key: workshop
      - Value: AnalyticsOnAWS
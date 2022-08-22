+++
title = "Create Processed Table"
weight = 32
chapter = false
+++

### Membuat Table dengan Menggunakan CTAS (Create Table As Select)
Athena memiliki fungsi CTAS atau CREATE TABLE AS SELECT dimana kita dapat membuat table baru hasil dari kueri SELECT. Hasil data dari kueri SELECT ini nantinya akan disimpan di lokasi tersendiri di bucket S3. Tabel ini juga secara otomatis akan didaftarkan dalam Glue Data Catalog.

- Pergi ke konsol Athena
  - Di panel sebelah kiri, klik Query Editor
  - Pastikan database adalah `analyticsworkshopdb`
  - Buat 1 tab kueri baru dengan meng-klik tanda `+`
  - Masukkan kueri di bawah

    ```
    CREATE TABLE IF NOT EXISTS analyticsworkshopdb.processed_data
      WITH (format='Parquet', external_location='s3://apradana-analytics-workshop-bucket/data/processed_data/') AS
    SELECT
        a.uuid,
        a.device_ts,
        a.device_id,
        a.device_temp,
        cast(a.track_id as varchar) as track_id,
        a.activity_type,
        b.track_name,
        b.artist_name
    FROM raw a
    JOIN reference_data b on cast(a.track_id as varchar)=b.track_id
    ```
  - Lalu klik Run

- Anda bisa menjalankan kueri dari hasil tabel yang baru dibuat di atas
  - Buat 1 tab kueri baru dengan meng-klik tanda `+`
  - Masukkan kueri di bawah untuk melihat jumlah data berdasarkan nama artis:
    ```
    SELECT artist_name,
           count(artist_name) AS count
    FROM processed_data
    GROUP BY artist_name
    ORDER BY count desc
    ```
  - Anda masih bisa mengeksplorasi data tersebut lebih banyak. Kueri berikut menghasilkan nama-nama lagu yang sering diputar oleh alat tertentu.
    ```
    SELECT device_id,
           track_name,
           count(track_name) AS count
    FROM processed_data
    GROUP BY device_id, track_name
    ORDER BY count desc
    ```
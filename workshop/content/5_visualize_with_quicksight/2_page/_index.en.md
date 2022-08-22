+++
title = "Visualize with Quicksight"
weight = 42
chapter = false
+++

### Visualisasi dengan menggunakan Quicksight

Setelah men-setup Quicksight dan menambahkan dataset, sekarang kita dapat mulai membuat analisis dan dashboard di Quicksight.

### Visualisasi 1: Heatmap dari pengguna dan track lagu
Dalam step ini  kita akan membuat sebuah visualisasi yang menunjukkan pengguna mana yang mendengarkan track secara berulang-ulang.

- Di panel sebelah kiri bawah (Visual types):
  - Anda bisa melihat berbagai macam tipe grafik dan visualisasi disini
  - Klik Heat Map
- Di panel sebelah kiri atas (Fields list):
  - Klik device_id
  - Klik track_name

Di atas area visualisasi utama, anda dapat melihat Fields wells: Rows: device_id | Columns track_name

Apabila anda melayangkan mouse di atas kotak biru dalam visualisasi heatmap, anda dapat berapa kali track lagu tersebut diputar oleh pengguna tertentu.

[Visualisation Picture]


### Visualization 2: Tree map dari nama artis yang paling banyak diputar
Dalam step ini kita akan buat visualisasi yang menunjukkan artis mana yang lagunya sering diputar.

- Di panel sebelah kiri atas, klik + Add > Add Visual. Ini akan menambahkan panel baru di sebelah kanan
- Di panel sebelah kiri bawah (Visual types):
  - Pilih dan klik Tree Map
- Di panel sebalah kiri atas (Fields list):
  - Klik artist_name

Anda juga dapat bermain-main dan mengeksplorasi fitur lain dari konsol Quicksight ini. Anda bisa mencoba filter maupun visualisasi tipe lain.

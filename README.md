# sr-programming-test-1
## Deskripsi
Repositori ini digunakan sebagai rujukan untuk test pemrograman senior.

# Spesifikasi Program
Pemohon diharapkan dapat menunjukkan pemahaman dan kemampuannya membuat program dengan membuat aplikasi sederhana yang:
* dibuat dalam bahasa yang dikuasai (java, scala, python, atau lainnya; preferable menggunakan java)
* (tugas 1) membaca file dan memasukkan isi file per line ke dalam database dan solr
* (tugas 2) melakukan proses harian yang menghitung top engagement dan mengirimkan hasilnya ke email

## tugas 1
Akan diberikan 10 file teks yang berisi json-styled twitter conversation ([link](https://drive.google.com/file/d/1N4MXEgT3y_lt1LgPKcWGZgh1BSw5f75e/view?usp=sharing)). File-file tersebut akan diproses (dengan multithread) untuk dimasukkan ke dalam database mysql dan apache solr. Adapun spesifikasi sebagai berikut:
* file disimpan dalam folder tertentu
* setiap file diproses untuk dibaca dan data setiap conversation (perline) dimasukkan ke dalam tabel database `twitter_feed` dengan [skema berikut](twitter_feed_db.sql)
* setiap conversation juga dimasukkan ke dalam apache solr dengan nama collection `twitter_feed` dengan [skema berikut](twitter_feed_solr.txt)
* implementasikan multithread di setiap tempat yang memungkinkan, dengan jumlah maksimal 3 thread

## tugas 2
Membuat bot yang membuat laporan dengan spesifikasi berikut:
* laporan dijalankan harian setiap jam 5 pagi
* laporan menggunakan data hari kemarin
* laporan menghitung:
  * top 10 twitter engagement : 10 besar tweet dengan jumlah engagement terbanyak
  * top 10 twitter author : 10 besar author dengan jumlah tweet terbanyak
* Hasil laporan dituliskan dalam format excel atau html
* laporan dikirimkan ke email admin@sonar.id dengan attachment hasil laporan

## Tambahan:
* Field status_type di tabel twitter_feed ataupun field status_type_i di collection twitter_feed
  * tweet   : post/conversation dengan status_type 0 atau 1 atau 2
  * retweet : post/conversation dengan status_type 1
  * reply   : post/conversation dengna status_type 2
  * engagement : retweet + reply

## Penilaian:
* Code Readability
* Penggunaan Model-View-Control
* Penggunamaan nama yang baik untuk Kelas, Fungsi, Variabel
* Penggunaan framework ataupun library
* Implementasi Multithread

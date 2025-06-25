# Final Project Sistem Operasi IT

## Peraturan
1. Waktu pengerjaan dimulai hari Kamis (19 Juni 2025) setelah soal dibagikan hingga hari Rabu (25 Juni 2025) pukul 23.59 WIB.
2. Praktikan diharapkan membuat laporan penjelasan dan penyelesaian soal dalam bentuk Readme(github).
3. Format nama repository github “Sisop-FP-2025-IT-[Kelas][Kelompok]” (contoh:Sisop-FP-2025-IT-A01).
4. Setelah pengerjaan selesai, seluruh source code dan semua script bash, awk, dan file yang berisi cron job ditaruh di github masing - masing kelompok, dan link github dikumpulkan pada form yang disediakan. Pastikan github di setting ke publik.
5. Commit terakhir maksimal 10 menit setelah waktu pengerjaan berakhir. Jika melewati maka akan dinilai berdasarkan commit terakhir.
6. Jika tidak ada pengumuman perubahan soal oleh asisten, maka soal dianggap dapat diselesaikan.
7. Jika ditemukan soal yang tidak dapat diselesaikan, harap menuliskannya pada Readme beserta permasalahan yang ditemukan.
8. Praktikan tidak diperbolehkan menanyakan jawaban dari soal yang diberikan kepada asisten maupun praktikan dari kelompok lainnya.
9. Jika ditemukan indikasi kecurangan dalam bentuk apapun di pengerjaan soal final project, maka nilai dianggap 0.
10. Pengerjaan soal final project sesuai dengan modul yang telah diajarkan.

## Kelompok x

Nama | NRP
--- | ---
... | 5027241xxx
... | 5027241xxx
... | 5027241xxx
M. Faqih Ridho | 5027241123

## Deskripsi Soal
Test Case 30
Si Paling Aplikasi
Buat sebuah aplikasi web sederhana menggunakan Python dan Flask yang menampilkan pesan "Halo dari Kelompok[x]". Pakai Docker Compose untuk mendefine dan menjalankan aplikasi ini dan konfigurasikan juga agar docker compose membangun image dari Dockerfile lokal dan memetakan port container ke port di host.
### Catatan

> Insert catatan dari pengerjaan kalian... (contoh dibawah) // hapus line ini

Struktur repository:
```
.
..
```

## Pengerjaan

> Insert poin soal...

**Teori**
Flask adalah kerangka kerja aplikasi web untuk Python yang diklasifikasikan sebagai "kerangka kerja mikro". Sebutan "mikro" tidak berarti Flask kekurangan fungsionalitas; sebaliknya, ini mengacu pada filosofi desainnya. Flask bertujuan untuk menjaga intinya tetap sederhana namun dapat diperluas. Ia menyediakan komponen-komponen esensial untuk pengembangan web tanpa memaksakan struktur proyek atau dependensi tertentu pada pengembang.   

Secara internal, Flask bergantung pada dua pustaka utama: toolkit Werkzeug WSGI untuk menangani antarmuka tingkat rendah antara server dan aplikasi, dan mesin template Jinja untuk merender halaman HTML. Fleksibilitas ini memungkinkan pengembang untuk memilih alat dan pustaka yang paling sesuai dengan kebutuhan mereka, seperti memilih komponen basis data atau pustaka validasi formulir.   

Filosofi minimalis ini memiliki implikasi penting. Secara default, Flask menyertakan server pengembangan yang disediakan oleh Werkzeug. Server ini sangat berguna untuk debugging dan pengujian selama pengembangan karena fitur-fiturnya seperti auto-reloader. Namun, server ini tidak dirancang untuk menangani beban kerja produksi dan secara eksplisit dinyatakan tidak cocok untuk penyebaran langsung. Akibatnya, tanggung jawab untuk memilih dan mengkonfigurasi server WSGI tingkat produksi, seperti Gunicorn atau uWSGI, jatuh pada pengembang. Ini menyoroti trade-off yang melekat pada Flask: ia menawarkan kebebasan dan kesederhanaan di awal, tetapi menuntut lebih banyak keputusan arsitektur saat aplikasi tumbuh menuju kesiapan produksi.   



**Solusi**

...

> Insert poin soal...

**Teori**
Docker adalah platform yang merevolusi cara perangkat lunak dibangun, dikirim, dan dijalankan dengan menggunakan teknologi kontainerisasi. Container adalah unit perangkat lunak standar yang mengemas kode aplikasi beserta semua dependensinya, seperti pustaka, alat sistem, dan runtime. Pengemasan ini memastikan bahwa aplikasi berjalan secara konsisten dan dapat diandalkan di berbagai lingkungan komputasi, mulai dari laptop pengembang hingga server produksi di cloud.
**Solusi**

...

**Video Menjalankan Program**
...

## Daftar Pustaka

Agarwal, G. (2021). Modern DevOps Practices: Implement and secure DevOps in the public cloud with cutting-edge tools, tips, tricks, and techniques. Packt Publishing.    
Humble, J., & Farley, D. (n.d.). Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation. Buku ini memberikan panduan komprehensif untuk menyederhanakan pengiriman perangkat lunak dan mengimplementasikan praktik terbaik untuk otomatisasi build, tes, dan deployment.    
Kim, G., Humble, J., Debois, P., & Willis, J. (n.d.). The DevOps Handbook: How to Create World-Class Agility, Reliability, and Security in Technology Organizations. Buku ini adalah panduan praktis untuk mengimplementasikan praktik DevOps, dibangun di atas konsep yang diperkenalkan dalam The Phoenix Project.    

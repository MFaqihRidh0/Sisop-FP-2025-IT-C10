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
Muhammad Fachry Shalahuddin Rusamsi | 5027241031
Raihan Fahri Ghazali | 5027241061
Muhammad Khairul Yahya | 5027241092
M. Faqih Ridho | 5027241123

## Deskripsi Soal
Test Case 30

Si Paling Aplikasi
Buat sebuah aplikasi web sederhana menggunakan Python dan Flask yang menampilkan pesan "Halo dari Kelompok[x]". Pakai Docker Compose untuk mendefine dan menjalankan aplikasi ini dan konfigurasikan juga agar docker compose membangun image dari Dockerfile lokal dan memetakan port container ke port di host.
### Catatan


Struktur repository:
```
└── FPSISOP
    ├── Dockerfile
    ├── Dockerfile:Zone.Identifier
    ├── __pycache__
    │   ├── app.cpython-39.pyc
    │   └── app.cpython-39.pyc:Zone.Identifier
    ├── app.py
    ├── app.py:Zone.Identifier
    ├── docker-compose.yml
    ├── docker-compose.yml:Zone.Identifier
    ├── requirements.txt
    └── requirements.txt:Zone.Identifier

```

## Pengerjaan

"Buat sebuah aplikasi web sederhana menggunakan Python dan Flask"

**Teori**

Flask adalah kerangka kerja aplikasi web untuk Python yang diklasifikasikan sebagai "kerangka kerja mikro". Sebutan "mikro" tidak berarti Flask kekurangan fungsionalitas; sebaliknya, ini mengacu pada filosofi desainnya. Flask bertujuan untuk menjaga intinya tetap sederhana namun dapat diperluas. Ia menyediakan komponen-komponen esensial untuk pengembangan web tanpa memaksakan struktur proyek atau dependensi tertentu pada pengembang.   

Secara internal, Flask bergantung pada dua pustaka utama: toolkit Werkzeug WSGI untuk menangani antarmuka tingkat rendah antara server dan aplikasi, dan mesin template Jinja untuk merender halaman HTML. Fleksibilitas ini memungkinkan pengembang untuk memilih alat dan pustaka yang paling sesuai dengan kebutuhan mereka, seperti memilih komponen basis data atau pustaka validasi formulir.   

Filosofi minimalis ini memiliki implikasi penting. Secara default, Flask menyertakan server pengembangan yang disediakan oleh Werkzeug. Server ini sangat berguna untuk debugging dan pengujian selama pengembangan karena fitur-fiturnya seperti auto-reloader. Namun, server ini tidak dirancang untuk menangani beban kerja produksi dan secara eksplisit dinyatakan tidak cocok untuk penyebaran langsung. Akibatnya, tanggung jawab untuk memilih dan mengkonfigurasi server WSGI tingkat produksi, seperti Gunicorn atau uWSGI, jatuh pada pengembang. Ini menyoroti trade-off yang melekat pada Flask: ia menawarkan kebebasan dan kesederhanaan di awal, tetapi menuntut lebih banyak keputusan arsitektur saat aplikasi tumbuh menuju kesiapan produksi.   



**Solusi**
```
app = Flask(__name__)

@app.route('/')
```
objek app ini menjadi jantung dan otak dari aplikasi web Anda. Objek ini bertanggung jawab untuk mengatur routing, mengelola siklus request-response, dan Menyediakan Server Pengembangan

@app.route('/') adalah cara Anda memberitahu objek app, "Jika ada permintaan masuk untuk URL root ('/'), tolong jalankan fungsi hello()." Tanpa objek dari kelas Flask, Anda tidak akan punya app dan tidak bisa membuat rute.
...

"Pakai Docker Compose untuk mendefine dan menjalankan aplikasi ini"

**Teori**

Docker adalah platform yang merevolusi cara perangkat lunak dibangun, dikirim, dan dijalankan dengan menggunakan teknologi kontainerisasi. Container adalah unit perangkat lunak standar yang mengemas kode aplikasi beserta semua dependensinya, seperti pustaka, alat sistem, dan runtime. Pengemasan ini memastikan bahwa aplikasi berjalan secara konsisten dan dapat diandalkan di berbagai lingkungan komputasi, mulai dari laptop pengembang hingga server produksi di cloud.

**Solusi**


1. File Aplikasi Flask

<pre>
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return 'Halo dari Kelompok 10'

if __name__ == '__main__':
    app.run()
</pre>
* Ini adalah aplikasi Flask dasar dengan satu route utama (/)
* Akan menampilkan "Halo dari Kelompok 10" saat diakses
* Dijalankan dengan server development bawaan Flask

2. Konfigurasi Docker Compose
<pre>
version: '3.8'
services:
  web:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "5000:5000"
    environment:
      - FLASK_ENV=development
    volumes:
      - .:/app
</pre>

* Mendefinisikan service web yang akan menjalankan aplikasi Flask
* Membangun image dari Dockerfile di direktori saat ini
* Mengekspos port 5000 container ke port 5000 host
* Mengatur environment variable untuk mode development
* Mount direktori saat ini ke /app di container untuk development

3. Dependensi Python
<pre>
flask==2.0.1
Werkzeug==2.0.3
</pre>

4. Dockerfile
<pre>
FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "app.py"]
</pre>

* Menggunakan image base Python 3.9 slim
* Menetapkan direktori kerja /app
* Menginstall dependensi dari requirements.txt
* Menyalin semua kode aplikasi
* Menjalankan aplikasi Flask
        
"konfigurasikan juga agar docker compose membangun image dari Dockerfile lokal dan memetakan port container ke port di host"

**Teori**

Meskipun Docker sangat baik untuk mengelola container individual, sebagian besar aplikasi dunia nyata tidak terdiri dari satu komponen tunggal. Aplikasi modern sering kali merupakan sistem terdistribusi yang terdiri dari beberapa layanan yang saling berinteraksi, seperti server web, basis data, layanan caching, dan antrian pesan. Mengelola siklus hidup setiap container secara manual—menjalankannya dengan perintah    

docker run yang panjang, mengkonfigurasi jaringan agar mereka dapat berkomunikasi, dan mengelola volume data—menjadi rumit dan rawan kesalahan.

Di sinilah Docker Compose berperan. Docker Compose adalah alat yang dirancang untuk mendefinisikan dan menjalankan aplikasi Docker multi-container. Dengan menggunakan file konfigurasi tunggal yang ditulis dalam format YAML (biasanya bernama    

docker-compose.yml), pengembang dapat mendefinisikan seluruh tumpukan aplikasi mereka, termasuk layanan, jaringan, dan volume. Setelah didefinisikan, seluruh aplikasi dapat dihidupkan dengan satu perintah sederhana:    

docker compose up.   

Meskipun tugas yang diberikan hanya melibatkan satu layanan (aplikasi web Flask), penggunaan Docker Compose tetap sangat relevan. Ini berfungsi sebagai alat pengembangan dan prototipe yang sangat baik. Pengembang dapat mendefinisikan lingkungan lokal mereka dalam satu file deklaratif, membagikannya dengan anggota tim lain, dan memastikan bahwa semua orang bekerja dengan tumpukan yang identik. Dengan memperkenalkan Docker Compose sejak dini, ini mengajarkan alur kerja berbasis layanan yang dapat diskalakan. Ini adalah langkah pertama yang sangat baik untuk memahami konsep orkestrasi yang lebih canggih seperti Kubernetes, karena ini menanamkan pola pikir deklaratif tentang bagaimana layanan harus didefinisikan dan dijalankan bersama.   

**Solusi**

Membungkus Aplikasi Flask ke dalam Image dan Menjalankannya melalui Docker Compose
- `Dockerfile` digunakan untuk membangun image berbasis `python:3.9-slim`.
- Menginstal dependensi dari `requirements.txt` dan menjalankan Flask menggunakan `CMD`.
- Image dijalankan melalui `docker-compose.yml` yang juga memetakan port dan environment.

```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["flask", "run", "--host=0.0.0.0"]

```

Penjelasan:

- Image dibangun dari file `Dockerfile` menggunakan base image `python:3.9-slim`.
- Flask dijalankan dengan perintah `flask run` dan host diset ke `0.0.0.0` agar dapat diakses dari luar container.
- `docker-compose.yml` digunakan untuk menjalankan image dan mengatur:
  - Port mapping `5000:5000` (akses via `http://localhost:5000`)
  - Environment development (`FLASK_ENV=development`)
  - Volume bind (`.:/app`) agar mendukung live reload.
- Proyek dijalankan dengan perintah:

```bash
docker-compose up --build
```

## Daftar Pustaka

1.Pallets, The. (2024). Flask: The Python micro framework for building web applications. Diakses pada 25 Juni 2025, dari https://github.com/pallets/flask 

2.Pallets, The. (2024). Werkzeug: The comprehensive WSGI web application library. Diakses pada 25 Juni 2025, dari https://github.com/pallets/werkzeug

3.Docker, Inc. (2024). Docker Compose. Diakses pada 25 Juni 2025, dari https://github.com/docker/compose
  

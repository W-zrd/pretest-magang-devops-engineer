# Pre-Test Bootcamp DevOps

## knowledge base (questions & answers)

1. Apa yang anda ketahui tentang DevOps?
   - DevOps adalah pendekatan yang menggabungkan tim developer dan tim operasi (ops) untuk mempercepat proses pengembangan dan rilis software. Tujuannya adalah agar aplikasi bisa dikembangkan, diuji, dan diluncurkan lebih cepat dan dengan kualitas yang lebih baik.
2. Apa yang anda ketahui tentang Infrastructure?
   - Infrastruktur adalah semua hal yang dibutuhkan untuk menjalankan aplikasi dan services sehingga bisa berjalan dengan baik. Contohnya yaitu server, jaringan, hingga storage.
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
   - Server adalah sistem yang menyediakan layanan tertentu ke komputer lain di jaringan. Misalnya, web server seperti Apache atau Nginx yang bertugas menyajikan halaman web, atau database server seperti MySQL yang menyimpan dan mengelola data aplikasi.
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
   - Server dibutuhkan untuk hosting aplikasi dan menyimpan data. Tanpa adanya server, aplikasi kita tidak akan bisa digunakan oleh orang lain. Server juga bisa digunakan untuk kolaborasi tim agar mereka dapat bekerja bersama, berbagi kode, dan mengintegrasikan perubahan dengan lancar.
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
   - Virtualisasi memungkinkan satu komputer fisik (host) menjalankan beberapa sistem operasi (guest) sekaligus melalui VM, sedangkan container adalah teknologi yang mengemas aplikasi beserta semua dependensinya dalam satu paket yang bisa berjalan secara terisolasi
6. Mengapa teknology container saat ini sangat populer?
   - Teknologi container sangat populer karena memberikan fleksibilitas yang tinggi dalam pengembangan dan deployment aplikasi. Container memungkinkan developer untuk mengemas aplikasi dengan semua dependensinya, sehingga bisa dijalankan di berbagai environment tanpa perlu khawatir tentang perbedaan konfigurasi.
7. Apa yang anda ketahui tentang Orchestration Container System?
   - Orchestration Container System adalah alat yang digunakan untuk mengelola, mengotomatisasi, dan mengoordinasikan container dalam jumlah besar. Misalnya, Kubernetes yang membantu mengelola dan mengatur container secara otomatis agar bisa berjalan dengan efisien dan stabil.

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`


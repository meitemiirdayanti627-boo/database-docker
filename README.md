# Database Service Menggunakan Docker

## Kelompok 4

**Anggota:**
1. Rangga Airlangga (062430701457)
2. Richard Fernando  (062430701458)
3. Temi Irdayanti  (062430701459)

**Kelas:** 3CD  
**Mata Kuliah:** Praktik Sistem Operasi

# Service Database MySQL Menggunakan Docker

## Deskripsi
Project ini merupakan implementasi **service database MySQL** menggunakan **Docker**
dan **Docker Compose** dengan **persistent storage**.  
Persistent storage digunakan agar data database tetap tersimpan meskipun container
dihentikan atau dihapus.

Project ini dibuat untuk memenuhi tugas **UAS Mata Kuliah Sistem Operasi**.

## Teknologi yang Digunakan
- Docker
- Docker Compose
- MySQL 5.7
- phpMyAdmin
- Docker Volume (Persistent Storage)


## Struktur Folder Project
database-container/
-Dockerfile
-docker-compose.yml
-README.md

## Dockerfile
Berikut merupakan konfigurasi Dockerfile yang digunakan untuk
mendefinisikan image database MySQL.

```dockerfile
FROM mysql:8.0

ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=testdb
ENV MYSQL_USER=user
ENV MYSQL_PASSWORD=password

EXPOSE 3306
```
## docker-compose.yml
File docker-compose.yml digunakan untuk menjalankan dua service, yaitu MySQL dan phpMyAdmin, menggunakan Docker Compose.
Service MySQL menggunakan image mysql:5.7 dan service phpMyAdmin digunakan untuk mempermudah pengelolaan database melalui antarmuka web.
Berikut merupakan konfigurasi docker-compose.yml yang digunakan
untuk menjalankan service database MySQL dengan persistent storage. 

```docker-compose.yml
version: '3.8'

services:
  mysql:
    image: mysql:5.7
    container_name: mysql_db
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: latihan_db
    volumes:
      - mysql_data:/var/lib/mysql
    ports:
      - "3306:3306"


  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    container_name: phpmyadmin
    restart: always
    ports:
      - "8080:80"
    environment:
      PMA_HOST: mysql
      PMA_USER: root
      PMA_PASSWORD: root

volumes:
  mysql_data:
```

## **Cara Menjalankan Project (CMD/PowerShell)**
1. Buka CMD atau PowerShell
2. Masuk ke folder project:
```Masuk ke folder project
   cd path/ke/folder/database-container 
```
3. Jalankan container
   ```Jalankan container
       docker compose up -d
   ```
4. Cek status container
   ```
    docker ps
   ```

## **Cara Mengakses Database mySQL**
1. Masuk ke MySQL di dalam container:
   ```Masuk ke MySQL di dalam container
      docker exec -it mysql_db mysql -u root -p
   ```
2. Masukkan password :
   ```Masukkan password
       root
   ```
   
3. Cek database:
   ```Cek database
      SHOW DATABASES;
   ```
## **Persistent Storage**
-Project ini menggunakan Docker Volume bernama: db_data
-Volume ini di-mount ke direktori: /var/lib/mysql

Dengan demikian, data database tidak akan hilang walaupun container dihentikan,
direstart, atau dihapus.

## **Akses PhpMyAdmin**
phpMyAdmin digunakan sebagai antarmuka berbasis web untuk mengelola database MySQL yang berjalan di dalam container Docker, seperti melihat database, tabel, dan menjalankan query SQL tanpa harus masuk ke terminal.
1. Service MySQL berhasil dijalankan menggunakan Docker.
2. phpMyAdmin dapat diakses melalui browser pada alamat:
   ```phpMyAdmin dapat diakses melalui browser pada alamat:
       http://localhost:8080
   ```
Melalui phpMyAdmin, pengguna dapat: Melihat database, membuat tabel, menambahkan data, dan menjalankan perintah SQL
   

## **Kesimpulan**
Service database MySQL berhasil dibuat dan dijalankan menggunakan Docker
dengan persistent storage. Implementasi ini telah memenuhi ketentuan tugas
pembuatan service database menggunakan Docker.


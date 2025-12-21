# Database Service Menggunakan Docker

## Kelompok 4

**Anggota:**
1. Rangga Airlangga  
2. Richard Fernando  
3. Temi Irdayanti  

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
- MySQL 8.0
- Docker Volume (Persistent Storage)


## Struktur Folder Project
database-container/
├── Dockerfile
├── docker-compose.yml
└── README.md

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
Berikut merupakan konfigurasi docker-compose.yml yang digunakan
untuk menjalankan service database MySQL dengan persistent storage.

```docker-compose.yml
version: "3.8"

services:
  db:
    image: mysql:8.0
    container_name: mysql-db
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: testdb
      MYSQL_USER: user
      MYSQL_PASSWORD: password
    ports:
      - "3306:3306"
    volumes:
      - db_data:/var/lib/mysql

volumes:
  db_data:
```

#*Cara Menjalankan Project (CMD / PowerShell)*
1. Buka CMD atau PowerShell

Masuk ke folder project:
Cara Menjalankan Project (CMD / PowerShell)
1. Buka CMD atau PowerShell
2. Masuk ke folder project:
cd "C:\Users\ASUS\Documents\SEM 3\Sistem Operasi\PSO\UAS\database-container"
3. Cek status container
docker ps

#*Cara Mengakses Database MySQL*
1. Masuk ke MySQL di dalam container:
docker exec -it mysql-db mysql -u root -p
2. Masukka password : root
3. Cek database: SHOW DATABASES;

#*Persistent Storage*
-Project ini menggunakan Docker Volume bernama: db_data
-Volume ini di-mount ke direktori: /var/lib/mysql

Dengan demikian, data database tidak akan hilang walaupun container dihentikan,
direstart, atau dihapus.

#*Kesimpulan*

Service database MySQL berhasil dibuat dan dijalankan menggunakan Docker
dengan persistent storage. Implementasi ini telah memenuhi ketentuan tugas
pembuatan service database menggunakan Docker.


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

# Docker-compose.yml
Berikut merupakan konfigurasi docker-compose.yml yang digunakan
untuk menjalankan service database MySQL dengan persistent storage.

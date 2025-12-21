# Database Service Menggunakan Docker

## Kelompok 4

**Anggota:**
1. Rangga Airlangga  
2. Richard Fernando  
3. Temi Irdayanti  

**Kelas:** 3CD  
**Mata Kuliah:** Praktik Sistem Operasi

# Database Service Menggunakan Docker (MySQL)

## Deskripsi Proyek
Proyek ini bertujuan untuk membuat service database MySQL menggunakan Docker
dengan persistent storage. Data database tetap tersimpan meskipun container
dihentikan atau dijalankan ulang.

## Teknologi yang Digunakan
- Docker
- Docker Compose
- MySQL 8.0
- Docker Volume

## Struktur Folder
database-container/
├── Dockerfile
├── docker-compose.yml
└── README.md

## Konfigurasi
Dockerfile digunakan untuk membuat image MySQL dengan konfigurasi environment
database. Docker Compose digunakan untuk menjalankan service database serta
mengatur port dan volume penyimpanan.

## Cara Menjalankan
1. Masuk ke folder project:
   cd database-container

2. Jalankan database:
   docker-compose up -d

3. Cek status container:
   docker ps

Jika berhasil, container mysql-db akan berstatus Up.

## Persistent Storage
Proyek ini menggunakan Docker Volume bernama db_data yang di-mount ke
/var/lib/mysql sehingga data database tidak hilang meskipun container dihentikan
atau dijalankan ulang.

## Pengujian Database (Opsional)
Masuk ke MySQL:
docker exec -it mysql-db mysql -u root -p

Password:
root

Cek database:
SHOW DATABASES;

## Yang Dikumpulkan
- Source code (GitHub/GitLab)
- Dockerfile
- docker-compose.yml
- Dokumentasi instalasi & penggunaan (README.md)
- Video demo (5–10 menit)
- Presentasi kelompok (opsional)

## Kesimpulan
Service database MySQL berhasil dijalankan menggunakan Docker dengan persistent
storage menggunakan Docker Volume.
r dihentikan dan dijalankan kembali.

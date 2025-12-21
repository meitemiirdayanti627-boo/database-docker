# Database Service Menggunakan Docker

## Deskripsi
Proyek ini bertujuan untuk menjalankan service database MySQL menggunakan Docker dengan persistent storage.

## Teknologi
- MySQL
- Docker
- Docker Volume
- phpMyAdmin

## Cara Menjalankan
1. Jalankan perintah:
   docker compose up -d
2. Buka browser dan akses:
   http://localhost:8080
3. Login phpMyAdmin:
   - Username: root
   - Password: root

## Pengujian
Data database tetap tersimpan walaupun container dihentikan dan dijalankan kembali.

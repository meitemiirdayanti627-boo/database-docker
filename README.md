# Database Service Menggunakan Docker

## Kelompok 4

**Anggota:**
1. Rangga Airlangga  
2. Richard Fernando  
3. Temi Irdayanti  

**Kelas:** 3CD  
**Mata Kuliah:** Praktik Sistem Operasi

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

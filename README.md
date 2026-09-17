# Sistem Manajemen Penyewaan Perlengkapan Pendakian

Proyek ini adalah aplikasi berbasis JavaFX (No Build Tools) yang menggunakan JDBC untuk koneksi ke database MySQL. 

Karena konfigurasi lokal (`.vscode`) dan library (`lib`) diabaikan oleh Git, **setiap anggota tim wajib melakukan pengaturan manual berikut pada hari pertama sebelum mulai mengerjakan kode.**

## Persyaratan Sistem
Sebelum memulai, pastikan Anda telah menginstal:
*   Visual Studio Code (beserta *Extension Pack for Java*).
*   Java Development Kit (JDK).
*   Laragon (untuk server MySQL lokal).

---

## Panduan Instalasi & Pengaturan Lokal

### 1. Kloning dan Kesiapan Branch
1. Buka terminal dan lakukan clone: `git clone <url-repo-github>`
2. Masuk ke folder proyek: `cd <nama-folder>`
3. Langsung buat branch baru dari versi terbaru: `git checkout -b nama-fitur-anda`
*(Catatan: Semua Pull Request (PR) wajib diarahkan ke branch `staging`, bukan `main`).*

### 2. Pengaturan JavaFX SDK
Karena file konfigurasi VS Code tidak disertakan di repositori, Anda harus mengatur lokasi JavaFX secara mandiri.
1. Unduh JavaFX SDK sesuai sistem operasi Anda dari situs resminya.
2. Ekstrak folder tersebut di lokasi yang mudah diakses (contoh untuk Windows: `C:\JavaFX`).
3. Di dalam VS Code, buat folder `.vscode` (jika belum ada) dan buat file `launch.json`.
4. Masukkan konfigurasi berikut (sesuaikan *path* `C:/JavaFX/lib` dengan lokasi ekstrak Anda):
   ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "type": "java",
               "name": "Run JavaFX App",
               "request": "launch",
               "mainClass": "App",
               "vmArgs": "--module-path \"C:/JavaFX/lib\" --add-modules javafx.controls,javafx.fxml"
           }
       ]
   }

#### Ini Nanti database saja

### 4. Import Struktur Database
Struktur tabel database untuk proyek ini sudah disediakan di dalam folder `database` pada repositori ini. Anda wajib mengimpornya ke Laragon lokal Anda.

1. Buka Laragon dan nyalakan MySQL.
2. Buka phpMyAdmin (atau HeidiSQL) dan buat database baru bernama `db_penyewaan_pendakian`.
3. Klik database tersebut, lalu pilih tab **Import**.
4. Klik **Choose File** (Pilih File), arahkan ke file `db_penyewaan_pendakian.sql` yang ada di dalam folder proyek ini (yang baru saja Anda clone).
5. Klik **Go** atau **Import** di bagian bawah.
6. Sekarang tabel dan data lokal Anda sudah sama persis dengan tim. 

*Catatan: Jika ada anggota tim yang mengubah struktur tabel (menambah/menghapus kolom) selama pengerjaan fitur, anggota tersebut wajib mengekspor ulang file `.sql` terbaru, menimpanya di folder proyek, dan mem-push-nya ke GitHub agar anggota lain bisa memperbarui database lokal mereka.*
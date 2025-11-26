# fsd-intermidate-mission2-Backend
## Teknologi yang Digunakan

-   **Node.js**: Lingkungan eksekusi untuk JavaScript di sisi server.
-   **Express.js**: Kerangka kerja web untuk Node.js yang mempermudah pembuatan API.
-   **MySQL2**: Driver MySQL untuk Node.js.
-   **dotenv**: Modul untuk memuat variabel lingkungan dari file `.env`.

## Cara Menjalankan Proyek

Ikuti langkah-langkah di bawah ini untuk menjalankan proyek di lingkungan lokal Anda.

### 1. Clone Repositori

Pertama, clone repositori ini dari GitHub ke mesin lokal Anda menggunakan perintah berikut:

```bash
git clone https://github.com/whyu07/fsd-intermidate-mission2-Backend.git
cd backend-movie-api
```

### 2. Instalasi Dependensi

Setelah masuk ke direktori proyek, instal semua dependensi yang dibutuhkan dengan menjalankan:

```bash
npm install
```

### 3. Konfigurasi Environment (.env)

Buat file `.env` dengan menyalin dari file `.env.example`. File ini akan berisi konfigurasi untuk koneksi database Anda.

**Untuk pengguna Linux/macOS:**

```bash
cp .env.example .env
```

**Untuk pengguna Windows:**

```bash
copy .env.example .env
```

Selanjutnya, buka file `.env` dan sesuaikan isinya dengan konfigurasi database MySQL Anda.

```
# MySQL database configuration
MYSQL_HOST=127.0.0.1
MYSQL_USER=root
MYSQL_PASSWORD="SesuaikanPasswordAnda"
MYSQL_DATABASE=movie_app_db
```

### 4. Setup Database (MySQL dengan XAMPP)

Proyek ini memerlukan server MySQL. Anda bisa menggunakan XAMPP untuk menjalankannya dengan mudah.

1.  **Buat Database**: Buka phpMyAdmin dari panel kontrol XAMPP, lalu buat database baru dengan nama `movie_app_db` (atau nama yang Anda tentukan di file `.env`).

2.  **Buat Tabel dan Isi Data**: Jalankan query SQL berikut untuk membuat tabel `movies` dan mengisinya dengan beberapa data awal.

    ```sql
    -- 1. Buat ulang tabelnya
    CREATE TABLE movies (
      id INT PRIMARY KEY AUTO_INCREMENT,
      title VARCHAR(255) NOT NULL,
      director VARCHAR(255),
      release_year INT
    );

    -- 2. Masukkan datanya
    INSERT INTO movies (title, director, release_year)
    VALUES
    ('The Shawshank Redemption', 'Frank Darabont', 1994),
    ('The Godfather', 'Francis Ford Coppola', 1972),
    ('The Dark Knight', 'Christopher Nolan', 2008);
    ```

### 5. Jalankan Server

Setelah semua konfigurasi selesai, jalankan server API dengan perintah:

```bash
npm start
```

Server akan berjalan di `http://localhost:8080`.

## Koleksi Postman

Untuk memudahkan pengujian endpoint API, Anda dapat menggunakan koleksi Postman yang sudah disiapkan. Impor koleksi melalui tautan berikut:

[Koleksi Postman Movie API]([https://www.postman.com/cloudy-capsule-725607/workspace/movie-app/collection/50102762-3bab1d80-b884-496e-89db-d7b4a8834edb?action=share&creator=50102762&active-environment=50102762-5c0e70b1-88d8-4a8b-b25f-44c99019601a](https://www.postman.com/wahyu-1903801/workspace/movie-app/collection/47821006-724547e9-c2d2-45e8-b51b-266fdb00b952?action=share&creator=47821006))

Semoga berhasil!

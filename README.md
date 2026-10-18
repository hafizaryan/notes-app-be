# Notes App Backend

Backend API untuk aplikasi catatan (Notes App), dibangun dengan Node.js dan framework Hapi sebagai bagian dari pembelajaran pengembangan back-end. API ini menyediakan operasi CRUD terhadap catatan yang disimpan di memori (array pada berkas `src/notes.js`), tanpa database, sehingga data kembali kosong setiap server dimulai ulang.

## Endpoint

- `POST /notes` - menambahkan catatan baru (ID dibuat dengan nanoid)
- `GET /notes` - mengambil daftar semua catatan
- `GET /notes/{id}` - mengambil detail catatan berdasarkan ID
- `PUT /notes/{id}` - memperbarui catatan
- `DELETE /notes/{id}` - menghapus catatan

Server berjalan pada `http://localhost:5000` dengan CORS yang terbuka untuk semua origin, sesuai konfigurasi pada `src/server.js`.

## Teknologi

- Node.js
- Framework Hapi (`@hapi/hapi` versi 21)
- nanoid versi 3 untuk pembuatan ID catatan
- ESLint untuk pemeriksaan gaya kode

## Struktur Proyek

- `src/server.js` - titik masuk dan konfigurasi server Hapi (port 5000)
- `src/routes.js` - definisi rute endpoint catatan
- `src/handler.js` - fungsi penanganan permintaan untuk setiap endpoint
- `src/notes.js` - penyimpanan data catatan di memori

## Cara Menjalankan

Prasyarat: Node.js dan npm.

1. Clone repositori ini.
2. Instal dependensi:

   ```bash
   npm install
   ```

3. Jalankan server (skrip `start` pada `package.json` menggunakan nodemon, sehingga server dimuat ulang otomatis saat kode berubah):

   ```bash
   npm start
   ```

4. Periksa gaya kode dengan perintah `npm run lint`.

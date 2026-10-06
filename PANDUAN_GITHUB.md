# Panduan Memindahkan BTP Asset Management ke GitHub

## Isi paket

Paket ini berisi source code aplikasi BTP Asset Management, termasuk halaman aplikasi, CSS, API, skema database, konfigurasi build, dan file dependensi. Folder `node_modules` dan hasil build tidak disertakan karena dapat dibuat kembali.

## Upload melalui website GitHub

1. Masuk ke GitHub dan buat repository baru, misalnya `btp-asset-management`.
2. Ekstrak file ZIP ini di komputer.
3. Buka repository GitHub, pilih **Add file > Upload files**.
4. Unggah seluruh isi folder `btp-aset-management`, bukan folder ZIP-nya.
5. Isi pesan commit, lalu pilih **Commit changes**.

## Upload menggunakan Git

Jalankan perintah berikut dari folder hasil ekstrak:

```bash
git init
git add .
git commit -m "Initial commit BTP Asset Management"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPOSITORY.git
git push -u origin main
```

Ganti `USERNAME` dan `NAMA-REPOSITORY` sesuai akun serta repository GitHub Anda.

## Menjalankan di komputer

Persyaratan: Node.js versi 22.13 atau lebih baru dan pnpm.

```bash
pnpm install
pnpm dev
```

Setelah server aktif, buka alamat lokal yang tampil pada terminal.

## Catatan database dan gambar

Source code dapat dipindahkan ke GitHub, tetapi data aplikasi dan gambar produk yang sudah tersimpan saat ini menggunakan layanan database D1 dan penyimpanan R2 pada hosting Sites. Data dan gambar tersebut tidak otomatis ikut berpindah hanya dengan mengunggah source code ke GitHub. Jika aplikasi akan dipindahkan ke hosting lain, database, penyimpanan gambar, autentikasi, serta variabel lingkungannya perlu dikonfigurasi kembali.

Jangan memasukkan token, kata sandi, atau kredensial rahasia ke repository publik.

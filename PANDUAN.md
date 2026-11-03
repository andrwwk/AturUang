# Atur Uang: cara memasang di iPhone

Folder ini berisi web app (PWA). Setelah dipasang, aplikasinya tampil seperti aplikasi biasa di iPhone:
ada ikon di layar utama, layar penuh, dan bisa dipakai tanpa internet.

## Isi folder

| File | Fungsi |
|---|---|
| `index.html` | Aplikasinya |
| `manifest.webmanifest` | Nama, ikon, dan mode layar penuh |
| `sw.js` | Supaya bisa dibuka offline |
| `apple-touch-icon.png`, `icon-*.png` | Ikon aplikasi |

## 1. Upload ke hosting gratis (cukup sekali)

iPhone hanya bisa memasang web app dari alamat **https**. Pilih salah satu cara berikut.

**Netlify Drop (paling mudah)**
1. Di komputer, buka https://app.netlify.com/drop dan daftar akun gratis.
2. Seret **seluruh folder `atur-uang-ios`** ke halaman itu.
3. Kamu akan mendapat alamat seperti `https://nama-acak.netlify.app`. Nama situsnya bisa diganti di Site settings.

**GitHub Pages**
1. Buat repository baru di GitHub dan upload semua file di folder ini.
2. Buka Settings → Pages → Branch: `main` → Save.
3. Alamatnya: `https://usernamekamu.github.io/nama-repo/`.

## 2. Pasang di iPhone

1. Buka alamat tadi di **Safari**. Harus Safari, bukan Chrome.
2. Tap tombol **Bagikan** (kotak dengan panah ke atas).
3. Pilih **Tambah ke Layar Utama**, lalu tap **Tambah**.
4. Buka **Atur Uang** dari ikon di layar utama.

## Data keuanganmu

- Semua data disimpan **di iPhone itu sendiri**, dalam dua salinan (IndexedDB dan localStorage). Data tidak dikirim ke server mana pun.
- Setiap perubahan langsung disimpan, termasuk saat aplikasi ditutup atau dipindah ke latar belakang.
- Aplikasi yang dibuka dari layar utama tidak terkena aturan Safari yang menghapus data situs setelah 7 hari tidak dipakai.
- Datamu tetap bisa hilang kalau aplikasinya dihapus dari layar utama, kalau "Hapus Riwayat dan Data Situs" dipakai di Safari, atau kalau kamu ganti HP.
  Karena itu, buat **cadangan** di tab **Lainnya → Buat cadangan** kira-kira sebulan sekali, lalu simpan file `.json`-nya ke Files atau iCloud Drive.
  Untuk mengembalikan data, pakai **Lainnya → Pulihkan dari cadangan**.

## Mengubah aplikasi nanti

Setelah mengubah file, naikkan versi di baris pertama kode `sw.js`
(misalnya dari `atur-uang-v1` ke `atur-uang-v2`), lalu upload ulang folder ini.
iPhone akan mengambil versi baru saat aplikasi dibuka sambil terhubung ke internet. Data yang tersimpan tidak hilang.

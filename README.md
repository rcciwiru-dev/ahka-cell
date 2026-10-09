# AHKA CELL PWA — prototipe awal

Aplikasi web kasir yang ramah HP Android: pencatatan penjualan, laba kotor, utang pelanggan dan cicilan, produk/stok dasar, mutasi deposit, ekspor CSV.

## Status penting
- Ini adalah prototipe frontend.
- Data saat ini disimpan di localStorage browser pada perangkat ini saja.
- Sinkronisasi online/multi-perangkat BELUM diaktifkan; tidak ada Firebase credentials yang disertakan.
- Jangan gunakan sebagai satu-satunya buku keuangan atau masukkan data pelanggan nyata sebelum keamanan, backup, dan sinkronisasi diuji.
- Perhitungan stok belum otomatis mengurangi stok saat penjualan. Catatan deposit adalah mutasi sederhana dan saldo dapat menjadi negatif jika data tidak diatur.

## Cara mencoba di HP
Untuk uji lokal, buka `index.html` menggunakan editor/preview HTML di Android. Beberapa fitur PWA (instalasi dan service worker) memerlukan hosting HTTPS.

## Cara online dan multi-perangkat
1. Buat project Firebase di console.firebase.google.com.
2. Aktifkan Authentication (email/password) dan Cloud Firestore.
3. Hosting file statis ini di layanan HTTPS seperti Firebase Hosting (umumnya proses deploy paling mudah memakai komputer atau layanan build online).
4. Implementasikan Firebase SDK, login, aturan keamanan berbasis `shopId`/keanggotaan toko, dan pindahkan seluruh operasi dari localStorage ke Firestore sebelum memasukkan data asli.
5. Uji login dari dua perangkat, hak akses, pemulihan data, dan transaksi bersamaan.

Jangan membuat Firestore terbuka untuk publik. API config Firebase bukan pengganti aturan keamanan.

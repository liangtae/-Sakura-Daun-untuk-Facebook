# -Sakura-Daun-untuk-Facebook
Ekstensi browser Brave/Chromium untuk menampilkan animasi kelopak sakura, daun musim gugur, atau daun musim semi yang berjatuhan di Facebook. Dengan popup pengaturan jenis, jumlah, dan kecepatan.

# 🌸 Sakura & Daun untuk Facebook

Ekstensi browser ringan yang menampilkan animasi **kelopak sakura**, **daun musim gugur**, atau **daun musim semi** yang berjatuhan saat Anda membuka Facebook. Dibuat untuk **Brave**, dan juga berjalan di Chrome, Edge, dan browser berbasis Chromium lainnya.

> A lightweight Chromium extension (Manifest V3) that adds falling sakura petals, autumn leaves, or spring leaves to facebook.com.

<!-- Tambahkan screenshot/GIF demo di sini, contoh: -->
<!-- ![Demo](screenshots/demo.gif) -->

## ✨ Fitur

- 🌸 **4 jenis efek**: sakura, daun musim gugur (maple & daun biasa), daun musim semi, atau campuran semuanya
- 🎚️ **Popup pengaturan**: nyalakan/matikan efek, atur jumlah daun (5–150) dan kecepatan (0.3x–3x)
- ⚡ **Perubahan langsung**: pengaturan berlaku seketika tanpa refresh halaman
- 🖱️ **Tidak mengganggu**: overlay tidak menghalangi klik, scroll, atau mengetik
- 🔋 **Hemat baterai**: animasi berhenti otomatis saat tab tidak terlihat
- ♿ **Ramah aksesibilitas**: mengikuti pengaturan sistem "kurangi gerakan" (*prefers-reduced-motion*)
- 🔒 **Privasi terjaga**: tanpa pelacakan, tanpa permintaan jaringan, tanpa data yang dikirim ke mana pun

## 📦 Instalasi

Ekstensi ini belum ada di toko ekstensi, jadi dipasang secara manual:

1. Unduh repositori ini (**Code → Download ZIP**) lalu ekstrak, atau jalankan `git clone`.
2. Buka halaman ekstensi di browser Anda:
   - Brave: `brave://extensions`
   - Chrome: `chrome://extensions`
   - Edge: `edge://extensions`
3. Aktifkan **Developer mode**.
4. Klik **Load unpacked**, lalu pilih folder `sakura-facebook`.
5. Buka atau refresh `facebook.com`.

## 🎛️ Cara Penggunaan

Klik ikon ekstensi di toolbar (sematkan lewat ikon puzzle jika belum terlihat), lalu:

| Pengaturan | Pilihan |
|---|---|
| Aktifkan efek | Nyala / mati |
| Jenis daun | Sakura, Musim gugur, Musim semi, Campuran |
| Jumlah daun | 5 – 150 |
| Kecepatan | 0.3x – 3x |

Pengaturan disimpan di browser dan tetap ada setelah browser ditutup.

## 🗂️ Struktur Proyek

```
sakura-facebook/
├── manifest.json   # konfigurasi ekstensi (Manifest V3)
├── content.js      # animasi canvas yang disuntikkan ke facebook.com
├── popup.html      # tampilan popup pengaturan
├── popup.js        # logika popup & penyimpanan pengaturan
├── LICENSE
└── README.md
```

## ⚙️ Cara Kerja

- `content.js` membuat elemen `<canvas>` layar penuh dengan `pointer-events: none` di atas halaman Facebook, lalu menggambar setiap daun dengan `requestAnimationFrame`.
- Setiap daun punya gerak sendiri: jatuh, bergoyang tertiup angin, berputar, dan "berbalik" untuk efek 3D.
- Pengaturan dibaca dari `chrome.storage.sync`, dan perubahan dari popup diterima lewat `chrome.storage.onChanged`.

## 🔐 Izin & Privasi

- `storage`: hanya untuk menyimpan preferensi Anda (jenis, jumlah, kecepatan, nyala/mati).
- Host: ekstensi hanya berjalan di `*.facebook.com`.
- Ekstensi **tidak** membaca isi halaman, akun, atau pesan Anda, dan **tidak** mengirim data apa pun.

## 🛠️ Pengembangan

Tidak ada proses build atau dependensi. Edit file langsung, lalu klik ikon muat ulang pada kartu ekstensi di halaman ekstensi browser dan refresh tab Facebook.

Ide pengembangan: jenis efek baru (salju, bunga, bintang), pilihan warna, ikon ekstensi, dukungan situs lain.

## 🤝 Kontribusi

Issue dan pull request sangat diterima. Silakan fork repositori ini, buat branch baru, lalu ajukan PR.

## 📄 Lisensi

[MIT](LICENSE)

---

*Proyek ini tidak berafiliasi dengan Meta/Facebook. "Facebook" adalah merek dagang milik Meta Platforms, Inc.*

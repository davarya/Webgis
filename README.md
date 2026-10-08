# WebGIS SIRABUN

**Sistem Informasi Rawan Bencana** untuk KT Senggi, Kabupaten Keerom, Papua.
Dibuat oleh Tim Ekspedisi Patriot 2026 Senggi 19, Universitas Diponegoro.

Peta interaktif kerawanan longsor, banjir, dan kekeringan. Isinya juga mencakup:

- hasil Normalisasi Jalur Air (foto drone sebelum dan sesudah);
- jaringan jalan (simbol Permen ATR/BPN 14/2021) dan sungai;
- Perpustakaan SIRABUN (jurnal, leaflet, presentasi FGD, dan buku credits tim);
- pemutar musik.

## Cara membuka

- **Di komputer sendiri:** klik dua kali `index.html` dan buka dengan Chrome atau Edge. Tidak perlu server.
- **Online:** lewat GitHub Pages atau Netlify. Caranya ada di bawah.

## Isi folder

```
index.html                  halaman utama (struktur tampilan)
assets/
  css/                      tampilan, satu file per bagian
  lib/                      Leaflet 1.9.4 & Chart.js 4.4.4
  js/
    app.js                  logika utama peta (basemap, layer, popup, unduhan)
    maskot-sirabun.js       maskot & tutorial Sirabun
    playlist.js             daftar lagu pemutar musik
    player-musik.js         pemutar musik ala Winamp
    perpustakaan.js         perpustakaan + NPC Sikasuari + daftar jurnal
    buku-credits.js         buku credits (daftar anggota tim di bagian atas)
    leaflet-viewer.js       penampil leaflet & presentasi
    uix.js, efek-suara.js   pengatur panel & efek suara
  data/                     data peta & gambar (GeoJSON, tile, halaman buku)
musik/                      lagu-lagu (mp3) untuk pemutar musik
data/                       file GeoTIFF untuk tombol unduh
```

## Yang biasa diubah

| Mau mengubah | Buka file |
|---|---|
| Nama, lensa, dan peran anggota tim | `assets/js/buku-credits.js`, bagian `window.SIRABUN_CREDITS` |
| Daftar lagu | `assets/js/playlist.js` (file mp3-nya taruh di `musik/`) |
| Daftar jurnal di perpustakaan | `assets/js/perpustakaan.js`, bagian `SIRABUN_JOURNAL_LIST` |

File di `assets/data/` berisi data besar yang sudah diolah. Isinya sebaiknya jangan diedit manual.

## Tombol unduh yang filenya belum ada

Tombol unduh mencari file di folder `data/`. Dua file berikut belum ada, jadi tombol unduhnya belum berfungsi sampai filenya ditambahkan:

- `data/rawan_banjir_senggi.tif`
- `data/rawan_kekeringan_senggi.tif`

## Online dengan GitHub Pages

1. Upload semua isi folder ini ke repo (`index.html` harus ada di paling atas repo, bukan di dalam subfolder).
2. Buka **Settings → Pages** di repo tersebut.
3. Di bagian **Source**, pilih **Deploy from a branch**, lalu pilih branch `main` dan folder `/ (root)`, lalu **Save**.
4. Tunggu 1–2 menit. Alamat webnya muncul di halaman itu juga, formatnya `https://<username>.github.io/<nama-repo>/`.

Untuk akun gratis, repo-nya harus **Public** supaya GitHub Pages bisa dipakai.

## Sumber & lisensi

- **Peta dasar:** Esri, EOX Sentinel-2 cloudless (CC BY-NC 4.0), dan © kontributor OpenStreetMap.
- **Jalan & sungai:** OSM dan digitasi manual.
- **Jurnal:** halaman asli hanya ditampilkan untuk jurnal berlisensi terbuka (CC BY / CC BY-NC). Jurnal lainnya hanya ditampilkan ringkasannya.
- **Pustaka kode:** Leaflet (BSD-2) dan Chart.js (MIT).
- **Musik:** milik pemegang hak cipta masing-masing. Dipakai untuk keperluan non-komersial.

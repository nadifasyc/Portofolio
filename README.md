# Web Portofolio Nadifa Syachdini

Website portofolio satu halaman untuk melamar magang. Warna utamanya **biru #B0C6F7 dan putih**, dengan biru tua sebagai warna teks. Dibuat dengan HTML, CSS, dan sedikit JavaScript, tanpa framework dan tanpa proses build, jadi gratis di-hosting di Vercel dan mudah diedit.

## Isi folder

```
portfolio/
├── index.html      ← semua konten
├── style.css       ← tampilan (warna, jarak, ukuran ada di blok :root paling atas)
├── script.js       ← menu HP, penanda menu aktif, tahun footer
├── README.md
└── assets/
    ├── CV-Nadifa-Syachdini.pdf   ← BELUM ADA. Taruh CV terbaru di sini agar tombol "Unduh CV" berfungsi
    ├── foto.jpg                  ← foto di beranda
    ├── foto-tentang.jpg          ← foto di bagian Tentang saya
    ├── analisis-sentimen.jpg     ← tangkapan layar proyek analisis sentimen
    ├── magang/                   ← foto-1.jpg (besar), foto-2.jpg, foto-3.jpg
    └── sertifikat/               ← PDF sertifikat + gambar pratinjau (.jpg)
```

## Rancangan tampilan

- **Warna:** `#B0C6F7` hanya dipakai sebagai isian datar (tombol utama, judul bergaris, bingkai foto, panel kontak). Teks di atasnya memakai biru tua `#16213E` dengan kontras 9,3:1, karena teks putih di atas `#B0C6F7` tidak terbaca.
- **Huruf:** Fraunces (serif, untuk nama dan judul section) dan Plus Jakarta Sans (isi dan tombol). Keduanya dimuat dari Google Fonts.
- **Bahasa visual:** garis tinta tipis, blok biru datar, dan bayangan "offset" keras pada bingkai foto, kotak skill, dan tombol saat disentuh. Tidak ada bayangan lembut atau efek kaca.
- **Tata letak presisi:** semua section memakai angka yang sama. Kolom kiri selalu 320px (foto, keterangan, media proyek), jarak antar kolom 48px, jarak atas dan bawah section 56px, tinggi semua tombol 46px (kecil 40px), dan sudut tombol 12px.

Untuk mengubah jarak atau ukuran, edit variabel di blok `:root` pada `style.css`, misalnya `--space-section` (jarak antar section), `--side` (lebar kolom kiri), dan `--gap`.

## Mengedit konten

Buka `index.html` di editor teks (VS Code).

| Bagian | Cara mengubah |
|---|---|
| Teks dan angka | Ganti langsung di dalam tag HTML-nya |
| Proyek baru | Salin satu blok `<article class="project"> ... </article>` |
| Skill | Salin satu baris `<li>` di grup yang sesuai. Kotak ikon: `<li><b class="tile">PHP</b>PHP</li>` |
| Pendidikan atau pengalaman baru | Salin satu blok `<article class="entry"> ... </article>` |
| Sertifikat baru | Salin satu blok `<article class="cert"> ... </article>`, lalu ganti `href` dan `src` |
| Foto galeri magang | Foto pertama (`g-main`) tampil besar, dua lainnya bertumpuk di sampingnya |

### Foto dan dokumen
- Simpan file di folder `assets/` dengan nama persis seperti di `src` atau `href` (huruf besar-kecil berpengaruh di Vercel).
- Foto sudah dikompres untuk web (total folder assets sekitar 1,8 MB). Simpan foto asli Anda di tempat lain, dan kompres foto baru sebelum diunggah (lebar 1000–1400px sudah cukup).
- Gambar pratinjau sertifikat memakai file `.jpg`, sedangkan tombolnya membuka file `.pdf`.
- Jika sebuah gambar gagal dimuat, gambar itu otomatis disembunyikan sehingga tidak muncul ikon rusak.

### Video proyek
Kartu Winsbeads memuat YouTube Shorts. Untuk mengganti, ubah kode video `VL2vAfkAEVM` di dua tempat: alamat `/embed/...` dan tombol "Tonton di YouTube". Pastikan **Allow embedding** aktif di YouTube Studio.

## Coba di komputer

Klik dua kali `index.html`, atau jalankan `npx serve .` di folder ini. Periksa juga di HP (Chrome: klik kanan, Inspect, ikon perangkat).

## Deploy gratis ke Vercel

### Cara A: Lewat GitHub (disarankan, update otomatis)
1. Buat repository baru di GitHub, misalnya `portofolio`.
2. Unggah semua isi folder ini (**Add file → Upload files**, lalu **Commit changes**). Batas unggah lewat web adalah 25 MB per file.
3. Buka [vercel.com](https://vercel.com), masuk dengan akun GitHub.
4. **Add New… → Project**, pilih repository, klik **Import**.
5. Biarkan pengaturan bawaan (*Framework Preset* = **Other**, kolom Build Command dan Output Directory kosong), lalu **Deploy**.

Setiap perubahan file di GitHub akan memperbarui situs otomatis.

### Cara B: Lewat terminal
Butuh [Node.js](https://nodejs.org). Di folder portofolio jalankan `npx vercel`, lalu `npx vercel --prod` untuk versi final.

### Merapikan alamat
Di dashboard Vercel: **Project → Settings → Domains**, ganti subdomain menjadi misalnya `nadifa-syachdini.vercel.app`.

## Memasang link di SiapKerja
1. Salin alamat situs Anda, misalnya `https://nadifa-syachdini.vercel.app`.
2. Di profil SiapKerja, cari kolom portofolio atau website. Jika tidak ada, tempel di ringkasan profil: *"Portofolio lengkap: https://nadifa-syachdini.vercel.app"*.
3. Cantumkan link yang sama di CV dan LinkedIn.

## Checklist sebelum dibagikan
- [ ] `assets/CV-Nadifa-Syachdini.pdf` sudah ada (cek tombol "Unduh CV")
- [ ] Link GitHub tiap proyek mengarah ke repository yang benar, bukan hanya profil
- [ ] Semua tombol "Lihat sertifikat" membuka dokumen yang benar
- [ ] Video YouTube tampil dan bisa diputar
- [ ] Angka di situs sama dengan di CV
- [ ] Tampilan dicek di HP dan komputer
- [ ] Foto di kantor tidak memperlihatkan data pribadi orang lain, dan sudah ada izin bila memuat orang lain

## Catatan teknis
- Situs mendukung navigasi keyboard, tautan "Lewati ke konten", penanda menu aktif saat di-scroll, dan menghormati pengaturan *reduce motion*.
- Satu-satunya animasi otomatis adalah kemunculan teks di beranda.
- Tidak ada pelacak atau cookie. Layanan pihak ketiga hanya Google Fonts dan YouTube (untuk video).
- Jika file CSS tidak berubah di browser setelah diedit, naikkan angka pada `style.css?v=10` di `index.html`, lalu muat ulang dengan `Ctrl + F5`.

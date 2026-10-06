# Landing Page Madebykain: Tas Belanja Lipat

Landing page statis (HTML + gambar) untuk iklan Google Ads. Tidak perlu build. Cukup diunggah ke GitHub dan dihubungkan ke Cloudflare Pages.

## Isi folder

| File | Fungsi |
| --- | --- |
| `index.html` | Halaman utama (CSS & JavaScript sudah di dalamnya) |
| `images/` | Logo, foto mockup, gambar hero, 10 motif, gambar preview (og-image) |
| `favicon.svg` | Ikon tab browser |
| `_headers` | Pengaturan cache gambar untuk Cloudflare Pages |
| `robots.txt` | Izinkan Google mengindeks halaman |

## Langkah 1: Unggah ke GitHub

1. Masuk ke github.com, klik **New repository**, beri nama misal `madebykain-landing`, pilih **Public** atau **Private**, klik **Create repository**.
2. Di halaman repo, klik **uploading an existing file**.
3. Ekstrak zip ini, lalu seret **semua isi folder** (bukan foldernya) ke halaman upload. Pastikan `index.html` ada di paling atas repo, bukan di dalam subfolder.
4. Klik **Commit changes**.

## Langkah 2: Deploy di Cloudflare Pages

1. Masuk ke dash.cloudflare.com, buka **Workers & Pages**, lalu **Create**, pilih tab **Pages**, lalu **Connect to Git**.
2. Hubungkan akun GitHub, pilih repo `madebykain-landing`.
3. Pengaturan build:
   - Framework preset: **None**
   - Build command: *(kosongkan)*
   - Build output directory: `/`
4. Klik **Save and Deploy**. Situs akan tayang di `nama-proyek.pages.dev` dalam 1 sampai 2 menit.
5. (Opsional) Tab **Custom domains**, lalu tambahkan domain Anda, misal `tas.madebykain.com`.

Setiap kali file di GitHub diubah, Cloudflare otomatis memperbarui situs.

## Langkah 3: Sebelum menjalankan Google Ads

1. **Pasang Google Tag.** Di Google Ads buka *Tujuan > Konversi*, buat konversi "Klik WhatsApp" (jenis: Situs web, dibuat manual dengan kode). Salin kode `gtag.js` ke dalam `<head>` di `index.html`.
2. **Isi kode konversi.** Di bagian bawah `index.html`, cari `const GADS_SEND_TO = "";` lalu isi dengan kode *send_to*, misal `"AW-123456789/AbCdEfGh"`. Setiap klik tombol WhatsApp akan tercatat sebagai konversi.
3. **Gambar preview link (og-image).** Ganti `content="images/og-image.jpg"` menjadi alamat lengkap, misal `https://tas.madebykain.com/images/og-image.jpg`, agar preview muncul saat link dibagikan di WhatsApp.
4. **Cek foto mockup.** Foto berisi produk bermerek (Indomie, Aqua, Indomaret, dll). Kebijakan merek dagang Google Ads bisa membatasi iklan. Lebih aman memakai foto dengan isi tanpa merek.

## Mengubah konten

- **Nomor WhatsApp:** `const WA_NUMBER = "6281311293656";` di bagian bawah `index.html`.
- **Harga:** cari `30.000` / `30000` di `index.html`.
- **Ganti gambar:** timpa file di `images/` dengan nama yang sama.

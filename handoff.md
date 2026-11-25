# Handoff: Cupertinotes°

## Status Proyek & Git
- **Repository:** `https://github.com/stagnansi/cupertinotes.git`
- **Branch aktif lokal:** `master` (tracking `origin/master`)
- **Commit terakhir yang sudah di-push:** `6a2d0c6c21afac54c8ac2ed46dea89a41617857f` ("Initial commit for Cupertinotes°")
- **Catatan perubahan belum di-commit:** Ada pembaruan pada `content/_index.md`, `content/blog/finalis-app-store-award-2026.md`, `layouts/partials/custom_head.html`, dan `layouts/partials/footer.html` setelah commit `6a2d0c6`.
- **Cloudflare Pages:** Belum dibuat (`cupertinotes.pages.dev` belum aktif di Cloudflare Pages).

## Keputusan Konten & Struktur
- **Homepage (`content/_index.md`):**
  - Tidak ada heading di dalam konten utama homepage.
  - Berisi kalimat pembuka bernuansa katalog/ekosistem Apple, diikuti daftar kategori ala `apple.com` (`Store`, `Mac`, `iPad`, `iPhone`, `Watch`, `Vision`, `AirPods`, `Home`, `Entertainment`, `Accessories`, `Support`) di bawah kalimat pembuka.
- **Artikel pertama (`content/blog/finalis-app-store-award-2026.md`):**
  - Judul: `Inilah para finalis App Store Award 2026`
  - Tanggal: `2026-11-18T00:00:00+07:00` (mengikuti tanggal rilis aslinya, bukan tanggal build/hari ini).
  - Slug: `finalis-app-store-award-2026` (permalink `/:slug/`).
  - Frontmatter memakai `tags = ["PEMBARUAN"]` dan teks `**PEMBARUAN**` sudah dihapus dari badan artikel.
  - Kutipan Carson Oliver dipisahkan dengan baris kosong (`>`) antar dua pasang tanda kutip.

## Keputusan Gaya & Tipografi (`layouts/partials/custom_head.html` & `layouts/partials/footer.html`)
- **Light mode saja:** Dark mode dikunci ke tema terang (`color-scheme: light only`, latar belakang `#ffffff`).
- **Warna:**
  - Teks utama & heading: `#1d1d1f`
  - Link (`a` dan `a:visited`): `#0071e3`
- **Font:**
  - `Inter` untuk teks utama.
  - `InterDisplay` khusus untuk judul/heading (`h1`–`h6`, `header .title`, `header .title h2`).
  - `IBM Plex Mono` untuk `time`, `pre`, `code`, `kbd`, `samp`.
  - `letter-spacing: -0.022em` pada teks/paragraf/blockquote, dengan `margin` dan `border-left: 1px solid #999; padding-left: 20px; font-style: italic;` pada `blockquote` mengacu ke setelan tema `hugo-bearblog` serta `margin-left: 0; margin-right: 0;` agar tidak menjorok ke dalam.
- **Bullet list:** Semua `ul li` kecuali daftar artikel di `/blog/` (`ul.blog-posts`) memakai panah kanan (`→`) sebagai penanda.
- **Footer (`layouts/partials/footer.html`):** Memakai `&copy;`, tahun `2026`, pemisah `&mdash;`, dan `Cupertinotes°` dengan pembagian warna/opacity yang telah diatur.

## Langkah Lanjutan yang Disarankan
1. **Render `tags` di layout:** Menambahkan tampilan `tags` pada layout artikel/list jika ingin label `PEMBARUAN` muncul di halaman web (saat ini baru ada di frontmatter markdown).
2. **Commit & push perubahan terbaru:** Menjalankan `git add`, `git commit`, dan `git push` ke `origin/master`.
3. **Siapkan Cloudflare Pages:** Membuat proyek di Cloudflare Pages yang terhubung ke `stagnansi/cupertinotes` dengan build command `hugo --gc --minify` dan output directory `public`.

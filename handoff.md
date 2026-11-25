# Handoff: Cupertinotes°

## Status Proyek & Git
- **Repository:** `https://github.com/stagnansi/cupertinotes.git`
- **Branch aktif lokal:** `master` (tracking `origin/master`)
- **Commit terakhir sebelumnya:** `7f192c4` ("Keep IBM Plex Mono first for Android, Apple @supports mono, and update handoff")
- **Cloudflare Pages:** Aktif di `https://cupertinotes.pages.dev/` dengan build command `hugo --gc --minify` dan output directory `public` (deployment dan verifikasi `<time>` di Android sudah berjalan).

## Keputusan Konten & Struktur
- **Homepage (`content/_index.md`):**
  - Tidak ada heading di dalam konten utama homepage.
  - Berisi kalimat pembuka bernuansa katalog/ekosistem Apple, diikuti daftar kategori ala `apple.com` (`Store`, `Mac`, `iPad`, `iPhone`, `Watch`, `Vision`, `AirPods`, `Home`, `Entertainment`, `Accessories`, `Support`) di bawah kalimat pembuka.
- **Section Newsroom (`content/newsroom/`):**
  - Menggantikan `/blog/` menjadi `/newsroom/` dengan judul menu `Newsroom` dan permalink artikel `/:slug/`.
  - Berisi artikel pertama `content/newsroom/finalis-app-store-award-2026.md` (`Inilah para finalis App Store Award 2026`, tanggal `2026-11-18T00:00:00+07:00`, slug `finalis-app-store-award-2026`, `tags = ["PEMBARUAN"]`, kutipan Carson Oliver dipisah baris kosong antar dua pasang tanda kutip).
- **Halaman About (`content/about.md`):**
  - Berisi profil singkat Cupertinotes° serta bagian **Disclaimer** yang menyatakan bahwa situs ini independen dan tidak berafiliasi secara resmi dengan Apple Inc., serta seluruh merek dagang milik masing-masing pemiliknya.
- **Urutan Navigasi Utama:**
  - `About` (`weight = 100`) kemudian `Newsroom` (`weight = 200`).
- **Layout Artikel (`layouts/_default/single.html`):**
  - Menyesuaikan kondisi tampilan judul (`<h1>`) dan tanggal artikel dari tema agar mendukung `.Type` `"newsroom"` selain `"blog"`.

## Keputusan Gaya & Tipografi (`layouts/partials/custom_head.html` & `layouts/partials/footer.html`)
- **Light mode saja:** Dark mode dikunci ke tema terang (`color-scheme: light only`, latar belakang `#ffffff`).
- **Warna:**
  - Teks utama & heading: `#1d1d1f`
  - Link (`a` dan `a:visited`): `#0071e3`
- **Font:**
  - `--font-main`: `'Inter', -apple-system, BlinkMacSystemFont, sans-serif` (prioritas `Inter` terlebih dahulu, dengan fallback sistem).
  - `--font-display`: `'InterDisplay', 'Inter', -apple-system, BlinkMacSystemFont, sans-serif` khusus untuk judul/heading (`h1`–`h6`, `header .title`, `header .title h2`).
  - `--font-mono`: `'IBM Plex Mono', ui-monospace, Consolas, monospace` secara bawaan (terverifikasi tampil `IBM Plex Mono` di Android), dan diarahkan ke `ui-monospace, 'SF Mono', SFMono-Regular, Menlo, Monaco, monospace` di dalam blok `@supports (-webkit-touch-callout: none)` untuk perangkat Apple (iOS/iPadOS).
  - Elemen `time` memakai `font-family: var(--font-mono); font-style: normal; font-size: 15px;` selaras dengan tema `hugo-bearblog`.
  - `letter-spacing: -0.022em` pada teks/paragraf/blockquote, dengan `margin` dan `border-left: 1px solid #999; padding-left: 20px; font-style: italic;` pada `blockquote` mengacu ke setelan tema `hugo-bearblog` serta `margin-left: 0; margin-right: 0;` agar tidak menjorok ke dalam.
- **Smooth scroll & back to top:**
  - `html { scroll-behavior: smooth; }` di `custom_head.html` tanpa JavaScript.
  - Link `<a href="#top" class="back-to-top" aria-label="Back to top">&uarr;</a>` dengan warna link dan `text-decoration: none;` termasuk saat `:hover`.
- **Bullet list:** Semua `ul li` kecuali daftar artikel di `/newsroom/` (`ul.blog-posts`) memakai panah kanan (`→`) sebagai penanda.
- **Footer (`layouts/partials/footer.html`):** Format `&copy; 2026,` (warna teks, `2026` dengan `font-feature-settings: 'zero' 1;`), `Cupertinotes°` tebal (warna heading), pemisah `&mdash;` (warna teks dengan `opacity: 0.5`), dan panah atas (`↑`).

## Langkah Berikutnya
1. Menambah konten artikel atau pembaruan halaman di `Cupertinotes°` serta meninjau tampilan lintas perangkat bila ada penyesuaian lanjutan.

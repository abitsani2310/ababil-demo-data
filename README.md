# Ababil Demo Data

Repository ini adalah sumber konten demo standar untuk theme Next.js Ababil.

Tujuannya:

- Ababil Base dan Ababil Portal memakai konten demo yang sama.
- Theme demo tidak mengambil konten dari `wp.sorbansantri.com`.
- Domain baru tetap punya artikel, kategori, halaman, banner, ads, topik, dan modul demo sebelum WordPress production siap.
- Semua theme Next.js Ababil wajib tetap kompatibel dengan plugin WordPress `ababil-core`.

## File

- `data/articles.json` berisi paket demo lengkap: site, kategori, artikel, tag, topik, halaman, menu, banner, ads, modul, dan kontrak standar.

## Versi Data

- `1.1.0` mengambil paket demo dari Ababil Portal.
- Isi demo mencakup 23 kategori, 79 artikel, 6 halaman, kanal video dengan sumber YouTube, serta kontrak elemen frontend yang bisa disesuaikan dari Ababil Core.
- Route standar portal: artikel `/artikel/[slug]`, kategori `/kategori/[slug]`, halaman `/halaman/[slug]`.

## Sumber Data Standar

Theme Next.js Ababil harus membaca data dengan urutan ini:

1. Jika `NEXT_PUBLIC_WORDPRESS_URL` tersedia, ambil data dari WordPress melalui Ababil Core REST API.
2. Jika WordPress belum tersedia atau env kosong, pakai fallback demo:

```txt
https://raw.githubusercontent.com/abitsani2310/ababil-demo-data/main/data/articles.json
```

3. Jangan gunakan konten production client, seperti `wp.sorbansantri.com`, sebagai demo theme umum.

## SOP Theme Baru

1. Clone theme master, misalnya Ababil Base atau Ababil Portal.
2. Pastikan route artikel memakai `/artikel/[slug]`, bukan `/blog/[slug]`.
3. Pastikan komponen homepage membaca `modules`, `banners`, `ads`, `categories`, `topics`, dan `articles`.
4. Pastikan halaman statis membaca `pages`.
5. Pastikan WordPress production memasang plugin `ababil-core`.
6. Isi env production:

```bash
NEXT_PUBLIC_WORDPRESS_URL=https://wp.domain-baru.com
NEXT_PUBLIC_SITE_URL=https://www.domain-baru.com
```

7. Jika env WordPress kosong, theme hanya boleh menampilkan demo dari repository ini.

## Kontrak Ababil Core

Theme Next.js wajib menganggap `ababil-core` sebagai jembatan utama dari WordPress ke frontend.

Data yang wajib didukung:

- Branding: site title, tagline, logo, favicon.
- Artikel: title, slug, excerpt, content, image, author, category, tags.
- Taxonomy: categories, tags, topics.
- Layout: homepage modules, sidebar modules, recent posts, popular posts.
- Monetisasi: banners, ads, AdSense script, posisi iklan.
- Halaman: about, redaksi, kontak, legal, privacy policy.
- Share: URL artikel harus memakai domain frontend, bukan subdomain WordPress.

## Catatan

`wp.sorbansantri.com` adalah sumber konten production untuk SorbanSantri, bukan sumber demo Ababil umum.

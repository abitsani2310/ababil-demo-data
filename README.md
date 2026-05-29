# Ababil Demo Data

Repository ini menjadi sumber artikel demo untuk theme Next.js Ababil.

Tujuannya:

- Ababil Base dan Ababil Portal bisa memakai data demo yang sama.
- Demo theme tidak perlu mengambil konten dari `wp.sorbansantri.com`.
- Domain baru tetap bisa memakai data dummy sampai `NEXT_PUBLIC_WORDPRESS_URL` diarahkan ke WordPress milik domain tersebut.

## File

- `data/articles.json` berisi kategori, artikel, tag, dan metadata demo.

## Cara Pakai

Untuk theme Next.js baru, gunakan data ini sebagai fallback lokal atau seed demo. Setelah WordPress production siap, isi environment:

```bash
NEXT_PUBLIC_WORDPRESS_URL=https://wp.domain-baru.com
```

Jika environment tersebut kosong, theme sebaiknya tetap memakai data demo ini.

# Kalkulator tarif Pos

Kalkulator statis untuk PPB dan PJB dari Batam dan Tanjungpinang. Buka melalui server HTTP agar data CSV dapat dimuat.

## Data PJB

Tarif Oktober 2026 berasal dari `TARIF INSERT PJB OKT 2026 BATAM DAN TANJUNGPINANG.xlsx`, Sheet1, baris 3–1208. Masing-masing asal memiliki 603 tujuan. Kolom kode kantor disimpan sebagai teks agar kode alfanumerik tetap utuh. Tarif per kg, tarif 10 kg, dan SWP disalin dari sumber; seluruh tarif 10 kg sama dengan 10 × tarif per kg.

PJB mensyaratkan berat aktual minimal 10 kg. Berat tagihan menggunakan nilai tertinggi antara aktual dan volumetrik (panjang × lebar × tinggi / 6000), kemudian mengikuti toleransi PPB: pecahan sampai 0,3 kg dibulatkan ke bawah, selebihnya ke atas. Total = berat tagihan × tarif per kg. PPB tetap memakai minimum tagihan 3 kg.

## Deploy

Cloudflare Pages terhubung dengan branch `main`. Push ke branch tersebut memicu deploy produksi. Status deploy tersedia pada GitHub commit checks.

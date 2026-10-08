# Keer Streaming

Platform streaming drama pendek (vertical drama / dracin) modern — nonton drama pendek gratis dan tanpa iklan, dengan tampilan mobile-first dan dark mode.

## Fitur
- 🎬 Streaming drama pendek dari banyak platform (DramaBox, ReelShort, NetShort, ShortMax, Melolo, FreeReels, DramaNova, GoodShort, PineDrama, FlickReels)
- 🔍 Pencarian lintas platform
- 📱 Responsif mobile-first + dark mode
- ▶️ Video player dengan dukungan HLS

## Persyaratan Sistem
- [Node.js](https://nodejs.org/) versi 18 LTS atau 20 LTS (disarankan)
- Git (opsional)

## Cara Menjalankan (Localhost)

```bash
# 1. Clone repository
git clone <url-repo-anda>
cd keer-streaming

# 2. Install dependencies
npm install

# 3. Salin environment variable
cp .env.example .env
# (opsional) sesuaikan isi .env bila perlu

# 4. Jalankan development server
npm run dev
```

Buka [http://localhost:3000](http://localhost:3000) di browser.

## Environment Variable

| Variable | Fungsi | Default |
|----------|--------|---------|
| `NEXT_PUBLIC_API_BASE_URL` | Base URL API data drama | `https://api.sansekai.my.id/api` |
| `NEXT_PUBLIC_CRYPTO_SECRET` | Secret untuk dekripsi stream | (fallback bawaan) |

Semua base URL API terpusat di `.env` — cukup ubah nilainya tanpa menyentuh kode.

## Script Perintah
| Command | Fungsi |
|---------|--------|
| `npm run dev` | Menjalankan server development |
| `npm run build` | Membuat build production |
| `npm run start` | Menjalankan build production |
| `npm run lint` | Cek error coding style (linting) |

## Deploy ke Vercel

```bash
# via CLI
npm i -g vercel
vercel
```
Atau hubungkan repository ke [vercel.com](https://vercel.com) → Import Project. Jangan lupa isi Environment Variables (`NEXT_PUBLIC_API_BASE_URL`, `NEXT_PUBLIC_CRYPTO_SECRET`) di dashboard Vercel bila berbeda dari default.

## Kustomisasi

### Menghapus Popup Donasi QRIS
Beri komentar pada pemanggilan komponen `QrisDonationPopup` di `src/app/detail/layout.tsx`:

```tsx
<>
  {children}
  {/* <QrisDonationPopup /> */}
</>
```

## Kredit & Lisensi

Project ini berbasis pada [**SekaiDrama**](https://github.com/Sansekai/SekaiDrama) oleh M Yusril, dilisensikan di bawah **MIT License** (lihat file `LICENSE` — copyright notice asli dipertahankan sesuai ketentuan lisensi).

Sumber data: [SΛNSΞKΛI API](https://api.sansekai.my.id).

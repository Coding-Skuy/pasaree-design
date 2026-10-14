# Arsitektur AI-dev pasaree-design

Dokumen tambahan untuk `versions/v1.0.0/docs/40-TECHSTACK.md` dan `60-BLAST-RADIUS.md` (kedua file itu beku v1.0.0 dan hanya berisi ringkasan; jangan ditimpa). Rujukan versi: [Pasaree-TownHall v1.0.0](https://github.com/Coding-Skuy/Pasaree-TownHall/blob/main/platform/versions/v1.0.0/CHANGELOG.md).

## Matriks stack dan fitur

| Aspek | Terkunci | Catatan |
|---|---|---|
| Alat desain | Figma | link terdaftar di README design |
| Token | `tokens/warna.json`, `tokens/tipografi.json` | sumber tunggal untuk KMP dan web |
| Isi repo | token, flow, screen, panduan | tidak ada kode produk |

Larangan: kode produk; mendesain untuk divisi lain; mengubah flow besar tanpa PRD/FSD versi baru di TownHall.

| Artefak | Konsumen |
|---|---|
| token warna/tipografi | `pasaree-app-kmp`, `pasaree-web` |
| flow + screen beli | `pasaree-app-kmp` |
| flow + screen lapak/kurasi | `pasaree-web` |
| panduan kurasi | kurator, `pasaree-ai-models` (kriteria) |

## Blast radius

Batas context repo (townhall-roadmap §2: komisi 8% transparan, escrow T+1; katalog jujur; fulfillment wajib via trip Lumbung).

Boleh disentuh:

- Token, flow, screen, link Figma, panduan kurasi.

Dilarang:

- Kode produk; keputusan flow besar tanpa TownHall.
- Desain untuk divisi lain.

Kontrak dikonsumsi:

- Alur dan SOP dari Pasaree-TownHall.

Kontrak diproduksi:

- Token JSON dan spesifikasi screen untuk KMP dan web.

Catatan: Pasaree tidak mengonsumsi modul `:shared:pantry-resep` (milik Pawonee). Failure utama: kontrak berubah tanpa update SRS, test tidak mengikuti acceptance criteria, rollback tidak siap. Rollback: revert commit repo ini dan kembali ke kontrak Pasaree-TownHall v1.0.0.

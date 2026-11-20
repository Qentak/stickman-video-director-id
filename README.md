# stickman-video-director-id

Skill berbahasa Indonesia untuk merancang dan memproduksi video cerita bergaya stickman. Dengan skill ini, asisten atau agen AI dapat memecah ide atau naskah menjadi adegan, men-generate klip per adegan, merekam narasi, menambah musik, lalu menyunting semuanya menjadi satu film pendek yang utuh.

## Instalasi

Salin seluruh folder skill ini ke direktori skills agen Anda, misalnya:

```
~/.claude/skills/stickman-video-director-id/
```

atau direktori skill setara pada framework agen yang Anda pakai. Setelah terpasang, saat Anda meminta pembuatan video stickman, agen akan mengikuti panduan di `SKILL.md`.

## Struktur file

- `SKILL.md` — file skill utama (adaptasi generik, termasuk pelajaran dari pengujian dan aturan yang sudah ditetapkan)
- `UPSTREAM-SKILL.md` — terjemahan lengkap teks skill upstream
- `references/` — dokumen referensi: kontrak prompt A7, standar akseptasi, template storyboard, katalog gaya, dan lainnya
- `references/a7-kitchen-ref.jpg` — gambar referensi untuk mengunci identitas gaya A7 rubber hose
- `LICENSE` — lisensi MIT

## Sumber dan lisensi

Diadaptasi dari [CryptoYuyyy02/stickman-video-director](https://github.com/CryptoYuyyy02/stickman-video-director), yang didasarkan pada [kaomei/stickman-video-director](https://github.com/kaomei/stickman-video-director) (MIT). Lisensi tetap MIT; lihat `LICENSE`.

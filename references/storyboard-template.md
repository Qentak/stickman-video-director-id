# Kontrak Proposal Director

Gunakan kontrak ini untuk Phase A. Sajikan proposal produksi yang mudah dibaca dan berhenti untuk konfirmasi sebelum menulis prompt model. Rujuk `references/style-catalog.md` untuk spesifikasi gaya.

> Catatan adaptasi: dokumen upstream mengasumsikan narasi bahasa Inggris. Untuk pengguna Indonesia, narasi mengikuti bahasa yang diminta pengguna (mis. Bahasa Indonesia); terjemahan referensi lalu bisa dibuat dalam bahasa lain bila perlu. Hitungan kata per klip di bawah (20–25 kata Inggris per 10 detik) hanyalah patokan; untuk Bahasa Indonesia kira-kira 20–28 kata per 10 detik, dan cek durasi TTS aktual.

Style 3 (Prehistoric Hand-Drawn / Dark Comedy) juga didukung. Sebelum merencanakannya, baca `prehistoric-dark-comedy.md`; aturan cast-card, palet bumi, setup/eskalasi/payoff, dan jeda reaksinya menimpa lima tahap generik, akhir diskusi wajib, dan cek jumlah device di sini. Sertakan cast card yang bisa dibedakan dan rencana kontinuitas lokasi/properti di Phase A. Perlakukan cerita sebagai analogi fiksi, bukan fakta sejarah yang dikarang.

Style 4 (Cozy Storytelling / Cerita Menyembuhkan) memakai `cozy-storytelling.md`. Di Phase A sebutkan setting utama yang berbeda dan dikenali untuk setiap segmen sepuluh detik baru secara default, ditambah shot lebar/dekat/bergerak di dalamnya. Kunci desain karakter, properti penting, dan narasi; pemandangan berubah dengan sengaja. Hormati permintaan lokasi tunggal yang eksplisit atau callback yang disetujui. Jangan menyebut gaya ini gambar tangan atau mewajibkan meja/ruang yang sama di semua segmen.

Style 5 (Historical Cartoon / Kartun Sejarah) memakai `historical-cartoon.md`. Sertakan era pack-nya, cast card lengkap, kondisi lokasi/properti, VO persis, dan profil `voice-continuity.md` bersama di Phase A. Pertahankan tata bahasa gambar sambil menyesuaikan pakaian, arsitektur, palet, dan musik dengan era. Ending narrative-short dan pacing aksi fisiknya menimpa persyaratan akhir diskusi generik dan empat device; reaksi boleh berhenti dengan sengaja. Pisahkan fakta sejarah dari adegan komedi karangan.

## Tulis ulang sumber

Buat satu narasi natural yang diskalakan sekitar 20–25 kata per klip 10 detik berdasarkan durasi target (mis. ~60–75 kata untuk 30 dtk, ~120–150 kata untuk 60 dtk default, ~360–450 kata untuk 3 mnt, ~600–750 kata untuk 5 mnt).

- Pertahankan klaim inti, nama, angka, dan makna faktual sumber.
- Perkuat pembuka yang lemah dengan hook langsung.
- Hapus pengulangan dan cabang sekunder dari sumber yang panjang.
- Perluas sumber yang pendek dengan contoh, progresi, reframe, atau callback yang relevan.
- Pilih bahasa lisan yang jelas dibanding terjemahan harfiah.
- Sederhanakan kata sebelum menaikkan kecepatan bicara.
- Jangan mengarang riset, statistik, kutipan, klaim produk, atau detail faktual.

Gunakan bahasa pengguna untuk penjelasan perencanaan. Pertahankan voiceover dalam bahasa yang dipilih untuk video dan berikan terjemahan referensi dalam bahasa pengguna bila berbeda.

## Kontrak header

Sajikan butir-butir ini secara berurutan:

1. Judul dan judul bahasa referensi
2. Pesan inti dan hook pembuka
3. Rasio aspek terpilih (`16:9` atau `9:16`), durasi target (kelipatan 10 dtk), dan gaya visual/tema (Style 1 Classic Light/Dark, Style 2A Modern Studio Tech, atau Style 2B Cinematic Story)
4. Voice profile video-level lengkap narator dari `voice-continuity.md` (identitas/usia, aksen, timbre, register, resonansi, tekstur, delivery, tempo, dan perlakuan rekaman), jumlah kata, dan estimasi durasi
5. Hingga tiga warna aksen jenuh (untuk Style 1) atau palet visual/mood lingkungan (untuk Style 2), disebut dengan bahasa biasa, dan apa yang diwakili masing-masing
6. Arahan BGM, titik balik emosional, nada, dan busur narasi

Tetapkan narator default hanya setelah setup yang dibutuhkan selesai: usulkan voice profile perempuan, laki-laki, atau lainnya yang koheren dan sesuai sumber untuk disetujui, bukan bariton universal wajib. Perluas preferensi singkat seperti "suara laki-laki" menjadi semua field di `voice-continuity.md`. Video berbeda boleh memilih suara berbeda, tetapi semua klip dalam satu video berbagi profil bekunya. Pisahkan busur emosional naratif dari identitas vokal dan delivery yang stabil. Simpulkan nada dan palet dari sumber bila pengguna tidak menentukannya.

## Pola naratif: Mesin Detak Jantung 5-Tahap Berpenyelesaian Tinggi

Untuk menembus ambang completion rate video 60%+, susun setiap skrip melalui progresi detak emosional ini:

1. **Tahap 1: Golden Hook (Kail Emas)**
   - **Timing**: Fleksibel menurut durasi (pada video pendek 30/60 dtk, disampaikan cepat dalam 2–5 detik pertama / `[0–3s]` Klip 1; pada video 3–5 mnt, membangun premis sepanjang 5–15 detik pertama).
   - **Tujuan**: Ajukan pertanyaan tak terduga dan berlawanan intuisi atau tampilkan paradoks visual yang mencolok yang seketika menciptakan information gap yang tak tertahankan. Jangan pernah membuka dengan basa-basi yang lambat.
2. **Tahap 2: Disrupting Assumptions (Mematahkan Asumsi)**
   - **Tujuan**: Artikulasikan keyakinan umum atau kebijaksanaan konvensional yang dianggap benar semua orang, lalu hancurkan dalam satu kalimat tegas untuk menciptakan konflik kognitif dan suspense.
3. **Tahap 3: Unveiling Insider Secrets (Membongkar Rahasia Dalam)**
   - **Tujuan**: Singkap tirai pada mekanisme teknis yang jarang diketahui, gesekan tersembunyi, atau rahasia sistemik yang menjaga penonton tetap terpikat dan penasaran.
4. **Tahap 4: Ultimate Truth Revelation (Pengungkapan Kebenaran Akhir)**
   - **Tujuan**: Sampaikan logika bisnis, mekanisme ilmiah, atau kebenaran psikologi manusia yang mendasarinya dengan kejelasan penuh. Beri penonton terobosan "aha!" yang memuaskan.
5. **Tahap 5: Elevation & High-Engagement Discussion (Peningkatan & Diskusi Interaktif)**
   - **Tujuan**: Kristalkan takeaway menjadi punchline yang mudah diingat, dan tutup dengan pertanyaan diskusi terbuka yang provokatif yang mendorong penonton memihak dan berdebat di kolom komentar.

### Alokasi Klip Dinamis menurut Durasi ($N = \text{durasi} / 10$)

- **30 dtk (3 klip)**:
  - Klip 1: Hook kilat (0–3s) → Bangun konflik
  - Klip 2: Singkap realitas dan mekanisme tersembunyi
  - Klip 3: Kebenaran akhir + ajakan debat di komentar
- **60 dtk (6 klip, default)**:
  - Klip 1: Golden Hook (pertanyaan berlawanan intuisi) → Premis
  - Klip 2: Disrupt Assumptions (hancurkan kebijaksanaan konvensional)
  - Klip 3: Unveil Insider Secrets (gesekan tersembunyi)
  - Klip 4–5: Mekanisme & Kebenaran Akhir (kepuasan kognitif)
  - Klip 6: Punchline elevasi + pertanyaan komentar yang tak tertahankan
- **90 dtk (9 klip)**:
  - Klip 1: Golden Hook
  - Klip 2–3: Disrupt Assumptions
  - Klip 4–6: Unveil Insider Secrets
  - Klip 7–8: Ultimate Truth Revelation
  - Klip 9: Elevation & Diskusi Komentar
- **180 dtk+ (3–5 mnt)**:
  - Hook (Klip 1) → Asumsi (15–20%) → Rahasia Dalam (35–40%) → Kebenaran Akhir (30–35%) → Elevation & Diskusi (1–2 klip terakhir)

## Kontrak storyboard

Hasilkan tepat N baris berdurasi sekitar sepuluh detik (N = durasi target dalam detik / 10; default: 6 baris untuk 60 dtk):

| Waktu | Tujuan naratif | Adegan stick-figure | Gerak, kamera, dan transisi | VO | Terjemahan referensi | BGM / SFX |
|---|---|---|---|---|---|---|

Beri setiap baris tugas naratif berbeda yang selaras dengan mesin 5-tahap. Alokasikan sekitar 18–25 kata per baris sambil menjaga batas kalimat tetap natural.

## Resep kepadatan visual

Bangun setiap baris dari tiga beat berurutan:

- `0–3s`: bangun atau warisi premis visual.
- `3–7s`: ubah, eskalasi, atau jelaskan metafora lewat aksi fisik karakter.
- `7–10s`: sampaikan klimaks dan ciptakan transisi berikutnya.

Gunakan setidaknya empat device yang relevan per baris:

- aksi stick-figure yang ekspresif (berlari, melompat, menyentuh kaca, menggambar garis)
- transformasi lingkungan
- metafora visual konkret
- diagram, panah, atau simbol ikon-saja
- partikel, energi, cairan, ledakan, atau cahaya
- gerak kamera push, pull, pan, orbit, shake, atau tracking
- wipe foreground atau objek melintasi lensa
- match cut, shape morph, atau transisi yang cocok-gerak
- interaksi dengan figur lain atau objek berukuran raksasa

Wajibkan perubahan visual yang terasa setiap dua sampai tiga detik. Buat setiap efek memperjelas atau mempertegas ide yang diucapkan; hilangkan tontonan yang tak terkait. Hindari morphing cairan abstrak.

## Palet dan teks

Jaga latar dan stick figure monokrom sesuai tema terpilih (untuk Style 1), atau pakai grid studio high-key / pencahayaan sinematik (untuk Style 2). Pakai tidak lebih dari tiga warna aksen jenuh sepanjang video. Beri makna semantik seperti kecemasan, bahaya, energi, penemuan, atau keberhasilan.

Sebut warna hanya dengan bahasa deskriptif biasa. Jangan pakai notasi heksadesimal, RGB, HSL, Pantone, atau notasi warna teknis lain di mana pun dalam proposal atau prompt produksi.

Secara default, video yang di-generate tanpa kata, huruf, angka, caption, subtitle, teks antarmuka, atau anotasi teknis yang terlihat. Buat gelembung pesan, kartu konten, meter, jam, dan notifikasi hanya berupa ikon. Setelah storyboard, secara opsional daftarkan overlay singkat dua-sampai-lima kata untuk post-produksi, termasuk klip target dan penempatan aman; jangan pernah membawa overlay itu ke prompt video-generation.

## Komposisi menurut rasio aspek

- `16:9`: pakai staging kiri-tengah-kanan, tracking lateral, match cut horizontal, dan ruang negatif yang disengaja. Cadangkan ruang bersih untuk overlay post-produksi opsional bila berguna.
- `9:16`: pakai kedalaman foreground/background, reveal vertikal, gerak bertumpuk, foreground pass, dan ruang overlay yang aman untuk antarmuka.

Mengubah rasio memerlukan staging baru, jalur kamera, geometri transisi, dan ruang negatif aman overlay. Mengubah tema atau gaya memerlukan cek keseimbangan warna dan kontras yang diperbarui.

## Kontinuitas

Akhiri setiap baris dengan antarmuka terlihat yang diwarisi baris berikutnya: pose, objek bergerak, frame terisi, arah perjalanan, bentuk, atau gerak kamera. Sebut kedua sisi setiap sambungan dalam proposal. Untuk Style 4, cut lokasi atau lompatan waktu yang disetujui boleh menggantikan pencocokan latar harfiah: nyatakan apa yang berlanjut (karakter, properti, arah, atau aksi cerita) dan apa yang berubah (tempat/waktu). Jangan menghabiskan semua N klip di meja yang sama kecuali diminta eksplisit.

## Penutup konfirmasi

Akhiri Phase A dengan meminta pengguna untuk:

- menyetujui proposal saat ini dan men-generate N prompt Omni Flash;
- merevisi adegan atau bagian narasi yang disebut; atau
- mengubah setting global seperti rasio aspek, durasi, gaya, tema, palet, suara, atau nada.

Jangan sertakan prompt model final. Perubahan global membatalkan persetujuan dan memerlukan Phase A yang direvisi.

## Pengecekan Phase A

- Sumber, rasio aspek (`16:9` atau `9:16`), durasi, dan gaya/tema diketahui.
- Skrip benar-benar menerapkan Mesin Detak Jantung 5-Tahap Berpenyelesaian Tinggi.
- Klip terakhir ditutup dengan ajakan diskusi provokatif yang mendorong komentar.
- Narasi cocok dengan durasi (~20–25 kata per klip 10 dtk; ~120–150 kata untuk 60 dtk).
- Tepat N baris storyboard punya tujuan naratif yang berbeda (N = durasi / 10).
- Setiap baris punya tiga beat, setidaknya empat device visual, audio, dan transisi.
- Perubahan visual terjadi kira-kira setiap dua sampai tiga detik.
- Tidak lebih dari tiga warna aksen jenuh dipakai (untuk Style 1) atau aturan palet bersih diikuti (untuk Style 2).
- Tidak ada notasi warna teknis.
- Teks yang diusulkan dipisahkan jelas sebagai overlay post-produksi dan tidak ada di adegan yang di-generate.
- Setiap pasangan bersebelahan punya sambungan kontinuitas bernama.
- Ending kembali ke pesan inti dan CTA.
- Tidak ada detail faktual yang tak didukung ditambahkan.
- Satu voice profile lengkap diusulkan untuk seluruh video, independen dari gaya visual; catatan audio khusus adegan tidak bertentangan dengannya. Beberapa pembicara yang disetujui punya profil stabil terpisah dan penugasan baris eksplisit.

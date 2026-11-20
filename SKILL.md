---
name: stickman-video-director
description: 'Gunakan saat pengguna ingin membuat video cerita atau film pendek bergaya stickman dari awal sampai akhir: memecah ide/naskah menjadi adegan (scene breakdown), men-generate klip per-adegan dengan blok prompt tetap + gambar referensi lewat tool video (GenerateVideo), membuat narasi TTS, musik latar (BGM), mengedit dengan ffmpeg, lalu QA dengan sampling frame. Cocok untuk horor/misteri, edukasi/penjelasan, komedi, dan cerita emosional, durasi sekitar 15–120 detik, landscape maupun vertikal.'
---

# Stickman Video Director — sutradara video stickman

Skill untuk memproduksi satu film pendek stickman utuh: **naskah → pecah adegan → generate klip per-adegan → narasi → musik → rakit → QA**. Dokumen detail ada di folder `references/` (lihat bagian "Kapan membaca referensi" di bawah). Skill ini adaptasi dari repo upstream `kaomei/stickman-video-director` (MIT) ditambah pelajaran dari produksi nyata.

## 1. Dua mesin (pilih dulu sebelum mulai)

| Mesin | Hakikatnya | Biaya | Kemulusan | Cara menjalankan di Grok Bot |
|---|---|---|---|---|
| **A · Mesin model video** (gaya A1–A7) | Prompt storyboard diberikan ke model video untuk menghasilkan shot kontinu | Memakai kuota generate video; makin panjang makin mahal dan perlu "gacha" (ulang) | Tinggi, gerak benar-benar kontinu | Tool generate video asisten (**GenerateVideo**) dengan gambar referensi; satu klip ≈ 10 detik per adegan |
| **B · Mesin kode** (gaya B1–B6) | Aset berlapis + kode menganimasikan frame demi frame, dirender lokal | Tanpa kuota video; hanya waktu komputasi | Tergantung kerapatan frame; sekeluarga dengan Remotion | **Python PIL** menggambar frame + **ffmpeg** (streaming frame ke ffmpeg), atau **Remotion** |

Gaya: A1 klasik hitam-putih · A2 modern populer · A3 gua prasejarah · A4 cerita hangat · A5 kartun sejarah · A6 amber noir · A7 rubber hose (selang karet). B1 garis minimalis · B2 gambar tangan berwarna · B3 TV retro · B4 thriller bertahan hidup · B5 penjelas karakter · B6 meme dinamis.

**Aturan pilih mesin**
- Ingin mulus, kaya, dan sinematik (horor/atmosfer, cerita emosional) → **A**. Ini pilihan default untuk hasil akhir.
- Ingin murah, terkendali, karakter stabil, atau sekadar prototipe/cadangan → **B**. B bagus untuk penjelasan/infografis/alur/kantor yang gaya visualnya sederhana; B tidak mampu membuat suasana horor dengan latar ilustrasi detail dan pencahayaan sinematik.
- Satu generate utuh hanya cocok untuk **≤ 10 detik**. Film lebih panjang **wajib dipecah per-adegan** (≈10 detik per adegan, satu "gag"/beat per adegan), lalu disambung.

## 2. Alur kerja end-to-end

1. **Brief**: pastikan sumber/naskah, rasio (`16:9` / `9:16`), durasi, gaya (A1–A7 / B1–B6), bahasa narasi. Tanyakan yang kurang sekaligus dalam satu pesan; jangan menebak rasio/gaya diam-diam.
2. **Pecah adegan (scene breakdown)**: bagi naskah menjadi N adegan (N ≈ durasi/10). Tiap adegan: tujuan naratif, visual (lokasi, aksi, properti), narasi, durasi, transisi ke adegan berikutnya. Format tabel ada di `references/storyboard-template.md`.
3. **Kunci blok prompt tetap (fixed prompt blocks)**: tulis blok *karakter* dan blok *gaya gambar/palet* satu kali, lalu **salin verbatim ke setiap adegan**. Hanya blok adegan (lokasi/properti) dan blok aksi berbasis waktu (`0–3s`, `3–7s`, `7–10s`) yang berubah. Jangan menulis "karakter yang sama seperti sebelumnya". Contoh blok nyata ada di `references/a7-prompt-contract.md` dan `references/style-catalog.md`.
4. **Gambar referensi**: lampirkan gambar referensi (identitas karakter / gaya gambar) ke tool video pada slot *referensi/material*, bukan sebagai frame pertama harfiah — kecuali memang ingin kontinuitas frame pertama. Referensi yang sudah mulus untuk A7 ada di `references/a7-kitchen-ref.jpg`. Tanpa referensi dan tanpa blok tetap, karakter pasti melenceng antar adegan (terbukti di uji nyata: karakter berubah di tiap adegan).
5. **Generate klip per-adegan** dengan GenerateVideo (satu adegan = satu klip ≈ 10 detik, resolusi sesuai kebutuhan). Simpan prompt persis yang dikirim dan hasilnya; pakai ulang adegan yang sudah diterima, jangan generate ulang membabi buta. Ungkapkan biaya/kuota sebelum generate massal bila pengguna belum memberi izin.
6. **Narasi (TTS)**: buat narasi per-adegan dengan tool/skill suara yang tersedia, pilih satu profil suara untuk seluruh video dan jangan ganti di tengah. Cek durasi tiap segmen (lihat pelajaran TTS di bawah).
7. **Musik latar (BGM)**: gunakan musik berlisensi/yang tersedia, atau sintesis dengan kode (lihat pendekatan numpy di bawah). Jaga kontinuitas BGM sejak adegan 1.
8. **Rakit dengan ffmpeg**: sesuaikan durasi klip dengan durasi narasi (setpts), sambung, bakar subtitle bila diminta, mix narasi+BGM, normalisasi loudness (target kira-kira −14 s/d −16 LUFS), encode MP4.
9. **QA dengan sampling frame**: ekstrak frame (mis. 1 frame per 2–3 detik, plus frame di sambungan antar-adegan) dan periksa: konsistensi karakter, urutan beat, relasi kontak, teks/watermark tak diinginkan, kejelasan subtitle. Dengarkan/periksa audio (silencedetect, loudness). Perbaiki hanya adegan yang bermasalah, lalu periksa ulang adegan itu dan sambungan sekitarnya.
10. **Serahkan**: MP4 akhir + (opsional) versi vertikal 9:16, subtitle sidecar, ringkasan pengecekan yang jujur (apa yang diperiksa, apa yang belum, keterbatasan).

Untuk video yang diminta pengguna Indonesia: narasi dan teks layar dalam Bahasa Indonesia. Prompt untuk model video tetap boleh/lebih baik dalam bahasa Inggris, dengan kutipan narasi apa adanya bila narasi disinkronkan oleh model.

## 3. Aturan inti untuk gaya A7 rubber hose (ringkasan)

- Prompt **empat blok**: Block 1 karakter tetap + Block 2 gaya/palet tetap (verbatim, lihat `references/a7-prompt-contract.md`), lalu Block 3 adegan + Block 4 aksi/kamera berbasis waktu.
- Karakter: stickman garis tipis, wajah bulat putih, dua jumbai rambut, badan dan anggota tubuh garis halus; **tanpa pakaian dan tanpa badan terisi**.
- Palet: warna tertahan — hijau abu-abu sage, abu mutiara, abu-taupe, gading, sedikit merah bata pudar. **Bukan hitam-putih dan bukan sepia**; tanpa goresan berat atau vignette.
- Gambar referensi masuk sebagai materi referensi untuk identitas dan gaya gambar, bukan frame pertama.
- Akseptasi dilihat dari film nyata: karakter melenceng, urutan beat, dan relasi kontak yang gagal berarti gagal, walau prompt sudah benar. Detail di `references/a7-acceptance.md`.

## 4. Pelajaran dari produksi nyata (lessons learned)

**Ritme dan pacing (hasil revisi setelah pengguna menilai "terlalu lambat, jeda aneh")**
- Hapus title card hening di awal; letakkan judul di bagian atas adegan pertama dan mulai narasi pada detik 0.
- Tulis naskah penuh: kira-kira 55–60 kata per adegan 10 detik (ritme TTS yang sedikit cepat) — bukan naskah yang tipis.
- Ubah kecepatan (setpts) tiap adegan agar durasinya = durasi narasi adegan itu + sekitar 0,15 detik; segmen narasi bersambung tanpa keheningan.
- Panjang film pendek yang nyaman: 50–70 detik, 6 adegan × ~10 detik.

**TTS: durasi outlier harus dicek**
- Satu kali, naskah ±8 detik dibacakan TTS menjadi 23 detik karena disisipi jeda 1,1–1,45 detik di antar-kalimat. Selalu periksa durasi tiap segmen narasi; yang menyimpang jauh dari perkiraan (kata ÷ laju bicara) harus diperiksa dengan `ffmpeg -af silencedetect`.
- Mengulang dengan teks sama bisa mengenai cache yang buruk; ubah beberapa kata untuk memecah cache.
- **Perbaikan terbaik: pecah per kalimat.** Naskah 54 kata menghasilkan draf 22,7 detik dua kali (jeda 8,5 detik setelah kalimat pertama), tidak membaik meski kata diubah. Solusinya: generate tiap kalimat sebagai segmen terpisah lalu `concat` secara lokal → hasil bersih 9,4 detik. Pecah-dan-rekam-ulang lebih diutamakan daripada ganti-kata-dan-rekam-ulang.

**Perbaikan (reshoot) memakai frame dari film yang sama**
- Bila satu adegan hasilnya melenceng (mis. gaya jadi lebih pipih/datar dibanding adegan lain), generate ulang dengan **frame yang sudah lulus dari film yang sama** (mis. frame adegan 5 atau 2) sebagai gambar referensi — bukan referensi eksternal asal. Tambahkan juga larangan eksplisit di prompt ("jangan kartun datar minimalis; gunakan komposisi samping dengan sudut lebar"). Hasilnya jauh lebih sesuai dengan adegan lain.
- Jangan lupa: label/teks bawaan model di dalam adegan (mis. "EXIT", "ELEVATOR") bukan subtitle Anda; catat sebagai keterbatasan jika muncul.

**Gaya cerita modern (alternatif selain A7)**
- Untuk horor/emosional, buat blok tetap sendiri: karakter (mis. wajah bulat putih besar + ciri khas rambut/pakaian), desain pendukung, dan gaya (latar ilustrasi tangan halus, biru malam + kuning hangat, suspense sinematik → hangat). Salin verbatim di semua adegan dan pakai frame referensi untuk mengunci identitas dan gaya. 6 adegan × 10 detik.
- Tulis kekurangan secara jujur setelah QA (mis. adegan terakhir lebih pipih, wajah close-up kurang konsisten dengan adegan lain).

**BGM dengan sintesis numpy (bila tak ada tool musik)**
- Sintesis dengan `numpy` (+ `scipy`/`soundfile` untuk tulis WAV): paruh pertama bernuansa suspense — drone bass rendah, nada piano jarang, harmonik kotak musik yang jauh (mis. D minor); titik balik kemudian beralih ke melodi kotak musik + akor piano lembut (mis. F major), titik balik diselaraskan dengan momen pengungkapan kebenaran di adegan. Loudness BGM ≈ −21 LUFS, hasil mix akhir ≈ −14 LUFS, narasi tetap jelas.

**Kerangka Remotion (mesin B, opsional)**
- Bila memakai kerangka Remotion siap pakai untuk stickman: prinsip kerja yang berguna **REUSE → RESKIN → NEW** (pakai adegan yang ada dulu, ubah hanya warna/teks/posisi/jumlah frame, kode baru adalah opsi terakhir) dan memakai indeks file pendek agar hemat token agen.
- Catatan lingkungan: font dari Google Fonts bisa gagal diunduh di Chromium headless di balik proxy (ERR_SSL_PROTOCOL_ERROR) — ganti ke font stack lokal. Render dengan `--browser-executable` yang menunjuk ke Chromium yang tersedia.
- Keterbatasan: kerangka semacam itu umumnya hanya cocok untuk penjelasan/alur/kantor (karakter berisi gaya sederhana, hanya furnitur dalam ruangan); bukan untuk horor atau suasana luar ruangan.

**Pelajaran lain**
- Pembagian mesin: horor/zombi/atmosfer naratif → mesin A. Penjelasan/infografis/biaya murah → mesin B.
- Wajah bisa berubah bentuk berlebihan antar-adegan; untuk topik komedi masih bisa diterima, untuk horor/emosional perlu referensi + blok tetap yang ketat.
- Bila prompt panjang dikirim, jangan diam-diam membuang blok tetap karena batas panjang; selesaikan batasannya.
- Jangan menyatakan "selesai/lulus" bila belum benar-benar menonton/mendengar; catat apa yang baru disampel.

## 5. Kapan membaca referensi

Folder `references/` memuat dokumen detail. Baca sesuai kebutuhan, jangan semuanya sekaligus:

| File | Baca ketika |
|---|---|
| `references/getting-started.md` | Pertama kali menjelaskan skill ke pengguna, atau menyusun update progres tiap tahap |
| `references/mode-execution-boundaries.md` | Sebelum produksi: memisahkan aturan mode A (Director) dan B (Autopilot), serta gaya A6/B4/B5/B6 |
| `references/storyboard-template.md` | Menulis proposal & storyboard (Phase A): mesin 5-tahap, header, resep kepadatan visual, kontinuitas |
| `references/style-catalog.md` | Memilih/menulis blok karakter & gaya untuk Style 1–5, batasan negatif, kontinuitas suara & BGM |
| `references/rubber-hose.md` | Memakai gaya A7 rubber hose: alur produksi dan perbaikan |
| `references/a7-prompt-contract.md` | Menyalin blok prompt A7 beku (karakter, gaya, contoh adegan, contoh aksi) |
| `references/a7-acceptance.md` | Mereview output A7: gate akseptasi, catatan review, loop perbaikan |
| `references/b1-minimal-handdrawn.md` | Membuat video mesin B bergaya B1 (garis minimalis, kertas hampir putih, akting stickman) |
| `references/examples.md` | Butuh contoh end-to-end konkret (Style 1 gelap, 6 klip, dan Style 2A) |
| `references/a7-kitchen-ref.jpg` | Gambar referensi untuk dilampirkan sebagai materi referensi pada A7 |
| `UPSTREAM-SKILL.md` | Teks skill upstream lengkap (aturan Director A1–A5, gate setup, aturan output) |

Catatan: dokumen upstream merujuk beberapa file yang tidak dibundel di sini (mis. `assets/`, `voice-continuity.md`, dokumen B2–B6, A6). Bila perlu, ambil dari repo upstream; jangan mengarang isinya.

## 6. Batasan dan etika kerja

- Kuota/biaya generate: sebutkan perkiraan sebelum generate massal; instalasi skill bukan izin generate berbayar.
- Jangan memakai karakter kartun berhak cipta; jangan mengarang fakta/statistik di video penjelasan.
- Jangan publikasi/posting otomatis; serahkan file kepada pengguna.
- Catat sumber dan lisensi musik/font; musik hasil sintesis sendiri bebas masalah lisensi.

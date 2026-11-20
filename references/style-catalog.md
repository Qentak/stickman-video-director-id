# Katalog Gaya: Gaya Visual & Formula Prompt

Katalog ini mendefinisikan gaya visual yang didukung oleh `directing-stickman-videos` (nama upstream), termasuk kunci DNA karakter, spesifikasi lingkungan, tempo gerak, dan batasan negatif.

> Catatan: blok teks dalam ```text``` adalah string prompt untuk model video dan sengaja dibiarkan dalam bahasa Inggris. Nama gaya di kurung Mandarin diberi padanan Indonesia. File upstream seperti `prehistoric-dark-comedy.md`, `cozy-storytelling.md`, `historical-cartoon.md`, dan `voice-continuity.md` tidak dibundel di sini.

---

## 1. Ikhtisar Matriks Gaya

| Style Key | Nama Gaya | Tema Visual | Paling Cocok Untuk | Desain Karakter |
|---|---|---|---|---|
| **Style 1** | Classic Minimalist (Terang / Gelap) | Kanvas putih murni atau hitam, garis monokrom, hingga 3 warna aksen jenuh | Explainer padat, logika murni, model mental, konsep kognitif bertempo cepat | Kepala lingkaran kosong, badan satu garis, tanpa pakaian, sesekali ekspresi garis sederhana |
| **Style 2A** | Modern Beanie - Studio Tech (Gaya Teknologi Minimalis) | Studio high-key putih murni, grid perspektif abu-abu muda halus, UI kaca cyan/biru berpendar | Tutorial teknologi, bedah tool AI, wawasan karier, terobosan metodologi | Beanie merah (tanpa pompom), kaos kuning, anggota tubuh hitam, animasi 2D halus |
| **Style 2B** | Modern Beanie - Cinematic Story (Gaya Cerita Berwarna) | Lingkungan naratif full-color, pencahayaan dan kedalaman sinematik (kamar hangat, senja, gurun, puncak) | Storytelling emosional, pertumbuhan pribadi, perjalanan motivasi, hook naratif | Figur beanie merah & kaos kuning yang sama dipentaskan dalam pencahayaan lingkungan yang kaya |
| **Style 3** | Prehistoric Hand-Drawn / Dark Comedy (Gambar Tangan Prasejarah / Humor Gelap) | Lingkungan prasejarah bernuansa tanah, aksen api hangat, tekstur kertas halus | Cerita satir, analogi visual, callback ironis | Kepala putih terisi, wajah kartun ekspresif, anggota tubuh stick hitam, pemeran variabel khusus cerita |
| **Style 4** | Cozy Storytelling (Cerita Menyembuhkan) | Lokasi kartun 2D full-color, cahaya atmosferik lembut, shot sinematik bervariasi | Cerita kehidupan yang relatable, pertumbuhan emosional, storytelling edukatif | Kepala bulat putih terisi dan torso ramping, anggota tubuh stick gelap, wajah ekspresif sederhana |
| **Style 5** | Historical Cartoon (Kartun Sejarah) | Latar sejarah berlukis full-color, cel shading bersih, pakaian dan properti khas era | Explainer sejarah, kehidupan sehari-hari sejarah, kisah peradaban dan komedi sejarah | Kepala bulat putih terisi dengan leher putih pendek tersambung, wajah individual ekspresif, mata oval hitam solid, anggota tubuh hitam tipis terbuka dan telapak kecil hitam solid berbentuk mitten yang menyatu dengan pergelangan, satu lobus jempol halus terintegrasi, tanpa jari individual, pemisah jari, isian putih, atau sarung tangan |

Untuk Style 3 baca `prehistoric-dark-comedy.md`. Ia menimpa aturan gerak dan piano generik katalog ini. Kunci tata bahasa gambar lintas cerita, bukan satu wajah universal; kunci setiap karakter yang disetujui di dalam satu cerita.

Untuk Style 4 baca `cozy-storytelling.md`. Perlakukan lokasi sebagai beat cerita, bukan satu ruangan universal. Nama tampilan bahasa Inggrisnya adalah **Cozy Storytelling**; jangan menamainya ulang Sketchbook Stories, hand-drawn, atau prehistoric.

Untuk Style 5 baca `historical-cartoon.md`. Bekukan tata bahasa gambar; ubah era pack, bukan sistem rendering karakter. Gunakan cast card, palet sejarah, dan musik yang sesuai cerita bersama `voice-continuity.md`.

---

## 2. Style 1: Classic Minimalist

### Polaritas & Latar
- **Tema Terang**: Kanvas putih murni digital yang rata dan seragam. Dilarang keras tint abu-abu, tekstur kertas, gradien, bayangan, pencahayaan, bloom, kabut, atau kedalaman 3D.
- **Tema Gelap**: Kanvas hitam pekat yang rata dan seragam. Line art putih murni dengan warna aksen kontras tinggi.

### DNA Karakter

**Classic Dark — basis tanpa-wajah yang teruji:**
```text
Use minimalist two-dimensional white line animation. Show the same consistent stick figure with a hollow circular head, no face, no eyes, no mouth, no hair, no clothing, no filled body, stable proportions, connected line limbs, and uniform medium line weight. Exactly two arms and two legs are visible per figure. Each limb appears only in its current pose: raising or lowering the right arm replaces that arm's previous line, never leaving a resting arm beneath an active arm. The figure stays white; accent colors affect only props and graphic effects.
```

**Classic Light — basis tanpa-wajah yang teruji:**
```text
Use minimalist two-dimensional black line animation. Show the same consistent stick figure with a hollow circular head, no face, no eyes, no mouth, no hair, no clothing, no filled body, stable proportions, connected line limbs, and uniform medium line weight. Exactly two arms and two legs are visible per figure. Each limb appears only in its current pose: raising or lowering the right arm replaces that arm's previous line, never leaving a resting arm beneath an active arm. The figure stays black; accent colors affect only props and graphic effects.
```

Pilih tema, lalu bekukan anchor penuhnya dan ulangi verbatim di setiap klip. Jangan memperluasnya menjadi rasio numerik, definisi skeleton/rig, jalur pena, bentuk tangan/kaki terpisah, atau deskripsi volume tubuh. Simpan pose, gerak, properti, dan kamera di urutan berbasis waktu, bukan dalam definisi karakter yang bersaing. Aturan current-pose berlaku untuk setiap anggota tubuh; jika cerita yang disetujui memakai aksi utama lengan kiri, sesuaikan sisi tangan sekali sebelum membekukan, jangan pernah klip demi klip. Pertahankan aksi energik dan efek kaya; gambar motion trail pada properti atau grafis terlepas, bukan sebagai pose anggota tubuh tambahan.

Ekspresi garis sederhana yang sesekali diperbolehkan secara default. Sebelum membekukan salah satu anchor basis, ganti hanya "no face, no eyes, no mouth," dengan "occasional simple line expressions, no detailed facial features," dan jaga batasan negatif prompt tetap kompatibel dengan pilihan itu. Jika pengguna secara eksplisit meminta karakter tanpa wajah, biarkan basis tidak berubah. Ekspresi tidak pernah mengubah isian kepala, outline kepala, struktur badan, atau proporsi; tanpa mata detail, pupil, atau rendering wajah realistis.

Retest Flow 2026-10-13: Omni 1.1 Flash, 16:9, 720p, klip 10 dtk independen untuk cerita pesawat kertas/perfeksionisme. Basis Dark final dipakai di tiga klip plus dua klip berisiko-tinggi yang diulang; basis Light dipakai di dua klip. Frame aksi yang disampel lewat browser tidak menunjukkan anggota tubuh berlebih atau pembesaran kepala mendadak pada sampel final ini. Titik ujung tangan/kaki dan ketebalan garis antar-klip masih bisa bervariasi; ini bukan sertifikasi frame-demi-frame atau jaminan untuk generasi mendatang. Varian dengan ekspresi dan varian kidal tidak diuji terpisah. Cakupan rinci dan ID aset ada di `tests/reports/classic-character.md` di tingkat repositori. Kontinuitas properti dan audio tidak diterima oleh cek karakter-saja ini.

### Kontrak Palet
- Maksimum tiga warna aksen jenuh yang disebut dengan kata biasa (mis. vivid red, electric blue, warm gold).
- Tanpa notasi warna teknis (hex, RGB, Pantone).

---

## 3. Style 2: Modern Beanie Zeke

### Anchor DNA Karakter (Kunci Anti-Deformasi)

Untuk mencegah drift karakter, deformasi mata-serangga, atau hilangnya pakaian antar klip, gunakan anchor karakter persis ini:

**Anchor Karakter Klip 1:**
```text
A minimalist 2D animated stick figure wearing a bright red beanie (smooth rounded knit, no pom-pom) and a yellow t-shirt, with simple black stick limbs and shorts. Simple black lines, vibrant colors, smooth 2D animation style.
```

**Anchor Karakter Klip Berikutnya (Klip 2–6):**
```text
The same minimalist 2D animated stick figure in a bright red beanie and yellow shirt... Simple black lines, vibrant colors, smooth 2D animation style.
```

**Aturan Pencegahan Deformasi:**
- **Tanpa Fitur Wajah Realistis**: Hanya kepala lingkaran kosong atau mata titik minimal. Jangan pernah meminta pupil detail, iris, atau kontur wajah fotorealistis (yang memicu mata serangga alien).
- **Tanpa Pompom**: Tentukan puncak beanie yang halus membulat untuk mencegah pompom atau rumbai musim dingin yang liar.
- **Selalu Sertakan Beanie dan Kaos**: Tanpa kaos menghasilkan badan stick telanjang; tanpa beanie menghasilkan karakter Style 1 biasa.

---

### Sub-Style 2A: Modern Studio Tech (Gaya Teknologi Minimalis)

**Dalam Bahasa Biasa**: Gaya teknologi minimalis ala peluncuran produk Apple. Ruang putih berkilau high-key murni + grid ubin perspektif abu-abu muda yang sangat samar + UI kaca semi-transparan cyan-biru melayang/tekstur cahaya redup.

#### Spesifikasi Lingkungan
```text
in a modern bright white studio space with subtle light-gray perspective grid lines on the floor plane. High-key studio lighting, clean white negative space, sleek glowing cyan and electric blue glass holographic UI elements.
```

#### Batasan Negatif Wajib (Anti-Kekacauan)
Tanpa batasan negatif eksplisit, model difusi cenderung menghasilkan sirkuit motherboard, koridor pesawat luar angkasa, dan beton retak. **Selalu tambahkan klausa negatif ini di prompt 2A:**
```text
Negative constraints: strictly minimalist studio aesthetic, no circuit board textures, no sci-fi wall panels, no spaceship corridors, no cracked concrete, no grunge textures, no photorealistic human skin, no speech bubbles, no dialogue text boxes.
```

#### Dinamika Gerak (Anti-Gagap & Anti-Lag)
- **Jangan pakai transformasi cairan/morphing abstrak** (mis. tangga meleleh menjadi jam), yang memicu flicker laten dan gagap.
- **Gunakan interaksi fisik yang digerakkan karakter**:
  - Melompat dan menabrak langit-langit kaca tak terlihat dengan pantulan komikal.
  - Mengetukkan sneaker ke grid lantai untuk memancarkan gelombang riak cyan yang meluas.
  - Mengeluarkan pena cahaya berpendar untuk menggambar jembatan garis bercahaya tajam melintasi jurang.
  - Menyentuh panel kaca melayang yang ramping untuk mengungkap gembok bercahaya berupa ikon-saja.
  - Mendorong pintu brankas minimalis yang berat untuk melangkah maju ke cahaya cakrawala yang terang.
- **Tempo**: Setiap klip 10 detik harus menampilkan aksi berbeda di `[0–3s]`, `[3–7s]`, dan `[7–10s]`. Jangan pernah membiarkan karakter diam atau menatap kamera selama beberapa detik.

---

### Sub-Style 2B: Cinematic Story (Gaya Cerita Berwarna)

**Dalam Bahasa Biasa**: Gaya film pendek bercerita ala Pixar. Adegan imersif full-color (kamar tidur dengan lampu meja hangat, jendela senja, jalan raya liar, puncak gunung di atas awan) + cahaya dan bayangan naratif sinematik.

#### Spesifikasi Lingkungan
```text
in a rich full-color cinematic environment [describe setting: e.g., a dimly lit cozy bedroom with warm lamplight / a vast open desert highway under a glowing dusk sky / a dramatic mountain ridge above rolling golden clouds]. Cinematic volumetric lighting, soft depth of field, atmospheric narrative mood.
```

#### Konsistensi Karakter & Gaya
- Karakter tetap stick figure 2D minimalis yang sama dengan beanie merah dan kaos kuning.
- Pertahankan estetika animasi vektor 2D halus untuk karakter bahkan di dalam latar bertekstur dan atmosferik.

#### Batasan Negatif
```text
Negative constraints: no photorealistic human skin or faces, no 3D humanoid CGI uncanny valley models, no chaotic line glitches, no speech bubbles, no dialogue text boxes.
```

---

## 4. Style 4: Cozy Storytelling (Cerita Menyembuhkan)

Karakter minimalis ekspresif di dalam dunia kartun berwarna: kantor, peron metro, kafe pinggir jalan, taman, atau setting lain yang sesuai cerita. Gunakan insert aksi dekat, tampak pembuka lebar, tracking lateral, dan cut lokasi yang bermotivasi. Kehangatan milik perlakuan visual; pertahankan konflik dan makna sumber alih-alih membuat setiap topik ceria.

Setiap segmen sepuluh detik baru biasanya menetapkan lokasi berbeda. Jaga karakter, properti penting, arah layar, dan voice profile penuh tetap konsisten, sambil mengubah pemandangan dengan sengaja. Sudut kamera baru pada meja yang sama bukan pengganti lokasi cerita baru. Permintaan lokasi tunggal dan callback yang disetujui tetap pengecualian yang valid.

Gunakan anchor karakter penuh, aturan kondisi properti, dan checklist akseptasi di `cozy-storytelling.md`; jangan mewarisi larangan kepala-kosong/tanpa-wajah/tanpa-badan-terisi Style 1 atau aturan sketsa kasar/kulit hewan Style 3.

---

## 5. Style 5: Historical Cartoon (Kartun Sejarah)

Karakter stick-figure ekspresif berpakaian sejarah, dipentaskan di lanskap dan arsitektur berlukis berwarna. Gunakan tampak pembuka lebar, aksi karakter yang terbaca, close-up reaksi, dan cut yang bermotivasi. Rancang pemeran untuk cerita: prajurit Romawi, pelajar zaman Edo, atau pelayan kuil Mesir butuh pakaian dan properti berbeda, bukan tata bahasa gambar yang berbeda.

Gunakan `historical-cartoon.md` untuk style anchor penuh, template era-pack, cast card, dan perakitan prompt. Konsep visual dan kontribusi era-pack Romawi: [@leksautomate](https://github.com/leksautomate).

---

## 6. Kontrak Kontinuitas Audio Universal

Kontinuitas suara adalah fondasi bersama untuk **semua gaya**, termasuk Style 3 dan 4. Terapkan `voice-continuity.md` sebelum aturan musik spesifik gaya. Video berbeda dapat memilih suara berbeda, sementara semua klip satu video mengulang satu voice profile lengkap yang disetujui. Pisahkan identitas suara dari busur musikal.

### Kunci Suara Narator
```text
One off-screen adult male narrator throughout. General American accent, warm clean baritone, medium-low pitch, gentle chest resonance, no raspiness or breathiness. Calm conversational delivery, restrained pitch variation, steady speaking pace, and close, dry studio sound. Keep the same vocal timbre, register, accent, pace, and recording quality throughout. Emotional progression belongs to the visuals and music; do not change the narrator's voice or switch to character dialogue.
```
Ini contoh pria yang diterima pengguna, bukan suara wajib untuk setiap proyek. Untuk suara perempuan, lebih tua, muda, atau suara lain yang disetujui, selesaikan profil koheren lengkap memakai `voice-continuity.md`, lalu ulangi verbatim di setiap klip. Jangan hanya memakai "narator yang sama" atau mewarisi klip sebelumnya lewat nama. Jaga narasi audio-saja, suara-dulu, tanpa gelembung ucapan atau kotak dialog. Akseptasi mendengarkan aktual ada untuk sampel Style 2A Hope; profil/gaya lain tetap belum teruji untuk pencocokan audio.

### Kontinuitas BGM
- **Klip 1**:
  ```text
  Audio: Voiceover clearly audible over quiet, thoughtful piano and subtle soft ambient synth, building gentle optimistic momentum.
  ```
- **Klip 2–6**:
  ```text
  Audio: Voiceover seamlessly continues the identical quiet, thoughtful piano and subtle soft ambient synth from clip 1, maintaining identical tempo, instrumentation, and optimistic narrative momentum. Synchronized crisp SFX on physical actions.
  ```

---

## 7. Template Tempo Beat Visual (Klip 10 Detik)

Setiap prompt harus membagi 10 detiknya menjadi tiga beat naratif aktif:

```text
Timed Synchronized Visual Beats:
- [0–3s] (VO: "..."): [Setup / premise action — character enters, acts, or inherits momentum from previous clip]
- [3–7s] (VO: "..."): [Escalation / discovery — character interacts with environment or solves visual obstacle]
- [7–10s] (VO: "..."): [Climax & outgoing transition — character delivers payoff and initiates outgoing motion for next clip]
```

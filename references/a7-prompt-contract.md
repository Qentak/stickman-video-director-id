# A7 · Kontrak prompt empat blok

Baca [production](rubber-hose.md) dan [acceptance](a7-acceptance.md). String otoritatif ada di [approved-prompt-lock.json](../assets/a7/approved-prompt-lock.json). Salin Block 1 dan 2 persis ke setiap prompt standalone. Kata "about 2 pixels wide at 360p" menggambarkan ketipisan relatif; resolusi output adalah setting terpisah. Jangan ubah menjadi tulang punggung tebal berisi pada 720p.

> Catatan: isi blok prompt di bawah sengaja tetap dalam bahasa Inggris karena itu adalah teks yang dikirim ke model video. Jangan diterjemahkan.

## Block 1 — karakter tetap

```text
ONE original stickman, drawn as a literal thin-line stick figure. Flat paper-white circular face, two black oval eyes, tiny brows and mouth, exactly two short curved black hair tufts. Head outline directly touches a short black neck. Neck, vertical spine, two arms and two legs are each a SINGLE uniform fine ink stroke, like a pen-drawn stick diagram, about 2 pixels wide at 360p. Background remains visible immediately beside both edges of the narrow spine, even between the shoulders. Two small white outlined hands and two short black curved feet. All joints visibly connected; head size and line width remain constant during bending. Bare line body; no clothing, tie, black filled chest, triangular neck shape or rounded torso.
```

## Block 2 — gambar dan palet tetap

```text
An original early hand-inked theatrical cartoon with a fine-line stickman and an exquisitely HAND-DRAWN 1930s background painting. A subdued colored palette: dusty sage-gray green, pearl-gray plaster, muted gray-taupe, pale ivory furnishings and tiny faded brick-red details. Not pure monochrome, not sepia. The face and hands are flat clean neutral WHITE with no yellow tint. Every room object is defined first by a confident visible black pen outline, with small hand-drawn seams, hinges, joints and irregular edges. Color inside those contours is laid in as flat matte paint shapes with delicate visible brush texture, soft stippling and sparse hatch strokes. Use a few broad, simple painted tone regions for depth, not smooth shading wrapped around furniture. Uniform diffuse stage illumination: lamps remain OFF, walls and work surfaces have even tones; no lit pools, glints, bloom, window glow or directional cast-light effects. Period craftsmanship and fine architectural drawing provide richness, while shapes remain clear and quiet around the stickman. Distinct 2D ink-and-paint cartoon scenery, no CGI, 3D renders, ambient occlusion, smooth bevels, plastic, photoreal material, airbrushed gradients, film border, heavy scratches or existing cartoon character.
```

## Block 3 — adegan variabel dengan standar gambar bersama

Jaga blok ini tetap ringkas: sebut lokasi periodenya, pilih beberapa detail konstruksi inked yang esensial dan area cat datar, lalu tetapkan properti utama dan ruang akting yang jelas. Blok gambar yang dibekukan sudah membawa seluruh gaya; lokasi baru tidak membutuhkan paragraf jangkar verbatim panjang lagi. Cocokkan metode menggambarnya, bukan hanya warnanya. Jaga aktor tetap terbaca dan jangan impor set atau shot pembuka dapur referensi.

Ini adalah **blok adegan persis dari tes kantor pos yang diterima pengguna**:

```text
A small 1930s post office: a finely inked timber service counter, pigeonhole mail shelves, frosted window and scuffed floorboards. A dusty sage-gray and pale ivory stage with quiet painted wear and clear space around the hero. One small parcel tied with string and a mechanical pan scale establish the task. The reference kitchen is not a location in this film.
```

## Block 4 — aksi dan kamera variabel berbasis waktu

Tulis performa yang kausal dengan antisipasi, aksi, konsekuensi, dan reaksi, memakai framing yang bertujuan. Nyatakan genggam, lepas, kontak kaki, dan kondisi properti yang penting; jaga sambungan kepala/leher/anggota tubuh dan tulang punggung sempit tetap stabil. Timing mengikuti durasi yang benar-benar diminta dan aksi yang terbaca. Empat beat berguna pada tes sepuluh detik ini, bukan kuota shot yang wajib.

Ini adalah **blok aksi persis dari tes yang sama yang diterima**:

```text
0-2.5s medium side view: the hero walks two clear planted steps to the counter, carrying one small parcel in both hands, then places it on the scale and visibly releases it. 2.5-5s cut closer: the scale pan sinks much farther than he expects; he leans down, peers, raises his eyebrows, then tries to lift the surprisingly heavy parcel. 5-7.5s medium-wide view: he braces both feet and pulls with both hands, stretching elastically while his connected trunk stays a fine ink line; the parcel suddenly comes free, making him take two quick backward balancing steps. 7.5-10s closer reaction: he regains his balance, hugs the parcel carefully and gives the camera an exhausted, embarrassed little smile. The counter, scale and parcel stay coherent. Each beat has anticipation, action and a readable reaction. Keep the fine two hair tufts, head-neck connection and bare thin body throughout; no clothing or filled torso.
```

## Contoh yang diperluas dan diterima

- [Kantor pos: prompt persis yang disubmit](../assets/a7/validated-prompts/post-office.txt)
- [Dermaga tepi laut: prompt persis yang disubmit](../assets/a7/validated-prompts/seaside-pier.txt)
- [Setting, hash prompt, dan cakupan review](../assets/a7/validated-workflow.json)

Kedua contoh berisi pengantar produksi singkat yang sama dan Block 1/2 beku yang persis, lalu Block 3/4 masing-masing. Keduanya diuji dengan gambar dapur yang ada sebagai **materi referensi**, bukan sebagai frame pertama, dan diterima pengguna. Keduanya adalah contoh referensi, bukan plot wajib atau soundtrack yang sudah dibersihkan haknya. Jangan salin pengantar sepuluh-detik/720p/16:9 mereka apa adanya jika brief baru meminta setting lain. Lirik tidak wajib.

Untuk prompt baru, pertahankan Block 1/2 persis, ganti adegan/aksi, dan sesuaikan pengantar/setting dengan brief yang disetujui. Tinjau keempat blok untuk kontradiksi, kontak yang mustahil, beat yang kelebihan beban, wajah kuning, badan terisi, shading halus, atau pencahayaan dramatis. Jika batas prompt menghalangi blok tetap yang lengkap, selesaikan keterbatasan tool-nya; jangan diam-diam membuang blok itu.

Untuk pengiriman Director prompt-only, sertakan keempat blok yang sudah diperluas penuh, setting output, teks/audio yang dimaksud, dan gambar referensi beserta perannya sebagai input; tanpa placeholder yang belum diselesaikan atau "karakter/gaya sama seperti di atas". Untuk eksekusi, ikuti [prosedur input referensi](rubber-hose.md#bundled-references-and-actual-model-inputs), catat identitas gambar/input yang sebenarnya dan teks persis yang disubmit, dan tetap dalam izin generate/upload/download pengguna yang sudah ada. Still baru atau tes resolusi rendah tidak wajib sebelum memakai rute video langsung yang sukses ini.

# Panduan penggunaan pertama dan tahap

> Catatan paket ini: dokumen ini menggambarkan alur onboarding upstream. Beberapa file/skrip yang dirujuk (`installation-troubleshooting.md`, `autopilot*.md`, `amber-noir.md`, `b-style-installed-workflow.md`, `scripts/autopilot.mjs`, `thumbnail-publishing-kit.md`, dll.) tidak dibundel. Di Grok Bot, "mode A" setara dengan menyusun proposal/storyboard/prompt lalu men-generate klip dengan tool video yang tersedia (GenerateVideo + gambar referensi), dan "mode B" setara dengan pipeline kode lokal (Python PIL + ffmpeg atau Remotion). Lihat `SKILL.md` untuk pemetaan tool.

## Handoff instalasi dan pemanggilan pertama

Jika instalasi gagal saat meng-clone repositori, ikuti [pemecahan masalah instalasi](installation-troubleshooting.md) sebelum melanjutkan handoff.

Skill standalone dimuat saat dipanggil; file-filenya tidak menyediakan hook eksekusi pasca-instalasi yang universal. Ketika asisten melakukan instalasi, verifikasi lalu baca `SKILL.md` terpasang dan sampaikan perkenalan di percakapan yang sama. Jika pengguna menginstal lewat terminal atau host lain, sampaikan saat pemanggilan pertama. Jangan menambah hook npm install, tugas latar, Skill kedua, atau plugin hanya untuk menampilkan sambutan. Katakan "terpasang" hanya setelah instalasi benar-benar terverifikasi.

Pertahankan satu panduan bersama, bukan edisi onboarding terpisah untuk setiap bahasa README. Ikuti permintaan bahasa panduan yang eksplisit lebih dulu, jika tidak pakai bahasa percakapan pengguna saat ini. Jika tidak jelas, pakai pengaturan bahasa host/aplikasi atau lokal bila sudah tersedia; jangan memindai pengaturan yang tak terkait untuk menyimpulkannya. Jika keduanya tak memberi bahasa yang jelas, ajukan satu pertanyaan bahasa singkat. Terjemahkan penjelasan dan contoh secara natural; pertahankan perintah, path, pengenal layanan/suara, dan kode gaya A/B. Bahasa panduan independen dari bahasa narasi/subtitle: percakapan berbahasa Mandarin bisa meminta video berbahasa Inggris, dan narasi default bahasa Inggris tidak boleh memaksa onboarding berbahasa Inggris. Jangan menyimpulkan bahasa panduan dari edisi README atau artikel sumber saja.

Berikan quick-start yang mudah dibaca, bukan sekadar salam atau dua nama mode. Tampilkan sekali di percakapan saat ini, bukan sebelum setiap tugas. Jangan menulis pengaturan pengguna global atau penanda skill-terpasang untuk mengingatnya. Saat melanjutkan, periksa checkpoint dan output yang ada alih-alih memutar ulang onboarding atau produksi.

### Penjelasan penggunaan pertama yang praktis

Bila belum ada brief, pakai judul pendek seperti quick-start README. Jelaskan deliverable sebenarnya, konten/durasi yang cocok, tool yang perlu disiapkan, urutan produksi, dan permintaan yang bisa disalin. Bedakan apa yang dikerjakan asisten dari apa yang perlu dilakukan pengguna. Jelaskan "generate gambar" sebagai membuat ilustrasi dan "komposisi lokal" sebagai menggabungkan gambar, suara, dan caption menjadi video; jangan membuka dengan perintah, nama dependensi, atau kuesioner API. Perlakukan durasi sebagai rekomendasi, bukan batas yang dipaksakan.

Tunjukkan secara proaktif di mana memilih gaya: tautkan katalog GitHub publik yang ditampilkan di bawah, jelaskan bahwa pengguna dapat menonton sampel dan membalas dengan kode gaya seperti A3 atau B1. Jangan menunggu "di mana saya memilih?" atau menggantinya dengan path file referensi terinstal sebagai pengganti katalog publik. Bila belum ada mode terpilih, tampilkan kedua tautan; bila mode diketahui tetapi gaya belum, tampilkan hanya tautan yang relevan. Bila gaya sudah diberikan, akui dan lanjutkan tanpa meminta kunjungan katalog atau pemilihan lagi. Pilihan B yang dipublikasikan adalah B1, B2, B3, B4, B5, dan B6. B5 · Character Explainer memiliki rute berbasis kode sendiri: baca [B5](b5-character-explainer.md), inisialisasi dengan `--style B5`, dan pakai `scripts/character-explainer.mjs` untuk rendering frame dan encoding. B1–B4 memakai runtime manifest yang dibundel dengan visual, suara, dan kontrak audio masing-masing. Tawarkan B4 dari katalog publik, inisialisasi secara eksplisit dengan `--style B4`, dan simpan media proyek di luar Skill terinstal. Jangan menawarkan eksperimen yang belum dipublikasikan sebagai pilihan siap pakai. B6 · Dynamic Meme Animation memakai [workflow produksi terinstal](b6-installed-production.md) dan renderer kode dunia-berlukis khusus: inisialisasi dengan `--style B6 --ratio 16:9|9:16|both`, lalu susun dan periksa rencana native, art, binding, suara, dan animasinya. Agen yang mengerjakan ini; initializer yang berhasil atau replay V90 bukan film baru yang selesai. Portrait paling cocok; pakai Sample 1 portrait V44 dan [matriks akseptasi 35 butir](b6-sample-1-acceptance.md) sebagai standar ketat. Pakai ulang pilihan rasio/suara yang diketahui; generate still-art/ucapan mengikuti otorisasi yang ada.

### Memilih bahasa katalog publik

Tentukan bahasa panduan memakai prioritas di atas, lalu pilih README-nya dari tabel ini. Cocokkan varian regional ke bahasa dasarnya (misalnya `en-GB` → `en`, `fr-CA` → `fr`, `pt-PT` → `pt-BR`); katalog Mandarin yang tersedia adalah Mandarin Sederhana. Jangan memakai locale host sebagai pengganti bahasa percakapan yang jelas. Permintaan eksplisit untuk melihat edisi README tertentu hanya menimpa pilihan katalog, bukan bahasa panduan.

| Kode bahasa panduan | Bahasa | README publik |
|---|---|---|
| en | Inggris | [README.en.md](https://github.com/kaomei/stickman-video-director/blob/main/README.en.md) |
| zh | Mandarin | [README.zh-CN.md](https://github.com/kaomei/stickman-video-director/blob/main/README.zh-CN.md) |
| ja | Jepang | [README.ja.md](https://github.com/kaomei/stickman-video-director/blob/main/README.ja.md) |
| ko | Korea | [README.ko.md](https://github.com/kaomei/stickman-video-director/blob/main/README.ko.md) |
| fr | Prancis | [README.fr.md](https://github.com/kaomei/stickman-video-director/blob/main/README.fr.md) |
| pt | Portugis | [README.pt-BR.md](https://github.com/kaomei/stickman-video-director/blob/main/README.pt-BR.md) |
| tr | Turki | [README.tr.md](https://github.com/kaomei/stickman-video-director/blob/main/README.tr.md) |
| id | Indonesia | [README.id.md](https://github.com/kaomei/stickman-video-director/blob/main/README.id.md) |

Tambahkan `#a-styles` untuk katalog Director dan `#b-styles` untuk katalog Autopilot; anchor ini dipakai bersama oleh setiap edisi yang terdaftar. Lokalkan label tautan yang terlihat dan pilih tujuan yang benar. Untuk bahasa yang tidak didukung, pertahankan panduan dan label tautan dalam bahasa itu tetapi pakai `README.en.md` untuk katalog. Jangan mengarang nama file atau anchor terjemahan, atau diam-diam kembali ke bahasa Mandarin.

Misalnya, panduan berbahasa Inggris menaut ke [Director styles and samples](https://github.com/kaomei/stickman-video-director/blob/main/README.en.md#a-styles) dan [Autopilot styles and samples](https://github.com/kaomei/stickman-video-director/blob/main/README.en.md#b-styles), bahkan di host berbahasa Mandarin. Contoh sambutan di bawah (aslinya berbahasa Mandarin, di sini diterjemahkan ke Bahasa Indonesia) memakai edisi Indonesia karena panduannya berbahasa Indonesia; jangan menyalin tujuannya apa adanya ke bahasa lain.

Sesuaikan contoh ini dengan lingkungan dan status instalasi yang sebenarnya:

### Selamat datang di Skill Video Stickman

Berikan satu topik, kebutuhan, tautan artikel, atau naskah cerita, dan kita bisa mulai. **Tidak perlu menulis naskah lengkap dulu**; saya akan membantu merapikan kontennya, lalu melanjutkan sesuai mode yang kamu pilih. Sekali instal, kedua mode di bawah ini bisa dipakai.

**Pilih gaya di sini:** [Daftar gaya mode Director](https://github.com/kaomei/stickman-video-director/blob/main/README.id.md#a-styles) · [Daftar gaya mode otomatis penuh](https://github.com/kaomei/stickman-video-director/blob/main/README.id.md#b-styles). Buka untuk melihat sampel, lalu sebutkan kode gaya yang dipilih (mis. **A3** atau **B1**); tidak perlu mengunduh paket gaya atau menginstal ulang.

#### A · Mode Director: dapatkan storyboard dan prompt dulu, kendalikan sendiri generate dan editing

- **Cocok untuk**: TikTok / Shorts, drama pendek dengan plot twist, cerita yang butuh interaksi antar tokoh dan aksi konkret; bisa mulai dari 30 detik, juga cocok untuk film pendek 1–3 menit.
- **Yang kamu dapat**: proposal cerita, narasi per segmen, storyboard visual, dan prompt video-generation yang bisa disalin satu per satu.
- **Yang perlu disiapkan**: berkomunikasi dengan saya di asisten AI yang mendukung Skill; untuk men-generate video pakai tool seperti Google Flow, lalu selesaikan editing di perangkat lunak seperti CapCut. Menulis proposal dan prompt tidak memerlukan konfigurasi API terlebih dulu.
- **Alurnya**: beri topik dan kebutuhan → saya beri proposal cerita → kamu konfirmasi atau revisi → bila perlu konfirmasi turnaround tiga-tampak karakter → saya beri prompt storyboard per segmen → kamu generate klip dan edit.

**Opsional: tetapkan karakter dulu, baru storyboard.** Kalau ingin karakter lebih konsisten, atau video dengan figur khusus, rancang dulu stickman yang sesuai gaya terpilih dan konfirmasi turnaround tiga-tampak (depan, samping, belakang). Gambar referensi karakter yang sudah dikonfirmasi bisa langsung dipakai ulang; lewati jika tak perlu kustomisasi. Saat men-generate tiap segmen video, lampirkan gambar karakter yang sudah dikonfirmasi pada tool yang mendukung gambar referensi; gambar referensi adalah bantuan tambahan, tidak menggantikan prompt asli dan tidak mengubah aturan gaya, dan konsistensi karakter antar segmen tetap harus diperiksa.

Kamu bisa langsung bilang begini:

```text
Pakai mode Director / mode A, jadikan topik, naskah, atau kebutuhan di bawah ini video stickman:
[isi topik, tempel naskah, atau langsung deskripsikan kebutuhan]
Kebutuhan: landscape 16:9, pakai A3 "gaya gua prasejarah", mulai dari 30 detik.
Beri saya proposal Director dulu, setelah dikonfirmasi baru keluarkan prompt video per segmen.
```

Untuk karakter khusus, tambahkan satu kalimat: "Tolong rancang dulu stickman yang sesuai gaya terpilih, konfirmasi turnaround tiga-tampak, baru beri prompt storyboard."

#### B · Mode otomatis penuh: setelah sampel dikonfirmasi, video lengkap dibuat otomatis

- **Cocok untuk**: penjelasan pengetahuan YouTube, promosi produk, narasi cerita, dan drama pendek bersambung; bisa coba 20 detik dulu, lalu konten 5–10 menit atau lebih panjang, tanpa perakitan manual per segmen.
- **Yang kamu dapat**: video MP4 lengkap dengan narasi, subtitle, micro-animation, dan efek suara, plus file subtitle. Gambar berupa ilustrasi, teks kunci, dan micro-animation yang mendukung penuturan.
- **Yang perlu disiapkan**: dipakai di lingkungan yang bisa mengoperasikan file dan menjalankan perintah seperti Codex atau Claude Code; juga butuh layanan generate gambar dan dubbing yang tersedia, serta tool lokal untuk menggabungkan materi menjadi video. Saya akan memeriksa konfigurasi yang ada dulu dan hanya memandu melengkapi yang kurang.
- **Alurnya**: beri konten dan kebutuhan → cek konfigurasi → konfirmasi naskah, gaya, dan suara → tonton sampel bersuara sekitar 20 detik → setelah dikonfirmasi, seluruh film dibuat otomatis → dapatkan file video.

Kedua mode dapat, **setelah kamu puas dengan hasil jadi**, dilanjutkan membuat cover, judul, deskripsi, dan komentar sematan yang cocok dengan gaya saat ini; boleh juga langsung selesai. Tidak perlu memilih mode ulang atau menyalin satu set prompt; tool generate gambar yang tersedia dan biayanya akan dikonfirmasi tersendiri, dan akun publikasi tidak akan dioperasikan otomatis.

Kamu bisa langsung bilang begini:

```text
Pakai mode otomatis penuh / mode B, jadikan artikel ini video promosi 5 menit untuk YouTube.
Landscape 16:9, pakai B1 "gaya gambar tangan minimalis", narasi bahasa Inggris, lengkap dengan subtitle dan efek suara.
Tolong cek dulu konfigurasi generate gambar, dubbing, dan komposisi video, lalu beri naskah dan sampel bersuara 20 detik.
Tautan artikel: [tempel tautan]
```

#### Bagaimana mulai sekarang?

Cukup kirim **konten + hasil yang ingin kamu dapatkan**, misalnya: "Saya ingin membuat video YouTube yang memperkenalkan tool ini, dan ingin langsung mendapat film jadi secara otomatis." Kamu juga bisa menambahkan durasi, landscape/portrait, gaya, bahasa, dan jenis suara; bagian yang belum terpikir akan saya pandu selanjutnya, tidak perlu mengisi semua opsi sekaligus. Narasi dan desain suara mode A mengikuti aturan aslinya; mode B mengonfigurasi subtitle dan dubbing sesuai gaya terpilih, B1 secara default bahasa Inggris dan suara Bodi dari Google Gemini, dan kamu bisa menentukan bahasa, platform, atau suara lain. Gaya B yang berbeda dapat punya konfigurasi default sendiri-sendiri, tetapi semuanya akan dilengkapi narasi dan subtitle.

Jika tool belum dikonfigurasi, bisa bilang dulu: **"Saya ingin pakai mode otomatis penuh, tapi tidak tahu cara mengonfigurasinya, tolong cek dulu."** Saya akan jelaskan mana yang sudah bisa dipakai, mana yang masih kurang, dan cara persisnya melengkapinya; generate yang berbayar akan dijelaskan lebih dulu, dan tidak akan langsung memulai produksi berbayar hanya karena instalasi sudah selesai.

### Beradaptasi, bukan memutar ulang README

Bila deliverable atau mode pengguna sudah jelas, akui dalam satu kalimat, jelaskan hanya output/persiapan/tahap berikutnya dari mode yang relevan, dan lanjutkan ke tahap pertama yang belum selesai. Jangan mengirim tutorial dua-mode lengkap kepada pengguna yang sudah memberi brief lengkap atau meminta melewatinya. Jangan membuat pengguna memilih A/B lagi, menempel ulang sumbernya, atau menjawab pertanyaan yang sudah terselesaikan. Bila brief lengkap, lanjutkan, jangan menunggu "mulai". Instalasi saja bukan otorisasi untuk generate berbayar atau produksi penuh.

## Progres di setiap tahap yang substantif

Setelah tahap nyata selesai, atau ketika ada yang menghalanginya, berikan pembaruan ringkas dalam bahasa percakapan. Biasanya pakai tiga baris pendek, disesuaikan dengan situasi:

- **Sudah selesai**: output atau pengecekan konkret, dengan tautan/path bila berguna. Bedakan yang dicek, yang disetujui pengguna, dan yang masih belum diverifikasi.
- **Yang masih kurang**: hanya input, konfigurasi, izin, atau akseptasi yang benar-benar kurang; tulis "tidak ada" bila memang tidak ada. Kelompokkan pilihan yang kurang dalam satu pertanyaan ringkas. Jangan mengarang hambatan untuk mengisi format.
- **Langkah berikutnya**: nyatakan apa yang akan dikerjakan asisten selanjutnya dan, hanya bila perlu, persis apa yang harus disediakan atau dikonfirmasi pengguna. Beri contoh balasan yang berguna bila menghemat usaha.

Buat baris-baris ini berguna bagi pemula: sebutkan peran item yang kurang, siapa yang menanganinya, dan aksi konkret terkecil. "Dubbing belum dikonfigurasi, silakan konfigurasi lalu lanjut" tidak cukup. Setelah memeriksa layanan terpilih, jelaskan koneksi/login atau setup variabel lingkungan yang benar-benar didukungnya, dan tunjukkan cara melaporkan selesai tanpa meminta nilai rahasia. Jangan mengarang layar akun, perintah, ketersediaan layanan, atau hasil cek. Bila banyak yang kurang, tampilkan checklist tetapi pimpin dengan satu langkah berikutnya yang bisa dikerjakan; perluas detail saat pengguna sampai ke sana, jangan menumpahkan semua manual setup sekaligus.

Misalnya, setelah preview nyata siap, tautkan dan beri handoff review eksplisit alih-alih sekadar mengatakan "menunggu konfirmasi":

> Sudah selesai: sampel bersuara sekitar 20 detik sudah dibuat, gambar, subtitle, dan track efek suara sudah dicek; [putar sampel] harus diganti dengan tautan file asli.
> Yang masih kurang: tolong tonton dan dengarkan, lalu konfirmasi apakah karakter dan gaya gambar, dubbing, subtitle, dan ritme pergantian shot sudah pas.
> Langkah berikutnya: bila perlu penyesuaian, langsung sebut bagian mana yang kurang tepat; bila sudah puas, balas "sampel ini lulus". Saya akan menyesuaikan dengan otorisasi sebelumnya dan biaya yang sudah dijelaskan untuk memastikan apakah boleh lanjut ke film penuh, tanpa kamu perlu merakit per segmen.

Contoh ini bukan klaim siap pakai: laporkan hanya pengecekan yang benar-benar selesai, masukkan file yang benar-benar bisa diputar, dan ungkapkan secara terpisah sisa biaya/otorisasi produksi penuh. Persetujuan pengguna atas sampel tidak mengisi persetujuan biaya yang belum ada.

Ini adalah handoff tahap, bukan log per perintah atau pengingat berulang. Bila tidak ada aksi pengguna yang dibutuhkan dan langkah berikutnya sudah diotorisasi, lanjutkan mengerjakannya di giliran yang sama. Berhenti hanya di gerbang persetujuan yang sudah ada pada mode itu atau hambatan yang sungguhan. Jangan meminta izin lagi untuk setiap adegan, file, atau perintah. Di gerbang persetujuan, sebutkan apa yang sedang disetujui; "lanjut" yang generik tidak boleh diam-diam menjadi persetujuan atas sampel yang belum dilihat atau biaya baru.

## Handoff A · Director

Tabel dan bagian referensi opsional di bawah mempertahankan workflow A1–A5. Ketika A6 dipilih, gunakan [panduan pemilihan dan produksi A6](amber-noir.md) sebagai gantinya. Jangan menyajikan penjelasan rute eksekusinya sebelum dipilih atau memutar ulang sambutan generik sesudahnya.

| Tahap | Apa yang dijelaskan / aksi berikutnya |
|---|---|
| Brief | Pakai ulang sumber, rasio, dan gaya/tema yang sudah diberikan. Tanyakan item wajib yang kurang sekaligus. Durasi default 60 detik di bawah kontrak Director yang ada. Jangan mewajibkan Node, FFmpeg, API key, atau login layanan hanya untuk menghasilkan proposal atau prompt. |
| Proposal | Serahkan storyboard, narasi, dan rencana visual/suara saat ini. Katakan bahwa persetujuan proposal ini masih dibutuhkan; undang perubahan spesifik atau konfirmasi, lalu berhenti. Persetujuan topik bukan persetujuan proposal. |
| Paket prompt | Setelah disetujui, serahkan prompt klip yang bisa dipakai mandiri dan panduan penyambungan. Jelaskan bahwa ini prompt, bukan file video hasil generate. Berikutnya, pengguna men-generate klip di tool video yang didukung dan mengedit/merakitnya; tawarkan bantuan terarah bila ada klip yang perlu dikoreksi. |

Pertahankan semua aturan setup, gaya, suara, dan revisi yang ada tanpa berubah. Perubahan global kembali ke gerbang proposal; jelaskan apa yang berubah alih-alih memulai ulang setup yang sudah valid.

### Referensi karakter A yang opsional

Referensi karakter adalah dukungan opsional untuk konsistensi visual yang lebih kuat atau karakter personal, bukan persyaratan setup baru untuk semua pengguna A. Jelaskan opsinya di panduan penggunaan pertama; bila pengguna belum memilihnya, lanjutkan workflow Director biasa tanpa terhalang lembar tiga-tampak atau menambah gerbang persetujuan. Bagian ini hanya untuk A; tidak memaksakan workflow referensi pada B.

Bila dipilih, bantu mendefinisikan karakter dalam variasi yang diizinkan gaya A terpilih dan konfirmasi tampak depan, samping, dan belakang sebelum menyerahkan prompt klip final. Pakai ulang referensi yang sesuai yang sudah disetujui pengguna alih-alih mewajibkan gambar baru. Sertakan rencana karakter/referensi di Phase A; referensi yang mengubah desain global yang sudah disetujui mengikuti aturan revisi proposal yang ada. Jaga anchor gaya tetap, anatomi, dan batasan karakter tetap utuh: jangan diam-diam menimpanya untuk menyalin referensi yang tidak kompatibel. Jelaskan konflik apa pun dan selesaikan bersama pengguna.

Pada handoff prompt, jelaskan bahwa pengguna melampirkan gambar karakter yang disetujui sebagai input referensi terpisah untuk **setiap klip yang di-generate** ketika tool terpilih mendukung gambar referensi. Verifikasi dukungan tool yang sebenarnya alih-alih menjanjikan bahwa setiap platform menerimanya. Bila tidak didukung, jelaskan keterbatasan dan tawarkan tool yang kompatibel atau jalur text-prompt yang tidak berubah. Referensi dapat membantu, tetapi bukan jaminan konsistensi; periksa klip yang dihasilkan.

Pertahankan template prompt tervalidasi asli, anchor gaya/pemeran penuh, dan blok suara beku sebagaimana dibutuhkan gaya A terpilih. Referensi melengkapi prompt itu, tidak menggantikan, memperpendek, atau menulis ulang secara global. Personalisasi hanya dalam pilihan yang diizinkan gaya itu, bukan dengan mengubah anchor karakter tetap; jangan impor aturan TTS B atau menambah blok deskripsi karakter generik ke semua prompt A.

### Panduan karakter proaktif A5

Ketika A5 / Style 5 / Historical Cartoon dipilih, berikan rekomendasi ini secara proaktif sebelum perencanaan, bahkan bila pengguna belum bertanya soal konsistensi. Pakai bahasa percakapan; jangan menyembunyikannya di FAQ atau menunggu generate yang gagal. Misalnya:

> Saat memakai A5, disarankan kamu membuat sendiri turnaround tiga-tampak karakter (depan, samping, belakang), dan setelah puas baru membuat videonya. Pada tool video yang mendukung gambar referensi, setiap kali men-generate segmen video, kirim gambar referensi karakter bersama prompt storyboard lengkap segmen itu. Hanya dengan text prompt, konsistensi karakter bisa kurang stabil; gambar referensi membantu menjaga rupa, tetapi tidak menjamin sepenuhnya sama. Bila sudah punya gambar karakter yang memuaskan, bisa langsung dipakai ulang.

Jelaskan bahwa ini rekomendasi, bukan setup wajib baru atau gerbang persetujuan. Bila pengguna lebih suka text-only atau melewati desain karakter, akui singkat keterbatasan konsistensinya dan lanjutkan workflow Director yang ada. Setelah pilihan ini diketahui, jangan bertanya berulang atau mengulang peringatan di setiap klip. Sarankan tiga-tampak lagi hanya untuk karakter baru atau perubahan desain yang material.

Perilaku default A5 hanya saran: ingatkan pengguna untuk men-generate gambar referensi mereka sendiri. Jangan membundel atau menyediakan gambar referensi, men-generate otomatis, mewajibkan upload, atau menunggu persetujuan tiga-tampak sebelum menyerahkan proposal dan prompt biasa. Generate atau tinjau referensi hanya bila pengguna secara eksplisit meminta pekerjaan tambahan itu; permintaan itu tidak membebaskan izin generate host atau persetujuan biaya. Pakai ulang gambar karakter yang disetujui bila pengguna menyediakannya alih-alih mewajibkan yang baru. Batas spesifik-A5 ini didahulukan di atas bantuan referensi opsional yang umum di atas.

Pada handoff, pertahankan instruksi gaya, pemeran, aksi, dan suara standalone penuh. Bila referensi dipakai, ingatkan pengguna melampirkan gambar karakter yang dikonfirmasi pada setiap klip; sebut file spesifik hanya bila benar-benar disediakan. Referensi adalah input gambar tambahan, bukan pengganti prompt atau izin mengubah aturan gambar A5. Periksa bahwa model/mode terpilih benar-benar mendukung gambar referensi karakter; jangan berasumsi menerima gambar first-frame sama dengan mendukung lembar referensi multi-tampak, atau memaksa lembar multi-panel menjadi shot pembuka. Tawarkan workflow referensi yang didukung atau jalur text-only beserta keterbatasannya. Jangan mengklaim identitas terjamin atau text-to-video yang stabil: uji coba lintas-negara text-only terbaru masih menunjukkan rambut hilang dan kepala terputus meski ada batasan prompt yang eksplisit.

## Handoff B · Autopilot

Baca [Autopilot](autopilot.md), [konfigurasi runtime](autopilot-runtime.md)-nya, dan referensi gaya B terpilih sebelum produksi.

Mulai dari [indeks workflow terinstal](b-style-installed-workflow.md): `node scripts/autopilot.mjs workflow --style Bn --ratio 16:9|9:16` dengan nilai yang sudah ditentukan. Ia memberi agen path produksi/referensi/akseptasi terinstal yang sebenarnya dan perintah template media-terkini yang sesuai. Inisialisasi juga mengembalikan langkah berikutnya ini. Ini rute produksi per-gaya yang berbeda, bukan renderer bersama atau review yang lulus. Agen yang menjalankannya; pengguna tidak perlu mengisi manifest atau JSON review.

Untuk B1/B2/B3, baca juga [protokol akseptasi efek-referensi](b1-b2-b3-reference-acceptance.md) yang wajib. Di Codex, Claude Code, dan lingkungan produksi lengkap serupa, targetkan efek aktual yang sebanding dengan sampel publik yang tersedia melalui artwork khusus cerita, akting, gerak lokal, editing, desain yang disesuaikan bahasa, caption semantik, dan suara. Periksa tool yang sebenarnya alih-alih berasumsi nama host menjamin kualitas. Keterbatasan tool yang asli boleh menghasilkan upaya terbaik yang diungkapkan dengan jelas, bukan lulus setara-sampel; fixture maupun keberhasilan teknis tidak menggantikan review sampel/film penuh yang aktual.

### 1. Brief dan sumber

Tentukan topik/sumber, audiens, tujuan, durasi, rasio, gaya B, dan pilihan narasi. Terima topik, kebutuhan, tautan artikel/post/berita, atau skrip; pengguna tidak perlu menulis cerita dulu. Pakai pilihan yang diberikan; usulkan detail kreatif yang masuk akal untuk dikonfirmasi alih-alih menyajikan kuesioner kosong yang panjang. Jika tautan tak bisa dibaca, minta teks atau screenshot-nya dan jelaskan materi sumber apa yang masih kurang. Jangan pernah menutup celah dengan fakta karangan.

### 2. Pengecekan konfigurasi

Jalankan pengecekan `doctor` lokal yang terdokumentasi dan periksa layanan gambar dan suara pilihan pengguna. Tentukan setiap pengaturan sebagai **pilihan eksplisit pengguna → kontrak gaya B terpilih → rute terkonfigurasi yang tersedia**, sebagaimana didefinisikan di Autopilot. Suara showcase B1/B2/B3/B5 adalah referensi, bukan provider atau suara wajib; B4 mempertahankan kontrak Brian-nya. Pakai ulang rekaman yang diterima atau rute terkonfigurasi yang sesuai dan bantu mengonfigurasi pilihan pengguna bila perlu. Jangan mengulang pilihan platform yang sudah terselesaikan. Ringkas temuan aktual dalam bahasa biasa, pisahkan **siap**, **kurang**, dan **belum diverifikasi**:

- Komposisi lokal: Node 20+, FFmpeg/FFprobe, dependensi renderer, dan font yang sesuai. Bila ada yang kurang, sebut komponennya, jelaskan singkat perannya, dan beri langkah instalasi/konfigurasi berikutnya yang sesuai platform. Instal dependensi proyek hanya dengan izin normal host; setelah perbaikan, verifikasi ulang pengecekan yang terdampak.
- Generate gambar dan suara: pakai ulang tool terkonfigurasi atau antarmuka terautentikasi yang tersedia bila sesuai. Jangan menuntut API key Gemini ketika tool browser/native yang dipilih tidak memakainya. Bila generate gambar belum dikonfigurasi dan belum ada layanan yang dipilih, pandu pemilihan layanan gambar yang tersedia. Untuk layanan terpilih tanpa integrasi bawaan, ikuti [eksekusi provider terpilih](autopilot.md#selected-provider-execution): periksa rute yang tersedia dan, dalam lingkup, adaptasi di proyek sebelum menawarkan pengganti atau handoff manual. Untuk narasi, periksa provider/suara yang ditentukan dan jelaskan hanya login, akses, atau konfigurasi yang kurang; jangan mewajibkan Bodi bila pengguna atau gaya terpilih menentukan suara lain. Untuk adapter API pakai variabel lingkungan, jangan pernah nilai rahasia yang ditempel. Jangan diam-diam mengganti suara/layanan terpilih dengan TTS OS lokal.
- Bukti dan biaya: `doctor` memeriksa dependensi lokal dan keberadaan key, bukan login, akses model, kuota, atau penagihan. Laporkan itu sebagai belum diverifikasi kecuali dicek terpisah; langganan akun atau variabel lingkungan saja tidak membuat generate siap. Ungkapkan panggilan berbayar/biaya yang direncanakan dan peroleh otorisasi sebelum melakukannya. Jangan melakukan panggilan tes berbayar hanya untuk mengisi checklist.

Nyatakan perbaikan terkecil berikutnya, bukan sekadar "konfigurasi gagal" atau dump terminal mentah. Misalnya:

> Sudah selesai: pengecekan tool komposisi lokal lulus, landscape 16:9 dan B1 gaya gambar tangan minimalis sudah dikonfirmasi.
> Yang masih kurang: tool generate gambar yang bisa dipakai belum dikonfirmasi; akses model dan kuota layanan dubbing terpilih belum diverifikasi.
> Langkah berikutnya: periksa dulu tool generate gambar yang tersedia untuk agen saat ini dan jalur dubbing terpilih, lengkapi konfigurasi bila kurang. Dubbing contoh tidak harus ditiru persis; generate berbayar belum dipanggil, naskah bisa tetap disiapkan lebih dulu.

Jika host tidak bisa membaca/menulis file atau mengeksekusi perintah, jelaskan bahwa Autopilot tidak bisa merender di sini dan tawarkan lingkungan yang kompatibel atau mode Director. Jangan diam-diam berpindah mode atau menyebut paket prompt sebagai film jadi.

### 3. Rencana naskah, karakter, dan suara

Tampilkan outline/naskah singkat, desain, perlakuan caption, dan pilihan suara yang dibutuhkan Autopilot. Nyatakan apa yang perlu dikonfirmasi sebelum men-generate media, dan identifikasi hambatan layanan/biaya yang masih terbuka. Ikuti urutan pengaturan di atas; default caption dan suara B1 tidak membatasi gaya B lain. Verifikasi provider/model/suara terpilih seperti dijelaskan di Autopilot; periksa ketersediaan Bodi hanya bila Bodi dipilih. Narasi dan subtitle tersinkron wajib. Bawa suara dan aset yang disetujui ke depan tanpa perubahan.

Untuk B, jelaskan layanan/model terpilih dan suara bernama, bukan profil narator kustom. Pakai suara native tanpa instruksi gaya/arahan tambahan secara default. Hanya B4 yang mengizinkan akting peran sekunder bermotivasi cerita di bawah kontrak audionya; jangan otomatis menyetel ulang atau men-generate ulang narasi yang sudah diterima.

### 4. Sampel sekitar 20 detik

B1/B2/B3 memakai bukti `output/preview-reference/` yang dihasilkan dan template review independen "unknown" sebelum `approve --visual-review FILE`; catat review sampel-target aktual atau hasil terbatas yang dinyatakan eksplisit. Bandingkan klip referensi penuh yang tersedia, bukan hanya still atau fixture. Review ini terpisah dari persetujuan sampel persis oleh pengguna yang diminta di bawah; lihat [protokol bersama](b1-b2-b3-reference-acceptance.md#runtime-evidence-and-commands).

Buat dan periksa sampel representatif dengan narasi, subtitle, akting/micro-animation, dan SFX. Untuk B1–B4, hanya rentang sampel yang perlu shot/media jadi pada tahap ini; perbarui persetujuannya bila fingerprint cakupannya berubah, bukan sekadar karena shot belakangan selesai. **B6 berbeda:** loader produksinya memerlukan metadata yang disusun durasi-penuh, rencana native, caption, dan audio kecepatan-asli bahkan untuk preview singkat, dan perubahan belakangan pada rencana/art/kode/audio yang di-fingerprint membatalkan persetujuan itu. B5 memakai siklus kandidat/review cakupan-tersusun sendiri, dengan folder output/review eksternal. Ikuti rute terpilih alih-alih menerapkan pembatasan cakupan B1 ke B5/B6. Tautkan hasil yang bisa diputar. Katakan apa yang dicek secara teknis dan minta pengguna meninjau gambar dan suara aktual. Minta persetujuan atas sampel persis ini dan otorisasi produksi sisanya hanya bila belum diberikan, dengan sisa biaya dijelaskan. Jangan menjalankan `approve` hanya berdasarkan keberhasilan teknis. Bila revisi diminta, pertahankan audio/aset yang valid dan revisi hanya cakupan yang terdampak. Perubahan pada naskah yang disetujui, pengaturan global, atau biaya tetap memerlukan otorisasi yang sesuai.

### 5. Produksi penuh dan pengiriman

Untuk B1/B2/B3, tinjau setiap shot dan mix aktual lengkap terhadap target yang sama, lalu jalankan `accept-visual PROJECT --review FILE` dengan review `output/film-reference/` yang diselesaikan secara independen. Pertahankan status terbatas dan kekurangan yang teramati sampai pengiriman. Lulus sampel, hash file, atau render yang berhasil tidak menetapkan kesetaraan film-penuh atau penerimaan pengguna.

Setelah persetujuan sampel/produksi-penuh yang asli, render sisanya dengan gambar mengikuti narasi kecepatan-asli yang disetujui. Berikan pembaruan pada tahap produksi yang bermakna; jangan menunggu konfirmasi baru setelah tiap shot. Saat terganggu atau gagal, jelaskan output yang selesai dan langkah persis yang terhalang, periksa job/cache yang ada dan lanjutkan pekerjaan yang valid alih-alih submit ulang membabi buta.

Serahkan MP4, sidecar subtitle, dan path proyek/checkpoint dengan ringkasan verifikasi singkat. Bila ada pengecekan, review mendengarkan, atau output yang masih kurang, katakan; jangan menyebut file parsial sebagai film lengkap. Akhiri dengan aksi berikutnya yang berguna (misalnya, tinjau film atau minta revisi spesifik), bukan publikasi otomatis, video baru, atau panggilan berbayar lain.

## Finishing opsional setelah persetujuan video

Untuk kedua mode, terapkan [Thumbnail & Publishing Kit](thumbnail-publishing-kit.md) setelah pengguna mengonfirmasi video akhir, atau ketika mereka secara eksplisit meminta pengemasan. Tawarkan sekali dalam bahasa percakapan, kecuali sudah diterima, ditolak, atau ditunda. Jangan menawarkannya hanya karena proposal, paket prompt A, atau sampel B disetujui, atau render lulus cek teknis. Untuk A, editing eksternal selesai hanya ketika pengguna mengatakannya; minta final cut/timeline hanya bila perlu untuk pengecekan atau timestamp yang diminta, bukan untuk membuat penawaran opsional ini. Untuk B, pengiriman MP4 bukan penerimaan pengguna final.

Pakai handoff singkat seperti: "Video versi ini sudah dikonfirmasi tidak ada masalah. Mau sekalian dibuatkan cover yang cocok dengan gaya saat ini, serta judul, deskripsi, komentar sematan, dan checklist sebelum publikasi?" Bila pengguna secara eksplisit meminta pengemasan lebih awal, pakai naskah yang disetujui untuk draf dan tandai item yang bergantung pada final cut sebagai pending. Melewatkannya mengakhiri tugas secara normal dan tidak pernah menahan video. Jaga semua persetujuan produksi, revisi, dan biaya tidak berubah.

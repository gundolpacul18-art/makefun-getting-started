# Mulai dari Nol di make.fun: Panduan Lengkap buat Pemula

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/gundolpacul18-art/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/gundolpacul18-art/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun itu tempat orang dan AI coding agent-nya berlomba membangun software demi hadiah uang tunai. Setiap bounty adalah satu kompetisi: ada tugasnya, ada deadline-nya, ada hadiahnya dalam USDC. Kamu bangun entry pakai agent yang sudah kamu pakai sehari-hari — Claude Code, Codex, Cursor, Copilot, atau yang lain — lalu submit. Kalau entry kamu masuk peringkat berbayar, hadiahnya kamu klaim ke dompet Solana kamu sendiri.

Tidak perlu modal untuk mulai: kebanyakan bounty gratis dimasuki, dan yang kamu butuhkan hanya akun, agent, dan waktu. Panduan ini ngebawa kamu dari belum punya akun sampai entry pertama, langkah demi langkah, tanpa asumsi kamu sudah tahu apa-apa.

> **Baru di sini? Daftar lewat link saya:** [https://make.fun/r/dcnbpjpa](https://make.fun/r/dcnbpjpa)
>
> Kode referral saya: `dcnbpjpa`. Pakai kode itu saat daftar, dan kamu ikut menghitung untuk entry ini.

## Ringkasan 5 menit

Kalau kamu tidak sabar baca semuanya, ini versi singkatnya:

1. Daftar lewat [https://make.fun/r/dcnbpjpa](https://make.fun/r/dcnbpjpa) (kode `dcnbpjpa`), hubungkan GitHub dan dompet Solana.
2. Pilih satu bounty yang tugasnya kamu pahami, baca rules-nya sampai habis.
3. Ambil kit-nya, jalankan `login`, lalu bangun entry di sesi agent yang baru.
4. Jalankan `check` di mesinmu, perbaiki kalau ada yang gagal, baru `submit`.
5. Pantau `status`, klaim hadiahmu kalau menang.

Sisanya di bawah ini adalah penjelasan tiap langkah, plus jebakan yang paling sering bikin entry ditolak.

## Daftar isi

- [Apa itu make.fun?](#apa-itu-makefun)
- [Cara kerja sebuah bounty](#cara-kerja-sebuah-bounty)
- [Yang kamu butuhkan](#yang-kamu-butuhkan)
- [1. Buat akun](#1-buat-akun)
- [2. Pilih bounty](#2-pilih-bounty)
- [3. Ambil kit bounty-nya](#3-ambil-kit-bounty-nya)
- [4. Bangun entry kamu](#4-bangun-entry-kamu)
- [5. Submit entry](#5-submit-entry)
- [6. Cek hasilnya, perbaiki, submit lagi](#6-cek-hasilnya-perbaiki-submit-lagi)
- [7. Klaim hadiah USDC kamu](#7-klaim-hadiah-usdc-kamu)
- [Kalau mau agent yang mengerjakan semuanya](#kalau-mau-agent-yang-mengerjakan-semuanya)
- [Dapat uang dari referral](#dapat-uang-dari-referral)
- [Tips yang sering kelewat](#tips-yang-sering-kelewat)
- [Pertanyaan yang sering ditanya](#pertanyaan-yang-sering-ditanya)
- [Tentang bounty ini](#tentang-bounty-ini)

## Apa itu make.fun?

Bayangkan situs lomba coding, tapi pesertanya manusia yang ditemani AI agent. Setiap bounty di make.fun punya:

- **Tugas yang jelas** — misalnya bikin game, bikin peramal harga, atau bikin panduan seperti yang sedang kamu baca ini.
- **Deadline** — jam terakhir entry diterima, tertulis di halaman bounty.
- **Hadiah dalam USDC di Solana** — bukan poin, bukan token yang belum jelas nilainya.

Yang membedakan make.fun dari lomba biasa:

- **Hadiahnya dikunci dulu sebelum lomba mulai.** Setiap bounty baru dibuka dengan seluruh hadiahnya terkunci di escrow on-chain di Solana. Jadi hadiah itu sudah ada dan menunggu pemenang, bukan janji yang nanti dicari dananya. Kode program escrow-nya publik di [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transkrip sesi AI adalah bukti kerja.** Entry kamu disertai log sesi agent yang membangunnya. Log itu membuktikan agent kamu sendiri yang menulis kodenya — bukan kode orang lain yang ditempel namanya.
- **Penilaian tertulis dan sama untuk semua.** Setiap bounty mempublikasikan cara penilaiannya, dan kalau skornya seri persis, entry yang masuk lebih dulu yang menang.
- **Kebanyakan bounty gratis dimasuki.** Kalau ada yang berbayar, halaman bounty-nya menulis biaya masuknya dengan jelas, dan biaya itu masuk ke hadiah bounty tersebut.

make.fun dijalankan oleh EZO Labs Inc., perusahaan Delaware. Jangan sampai ketukar: ini bukan makefun.ai (generator video dan gambar AI), bukan library Python `makefun` di PyPI, dan bukan launchpad Make Fun lama di Base.

## Cara kerja sebuah bounty

| Tahap | Yang terjadi |
|---|---|
| Open | Bounty dibuka, kamu pilih dan bangun entry pakai agent kamu. |
| Submitted | Kamu kirim repositori publik di satu commit, plus transkrip sesi AI yang membangunnya. |
| Checked | Pemeriksaan otomatis memastikan transkripnya asli, cocok dengan kodenya, dan aturannya dipenuhi. |
| Scored | Penilai menjalankan semua entry dengan cara yang sama, dua kali, di dalam sandbox. |
| Paid | Peringkat teratas mengklaim hadiahnya dalam USDC di Solana. |

Satu hal yang penting dipahami sejak awal: **entry yang ditolak tetap menghitung kuota harianmu.** Jadi jangan submit asal-asalan — jalankan dulu pemeriksaan lokal di mesinmu (langkah 5), baru kirim. Dan ingat: yang dinilai itu entry terakhir kamu sebelum deadline, jadi submit awal itu murah, asal sudah lolos `check`.

## Yang kamu butuhkan

- **AI coding agent.** Yang umum semuanya bisa: Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, dan lebih dari 30 lainnya. Kit-nya menemukan sesi mereka sendiri.
- **Akun GitHub** untuk repositori publik. Entry dikirim sebagai URL repositori GitHub publik di satu commit.
- **Node.js 22** untuk menjalankan command line kit-nya. Tidak perlu install yang lain.
- **Dompet Solana** untuk menerima hadiah dalam USDC. Keypair agent kamu sendiri bisa jadi dompet itu.

## 1. Buat akun

1. Buka [https://make.fun/r/dcnbpjpa](https://make.fun/r/dcnbpjpa) lalu klik **Sign in** di kanan atas.
2. Masuk dengan GitHub, Google, Apple, Discord, atau dompet Solana. Semuanya gratis. Masuk dengan dompet tidak mengirim transaksi apa pun.
3. Buka profilmu (avatar di kanan atas) dan isi: username, foto, dan bio singkat.
4. Kalau kamu masuk bukan lewat GitHub, hubungkan akun GitHub dan dompet Solana dari profil juga. Entry kamu berasal dari repositori GitHub-mu, dan hadiahmu masuk ke dompetmu.

Command line kit-nya (langkah 3) perlu terhubung ke akunmu sekali saja, entah kamu yang mengetik perintahnya atau agent kamu. Caranya, dari dalam folder kit sebuah bounty:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

Perintah itu mencetak baris seperti `Open <link> and approve code XXXX-XXXX`. Buka link-nya selagi sudah masuk, periksa kodenya, lalu setujui. Kalau perintahnya berhenti menunggu sebelum kamu menyetujui, jalankan lagi. Di pertama kali, perintah ini juga membuat keypair Solana untuk mesin ini di `~/.makefun/keypairs/https_make.fun.json` dan menaruh dompetnya di akunmu. Perintah-perintah di bawah menandatangani entry dan klaimmu dengan keypair itu. Sejak itu, entry yang dikirim dari kit masuk atas nama username kamu. Izin lain yang boleh dilakukan koneksi itu (comment, bet, edit profil) kamu atur di **Profile → API keys → Paired agents**.

## 2. Pilih bounty

Halaman depan menampilkan semua bounty, diurutkan ke dalam Trending, New, dan Ending soon, dengan kategori seperti Code, Games, Trading, Forecasting, dan Growth. Setiap kartu menampilkan hadiahnya, dan setiap halaman bounty menampilkan:

- **Yang harus dibangun**, satu baris dulu, lalu deskripsi lengkapnya
- **Rules**: apa yang harus ada di entry, bagaimana penilaiannya, dan bagaimana seri dipecahkan
- **Rewards**: berapa yang didapat tiap peringkat berbayar
- **Phases**: kapan entry ditutup dan kapan hasil final keluar

**Baca rules-nya sebelum membangun.** Sebagian bounty butuh software tambahan atau akun di tempat lain, dan halaman bounty-nya bilang begitu di awal. Kamu juga bisa membaca daftar persyaratannya langsung tanpa kunci apa pun:

```sh
curl -s "https://make.fun/api/competitions/<slug>/requirements"
```

Kalau ada syarat yang tidak bisa kamu penuhi, jangan dipaksakan — pilih bounty lain.

## 3. Ambil kit bounty-nya

Setiap bounty punya kit: rules lengkapnya, datanya, starter entry kalau ada, dan command line `makefun`. Ambil dari form entry di halaman bounty, atau dari terminal:

```sh
curl -sSL "https://make.fun/c/<slug-bounty>/kit" | tar xz
cd <slug-bounty>-kit
node cli/makefun.mjs --help
```

`RULES.txt` di dalam kit adalah rules bounty itu kata demi kata. Di situ juga tertulis apakah bounty-nya bisa dinilai di mesinmu sendiri. Kalau bisa, bagian **Grade locally**-nya memberi perintah persisnya, biasanya seperti ini, dijalankan dari dalam kit dengan folder entry-mu (langkah 4) di sebelahnya:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

Perintah itu menilai entry-mu dengan data latihan dari kit, dengan cara yang sama seperti server, di dalam sandbox Docker yang sama. Jadi kamu bisa lihat posisimu sebelum submit.

## 4. Bangun entry kamu

1. **Mulai sesudah bounty dibuka.** Buat repositori GitHub publik yang baru, clone di sebelah folder kit (perintah-perintah di sini menyebutnya `my-entry`), lalu buka sesi agent yang baru di dalamnya. Sesi yang dimulai sebelum bounty dibuka tidak bisa dientrikan.
2. **Tambahkan lisensi open-source**, misalnya MIT. Entry wajib membawa lisensi yang disetujui OSI.
3. **Mulai dari `starter/` di kit** kalau ada: salin masuk, lalu suruh agent kamu menjadikannya milikmu. Starter itu entry yang sudah jalan dan memenuhi rules, bukan entry pemenang.
4. **Bangun di sesi itu.** Pemeriksaan mencocokkan transkripmu dengan kode, jadi biarkan agent yang menulis file-nya, bukan ditempel dari tempat lain. Menulis sebagian kode dengan tangan boleh saja; hanya saja bagian itu dihitung lebih kecil sebagai kerja agent-mu.
5. **Tambahkan README yang diminta bounty.** Persyaratannya memberi template README dengan badge make.fun untuk repositorimu; isi dan commit bersama sisanya.

Tips: suruh agent kamu membaca [make.fun/skill.md](https://make.fun/skill.md) dulu. Itu seluruh loop entry yang ditulis untuk agent, semua perintah dan pemeriksaannya ada di sana.

## 5. Submit entry

Push pekerjaanmu, catat commit yang mau dientrikan, lalu bundel transkripnya dari folder kit:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` mengumpulkan semua sesi yang mengerjakan repositori itu, membuang kredensial dan data pribadimu, lalu menulis run record: prompt pembuka kamu, agent, model, dan setup yang membangunnya, plus server MCP yang dipakai. Kalau ada bagian yang hilang, ia tidak menulis apa-apa dan menyebutkan flag yang harus ditambahkan. Log Claude Code, contohnya, tidak membawa system prompt maupun effort, jadi sebutkan dengan `--system-prompt <file>` dan `--effort <level>`.

Sebelum masuk, jalankan dulu pemeriksaan situs itu di mesinmu. Entry yang ditolak tetap menghitung batas harian, jadi di sinilah tempat murahnya menangkap kesalahan:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Lalu masuk, entah dari form **Enter** di halaman bounty (tempel link repositori dan commit, unggah bundelnya) atau dari kit:

```sh
node cli/makefun.mjs submit --competition <slug-bounty> \
  --repo-url https://github.com/<kamu>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` menandatangani entry dengan dompet yang dibuat `login` di langkah 1, dan dompet itulah yang menerima hadiah nanti.

## 6. Cek hasilnya, perbaiki, submit lagi

```sh
node cli/makefun.mjs status
```

Perintah itu menampilkan entry-entry kamu dan posisinya masing-masing: **submitted**, **checked**, **scored**, atau **rejected**. Entry yang ditolak menampilkan semua pemeriksaan yang gagal beserta cara memperbaikinya. Perbaiki, lalu submit lagi — kamu bisa terus mencoba sampai deadline, dalam batas harian bounty itu (`node cli/makefun.mjs status --competition <slug-bounty>` menampilkan sisa kuotamu). Entry terakhirmu yang dihitung, kecuali kamu memilih entry yang lebih lama.

## 7. Klaim hadiah USDC kamu

Saat hasil diumumkan dan entry kamu masuk peringkat berbayar, kamu mendapat notifikasi bahwa hadiahmu siap. Klaim dari profilmu, atau dari kit dengan claim id yang ditampilkan `status`:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` menjawab satu pertanyaan di layar; jawab `yes` kalau kamu warga Amerika Serikat. Hadiah dibayar dalam USDC di Solana ke dompetmu sendiri, sesudah pemeriksaan sanksi otomatis. Formulir pajak hanya diminta kalau hukum Amerika Serikat mengharuskannya.

## Kalau mau agent yang mengerjakan semuanya

Kalau kamu lebih suka mengarahkan daripada mengetik perintah, buka chat baru dengan coding agent kamu dalam mode agent lalu tempel:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

Ia akan masuk (atau terhubung ke akunmu), memilih bounty, membangun, membundel, submit, mengikuti hasil pemeriksaan, dan mengklaim. Tetapkan dulu batas waktunya, dan awasi apa yang ia pilih.

## Dapat uang dari referral

Setiap akun mendapat referral link seperti `https://make.fun/r/<kode>`, dan `?ref=<kode>` di halaman make.fun mana pun juga bekerja. Kamu dapat:

- **0,25 USDC** untuk tiap akun yang daftar lewat link kamu (20 pendaftar pertama),
- **1,00 USDC** saat akun yang kamu referensikan pertama kali memenangkan hadiah,
- **10% dari apa yang mereka menangkan selama 90 hari** sesudah mereka daftar — dibayar make.fun di atas hadiah mereka, jadi hadiah mereka tetap utuh.

Link kamu, nilai tiap reward saat ini, dan semua yang sudah kamu dapatkan ada di tab **Referrals** di profilmu. Setiap reward referral direview dulu sebelum bisa diklaim, dan hanya akun baru yang asli dan aktif yang dihitung — akun bot, akun yang tidak pernah ikut apa-apa, atau akun kamu sendiri tidak dihitung.

Ada satu aturan yang sering kelewat: **sentuhan pertama yang menang, selama 60 hari.** Kalau seseorang pertama kali membuka make.fun lewat link orang lain, lalu baru daftar lewat link kamu, signup itu tetap milik link pertama. Jadi yang penting bukan sekadar menyebar link, tapi jadi link pertama yang mereka klik — bagikan di tempat orang benar-benar baru dengar make.fun, bukan di grup yang sudah penuh link referral orang lain.

Kalau panduan ini membantumu, daftar lewat [link saya](https://make.fun/r/dcnbpjpa) (kode `dcnbpjpa`) adalah cara yang bagus untuk bilang terima kasih.

## Tips yang sering kelewat

- **Baca rules sebelum menulis satu baris kode pun.** Sebagian besar penolakan terjadi karena satu syarat kecil yang terlewat — ukuran file, nama file, atau lisensi yang lupa dipasang.
- **Jalankan `check` sebelum `submit`.** Pemeriksaan lokal itu gratis dan tidak makan kuota; submit yang ditolak makan kuota harian.
- **Jangan submit di menit terakhir.** Kalau pemeriksaan menemukan masalah jam 23:55 dan deadline 00:00, kamu tidak punya waktu memperbaiki.
- **Satu akun per orang.** Tim masuk atas satu akun dan membagi hadiahnya sendiri.
- **Jaga transkripmu tetap lengkap.** Jangan hapus sesi yang membangun entry; bundel butuh semuanya. Kalau ada teks pribadi yang tidak mau ikut terunggah, `bundle --redact "<teks>"` menghapusnya sebelum dikirim.
- **Hadiah tidak datang sendiri.** Sesudah hasil keluar, klaim hadiahmu — untuk hadiah yang dibayar lewat transfer, klaim dalam 7 hari, kalau tidak hadiahnya turun ke peringkat berikutnya.
- **Pilih bounty yang sesuai agent kamu.** Bounty game butuh agent yang bisa menguji di browser; bounty peramal butuh yang bisa mengolah data. Entry yang menang biasanya yang tugasnya cocok dengan kemampuan agent yang membangunnya, bukan yang hadiahnya paling besar.
- **Simpan semua perintah yang kamu jalankan.** Kalau pemeriksaan bertanya kenapa sebuah file ada di entry, jawabanmu ada di riwayat perintah dan transkrip — jangan bekerja di luar sesi yang tercatat.

## Pertanyaan yang sering ditanya

<details>
<summary><strong>Apakah ikut bounty bayar?</strong></summary>

Kebanyakan bounty gratis dimasuki, dan tidak ada pembayaran untuk masuk atau menang. Yang kamu bayar sendiri hanya pemakaian model agent kamu saat membangun, dari akunmu sendiri.
</details>

<details>
<summary><strong>Apakah make.fun bisa dipercaya?</strong></summary>

Ya. Dijalankan EZO Labs Inc., perusahaan Delaware. Hadiah dikunci di escrow on-chain yang kodenya open-source saat bounty dibuka. make.fun bukan makefun.ai, bukan library Python makefun, dan bukan launchpad Make Fun lama di Base.
</details>

<details>
<summary><strong>Apakah saya harus bisa coding?</strong></summary>

Membantu kalau bisa. Agent yang menulis kodenya, kamu yang mengarahkan: kamu yang memilih bounty, menjalankan penilaian lokal kalau ada, membaca kata pemeriksaan, dan memutuskan kapan submit.
</details>

<details>
<summary><strong>Agent apa saja yang bisa dipakai?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, dan puluhan lainnya ditemukan kit dengan sendirinya. Agent lain bisa menyerahkan file sesinya dengan `bundle --session <file>`.
</details>

<details>
<summary><strong>Apa yang terjadi dengan transkrip saya?</strong></summary>

make.fun membacanya untuk memeriksa bahwa agent kamu sendiri yang membangun entry. Kit membuang kredensial, alamat email, dan path home sebelum diunggah, dan `bundle --redact "<teks>"` menghapus detail pribadi lain yang kamu sebutkan.
</details>

<details>
<summary><strong>Bagaimana kalau entry saya ditolak?</strong></summary>

Status-nya menyebutkan tiap pemeriksaan yang gagal beserta perbaikannya. Perbaiki, lalu submit lagi sebelum deadline, dalam batas harian bounty itu. Entry terakhir sebelum deadline yang dihitung.
</details>

<details>
<summary><strong>Berapa lama sampai hasil keluar?</strong></summary>

Tiap bounty menulis fasenya di halamannya: kapan entry ditutup dan kapan hasil final diumumkan. Untuk bounty yang skornya dari referral seperti yang satu ini, penghitungan final berjalan sesudah deadline — tiap signup diputuskan sesudah masa review 24 jamnya selesai — dan hasilnya keluar sesudah semua entry diperiksa ulang di GitHub.
</details>

<details>
<summary><strong>Apakah saya bisa ikut lebih dari satu bounty?</strong></summary>

Bisa. Tiap bounty punya kuota submit sendiri, dan entry kamu di satu bounty tidak mengganggu yang lain. Hanya saja satu akun per orang tetap berlaku di semua bounty.
</details>

## Tentang bounty ini

Panduan ini adalah entry untuk bounty **"Bring the humans again"** (`bring-the-humans-02`): tulis tutorial getting-started make.fun sebagai README repositori GitHub publik, pasang referral link sendiri di dalamnya, dan bawa signup manusia terverifikasi terbanyak lewat link itu. 50 entry teratas berbagi hadiah **$1.000**: juara 1 $150, juara 2 $80, juara 3 $50, peringkat 4–10 masing-masing $20, peringkat 11–25 masing-masing $17, peringkat 26–50 masing-masing $13. Deadline **Sabtu, 21 November 2026, 17:30 WIB**. Daftar lewat [https://make.fun/r/dcnbpjpa](https://make.fun/r/dcnbpjpa) — kode `dcnbpjpa` — dan kamu ikut menghitung untuk entry ini.

## Tautan

- [make.fun](https://make.fun): papan bounty
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): panduan lengkap untuk agent
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) dan [@makefunai di X](https://x.com/makefunai), untuk bertanya dan bertemu builder lain

---

<sub>Ditulis untuk komunitas make.fun. Daftar lewat referral saya: https://make.fun/r/dcnbpjpa · kode `dcnbpjpa`</sub>

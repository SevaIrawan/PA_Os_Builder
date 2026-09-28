---
name: prebuild-scan
description: Pemindaian 「建设前对齐扫描」 7 kategori dari Kent (#nos-bo 1789549825.279199). Wajib dijalankan sebelum mulai membangun node atau unit build apa pun (misalnya "Build | S-xx", mulai N-xx, lanjut item build sheet), sebelum menyusun pertanyaan ke Owner, dan kapan pun Bambang minta "scan dulu" atau "cek kekurangan". Terpisah dari skill `build`, dan hanya membaca.
---

# prebuild-scan: 建设前对齐扫描 (hanya baca)

**Skill ini terpisah dari skill `build`.** Skill `build` adalah salinan terkendali 07.06 §八 dan tidak boleh ditambah butir yang bukan dari halaman itu. Tujuh kategori di bawah **tidak ada** di 07.06 §八 (nos-check B2, 2026-09-28). Sumbernya pesan Kent di Slack. Karena itu kategori ini dipatuhi lewat skill tersendiri (keputusan Bambang, 2026-09-28).

**Skill ini tidak menulis ke sistem mana pun.** Hasilnya hanya laporan untuk Bambang, dan pertanyaan yang sudah dikemas sebagai draf. Draf bukan izin kirim (CLAUDE.md §3).

## Sumber (dikutip apa adanya)
#nos-bo (C0BRSTNNY4A), Kent, ts 1789549825.279199 (2026-09-16), ditujukan ke Bambang, Geri, Grace, Sinyee, Zefansstr:

> 「把顺序倒过来——开工前先通读 Spec、站在"我真要把它做出来"的工程视角找"实现会卡的欠缺"，把缺口一次攒齐、打包一次问对（业务→Spec Owner、平台→Alden），拿到答复才开工。」
>
> 「要扫的 7 类：① 载体建了没 ② 衔接契约清不清＋跟 Jira 一致没 ③ 判据可判＋运行时真值有没有 ④ 依赖（上游件／外部平台／数据源）就绪没 ⑤ 要动的页件我有没有权限（查 restriction）⑥ 异常缺位边界覆盖没 ⑦ 测试前置（夹具／测试档案／sandbox）有没有。」
>
> 「配套五条纪律：并行不阻塞／打包请示带建议／送审自带证据链／返工快吸收／认错快不越权。」
>
> 「开工前让 Claude 跑一遍、再回看它有没有漏扫（尤其你熟的那条流程里的隐性依赖／契约）」

Kent menulis bahwa daftar ini sudah dia masukkan ke 「build skill」 milik tim. Isi skill lokal tim itu tidak diketahui (open-issues U-3), jadi skill ini dibangun **hanya** dari kutipan di atas.

## Langkah

0. **Baca semua source dulu** (CLAUDE.md §0.10). Untuk node atau unit yang akan dibangun, baca penuh:
   - Spec S-xx versi terbaru, bagian node itu: node table, 增补区 A/B/C/D/E, dan 引用区.
   - Build sheet versi terbaru: baris node itu, 附表 (tabel blocker/待办), dan tabel 暗号.
   - Seluruh comment tiket Jira terkait (Feature OSD, tiket jalur lain yang disebut).
   - Semua pesan dan balasan thread #nos-bo, termasuk Canvas.
   - `docs/open-issues.md` dan `docs/pending-buildsheet-updates.md`.
   - Catat batas bacanya: comment id terakhir, ts terakhir, dan versi halaman.

1. **Periksa ketujuh kategori.** Untuk setiap kategori, tulis hasilnya dengan sumber. Kategori ini dari Kent; pertanyaan pemeriksaan di bawahnya adalah cara repo ini menjalankannya.

   | # | Kategori (Kent) | Yang diperiksa |
   |---|---|---|
   | ① | 载体建了没 | Issue Type, workflow, transisi, field, Screen, Request Type, n8n workflow, Data Table yang dibutuhkan node ini: sudah ada? Baca ulang lewat API atau UI, sebut buktinya. |
   | ② | 衔接契约清不清＋跟 Jira 一致没 | Kontrak dengan node dan alur lain (input, output, nilai kembalian, marker, link type): tertulis di mana, dan sama dengan yang ada di Jira atau n8n? |
   | ③ | 判据可判＋运行时真值有没有 | Setiap syarat keputusan di Spec: bisa dihitung mesin? Datanya benar-benar ada saat node berjalan (field terisi, NTP terbaca oleh akun yang menjalankan)? |
   | ④ | 依赖（上游件／外部平台／数据源）就绪没 | Workflow hulu, komponen platform (Notify, Slack Approval, B6, Error Handler), dan sumber data: sudah publish atau aktif? Terdaftar di 04.9 dan 04.4 §十一? |
   | ⑤ | 要动的页件我有没有权限（查 restriction） | Akun mana yang akan dipakai (CLAUDE.md §2), dan apakah akun itu bisa membaca atau menulis objek tersebut? Termasuk batas tulis Bambang (CLAUDE.md §3) dan lima kelas Alden (masih draf, K-1). |
   | ⑥ | 异常缺位边界覆盖没 | Jalur error, nilai kosong, atasan tidak terbaca, klik ganda, ulang jalan, hasil 0 (07.06.1 E9, E16): tertulis di Spec dan tertangani? |
   | ⑦ | 测试前置（夹具／测试档案／sandbox）有没有 | Tiket TEST, arsip tes NTP, whitelist Slack (04.5.3), cara pin atau matikan node tulis (07.06.1 E6): sudah siap? |

2. **Pisahkan hasilnya.**
   - **Sudah ada jawabannya di source:** kutip, jangan ditanyakan.
   - **Kekurangan yang bisa dikerjakan sendiri** dalam batas tulis: masukkan ke daftar kerja.
   - **Kekurangan yang perlu jawaban orang lain:** kemas jadi satu paket pertanyaan.

3. **Kemas pertanyaan** sesuai 「打包请示带建议」:
   - Pertanyaan bisnis → Owner Spec. Pertanyaan platform → Alden (sesuai kutipan Kent; lihat juga 07.06 §三 归口表).
   - Setiap pertanyaan membawa usulan jawaban.
   - Pertanyaan bisnis ditulis sebagai pilihan bisnis tanpa istilah teknis (07.06 §三-4).
   - Draf wajib memuat baris 「Sudah dicek: …」 (CLAUDE.md §0.10).
   - **Tidak dikirim** tanpa perintah Bambang.

4. **Laporkan ke Bambang** dalam satu tabel:

   | Kategori | Hasil | Sumber dan batas baca | Tindak lanjut (sendiri / tanya siapa / sudah terjawab) |
   |---|---|---|---|

   Setelah itu, minta Bambang memeriksa apakah ada yang terlewat, terutama ketergantungan tersembunyi di alur yang dia kenal (sesuai kutipan Kent).

## Lima disiplin pendamping (Kent)
Dipakai sepanjang kerja, bukan hanya saat pemindaian: 「并行不阻塞／打包请示带建议／送审自带证据链／返工快吸收／认错快不越权」. Arti masing-masing tidak dijabarkan di sumber, jadi tidak dijabarkan di sini.

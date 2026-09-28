# CLAUDE.md: PA_Os_Builder

Repo ini adalah tempat kerja Claude untuk membantu **Bambang** membangun alur NOS (Nexmax Operating System) sebagai builder BO.
Semua isi file ini diambil dari source yang tercatat di `docs/sources.md`, dibaca pada 2026-09-26. Setiap aturan menyebut sumbernya.

---

## 0. Aturan paling utama: jangan membuat kesimpulan sesat

Aturan ini ada karena kesalahan sebelumnya: kesimpulan tanpa dasar membuat pekerjaan berantakan. Aturan ini berlaku di atas semua bagian lain.

1. **Tidak ada sumber, tidak boleh disebut fakta.** Setiap pernyataan tentang NOS harus menyebut sumbernya:
   - Confluence: pageId + bagian
   - Jira: key + comment id
   - Slack: channel + ts
   - Hasil API: tool + waktu
2. **Hanya enam label status** (Anchor 04 §七.6): 已验证／已完成但未验收／进行中／待决策／被阻塞／未开始.
3. **Kutipan harus dibedakan dari inferensi.** Kutipan ditulis apa adanya dalam 「」. Inferensi harus diberi label **"inferensi, belum dikonfirmasi"**. Pernyataan tentang diri sendiri dari seseorang, misalnya "hanya menambah satu baris", dicatat sebagai pengakuan orang itu, bukan sebagai sesuatu yang sudah diverifikasi Claude. Praktik ini meniru cara build sheet S-05 (2096463922) ditulis.
4. **Belum dibaca berarti tidak diketahui.**
   - Link yang tidak dibuka dianggap belum dibaca (Anchor 04 §七.2).
   - 🔲, 「待定」, 「规划中」, dan 「锁定」 dianggap celah. Jangan diisi sendiri (07 §二).
5. **Tidak ada akses berarti dilarang** (aturan Bambang, 2026-09-26). Jangan mencari jalan lain, jangan minta ekspor, dan jangan menebak isinya.
6. **Hasil 0 atau 404 bukan bukti bahwa sesuatu tidak ada.**
   - Hasil kosong bisa berarti tidak terlihat oleh akun yang dipakai. Pastikan dengan probe pembanding (07.06.1 E16).
   - Timeout MCP bukan tanda berhasil atau gagal. Baca changelog-nya (build sheet S-05, bagian 本轮踩坑).
7. **Konflik antar-source tidak didamaikan sendiri** (Anchor 04, 权威使用原则). Catat di `docs/open-issues.md` lalu tanyakan.
8. **File di `docs/` hanya snapshot atau peta.** Isinya bukan pengganti membaca halaman Confluence saat bekerja. Sebelum menulis ke halaman mana pun, ambil dulu versi terbarunya (07 §二「先查后写」).
9. **Tanya dulu sebelum bertindak** (preferensi Bambang). Kalau ragu, tanyakan. Jangan berasumsi.
10. **Baca semua source dulu sebelum membuat apa pun** (aturan Bambang, 2026-09-28). Aturan ini ada karena kesalahan nyata: OSD-116 c50595 (a) menanyakan ke Alden field dan Screen N07, padahal Alden sudah menjawabnya di #nos-bo 1790228926.781229 butir 5. Pesan itu bahkan sudah dikutip di file ini (§3), tapi butir 5-nya tidak dibaca.
    Sebelum membuat draf pertanyaan, comment, keputusan, rekomendasi, atau perubahan konfigurasi:
    - Cari topiknya di **semua** tempat berikut, dan baca **penuh**, bukan potongan:
      - seluruh comment tiket Jira terkait (OSD-116, NSE-1137, dan tiket lain yang disebut);
      - semua pesan dan **semua balasan thread** di #nos-bo, termasuk Canvas yang dilampirkan;
      - halaman Confluence terkait, versi terbaru (CQL untuk kata kuncinya);
      - build sheet, `docs/open-issues.md`, dan `docs/pending-buildsheet-updates.md`.
    - Kalau satu pesan sudah dipakai sebagai sumber, baca **seluruh isi pesan itu**, bukan hanya kalimat yang dicari.
    - Setiap draf wajib memuat baris 「Sudah dicek: …」 yang menyebut sumber, batas bacanya (comment id atau ts terakhir), dan tanggal bacanya.
    - Kalau ada sumber yang belum dibaca penuh, sebutkan, dan **jangan kirim** draf sebelum sumber itu dibaca.
    - Pertanyaan ke orang lain hanya boleh diajukan untuk hal yang **tidak ada** di sumber mana pun. Hal yang sudah dijawab dikutip, bukan ditanyakan ulang.

---

## 1. Siapa siapa

| Orang | Peran | Sumber |
|---|---|---|
| **Bambang** (pengguna) | Anggota departemen Backend Operations (BO). Builder S-05. | Bambang, 2026-09-26; OSD-116 c50071 (serah terima dari Kent) |
| Kent | **HOD BO** (atasan Bambang). Schema Owner 04.10. | Bambang, 2026-09-26; 04.10 (1738735636) |
| Alden | Owner 04.4, 04.4.1, 04.5.2, 04.5.3, dan 04.6–04.9 (platform). Tanda tangan teknis N9. | Anchor 04 §六; OS 开发流 Spec N9 |
| Kayden | Owner 04.0–04.3, 04.5, dan 04.5.1. Tanda tangan bisnis N9. | Anchor 04 §六; OS 开发流 Spec N9 |
| Felix_HR | Owner/desainer Spec S-05 (HR) | OSD-116 c49003; build sheet S-05 |
| Geri | Jalur resign (NSE-1137). Membangun entry `qa01CkZBQfx8eLsK`. | OSD-116 c50381; build sheet S-05 |

Siapa pemutus di setiap Gate: lihat `docs/04-anchor-navigation.md` §2.

---

## 2. Akun dan connector: siapa yang tercatat sebagai penulis

| Connector | Akun | Dipakai untuk | Sumber |
|---|---|---|---|
| **Atlassian_Rovo** | **Backend Operations** (boteam001@nexmaxorg.com), akun kerja **bersama** tim BO | Membaca Confluence. **Konfigurasi dan tes Jira** (Issue Type, Workflow, tiket TEST). Membaca tiket SSCSD. | Bambang, 2026-09-26; build sheet S-05 偏差登记「建设用账号：Jira 配置与测试一律使用 Backend Operations 账号」; SSCSD-411/421/422/423: reporter dan assignee = Backend Operations (diamati di sesi 2026-09-26 lewat Atlassian_Rovo `searchJiraIssuesUsingJql`) |
| **Atlassian_MCP** | **Akun pribadi Bambang** (accountId 712020:0ec04d28-9941-4568-b144-a1c4f2dcf138) | **Edit build sheet** mulai v13 (satu-satunya halaman Confluence yang boleh ditulis Claude, atas izin Bambang). Membaca Jira. Comment Jira (OSD-116) adalah praktik Bambang sendiri, dan Claude tidak menulis comment kecuali diminta eksplisit (§3). | Build sheet S-05 偏差登记「OSD-116 Comment 使用个人账号」「本建造单页自 v13 起改由个人账号写入」; OSD-116 (mention "Bambang") |
| Slack | Belum diverifikasi | Hanya membaca | — |
| n8n | Login yang tampil: "Alden Lee" (project personal). Menurut 04.6: 「开发者／BO 团队共用平台 Owner 的同一登录账号」. | Membaca. Membuat atau mengubah workflow hanya dengan izin. | Diamati di sesi 2026-09-26 lewat n8n `search_projects`; 04.6 (1690927120) |

Batas akses yang sudah terbukti:
- Akun pribadi Bambang **tidak bisa melihat** tiket SSCSD yang diuji. Atlassian_MCP `searchJiraIssuesUsingJql` dengan `key in (SSCSD-411, SSCSD-421, SSCSD-422, SSCSD-423)` mengembalikan 「Issue does not exist or you do not have permission to see it」 (diamati di sesi 2026-09-26).
- Akun Backend Operations punya scope Jira `read:jira-work`/`write:jira-work` saja, **tanpa hak konfigurasi**. Konfigurasi dilakukan manual lewat UI lalu diverifikasi lewat API (build sheet S-05, 本轮实建与回读).
- Di **UI** Jira, akun BO punya menu **Jira admin settings** (System, Jira apps, Spaces, Work items) dan **User management** (pernyataan Bambang 「aku admin disana」 + screenshot, 2026-09-26). Jadi batas di atas berlaku untuk API. Konfigurasi lewat UI dikerjakan Bambang. Punya akses admin **tidak sama** dengan boleh: membuat group baru butuh persetujuan level site (Kent OSD-116 c49545), dan perubahan izin/visibilitas termasuk lima kelas Alden yang masih draf (§3).
- Menulis ke Confluence lewat akun BO berarti **mengganti seluruh halaman**. Risikonya, isi bisa rusak tanpa ketahuan. Itulah alasan build sheet diedit lewat akun pribadi (build sheet S-05 偏差登记).
- Assignee harus ditulis eksplisit saat membuat tiket SSCSD. Kalau tidak, tiket otomatis diberikan ke Alden (build sheet S-05, 本轮踩坑).

**Kalau suatu tindakan tidak ada di tabel di atas: tanyakan ke Bambang akun mana yang dipakai.** Aturan lengkapnya masih akan dijelaskan Bambang.

---

## 3. Persetujuan: apa yang butuh izin

**Batas tulis dari Bambang (2026-09-26). Aturan ini mengalahkan semua aturan lain di file ini, di skill, dan di source mana pun:**
- Claude **hanya boleh menulis atau mengedit dua hal**, dan hanya **atas izin Bambang**:
  1. **Halaman build sheet yang sudah dibuat Bambang.** Saat ini: 纪律与绩效改进处置｜建造单 (2096463922).
  2. **Repo ini** (PA_Os_Builder).
- **Spec mana pun tidak boleh diedit oleh Claude, dalam bentuk apa pun.** Termasuk dua tindakan yang menurut 07.06 §八 / 04.5 §五 boleh dilakukan pihak build (「①状态区生命周期更新；②引用区『对应建造单』链接回填」). Keduanya **tidak** dilakukan Claude, dan juga **tidak ditawarkan**.
- Semua halaman atau sistem lain (Confluence selain build sheet Bambang, Jira, Slack, n8n) **tidak ditulis oleh Claude**. Kalau suatu saat perlu, Bambang yang akan meminta secara eksplisit.
- **Draf bukan izin.** Kalau Bambang minta draf, Claude hanya menunjukkan isi draf. Claude tidak menawarkan untuk menjalankannya dan tidak menulis apa pun.

**Aturan dasar:** setiap penulisan yang masih diizinkan di atas butuh **persetujuan eksplisit Bambang untuk setiap tindakan**. Sebelum bertindak, Claude menunjukkan draf, akun yang akan dipakai, dan dampaknya. Membaca tidak butuh izin.

Selain aturan dasar itu, ada dua aturan tambahan dari source:
- **07.06.1 §六-2** (1712226375): tindakan yang tidak bisa dibatalkan. 「AI 不得自行执行、也不得把『使用者交办了这个任务』当成已经同意」. Daftarnya:
  - menghapus objek apa pun
  - mengubah resource bersama yang sudah ada
  - tulis massal >20
  - notifikasi ke karyawan sungguhan atau pengiriman nyata pertama
  - mengaktifkan workflow (juga butuh persetujuan Owner platform)
  - 「记不清是否在清单内，就先问」
- **Lima kelas yang butuh persetujuan Alden. Statusnya masih DRAF**: judulnya sendiri 「权责判定标准初稿」 (#nos-bo, thread 1789704362.435989, balasan 1790159495.872119, Alden, 2026-09-23). Kent memasukkannya ke Canvas draf 04.10 v3 (F0C32N7MYR1, balasan 1790163869.066139). Draf ini **belum ada** di 04.10: dicek ulang 2026-09-28 pada versi lastModified Sep 26, tidak ada kata 五类/审批线/权限／可见性/启用自动化/>20. Canvas v3 (dibaca penuh 2026-09-28) masih berlabel 「提案 v3」 dan menandai cakupan 主单侧 sebagai 〔待定〕. Alden (1790228926.781229) meminta Kayden 「点头」 atas perubahan cakupan; sampai balasan terakhir thread (2026-09-25) belum ada jawaban Kayden.
  1. mengubah objek bersama yang sudah dipakai alur lain, **bila perubahan itu mengubah perilaku alur lain** (「且改完会改变别人的行为」)
  2. izin/visibilitas
  3. penghapusan
  4. mengaktifkan otomasi
  5. data asli >20 record

  Di pesan yang sama: persetujuan harian 04.10 dipegang 「由 Kent 以 Schema Owner 审批」. Alden menegaskannya lagi pada 2026-09-24 (balasan 1790228926.781229): sisi 主单 SSCSD masuk 04.10 di bawah persetujuan Kent, 「我只在五类风险时点头」.
- **Aturan persetujuan untuk field arsip karyawan (NTP/TCL)**: sekarang ada di 04.8 §四 (v23, 2026-09-28, dibaca penuh 2026-09-28): 「改已在用的档案字段（改选项或取值、设必填、缩小作用范围）、涉及档案可见性（issue security、权限）、删除字段、批量改真实档案超过 20 条，须平台 Owner 确认；其余（为本流程新增字段、挂本流程的屏、设为选填）由 Schema Owner 按 04.10 第五节建立并在第五节登记，平台 Owner 事后抽查。」 Alden (#nos-bo thread 1789704362.435989, 2026-09-28 16:36): 「过渡做法到此结束」. Aturan sementara sebelumnya (「审批线写出来前照昨天那句先找我」, 1790228926.781229; 「BO 起草、我点头、再建」, 1790160397.275109) sudah digantikan.
- Untuk semua butir di atas, Claude memberi tahu Bambang. Keputusan akhir tetap di tangan Bambang. Lihat `docs/open-issues.md` K-1.

Larangan mutlak:
- **Data produksi** hanya diubah lewat n8n workflow, 「不得用 Atlassian MCP 或其他渠道直改生产数据」 (07.06.1 §六-3).
- **Secret:** 「不进代码、不进文档、不经 AI 通道」 (04.4.1, 1729888419). Secret diisi manual oleh Owner platform (04.6).
- **Spec: Claude tidak mengedit sama sekali** (aturan Bambang, lihat batas tulis di atas). Catatan source: 07.06 §八 dan 04.5 §五 mengizinkan pihak build melakukan dua tindakan di Spec. Aturan Bambang lebih ketat, dan aturan Bambang yang berlaku. Butir yang sama di salinan skill `build` adalah teks source, **bukan izin untuk Claude**.
- **Tiket di project arsip personel dan buku besar (人员档案与事件账本类) tidak boleh dihapus permanen, termasuk tiket tes.** Penanganannya hanya ada tiga: Cancel, VOID 化, atau 编辑覆盖 (04.5.3 §四-1). Contoh NTP diambil dari build sheet S-05 bagian 测试 dan 1587347525 规则 2. Semua penghapusan untuk bersih-bersih termasuk tindakan yang tidak bisa dibatalkan: buat daftarnya dulu dan tunggu konfirmasi Bambang (04.5.3 §四-3).

---

## 4. Urutan kerja

Diambil dari 07.06.1 §四, 07.06 §八, dan Anchor 04 §七. Detailnya ada di `docs/04-anchor-navigation.md` §1.

1. Jira dulu: task, Parent, hulu/hilir, comment.
2. 07 §二/§三.
3. Panduan tahap yang sedang dikerjakan (untuk build: 07.06 dibaca penuh).
4. Anchor 04, lalu buka halaman 04.x yang ditunjuk.
5. 07.06.1 §三 速查.
6. Pisahkan jalur API dan jalur manual (07.06 §六). Cek tempat daftar sebelum membuat objek. Buat, daftarkan, baru aktifkan.
7. Setelah menulis, **wajib baca ulang (回读)**. Tanpa bukti baca ulang, pekerjaan tidak boleh dilaporkan selesai (Anchor 04 §七.8; 07.06 §6.1-3).
8. Setiap unit build selesai, lakukan 收口三件套 (07.06 §三-8): catat baris di build sheet, perbarui status halaman kontrak, tulis balik kesimpulan comment ke dokumen.

---

## 5. Kondisi wajib berhenti

Anchor 04 §七, dikutip apa adanya:
> **强制停止条件**｜权威页打不开；规则冲突；业务语义未裁决；Owner 不明；前置未齐；登记触发命中但无行；测试／回读证据缺失；实际配置与 Spec／建造单不一致。停止时必须指出阻塞对象、阻塞人和恢复条件。

Kalau standarnya tidak ada, buat laporan dengan format **标准缺口回报** (enam field, 07 §三). Bedakan dulu apakah itu celah standar atau ketidakjelasan bisnis. Ketidakjelasan bisnis diselesaikan lewat 白话对齐 (pertanyaan pilihan bisnis tanpa istilah teknis, 07.06 §三-4).

---

## 6. Tes

Sumber: 04.5.3 (1729626578, lastModified 2026-09-28, v17). Dibandingkan dengan versi 2026-09-25, yang berubah hanya syarat 2 pada pengecualian 「收件人就是主体」 di §二. Aturan di bawah tidak berubah (dicek 2026-09-28, audit D-17). Bagian 测试 di build sheet S-05 memuat versi yang lebih lama. Kalau keduanya berbeda, **04.5.3 terbaru yang dibaca**.
- Tiket tes Jira wajib punya **dua penanda**, 「两项须同时具备，任一缺失视为未标识」 (04.5.3 §三): judul diawali `TEST｜`, **dan** subjek tiket menunjuk ke arsip tes.
  - Build sheet S-05 mencatat bahwa tes struktur tanpa subjek (SSCSD-411, dengan preseden GPM) hanya memenuhi penanda pertama. Ini ketegangan dengan 04.5.3, lihat `docs/open-issues.md` K-7. Claude tidak memutuskannya.
- Tiket tes di SSCSD untuk S-05 dibiarkan di status akhirnya dan tidak dihapus (build sheet S-05, 测试单登记). Untuk project arsip dan buku besar berlaku aturan di §3.
- Whitelist Slack (04.5.3 §二):
  - 甲: DM diri sendiri
  - 乙: #nos-bo (C0BRSTNNY4A), #nos-ops (C0BBT5ZC9L6)
  - 丙: #nos-governance (C0C0S5CD1S9), 「OS 开发流一族（时效件、N10 对齐）的测试频道」
- **Dilarang mengirim ke:** #sscos-hr (C0BHL8AE68G), #epic-nse-1045-squad (C0BKUAGTKP1), #general (C06411GVD5K).
- Penanda tes di Slack: `🧪 【SSCOS 测试 · 请勿处理 ｜ TEST — do not action】`.
- `test_workflow` n8n akan benar-benar mengirim. Nonaktifkan node tulis/kirim, atau isi pinData secara eksplisit (07.06.1 E6).
  - Cara membuktikannya (07.06.1 E6 验收, versi 2026-09-26): baca ulang objek tujuan, lalu periksa **setiap node yang menulis atau mengirim**. Node yang benar-benar jalan menghasilkan balasan sungguhan (nomor tiket, ts pesan) dan butuh ratusan milidetik. Waktu 0 berarti node itu di-pin atau dinonaktifkan. 「执行记录顶层的 pinData 字段不作判据」.

---

## 7. Isi repo

| Path | Isi |
|---|---|
| `docs/anchor-04.md` | Salinan **lengkap** Anchor 04 (snapshot 2026-09-26) |
| `docs/04-anchor-navigation.md` | Peta navigasi, 8 tahap (3 Gate audit), node OS 开发流, Skill per tahap, dan tempat daftar |
| `docs/open-issues.md` | Kontradiksi antar-source dan hal yang tidak diketahui. **Tidak boleh didamaikan sendiri.** |
| `docs/sources.md` | Daftar source yang dibaca, termasuk yang dilarang |
| `docs/evidence/` | Bukti hasil cek live (tool + waktu) untuk klaim "diamati di sesi" |
| `docs/pending-buildsheet-updates.md` | Antrean draf update build sheet S-05, ditulis sekaligus dalam satu versi (permintaan Bambang, 2026-09-28). Draf, bukan izin menulis. |
| `docs/pending-0409-registration.md` | Draf registrasi 04.9 untuk N04/N05/N07/N20 (4 baris indeks + 4 blok 04.9.7). Ditulis Bambang sendiri, menunggu jawaban Alden OSD-116 c50670. Draf, bukan izin menulis. |
| `.claude/skills/build/` | Salinan terkendali Skill 流程建设 (07.06 §八). Dipakai untuk "Build \| S-xx". |
| `.claude/skills/nos-gate/` | Router Anchor 04 §七: dari key Jira ke Gate dan halaman yang wajib dibaca |
| `.claude/skills/prebuild-scan/` | 「建设前对齐扫描」 7 kategori dari Kent (#nos-bo 1789549825.279199). Wajib sebelum membangun node apa pun. Terpisah dari skill `build` karena tidak berasal dari 07.06 §八 |
| `.claude/skills/nos-check/` | Cek kesiapan lingkungan (07.06 环境就绪) dan cek drift snapshot/Skill terhadap Confluence |

Bahasa: chat dengan Bambang memakai **bahasa Indonesia**. Bahasa untuk menulis ke Jira atau Confluence **belum ditetapkan** (K-6), jadi tanyakan dulu.

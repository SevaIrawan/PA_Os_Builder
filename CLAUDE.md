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

---

## 1. Siapa siapa

| Orang | Peran | Sumber |
|---|---|---|
| **Bambang** (pengguna) | Anggota departemen Backend Operations (BO). Builder S-05. | Bambang, 2026-09-26; OSD-116 c50071 (serah terima dari Kent) |
| Kent | **HOD BO** (atasan Bambang). Schema Owner 04.10. | Bambang, 2026-09-26; 04.10 (1738735636) |
| Alden | Owner platform (04.4/04.6/04.7/04.8/04.9). Tanda tangan teknis N9. | Anchor 04 §六; OS 开发流 Spec N9 |
| Kayden | Tanda tangan bisnis N9. Owner 04.0–04.3 dan 04.5. | Anchor 04 §六; OS 开发流 Spec N9 |
| Felix_HR | Owner/desainer Spec S-05 (HR) | OSD-116 c49003; build sheet S-05 |
| Geri | Jalur resign (NSE-1137). Membangun entry `qa01CkZBQfx8eLsK`. | OSD-116 c50381; build sheet S-05 |

Siapa pemutus di setiap Gate: lihat `docs/04-anchor-navigation.md` §2.

---

## 2. Akun dan connector: siapa yang tercatat sebagai penulis

| Connector | Akun | Dipakai untuk | Sumber |
|---|---|---|---|
| **Atlassian_Rovo** | **Backend Operations** (boteam001@nexmaxorg.com), akun kerja **bersama** tim BO | Membaca Confluence. **Konfigurasi dan tes Jira** (Issue Type, Workflow, tiket TEST). Membaca tiket SSCSD. | Bambang, 2026-09-26; build sheet S-05 偏差登记「建设用账号：Jira 配置与测试一律使用 Backend Operations 账号」; SSCSD-411/421/422/423: reporter dan assignee = Backend Operations (diamati di sesi 2026-09-26 lewat Atlassian_Rovo `searchJiraIssuesUsingJql`) |
| **Atlassian_MCP** | **Akun pribadi Bambang** (accountId 712020:0ec04d28-9941-4568-b144-a1c4f2dcf138) | **Comment Jira** (OSD-116). **Edit build sheet** mulai v13. Membaca Jira. | Build sheet S-05 偏差登记「OSD-116 Comment 使用个人账号」「本建造单页自 v13 起改由个人账号写入」; OSD-116 (mention "Bambang") |
| Slack | Belum diverifikasi | Hanya membaca | — |
| n8n | Login yang tampil: "Alden Lee" (project personal). Menurut 04.6: 「开发者／BO 团队共用平台 Owner 的同一登录账号」. | Membaca. Membuat atau mengubah workflow hanya dengan izin. | Diamati di sesi 2026-09-26 lewat n8n `search_projects`; 04.6 (1690927120) |

Batas akses yang sudah terbukti:
- Akun pribadi Bambang **tidak bisa melihat** tiket SSCSD yang diuji. Atlassian_MCP `searchJiraIssuesUsingJql` dengan `key in (SSCSD-411, SSCSD-421, SSCSD-422, SSCSD-423)` mengembalikan 「Issue does not exist or you do not have permission to see it」 (diamati di sesi 2026-09-26).
- Akun Backend Operations punya scope Jira `read:jira-work`/`write:jira-work` saja, **tanpa hak konfigurasi**. Konfigurasi dilakukan manual lewat UI lalu diverifikasi lewat API (build sheet S-05, 本轮实建与回读).
- Menulis ke Confluence lewat akun BO berarti **mengganti seluruh halaman**. Risikonya, isi bisa rusak tanpa ketahuan. Itulah alasan build sheet diedit lewat akun pribadi (build sheet S-05 偏差登记).
- Assignee harus ditulis eksplisit saat membuat tiket SSCSD. Kalau tidak, tiket otomatis diberikan ke Alden (build sheet S-05, 本轮踩坑).

**Kalau suatu tindakan tidak ada di tabel di atas: tanyakan ke Bambang akun mana yang dipakai.** Aturan lengkapnya masih akan dijelaskan Bambang.

---

## 3. Persetujuan: apa yang butuh izin

**Aturan dasar di repo ini:** setiap penulisan ke sistem luar (Jira, Confluence, Slack, n8n) butuh **persetujuan eksplisit Bambang untuk setiap tindakan**. Sebelum bertindak, Claude menunjukkan draf, akun yang akan dipakai, dan dampaknya. Membaca tidak butuh izin.

Selain aturan dasar itu, ada dua aturan tambahan dari source:
- **07.06.1 §六-2** (1712226375): tindakan yang tidak bisa dibatalkan. 「AI 不得自行执行、也不得把『使用者交办了这个任务』当成已经同意」. Daftarnya:
  - menghapus objek apa pun
  - mengubah resource bersama yang sudah ada
  - tulis massal >20
  - notifikasi ke karyawan sungguhan atau pengiriman nyata pertama
  - mengaktifkan workflow (juga butuh persetujuan Owner platform)
  - 「记不清是否在清单内，就先问」
- **Lima kelas yang butuh persetujuan Alden** (#nos-bo, thread 1789704362.435989, balasan 1790159495.872119, Alden, 2026-09-23):
  1. mengubah objek bersama yang sudah dipakai alur lain, **bila perubahan itu mengubah perilaku alur lain** (「且改完会改变别人的行为」)
  2. izin/visibilitas
  3. penghapusan
  4. mengaktifkan otomasi
  5. data asli >20 record

  Pesan yang sama juga menyebut: persetujuan harian 04.10 dipegang 「由 Kent 以 Schema Owner 审批」. Untuk kelima kelas ini, Claude juga memberi tahu Bambang. Lihat `docs/open-issues.md` K-1.

Larangan mutlak:
- **Data produksi** hanya diubah lewat n8n workflow, 「不得用 Atlassian MCP 或其他渠道直改生产数据」 (07.06.1 §六-3).
- **Secret:** 「不进代码、不进文档、不经 AI 通道」 (04.4.1, 1729888419). Secret diisi manual oleh Owner platform (04.6).
- **Isi Spec** (节点、分支、契约、文案、角色) tidak boleh diubah oleh pihak build. Pihak build hanya boleh mengubah status siklus hidup dan mengisi balik link build sheet (07.06 §八; 04.5 §五).
- **Tiket di project arsip personel dan buku besar (人员档案与事件账本类, contohnya NTP) tidak boleh dihapus permanen, termasuk tiket tes.** Penanganannya hanya ada tiga: Cancel, VOID 化, atau 编辑覆盖 (04.5.3 §四-1). Semua penghapusan untuk bersih-bersih termasuk tindakan yang tidak bisa dibatalkan: buat daftarnya dulu dan tunggu konfirmasi Bambang (04.5.3 §四-3).

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

Semua dari 04.5.3 (1729626578), sebagaimana dicatat di build sheet S-05 bagian 测试:
- Tiket tes Jira wajib punya **dua penanda**, 「缺一视为未标识」: judul diawali `TEST｜`, **dan** subjek tiket menunjuk ke arsip tes (04.5.3 §三). Tes struktur tanpa subjek hanya memenuhi penanda pertama, dan hal ini wajib ditulis terus terang (build sheet S-05, contoh SSCSD-411).
- Tiket tes di SSCSD untuk S-05 dibiarkan di status akhirnya dan tidak dihapus (build sheet S-05, 测试单登记). Untuk project arsip dan buku besar berlaku aturan di §3.
- Whitelist Slack: DM diri sendiri, #nos-bo (C0BRSTNNY4A), #nos-ops (C0BBT5ZC9L6).
- **Dilarang mengirim ke:** #sscos-hr (C0BHL8AE68G), #epic-nse-1045-squad (C0BKUAGTKP1), #general (C06411GVD5K).
- Penanda tes di Slack: `🧪 【SSCOS 测试 · 请勿处理 ｜ TEST — do not action】`.
- `test_workflow` n8n akan benar-benar mengirim. Nonaktifkan node tulis/kirim, atau isi pinData secara eksplisit (07.06.1 E6).

---

## 7. Isi repo

| Path | Isi |
|---|---|
| `docs/anchor-04.md` | Salinan **lengkap** Anchor 04 (snapshot 2026-09-26) |
| `docs/04-anchor-navigation.md` | Peta navigasi, 8 tahap (3 Gate audit), node OS 开发流, Skill per tahap, dan tempat daftar |
| `docs/open-issues.md` | Kontradiksi antar-source dan hal yang tidak diketahui. **Tidak boleh didamaikan sendiri.** |
| `docs/sources.md` | Daftar source yang dibaca, termasuk yang dilarang |
| `.claude/skills/build/` | Salinan terkendali Skill 流程建设 (07.06 §八). Dipakai untuk "Build \| S-xx". |
| `.claude/skills/nos-gate/` | Router Anchor 04 §七: dari key Jira ke Gate dan halaman yang wajib dibaca |
| `.claude/skills/nos-check/` | Cek kesiapan lingkungan (07.06 环境就绪) dan cek drift snapshot/Skill terhadap Confluence |

Bahasa: chat dengan Bambang memakai **bahasa Indonesia**. Bahasa untuk menulis ke Jira atau Confluence **belum ditetapkan** (K-6), jadi tanyakan dulu.

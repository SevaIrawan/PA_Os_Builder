# Isu terbuka: kontradiksi antar-source dan hal yang tidak diketahui

> Anchor 04 menyatakan: 「评论、旧任务描述、记忆或既有配置与权威页冲突时，不得自行调和」.
> Karena itu Claude **tidak memilih salah satu sisi** dari kontradiksi di bawah. Setiap kali sebuah item ikut memengaruhi pekerjaan, Claude menyebutnya dan menunggu keputusan Bambang atau Owner halaman terkait.
> Semua kutipan di bawah sudah dicocokkan dengan teks source yang dibaca pada 2026-09-26. Bagian yang dipotong ditandai 「…」. Tanda kutip bersarang 「」 di dalam 「」 ditulis sebagai 『』.
> Kalau sebuah item sudah diselesaikan oleh Owner-nya, pindahkan ke bagian "Selesai" dan cantumkan buktinya (pageId dan versi, atau comment id).

## A. Kontradiksi antar-source

### K-1 · Siapa yang menyetujui tindakan yang tidak bisa dibatalkan
- **1587347525** (NOS V1｜信息架构与分工（Claude Code 入口）, Jul 13, 2026; cakupannya NOS V1):
  - 「③不可逆动作先经 Alden 确认」
  - Daftar 规则 2 berisi: hapus, portal terlihat atau kirim notifikasi ke karyawan sungguhan, ubah resource bersama, tulis massal >20, aktifkan workflow.
- **07.06.1 §六-2** (1712226375, lastModified halaman 2026-09-25):
  - 「得到正在使用它的开发者明确同意之后才做。拍板的人就是这位开发者本人，不需要再向上请示」
  - Mengaktifkan workflow tetap 「须平台 Owner 批准」.
- **Slack #nos-bo, thread 1789704362.435989, balasan 1790159495.872119** (Alden, 2026-09-23): ada lima kelas yang tetap perlu persetujuan Alden:
  1. mengubah objek bersama yang sudah dipakai alur lain, bila perubahan itu mengubah perilaku alur lain (「且改完会改变别人的行为」)
  2. izin atau visibilitas
  3. penghapusan
  4. mengaktifkan otomasi
  5. perubahan data asli >20 record

  Yang lain 「不用找我」. Pesan yang sama juga menyebut persetujuan harian 04.10 dipegang 「由 Kent 以 Schema Owner 审批」.
  - **Status: draf.** Judul bagiannya 「权责判定标准初稿」. Kent memasukkannya ke Canvas draf 04.10 v3 (F0C32N7MYR1, balasan 1790163869.066139). Draf ini belum ada di salinan 04.10 (lastModified Sep 22).
  - Alden, 2026-09-24 (balasan 1790228926.781229): 「我只在五类风险时点头」. Field arsip NTP/TCL: 「审批线写出来前照昨天那句先找我」, merujuk ke 「BO 起草、我点头、再建」 (balasan 1790160397.275109).
- **Cara Claude bertindak sampai ada keputusan:**
  - Selalu minta persetujuan Bambang (07.06.1).
  - Untuk lima kelas di atas, Claude juga menyebutkan bahwa menurut pesan Alden di Slack persetujuan Alden diperlukan.
  - Claude tidak menyimpulkan bahwa persetujuan salah satu pihak sudah cukup.
  - Belum diverifikasi apakah lima kelas itu sudah ditulis di 04.10 atau 04.6.

### K-2 · Siapa yang memutuskan audit 切分 (N5) dan 验收 (N14)
- **Anchor 04 §一/§二** dan **OS 开发流 Spec N5/N14** (1729200354): 「Kayden 或 Alden」 (OR).
- **07.06 §三 归口表** (1730347066): 「切分→Kayden」 dan 「验收→Kayden」.

### K-3 · Format nama n8n workflow
- **04.6 §二 no. 3** (1690927120): `{流程名}｜{Spec 节点 ID}｜n8n-{动作}` (contoh: `员工离职｜N2｜n8n-路由分发`).
- **04.4 §十** (1677066244): `{流程名}｜{Spec 节点 ID}｜{模式编号或动作}`.
  - 04.9 §一 (1693089805) dan 07.06 §四 (1730347066) merujuk 04.4 §十 dengan format `{模式或动作}`.
- **Draf checklist engineering review v1 dari Alden** (#nos-bo, thread 1789704362.435989, balasan 1790323114.589099, 2026-09-25; draf, 「有意见再出 v2」) butir 5: 「件名：合『{流程名}｜N{x}｜n8n-{动作}』…｜机｜04.6 §二第 3 条」. Kalau draf itu berlaku, nama S-05 yang sekarang akan gagal cek mesin.
- **Kondisi nyata S-05** (build sheet 2096463922 §五): `纪律与绩效改进处置｜N04｜路由分发`, tanpa `n8n-`.
- Nama komponen platform memakai format `NOS | Platform | …` (halaman yang sama, §六).

### K-4 · Letak tombol Manual Trigger untuk tiket pemeliharaan (维护单)
- **04.4 模式二** (1677066244): 「处理人在主单/子单卡片上点"标记文档需更新"」
- **04.2 §六** (1676607500): 「处理人在自己所在的执行卡上用 Manual Trigger 按钮标记」

### K-5 · Apakah bentuk C wajib punya jalan keluar 「已改道」
- Dicatat di build sheet S-05 (2096463922, tabel lampiran halaman pertama): 04.3 §二 meminta tiga jalan keluar terminal dari 「待审批」. Spec S-05 tabel E dan contoh pada alur resign tidak punya 「已改道」.
- Build sheet mencatatnya sebagai 「待办（建造侧提出·双签未表态）」.

### K-6 · Bahasa saat menulis ke Jira atau Confluence
- **07.06.1 §六-6** (1712226375): 「Atlassian 对象一律用英文原词…回复用中文」.
- Dalam praktik, Bambang menulis comment OSD-116 dalam bahasa Inggris (contoh c50237) dan mengobrol dengan Claude dalam bahasa Indonesia.
- **Belum ditetapkan.** Tanyakan ke Bambang sebelum menulis apa pun.

### K-7 · Tiket tes tanpa subjek vs aturan dua penanda
- **04.5.3 §三** (1729626578, lastModified 2026-09-25): 「两项须同时具备，任一缺失视为未标识」 (judul `TEST｜` + subjek arsip tes).
- **Build sheet S-05** (2096463922, bagian 测试): tes struktur SSCSD-411/421/422/423 tidak punya subjek, jadi 「本轮 SSCSD-411 仅满足前者」. Dasarnya preseden GPM (「标题 TEST｜，不涉真实员工」).

### K-8 · Nomor bagian di salinan terkendali vs aturan 07.06 §八
- **07.06 §八** (1730347066): 「不得把章节号或步骤正文写死在 Project Instruction——按语义标题定位」.
- `CLAUDE.md` §4, `docs/04-anchor-navigation.md`, dan skill `nos-gate`/`nos-check` di repo ini masih menyebut nomor bagian (§七, §二, …) sebagai penunjuk sumber.
  - Skill `build` sudah memakai judul bagian.
  - Nomor bagian dipakai sebagai rujukan kutipan, bukan sebagai langkah yang menggantikan halaman.
- Apakah ini dianggap melanggar aturan 07.06 §八 perlu diputuskan Bambang.

### K-9 · Siapa 「HR Ops & Data 角色组」 di Jira (perintah Kayden OSD-116 c50445)
- **c50445** (Kayden, 2026-09-24): 「Abort Case（id 11）转态权限配给 HR Ops & Data 角色组；N07「确认重复」同口径。执行顺序请写死：先把主单转「已取消」，再取消未关子单」.
- **04.3 §六** (1676771343, dibaca 2026-09-26), baris tabel: 「**主单**转入「已取消」（执行中止）｜仅服务账号、该主单所在 Project 的 Owner，与该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」.
- **Halaman yang sama, 执法点**: 「Jira workflow Condition 不承担"限定哪个人有权批"的职责——它收紧为"仅服务账号可转态"。审批权校验发生在 Slack 审批卡的回传链路上」. Bunyi ini berbeda dengan baris tabel di atas.
- **Preseden Grade** (1742766267): condition tiket utama = group `SSCOS｜Service Accounts` saja. Keputusan Alden c48475/c48531: 「主单侧只放服务账号，不放 Administrators」.
- **Tidak ada source** di 15 halaman yang dicari (04.0, 04.1, 04.3, 04.7, 04.10, Spec S-05, build sheet S-05/resign/Grade, HR｜盘点与切分, dll.) yang memetakan HR Ops & Data ke group Jira tertentu.
  - HR｜盘点与切分 (1745158181): 「HR Ops & Data 3人」, Function Lead Felix, tanpa nama anggota.
  - Group HR yang ada di Jira: `SSCOS｜HR`. Anggota yang terbaca: Felix_HR dan Yuki Liew_HR, keduanya punya application role Jira Service Desk (E10). Di source, group ini hanya dipakai untuk trigger Automation N12 resign dan security level NTP 10344.
  - Pengecekan ini dilakukan Atlassian_MCP `getJiraUser` hanya untuk Felix_HR dan Yuki Liew_HR. Apakah ada group lain untuk HR Ops & Data (akun lain, atau lewat User management) belum dicek. Menurut 07.06.1 E16, hasil yang tidak menemukan sesuatu bukan bukti bahwa hal itu tidak ada.
- Menurut 04.3 (dibaca Claude), urutan 「主单先、子单后」 hanya ada sebagai kalimat Kayden. Teks 04.3 menulis 「在同一动作范围内」.
- **Status:** 待决策. Yang berhak menjawab adalah Kayden (pemberi perintah, Owner 04.3). Bambang meminta item ini dilewati dulu (2026-09-26).

## B. Tidak diketahui atau tidak bisa diakses

| # | Hal | Status | Alasan / sumber |
|---|---|---|---|
| U-1 | Space **NW**: 00｜知识库治理 (1647870014) dan 05｜页面结构与字段词汇表 (1656783199) | **Dilarang** | Laporan agent pembaca di sesi 2026-09-26: Rovo mengembalikan 404, Atlassian_MCP `getConfluenceContent` mengembalikan 403 "Space is restricted". Bukti mentahnya tidak disimpan. Aturan Bambang: tidak ada akses berarti dilarang. |
| U-2 | 04.12 / 机读标记总清单 (2091876367), 04.11 (1764524046), 04.4.2 (1751547935), 04.4.3 (2076508181), 04.4.4 (2102067228), 01｜OS 模块模型与铁律 (1674707036) | Belum dibaca | Dirujuk oleh berbagai halaman: 04.12 oleh 07.07 dan build sheet; 04.11 oleh 07.06 dan build sheet; 04.4.2–04.4.4 oleh 04.4, 04.9.1, dan build sheet; 01 oleh 04.5, 04.2, 04.6, 04.5.1, dan OS 开发流 Spec. Belum dibuka di sesi ini. |
| U-3 | Skill lokal BO milik tim: `.claude/skills/build`, 主脑, 复盘官, `ledger/inbox` | Isinya tidak diketahui | Kent menyebutnya di #nos-bo (1789549825.279199, 1789704362.435989) dan OSD-116 c50071. Tidak ada di Confluence dan tidak bisa diakses dari sini. Skill `build` di repo ini dibangun **hanya** dari 07.06 §八. |
| U-4 | Identitas akun connector Slack | Belum diverifikasi | Hanya dipakai untuk membaca. Menulis ke Slack butuh persetujuan per tindakan. |
| U-5 | Salinan 04.9.3 (1765015618) di scratchpad terpotong | Salinan tidak lengkap | Kalau dibutuhkan, buka ulang halamannya. |
| U-6 | Tiga lampiran Canvas di #nos-bo (F0C2VSAATHA, F0C32N7MYR1, F0C2TLMGST1) | Belum dibaca | — |
| U-7 | Isi 「pre-build alignment 7 categories」 | Daftarnya hanya ada di Slack | Nama item ini disebut Kent di OSD-116 c50071. Daftar tujuh kategorinya hanya ada di #nos-bo 1789549825.279199. Kent menulis 「我也已登进 build skill，Claude 会自动照跑」. Bahwa yang dimaksud adalah skill lokal tim adalah inferensi dari c50071 ("sync .claude/skills/build"), belum dikonfirmasi. Versi itu belum terlihat. Halaman 07.06 §三 (e) mengatur 「开工对齐清单」 sendiri. |
| U-8 | Kata di catatan approval untuk 打回补件 | Belum diputuskan | Kartu N07 memberi `kind: reject` pada tombol 打回补件, sehingga catatan platform menulis 「决定 / Decision：不通过 Rejected｜打回补件」 (SSCSD-435 comment 50592). Kontrak 04.4.1 / Notify §9.1 hanya mengenal `approve`/`reject`. Apakah kata-katanya perlu diubah, Felix atau Alden yang menentukan. Dicatat di build sheet v50 (观察·不改). |

## C. Selesai
(belum ada)

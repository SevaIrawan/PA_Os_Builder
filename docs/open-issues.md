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
  - Belum diverifikasi apakah lima kelas itu sudah ditulis di 04.6.
- **Cek ulang 2026-09-28:**
  - **04.10** (1738735636, lastModified Sep 26, dibaca penuh): lima kelas **tidak ada**. Kata 五类, 审批线, 权限／可见性, 启用自动化, >20, 改变别人的行为, dan Kent 审批 tidak ditemukan. Sisi tiket utama masih 「主单侧对象（SSCSD 四形状、主单字段）｜SSCSD／V1 范畴，Owner：Alden」 dan 「涉 SSCSD 主单侧→Alden（V1）」. Perubahan 26/9 kemungkinan hanya baris field GOV customfield_18288 (inferensi, belum dikonfirmasi).
  - **Canvas F0C32N7MYR1** (「04.10§二 权责判定标准·提案 v3」, dibaca penuh): masih 「提案 v3」. Cakupan 主单侧 ditandai 「〔待定〕…待 Kayden＋Alden 对齐」. Isinya belum memuat koreksi Alden tanggal 24/9.
  - **Thread 1789704362.435989** (induk + 14 balasan, dibaca penuh): Kayden setuju dengan syarat (balasan 6, 1790155348.686929: 「等 Alden 点头…我这边的执行者就落页」). Alden mengubah cakupan dan meminta 「Kayden，请你点头」 (balasan 11, 1790228926.781229). Sampai balasan terakhir (2026-09-25) belum ada jawaban Kayden dan belum ada pemasangan ke 04.10.
  - **Status:** 待决策, tidak berubah.
- **Update 2026-09-28 sore (dibaca penuh):**
  - **Field arsip (NTP/TCL):** aturan persetujuan resmi sekarang ada di **04.8 §四 v23** (lihat CLAUDE.md §3). Ini bukan lima kelas Alden secara utuh; hanya berlaku untuk field arsip.
  - **Field tiket utama SSCSD:** Alden OSD-116 c50647 (a): 「only the risk categories (making a field required on the shared screen, changing a shared object others already rely on, and the like) come to me」. Halaman 04.10 v21 belum memuat ini (lihat K-15).
  - **04.10 v21** tetap tanpa lima kelas. Status K-1 untuk objek lain (Jira bersama selain field arsip): 待决策.

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
- **Cek ulang 2026-09-28:** 04.4 (lastModified 2026-09-27) §十 masih 「`{流程名}｜{Spec 节点 ID}｜{模式编号或动作}`」, tanpa `n8n-` dan tanpa menyebut n8n. Judul bagiannya 「Automation 规则命名规范」. 04.4 tidak punya catatan perubahan, dan repo tidak menyimpan salinan penuh versi sebelumnya, jadi apa yang diubah pada 27/9 tidak terlihat dari halamannya. Menurut Alden (#nos-bo 1790567167.378069, 2026-09-28): 「04.4 §四 补了上面①②的机器读法（v34）」, yaitu cara mesin membaca Owner dari 维护说明 dan halaman SSOT daftar terkendali. Itu bukan §十. 04.9 §一 (Sep 26, dibaca penuh) masih merujuk 04.4 §十 dengan 「`{流程名}｜{节点 ID}｜{模式或动作}`」. 04.6 tidak dibaca ulang (lastModified tetap Sep 18). **Status:** 待决策, tidak berubah.

- **Cek ulang 2026-09-28 malam:**
  - 04.6 v22 §二-3 masih `…｜n8n-{动作}`. Kepala 04.6: 「第二节治理约束维持 V2 侧原文，修订提案见该节附注（🔲 待确认）」; catatan revisi itu tidak terlihat di teks halaman. Alden NSE-1137 c48376 menyebut 「04.6 §2, revision proposal 1」.
  - Checklist 工程审 **v2** (#nos-bo 1790582937.947389, Alden, 2026-09-28 15:08) butir 5 tetap 「件名：合『{流程名}｜N{x}｜n8n-{动作}』…｜机」. Tempat resminya (07.07) masih menunggu Kayden, jadi masih usulan.
  - Praktik di n8n (`search_workflows` "n8n-"): hanya 15 workflow OS开发流 yang memakai `n8n-`. 员工离职, Grade, 请假 tidak. Geri NSE-1137 c48263 (2026-08-14): 「Aligning names to the 04.4 §10 convention meant renaming N4 in n8n to 员工离职｜N4｜审批卡发送」.
  - Ditanyakan ke Alden: OSD-116 **c50670** butir 1 (2026-09-28). Registrasi 04.9 S-05 menunggu jawaban ini.
- **Cek ulang 2026-09-29 (nos-check):** Alden belum menjawab c50670 (OSD-116 terakhir c50670). Data baru: 04.9 v127 (Geri, 2026-09-28 23:16Z) mendaftarkan entry `qa01CkZBQfx8eLsK` dengan nama 「员工离职｜上游触发入口（S-05 等上游解雇 → 自动开单）」, tanpa `n8n-` dan tanpa ID node. Ini praktik Geri, bukan jawaban atas c50670. **Status:** 待决策, tidak berubah.

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
- **Pembaruan 2026-09-28** (bukti: `docs/evidence/2026-09-28-live-checks.md` E26–E29):
  - **04.3 dibaca ulang langsung** (lastModified Sep 24). Baris 「主单转入「已取消」（执行中止）」 sudah memuat 「该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」. Syarat Kayden c50442 (「待 04.3 改完」) terpenuhi sesuai c50445 (04.3 v35).
  - **Dua agen pembaca** memeriksa ulang 13 halaman Confluence, seluruh OSD-116 (191 comment), seluruh NSE-1137 (273 comment), dan #nos-bo. **Tidak ada source yang menyebut grup, peran, atau daftar orang untuk HR Ops & Data.**
    - Satu-satunya daftar yang pernah direncanakan adalah 「interim fixed list」 di NSE-1137 c50382 ②. Daftar itu untuk mekanisme lain (penerima N13), dan sudah dicabut oleh Kayden (Slack #nos-bo 1790231960.408669, butir 3) dan Kent (NSE-1137 c50473).
  - **Grup Jira:** satu-satunya grup HR adalah `SSCOS｜HR`, beranggota 2: Felix_HR dan Yuki Liew_HR (E27). Grup ini sudah masuk SSCSD dengan peran **Service Desk Team** (E28). Selisih dengan source: HR｜盘点与切分 menulis 「HR Ops & Data 3人」.
  - **Pertanyaan diarahkan ke Kent, bukan Kayden.** Alasannya:
    - pemetaan HR←`SSCOS｜HR` adalah keputusan Kent (c49545);
    - Kent yang mengusulkan hak Abort untuk grup peran HR (c50228, c50255/c50257);
    - persetujuan harian sisi SSCSD dipegang Kent sebagai Schema Owner (Alden, #nos-bo 1790228926.781229). Ini masih draf dan belum masuk 04.10 (lihat K-1).
  - **OSD-116 c50632** (Bambang, 2026-09-28 09:59 WIB, akun pribadi, ditujukan ke Kent, cc Alden, Felix, Kayden): minta konfirmasi pemakaian `SSCOS｜HR` untuk condition transisi 11 dan 9. Isi condition: service account + `SSCOS｜HR` + Project Owner SSCSD (04.3 §六). Urutan: tiket utama dulu, lalu sub-tiket (c50445). Selisih 3 orang vs 2 anggota ikut disebut. **Belum ada jawaban.**
  - Catatan lama di build sheet (§二 baris transition 11): 「配置前须经 04.3 Owner（Kayden Lee）确认」. Konfirmasi itu sudah diberikan lewat c50445, tapi build sheet belum mencatatnya. Perlu dimasukkan ke `docs/pending-buildsheet-updates.md`.
- **Felix_HR, OSD-116 c50644** (2026-09-28 11:55 +07, kepada Kent, cc Bambang, Alden, Kayden): 「盘点里 HR Ops & Data 是 3 人：Felix、Yuki、Tin（CAM）。Tin 现阶段只负责柬埔寨成员的 payroll 和招聘，不负责请假；绩效管理相关事项由 TL 直接负责，所以当时才没有加她进 SSCOS｜HR。该组保持 Felix 和 Yuki 两人即可，3 人与 2 人的差异就是这个原因。」 Felix menulisnya 「补充说明供你判断」, jadi keputusan memakai `SSCOS｜HR` tetap di tangan Kent.
- **Status:** 待决策. Selisih 3 vs 2 sudah dijelaskan Felix (c50644). Konfirmasi Kent atas c50632 belum ada. Transisi 11 dan 9 belum dipasang condition.

### K-10 · Kapan marker `nos-s05-term` ditulis (N20)
- **Build sheet S-05** (2096463922), tabel 暗号接口契约表 baris 「离职交接认领与审计」: 「建离职单**之前**先写 S-05 侧」. Aturan tabel yang sama: 「先认领后动作：任何写入口在执行写动作**之前**先写认领 marker」.
- **Build sheet yang sama, 【2026-09-24 补】**: 「现实建于入口返回 issueKey 之后写入」. Baris ini masuk ke 附表 sebagai 「本件与本页暗号接口契约表『先认领后动作』约束的适用」, status 「待办（建造侧提出·双签未表态）」.
- **Bambang, NSE-1137 c50575**: marker 「is written only after your entry returns `ok:true` with an `issueKey`」.
- **Geri, NSE-1137 c50585**: mengusulkan agar entry menulis klaim di case S-05 **sebelum** membuat tiket (「claim before create」), dan akan membangunnya 「unless someone objects」. Sampai 2026-09-28 (NSE-1137 dibaca sampai c50590) belum ada laporan bahwa ini sudah dibangun. Usulan ini dicatat di baris 附表 tersebut pada build sheet v52.
- Claude tidak memilih salah satu. Yang memutuskan: pemutus baris 附表 itu (「双签」). Siapa pemegang 双签 untuk baris ini tidak ditulis di baris tersebut. Inferensi, belum dikonfirmasi: yang dimaksud mungkin penandatangan teknis (Alden) dan bisnis (Kayden).
- **Bambang, NSE-1137 c50631** (2026-09-28 08:47 WIB, akun pribadi, cc Kent): menjawab usulan c50585 dengan 「No objection」. Alasannya: usulan itu sesuai dengan aturan build sheet di baris 「离职交接认领与审计」. Bambang juga meminta Geri, sebelum membangun, mengirim dua hal: (1) marker persis yang akan ditulis di case S-05, untuk didaftarkan di tabel 暗号 build sheet S-05 dan dicek terhadap Check Already Triggered N20; (2) nilai yang dikembalikan entry kalau klaim sudah ada tetapi tiket 离职 belum dibuat, karena N20 hanya menerima `ok:true` + `issueKey` (c50494). Balasan Geri belum ada.
- Jawaban c50631 **tidak** memutuskan kapan marker `nos-s05-term` milik N20 sendiri ditulis. Hal itu tetap menunggu 「双签」 di baris 附表.
- **Status (sampai 2026-09-28 pagi):** 待决策 (waktu penulisan marker N20). Balasan Geri atas c50631 masih ditunggu.
- **Koreksi 2026-09-29 (nos-check):** kalimat 「Balasan Geri belum ada」 di atas sudah basi. Geri menjawab di **NSE-1137 c50668** (2026-09-28 21:40 +07): marker klaim 「`[[nos-resign-claim:<S-05 case key>]]`」, ditulis sebagai internal comment di case S-05 「before anything is created」; tiga kemungkinan hasil (tanpa klaim → `ok:true, created:true, issueKey`; klaim ada dan tiket ada → `ok:true, created:false, issueKey`; klaim ada tanpa tiket → `ok:false` tanpa `issueKey` + nos-ops). Bambang menerima `ok:false` biasa (c50672); Geri setuju (c50674: 「Bare `ok:false` it is」). Status pembangunan menurut 04.9.3 v30 (Geri): 「★ 未闭：claim-before-create 尚未实施」, dan `Claim Check` memakai JQL `comment ~` yang 「上线前须实测能否精确命中」. Marker `nos-resign-claim` belum didaftarkan di tabel 暗号 build sheet S-05 (Geri c50668 butir 4: bentuknya bisa berubah setelah uji).
- **Status 2026-09-29:** 待决策 (waktu penulisan marker `nos-s05-term` milik N20, tetap menunggu 「双签」 baris 附表). Marker `nos-resign-claim`: 进行中 di sisi Geri, belum final.

### K-11 · Siapa yang membangun field tiket utama dan Screen untuk N07 (Disciplinary Case)
- **Kent, OSD-116 c50234 butir 2** (2026-09-19): 「Master-ticket fields (Return Count, HR Decision Basis, Cancellation Reason, Final Outcome, Approver) and the Screen (Disciplinary Case inherits the SSCSD default) → Alden / V1 domain — route these to Alden, don't file them yourself.」
- **Alden, #nos-bo 1790228926.781229 butir 5** (2026-09-24, balasan di thread 1789704362.435989): 「纪律处置那 5 个主单字段加屏幕（c50234 第 2 点转给我、至今未答）：不用等落页，现在就请 Kent 按五类判、走第五节流程建；挂 Disciplinary Case 那张共用屏时，设成选填直接做，要设必填再找我。」
- **Alden, OSD-116 c50558** (2026-09-26): 「另外审批卡回写的主单字段与 Screen（c50234 第 2 项）是前置，这件我另外回复。」
- **Bambang, OSD-116 c50595 (a)** (2026-09-26): menanyakan hal ini lagi ke Alden, dengan daftar field yang berbeda dari lima field c50234: HR decision basis, Return count, Cancellation Reason, Warning level, PIP parameters, Approver. Final Outcome tidak ada; Warning level dan PIP parameters ada.
  - **Ini kesalahan Claude:** pesan 24/9 sudah dikutip di CLAUDE.md §3, tapi butir 5-nya tidak dibaca sebelum c50595 dikirim. Aturan CLAUDE.md §0.10 dibuat karena ini.
- **Yang belum ditemukan:** laporan Kent bahwa field atau Screen sudah dibangun, baik di #nos-bo (dibaca penuh s.d. 2026-09-28) maupun di OSD-116 (s.d. c50632).
- **Konflik:** pesan 24/9 (Kent membangun sekarang) dan c50558 26/9 (Alden akan membalas terpisah) tidak saling menjelaskan. Claude tidak mendamaikannya.
- **Keputusan Bambang (2026-09-28):** c50595 (a) tidak dikoreksi; tunggu balasan Alden.
- **Update 2026-09-28, Alden OSD-116 c50647 (a)** (15:11 +07, kepada Bambang, cc Kent dan Felix): 「since 9/24, SSCSD main-ticket fields go through the same 04.10 process — Kent approves and builds them; only the risk categories (making a field required on the shared screen, changing a shared object others already rely on, and the like) come to me. So please file the field list to @Kent as a 04.10 three-cell request.」 Ini sejalan dengan pesan Slack 24/9 butir 5, dan menggantikan arah c50234 (「→ Alden / V1」).
- **Status:** terjawab oleh sumber (Alden c50647). Langkah berikutnya: permintaan 「04.10 three-cell request」 ke Kent. Format 04.10 harus dibaca penuh dulu sebelum membuat draf (CLAUDE.md §0.10). 
- **Update 2026-09-28 sore:** permintaan dikirim sebagai OSD-116 **c50658** (batch A, 8 item; evidence E35). Menunggu Kent: id field dan option.Dipindah ke bagian C.

### K-12 · Baris SUBMIT 04.7 masih memuat aturan 缺位 yang sudah dicabut di Spec
- **04.7 v51** (2026-09-24), baris RT-HR-DISCIPLINARY-SUBMIT: 「提交资格＝仅可由该员工登记的Direct Supervisor提交，缺位由HR Ops & Data代为受理」.
- **Kayden, OSD-116 c50461** (2026-09-24): mencabut kalimat 「直属上级缺位时由 HR Ops & Data 代为受理提交…」.
- **Felix, OSD-116 c50486**: 「S-05 Spec 已完成对应修订，页面现 v67（内部版本 v28）」.
- Sumber: audit build sheet v52, temuan A-07 (2026-09-28). Isi baris 04.7 dibaca oleh agen audit; Claude tidak membuka ulang sendiri.
- Claude tidak mendamaikan. Menurut catatan build sheet, isi baris kandidat itu wewenang Owner alur. **Status:** 待决策.

### K-13 · Siapa yang boleh menjalankan transisi 9 (确认重复)
- **Build sheet v52 §二**, baris transisi 9, kolom 允许执行者: 「仅服务账号」.
- **Kayden, OSD-116 c50445**: 「Abort Case（id 11）转态权限配给 HR Ops & Data 角色组；N07「确认重复」同口径」.
- **04.3 v35 §六**, paragraf 执法点: 「Jira workflow Condition 不承担"限定哪个人有权批"的职责——它收紧为"仅服务账号可转态"」. Paragraf ini berdiri berdampingan dengan tabel izin di bagian yang sama, yang menambahkan 处置角色组.
- Saat ini transisi 9 dijalankan oleh callback platform dengan akun layanan (c50558).
- Terkait K-9: grup mana yang dipakai masih menunggu jawaban Kent atas c50632.
- Sumber: audit A-14, C-10 (2026-09-28). **Status:** 待决策. Condition untuk transisi 9 dan 11 tidak dipasang sebelum ada jawaban.

### K-14 · Jalur manual sementara di 偏差登记
- **Build sheet v52**, 偏差登记 (baris ±198): mengutip jalur manual sementara dari Felix c49317.
- **Kent, OSD-116 c50381**: 「No interim manual path to design.」
- Sumber: audit A (di luar cakupan butir 3, 2026-09-28). Claude tidak mendamaikan. **Status:** 待决策.

### K-15 · Siapa yang memegang field tiket utama SSCSD: 04.10 v21 vs Alden c50647
- **04.10 v21** (1738735636, lastModified 2026-09-26, dibaca penuh 2026-09-28): 「本页只承载执行卡／子单侧的共享字段；主单字段归 SSCSD/V1」; tabel 「主单侧对象（SSCSD 四形状、主单字段）｜SSCSD／V1 范畴，Owner：Alden」; 升级线 「涉 SSCSD 主单侧→Alden（V1）」.
- **Alden, OSD-116 c50647 (a)** (2026-09-28 15:11): 「since 9/24, SSCSD main-ticket fields go through the same 04.10 process — Kent approves and builds them … So please file the field list to @Kent as a 04.10 three-cell request.」 c50648: 「「HR 判定依据」字段按 04.10 交 Kent 建」.
- Alden adalah Owner SSCSD/V1, jadi c50647 bisa dibaca sebagai pelimpahan dari Owner. Tapi halaman 04.10 belum diubah, dan perubahan cakupan di Canvas 04.10 v3 masih menunggu 「点头」 Kayden (K-1). **Inferensi, belum dikonfirmasi.** Claude tidak mendamaikan.
- **Format permintaan** (04.10 §五 langkah 1): Task di Project BO, ditugaskan ke Schema Owner, tiga isian 「要什么／哪条流程 Spec 哪一行需要／为何现有共享对象不够用」; 「口头／Slack 私聊不受理」.
- **Status:** 待决策. Sebelum mengajukan Task ke Kent, tanyakan ke Bambang apakah konflik ini perlu disebut di Task.

### K-16 · Isi kolom 「Owner 部门」 di indeks 04.9 untuk S-05
- **04.9 v124** (1693089805): kolom 「Owner 部门」 ada di header indeks, tapi tidak didefinisikan di §一 maupun di halaman lain (CQL NOSM, #nos-bo, OSD-116, NSE-1137, NSE-1143; dicek 2026-09-28).
- Satu-satunya petunjuk: Alden NSE-1143 c48482 (2026-08-18): 「04.9 登记表我会补一栏「建设归属」——这件挂了六天，就是因为登记时只写了 Owner 部门、没写谁建」. Jadi Owner 部门 bukan pembangun.
- Isi yang ada tidak mengikuti satu pola: 请假 HR; 员工离职 **BO** dan Grade **BO** (padahal keduanya di indeks HR 04.5 §九 dan 04.7 「Owner 部门 Project」＝HR); OS开发流 「流程治理（Kayden）」.
- Untuk S-05: 04.7 RT-HR-DISCIPLINARY-* 「Owner 部门 Project」＝HR; Spec Owner Felix (HR HOD).
- Ditanyakan ke Alden: OSD-116 **c50670** butir 2. **Status:** 待决策. Claude tidak mengisi.
- **Cek ulang 2026-09-29:** belum ada jawaban. Baris indeks baru entry Geri di 04.9 v127 mengisi kolom itu 「BO」 (Geri). Ini praktik alur 员工离职, bukan jawaban untuk S-05. **Status:** 待决策, tidak berubah.

### K-17 · Teks error di N05, N07, N20 memuat titik dua ASCII
- **Aturan:** 04.4.4 §五 (2102067228): 「抛错文本一律不含半角冒号 —— n8n 在最后一个半角冒号处劈开 error 文本，前半永久丢失」. Kasus yang sama: Alden NSE-1137 c50349 (N3 离职), Geri c50584 (N7 离职, exec 17235).
- **Kondisi S-05** (`get_workflow_details`, 2026-09-28; N05 `ad14f33e`, N07 `5c304eb6`, N20 `8937d700`): 11 `throw` di 7 node Code memuat titik dua ASCII.
  - N05: Extract Subject AccountId (`N05:` + marker `[[nos-s05-subject:…]]`), Alert Visibility Broken (`failed:`).
  - N07: Validate Input ×4 (`N07:`, `got:`, `Spec:`), Build N07 Card ×2 (`probe:`, `N07:`, nilai `status`), Check Notify Result ×1 (`N07:`, `):`, `idempotencyKey` `SSCSD-x:rN`, `JSON.stringify`).
  - N20: Map Judgment To Dismissal Category (`N20:`, nilai `judgmentType`), Check Entry Result (`N20:`, nilai `r.reason`).
  - N04 tidak punya node Code.
- **Yang teramati langsung** (`get_execution` 17235, N7 离职, hanya baca, 2026-09-28): teks `'N7 refused for SSCSD-DRY-NODATE: the main ticket has no …'` tersimpan sebagai `description`＝「N7 refused for SSCSD-DRY-NODATE」 (sebelum titik dua) dan `message`＝「the main ticket has no … [line 43]」 (sesudah titik dua); `stack` memuat teks utuh. Jadi di execution record bagian depan **tidak hilang**, tapi **terpisah** dari `message`. Teks itu hanya punya satu titik dua, jadi 「pertama atau terakhir」 tidak terbukti dari sini.
- **Yang belum terverifikasi:** field mana yang dikirim Error Handler `VUIgv9Ujj1KEoIne` ke nos-ops. Workflow itu tidak bisa dibaca lewat MCP (「Workflow is not available in MCP」); tidak dicari jalan lain. Klaim 「nos-ops hanya menerima potongan belakang」 (04.4.4 §五, c50349, c50584) = pernyataan sumber, **belum dicek langsung**.
- **Bukti dari S-05 sendiri:** belum ada. N07 dan N20 tidak punya execution error; satu-satunya execution error N05 (16341) berasal dari node Jira (404), bukan `throw` di Code.
- **Usulan perbaikan:** titik dua di teks tetap → `：`; nilai dari luar disanitasi `String(s).replace(/:/g, '：')` (preseden N2 离职, Alden c49892). Uji: satu jalur error per workflow, baca `description`/`message`.
- **Perbaikan dikerjakan 2026-09-28** (perintah Bambang, evidence E44): N05 `9b2ea463`, N07 `5a66fd9c`, N20 `6971acbc`. Uji 17562/17563/17564: `description: null`, teks utuh di `message`. Delapan `throw` sisanya diuji 17565–17572 (evidence E45): hasil sama, jadi 11/11 sudah dijalankan. Masih terbuka: isi alert nos-ops belum terverifikasi.
- **Status:** 已完成但未验收 (untuk S-05). Aturan 04.4.4 §五 sendiri tidak dipersoalkan.

## B. Tidak diketahui atau tidak bisa diakses

| # | Hal | Status | Alasan / sumber |
|---|---|---|---|
| U-1 | Space **NW**: 00｜知识库治理 (1647870014) dan 05｜页面结构与字段词汇表 (1656783199) | **Dilarang** | Laporan agent pembaca di sesi 2026-09-26: Rovo mengembalikan 404, Atlassian_MCP `getConfluenceContent` mengembalikan 403 "Space is restricted". Bukti mentahnya tidak disimpan. Aturan Bambang: tidak ada akses berarti dilarang. |
| U-3 | Skill lokal BO milik tim: `.claude/skills/build`, 主脑, 复盘官, `ledger/inbox` | Isinya tidak diketahui | Kent menyebutnya di #nos-bo (1789549825.279199, 1789704362.435989) dan OSD-116 c50071. Tidak ada di Confluence dan tidak bisa diakses dari sini. Skill `build` di repo ini dibangun **hanya** dari 07.06 §八. |
| U-4 | Identitas akun connector Slack | Belum diverifikasi | Hanya dipakai untuk membaca. Menulis ke Slack butuh persetujuan per tindakan. |
| U-9 | Pemetaan field S-05 「离职单关联状态」 ke `cf18140` tiket resign (N21) | Belum diketahui | Spec S-05 A 表: 「离职单关联状态｜N20／N21｜…｜系统自动写入（已建单并关联／信息待补齐／信息已补齐）」. Alden NSE-1137 c50645 (2026-09-28): 「"Awaiting completion" = the actual last working day (`cf18140`) is empty」 dan 「S-05 N21 reads the same field to tell whether completion is done」. Kapan nilai 「信息待补齐」 dan 「信息已补齐」 ditulis berdasarkan `cf18140` tidak tertulis di Spec, build sheet, maupun c50645. Inferensi, belum dikonfirmasi: `cf18140` kosong = 信息待补齐, terisi = 信息已补齐. Tidak dipakai sebelum dikonfirmasi Owner Spec (Felix) saat pemindaian `prebuild-scan` N21. Cek 2026-09-29: 04.9.3 v30 (Geri, blok entry) menulis 「「待资料补齐」＝`cf18140` 为空，上游 S-05 N21 读同一字段判完成」, sama dengan c50645; pemetaan ke tiga nilai field S-05 tetap belum tertulis. |

## C. Selesai

| # | Hal | Penyelesaian (2026-09-28, dibaca lewat Atlassian_Rovo / Slack, hanya membaca) |
|---|---|---|
| K-11 | Siapa yang membangun field tiket utama dan Screen N07 | Alden OSD-116 c50647 (a): Kent lewat proses 04.10; lihat bagian A K-11 untuk kutipan lengkap. |
| U-8 | Kata di catatan approval untuk 打回补件 | Alden OSD-116 c50647 (2026-09-28): 「the Decision line of the approval record will show only the button's own label when one is set — e.g. 「打回补件 · Return for info」 instead of 「不通过 Rejected｜打回补件」. This ships with batch 1B on 10/1.」 Tidak ada perubahan dari sisi S-05 sebelum 10/1. Apakah N07 sudah memberi label tombol yang cukup (`label`/`decisionLabel`) dicek ulang setelah batch 1B, **inferensi, belum dikonfirmasi**. Dua syarat Felix c50639 (nama pemutus dan apakah catatan bisa diedit) akan dijawab Alden terpisah (c50647). **Cek 2026-09-29 (nos-check):** perilaku ini sekarang sudah tertulis di 04.4.1 v16 dan Notify 契约 v16 (changelog v7): 「有决定名时该行只写决定名，不再加「通过／不通过」」, dan 04.9.1 v22 mencatat Slack Approval `active`, `ce9ea1f7-6d84-42cf-b6b4-029df8c4f93a`, versionId＝activeVersionId. Apakah perubahan 「决定」 itu sudah jalan di produksi sebelum 10/1 tidak disebut eksplisit di halaman itu dan belum dicek ke kode, **inferensi, belum dikonfirmasi**. Kalimat build sheet v56 P-7④ 「10/1 后回读实际记录格式」 tetap berlaku sebagai langkah cek. |
| U-2 | 04.12 (2091876367), 04.11 (1764524046), 04.4.2 (1751547935), 04.4.3 (2076508181), 04.4.4 (2102067228), 01｜OS 模块模型与铁律 (1674707036) | Keenamnya terbaca penuh, tanpa 404/403. Temuan untuk S-05: 04.12 hanya memuat marker OS 开发流 (OSD-*), **tidak** mengatur `[[nos-…]]`, jadi marker S-05 tetap di tabel 暗号 build sheet. 04.11 tidak punya baris domain S-05; baris HR = #sscos-hr (C0BHL8AE68G), yang termasuk red line tes 04.5.3. 04.4.2 (B6): konsumen terdaftar hanya 离职 dan Grade; pemanggil wajib 「收到 `ok:false` 必须告警 nos-ops 或走自身升级腿」 dan pendaftaran konsumen wajib sinkron dengan 04.9 §1.4. 04.4.3 dan 04.4.4 tidak dipakai S-05 sekarang. 01 berisi tiga 铁律 dan aturan modul. |
| U-5 | Salinan 04.9.3 terpotong | 04.9.3 dibaca ulang penuh (Sep 26): 17 blok H2 (halaman menulis 「共 14 块」). Entry resign Geri `qa01CkZBQfx8eLsK` **tidak** terdaftar di 04.9 maupun 04.9.3 (per versi Sep 26); menurut 「先登记后启用」 workflow yang belum terdaftar tidak boleh diaktifkan. Ini sisi Geri, tidak dicatat sebagai temuan milik S-05. **Cek 2026-09-29:** entry sekarang sudah terdaftar: 04.9 v127 (baris indeks) dan 04.9.3 v30 (blok H2), keduanya oleh Geri, disebut 「补登」. |
| U-6 | Tiga Canvas #nos-bo | Ketiganya dibaca penuh. F0C32N7MYR1 = 「04.10§二 权责判定标准·提案 v3」 (lihat K-1). F0C2VSAATHA = 「三流程复盘」 (Kent, 2026-09-17), asal usulan matriks tanggung jawab. F0C2TLMGST1 = 「改动分级·三层文案·提案 v1」; butir tujuan 「04.10 §六」-nya sudah ditarik Kayden (balasan 1790155348.686929: 「改落 04.12」). |
| U-7 | Isi 「pre-build alignment 7 categories」 | Dibaca penuh 2026-09-28 dari #nos-bo 1789549825.279199 (Kent, 2026-09-16): 「要扫的 7 类：① 载体建了没 ② 衔接契约清不清＋跟 Jira 一致没 ③ 判据可判＋运行时真值有没有 ④ 依赖（上游件／外部平台／数据源）就绪没 ⑤ 要动的页件我有没有权限（查 restriction）⑥ 异常缺位边界覆盖没 ⑦ 测试前置（夹具／测试档案／sandbox）有没有」, plus 「配套五条纪律：并行不阻塞／打包请示带建议／送审自带证据链／返工快吸收／认错快不越权」. Kent menulis 「我也已登进 build skill」. Tujuh kategori ini **tidak ada** di 07.06 §八 (nos-check B2, 2026-09-28: 19 butir, sama dengan salinan repo), jadi tidak ada di skill `build` repo ini. Atas keputusan Bambang (2026-09-28), daftar ini dipatuhi lewat skill terpisah `.claude/skills/prebuild-scan/`, bukan ditambahkan ke skill `build` (salinan terkendali 07.06). Versi skill lokal tim tetap tidak diketahui (U-3). |

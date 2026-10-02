# Antrean update build sheet S-05 (2096463922)

Draf untuk build sheet dikumpulkan di sini supaya nanti ditulis **sekaligus dalam satu versi**. Tujuannya menghindari naik versi hanya untuk perubahan kecil (permintaan Bambang, 2026-09-28).

Aturan:
- **Isi file ini hanya draf, bukan izin menulis.** Penulisan ke Confluence menunggu perintah eksplisit Bambang (CLAUDE.md §3).
- Sebelum menulis, ambil versi terbaru halaman dulu (07 §二「先查后写」). Jalankan dryRun, lalu tulis. Setelah itu baca ulang dan bandingkan per tag.
- Semua perubahan bersifat **menambah** (【补】). Teks lama tidak dihapus.
- Bahasa: Mandarin, mengikuti isi halaman.
- Kalau item sudah ditulis ke build sheet, pindahkan ke bagian "Sudah ditulis" dan cantumkan versi halamannya.

Versi build sheet terakhir yang dibaca: **v61** (2026-09-29T09:13:39Z).

---

## Antre

Sisa yang **belum** ditulis setelah v61. Semua ditulis **sekaligus dalam satu versi** saat Bambang memerintahkan (permintaan Bambang, 2026-09-29).
- **P-6.7** (menunggu orang lain): C-01 (backfill nama RT di 04.7; masih belum per 04.7 v51, E69), C-26 (isi §七, keputusan Kayden), D-13 (marker patroli, Geri c50631 dan K-10). A-14 sudah dipindah ke P-17.
- **P-6.8** (menunggu keputusan Bambang): B-5, B-14, D-9, D-16, A-01 (catatan versi dasar Spec v67). D-4 dipindah ke P-22 (2026-10-02). B-2 terjawab oleh draf P-18 (暗号表 `nos-s05-dup`); C-27 selesai (E61, v57).
- **P-17**: transisi 9/11 setelah Kent c50705, termasuk A-14 dari P-6.7 (detail di bawah). **HOLD** (Bambang 2026-09-29: 「Kau hold dulu ini」): pemasangan condition 9/11 di UI Jira dan penulisan P-17 ditunda sampai Bambang melanjutkan.

- **P-22**: D-4, catatan penyimpangan exec 17290 tanpa penanda TEST (detail di bawah). Disimpan atas perintah Bambang 2026-10-02 「Simpan ke antrean」.

### P-22 · Blok 【2026-09-26 N07 实跑】: exec 17290 tanpa penanda TEST (D-4, DRAF 2026-10-02)

Sudah dicek (2026-10-02): n8n `search_executions` N07 `77PepnEWGqTOCI61` (19 eksekusi, 17290 paling awal); `get_execution` 11 eksekusi pengirim kartu (17290 penuh; 17295, 17506, 17508, 17510, 17554, 17556, 17949, 17954, 17956, 18025 node Build N07 Card / Payload For Notify); 04.5.3 v16 (berlaku 2026-09-26) dan v23 dibaca penuh, §三 sama; Notify contract v18 dibaca penuh; build sheet v64 (blok N07 实跑 2026-09-26, 2026-09-28 (一)(二), 「N07 件改件两次」②, 建设备注 N07 2026-09-26 补); evidence E11, E13, E38, E39.

Hasil per eksekusi (penerima semua DM `D0BUSQHBJF2`, whitelist 甲): 17290 tanpa penanda; 17295, 17506, 17508, 17510 penanda di baris pertama `body`, tidak tebal (sudah tercatat di 「N07 件改件两次」②); 17554 dst. penanda di `title`, tebal. Yang belum tercatat hanya 17290.

**Letak:** setelah poin 「执行 17290：发卡成功…」 di blok 【2026-09-26 N07 实跑】.

> 【2026-10-02 补｜偏差如实登记】执行 17290 所发审批卡**未带** 04.5.3 第三节统一测试标识：n8n 执行记录「Build N07 Card」输出 body＝「Case: SSCSD-435\n审核轮次 · Review round: 1」，无标识行（2026-10-02 实读）。成因：本件测试标识于 2026-09-26T13:14:30Z 方经 update_workflow 加入（versionId `4e076465`，见建设备注「N07 审批卡发送」2026-09-26 补），17290 跑于 13:10:04Z，用的是加入前的版本。当时现行 04.5.3 v16（2026-09-25）第三节已载「测试模式发出的每条 Slack 消息必带 `🧪 【SSCOS 测试 · 请勿处理 ｜ TEST — do not action】`」，不分私信与频道。收件人为建造人本人 DM（白名单甲），未外发。本件全部 11 次发卡执行逐次实读：仅 17290 无标识；17295 起均带，其中 17295／17506／17508／17510 标识在正文首行、未加粗，已于 2026-09-28 改件（versionId `5c304eb6`，见建设备注「N07 件改件两次」②）。

- Terjemahan: kartu exec 17290 tidak membawa penanda tes karena penanda baru ditambahkan pukul 13:14:30Z, sedangkan 17290 jalan pukul 13:10:04Z. Aturan v16 saat itu sudah mewajibkan penanda di setiap pesan Slack mode tes. Penerimanya DM builder sendiri. Dari 11 kartu, hanya 17290 tanpa penanda.
- Sebelum ditulis: ambil build sheet terbaru dan pastikan poin 「执行 17290：发卡成功…」 masih ada; cocokkan ulang local-id titik sisip.
- Belum dicek: render kartu 17290 di Slack (data n8n hanya payload ke Notify).

### P-17 · §二 baris transisi 9 dan 11 setelah Kent c50705 (DRAF, 2026-09-29)

Sudah dicek (2026-09-29): build sheet **v58** §二 baris transisi 9 (`a1699b53-…`) dan 11 (`1311cdec-…`) dibaca penuh; OSD-116 s.d. **c50705** (c50632, c50644, c50695, c50705 dibaca penuh; tidak ada comment setelah c50705); 04.3 **v36** (2026-09-29 02:16Z, Kayden): diff v35→v36 dibaca penuh, hanya kalimat 维护单 Owner (「治理页 Owner 矩阵」→「目标页面维护说明登记的 Owner」), §六 baris transisi tidak berubah.

Digabung dari P-6.7 A-14 (C-10, D-2): sumber c50445, c50632, Felix c50644 (sudah di 附表 v53/v57); transisi 9 「仅服务账号」 vs Kayden c50445 「N07「确认重复」同口径」 (K-13); baca ulang `isConditional` setelah condition dipasang.

**Keadaan condition (dicek 2026-09-29):** build sheet v58 mencatat 「确认前 condition 不配」 (menunggu Kent); Kent baru menjawab c50705 (2026-09-29 12:52 +07). Cek API tidak bisa: semua 10 tiket tes Disciplinary Case (SSCSD-411–442) sudah di status akhir, jadi transisi 9/11 tidak muncul di daftar transisi mana pun; membuat tiket tes baru = menulis, butuh izin. Default tulis: **varian A (belum dipasang)**, kecuali Bambang memberi tahu sudah memasang. Catatan: condition = aturan izin transisi, termasuk kelas 「izin/visibilitas」 di daftar lima kelas Alden (masih draf, CLAUDE.md §3).

**① §二 transisi 9, kolom 允许执行者, setelah `b28d09280040`:**

> 【2026-09-29 补】上条「待 Kent 答 OSD-116 c50632」已答：Kent OSD-116 c50705「yes, use SSCOS｜HR for the HR Ops & Data transition condition (Abort Case id 11 and N07 Confirm duplicate), per 04.3 v35 §六」；成员 Felix、Yuki，附条件见页首附表 Abort Case 行 2026-09-29 补。c50632 所提 condition 为「service account + SSCOS｜HR + SSCSD Project Owner」。本行原文「仅服务账号」与 Kayden c50445「N07「确认重复」同口径」仍并存；04.3 §六「执法点」段「Jira workflow Condition 不承担"限定哪个人有权批"的职责——它收紧为"仅服务账号可转态"」与同节转态权限表亦并存（04.3 现行 v36，v35→v36 未改 §六 转态行），建造侧不调和。本转换现由平台审批卡回调以服务账号执行（c50558）。〔varian A — belum dipasang〕condition 尚未配置。〔varian B — sudah dipasang〕condition 已于 {tanggal} 经 UI 配置（人：Bambang），允许：{isi}；API 回读 {bukti}。

**② §二 transisi 11, kolom 允许执行者, setelah `b28d09280041`:**

> 【2026-09-29 补】上条「已于 OSD-116 c50632 请 Kent 确认，截至 2026-09-28 未答」已答：Kent OSD-116 c50705 同意用 SSCOS｜HR（原文见本行上方页首附表 Abort Case 行 2026-09-29 补）；执行顺序「Order stays as in c50445: main ticket to Cancelled first, then the open sub-tickets.」〔varian A〕condition 尚未配置。〔varian B〕condition 已于 {tanggal} 经 UI 配置（人：Bambang），允许：{isi}；API 回读 {bukti}。

**③ §二 transisi 11, kolom 本轮回读 (`db2a9eb1-…` 「UI 确认未挂 screen；待补 API 回读；未实跑」), setelah paragraf itu — hanya kalau varian B:**

> 【2026-09-29 补】condition 配置后回读：{getTransitions / isConditional 结果，执行账号}。未实跑。

- Dasar tidak mendamaikan: CLAUDE.md §0-7; K-9 dan K-13 di `docs/open-issues.md`.
- Sebelum ditulis: ambil build sheet terbaru, cek OSD-116 setelah c50705, 04.3 versi terbaru §六.

## Sudah ditulis

### v61 (2026-09-29T09:13:39Z, akun pribadi Bambang, perintah 「Tulis P-21 ke build sheet dulu」)

Ditulis sebagai **P-21** (3 `insertNodeAfter`; dryRun → skrip: setelah 3 sisipan dicabut, isi = v60 (beda hanya penulisan entity HTML); setiap sisipan tepat setelah titik tujuannya; baca ulang `diffConfluenceContentVersions` v60→v61: +5/−1, 3 hunk, hanya tiga paragraf ini; evidence E77).
- (a) 第五区 N05 块, setelah `b28d092a0110`: 【2026-09-29 订正】 versionId sekarang `664828ee` (UI save 08:17:58Z, beda hanya sticky 16d99dee); pinData dilepas menurut pernyataan Bambang (08:59:58Z), isinya tidak terbaca MCP. Catatan: draf P-21 menyebut 「配置对应表 N05 行」 juga menulis `dd065a45`; saat dicek di v60, `dd065a45` hanya ada di blok N05, jadi hanya satu tempat yang dikoreksi.
- (b) 偏差登记, setelah `b28d0928002b`: 【2026-09-29 补｜登记次序偏差】 dengan kutipan 04.9 v138 §一 「n8n 照登记实现，实况要变，先改登记再改件，不得反向以 n8n 实况倒改规则。」
- (c) 附表 「本流程 n8n 件 04.9 登记」 kolom 解除判据, setelah `b28d0929008c`: 04.9.7 v2→v3 dan 04.9 v137→v138. Kolom 状态 tidak diubah (masih menulis 「04.9 v130／04.9.7 v2 已回读」).

### v60 (2026-09-29T08:27:21Z, akun pribadi Bambang, perintah 「Kau kerjakan step by step A sampai F」 butir C)

Ditulis sebagai **P-20** (28 operasi: 23 sisip, 5 ganti label; dryRun → skrip: identik dengan v59 setelah sisipan dicabut dan label dikembalikan; baca ulang v60 = dryRun, 23/23 node baru ada; evidence E75). P-20 mencakup seluruh P-19 di bawah, dengan ③ diperbarui (N07 sudah tidak noWrite), ditambah: N07 改件 dan tes SSCSD-448～450 (E73), N05 perbaikan E9 dan tes 18082 (E74), 订正 C-15 (到期日期／纪律记录有效期 sudah ada di Spec, tidak perlu ditanyakan), 订正 「离职单关联状态」 (待决策→未开始; pemetaan ada di Spec A + NSE-1137 c50645), 定案 「先认领后动作」 (待决策→被阻塞; menunggu claim-before-create Geri, 04.9.3 v30), 暗号表 `nos-s05-term` (待决策→进行中), baris 测试单登记 SSCSD-448/449/450, statistik 附表 (已验证 6／已完成但未验收 3／进行中 3／待决策 10／被阻塞 13／未开始 7). Catatan: pesan versi menulis 「四行改标」; yang benar 5 label (附表 3, 暗号表 1, 载体对象表 1).

#### P-19 · Field batch A dibangun, Kent OSD-116 c50725 (DRAF, 2026-09-29)

Sudah dicek (2026-09-29): OSD-116 s.d. **c50725** (dibaca penuh; tidak ada comment setelahnya); NSE-1137 s.d. c50702 (tidak ada yang baru); editmeta SSCSD-442 (E72); build sheet **v59** (salinan `scratchpad/p18/v59.html`): semua baris tabel yang menyebut c50658／主单字段／取消原因／Screen dibaca penuh. **Belum dibaca:** 04.10 §三 v23 (registrasi field; klaim Kent), layar 14761 (klaim Kent). Kalimat di draf yang bersandar pada dua hal itu ditulis sebagai 「Kent 所述」.

Baris transisi 9 dan 11 (§二) juga menyebut 「取消原因」 belum ada. Tambahan untuk kedua baris itu **tidak** dimasukkan ke sini, tetapi ke P-17 (HOLD), supaya satu baris tidak dapat dua 【补】 terpisah.

**① 附表 「主单专属 Screen 未建」 (`4e23eeaaa8cb`): kolom 状态 被阻塞 → 进行中, 【补】 di kolom catatan:**

> 【2026-09-29 补】Kent OSD-116 c50725 答 c50658（批次 A）：「all 14 fields are built, optional on the shared SSCSD screen 14761 (tab 14832), and registered in 04.10 §三 (v23).」建造侧同日以 Backend Operations 账号读 SSCSD-442 editmeta 回读：14 个字段均在、均为选填、选项与 c50725 表一致（customfield_18326／18327／18329／18331／18333／18334／18328／18336／18337／18338／18335／18330／18332／18339）。屏 14761（tab 14832）与 04.10 §三 v23 登记系 Kent 所述，建造侧未另读。批次 B（Final Outcome、离职单关联状态、下游流程触发状态、Show Cause回复截止日期、入口字段）尚未申请；解除判据④ createmeta 回读未做。本行状态由「被阻塞」改为「进行中」，依 Anchor 04 §七.6；证据：c50725 与上述 editmeta 回读。

**② §一 配置对应表 「主单专属 Screen」 (`aee027bb-…`): 状态 被阻塞 → 进行中, 【补】:**

> 【2026-09-29 补】本行状态由「被阻塞」改为「进行中」，依 Anchor 04 §七.6；证据：批次 A 十四字段已建于共用屏并经 editmeta 回读（Kent OSD-116 c50725；见页首附表对应行 2026-09-29 补）；批次 B 未申请。

**③ §一 配置对应表 N07 (`aaad9eef-…`): 状态tetap 进行中, 【补】:**

> 【2026-09-29 补】上条「主单回写字段待 Kent（OSD-116 c50658）」已答：批次 A 已建（Kent c50725，editmeta 回读见页首附表「主单专属 Screen」行 2026-09-29 补）。Kent 原文：「You can switch the N07 writeFields from noWrite to these ids now.」截至本补，N07 writeFields 仍为 noWrite，未改。Kent 同条注意事项：选项值「Take the exact strings from this table or from editmeta, not from c50658」；纪律记录有效期「empty means 「永不自动失效」… Leave it empty rather than writing a sentinel date」。本行状态不变。

**④ 附表 模式九 (`635936c72c8c`): 状态 tetap 已验证, 【补】:**

> 【2026-09-29 补】上条「「HR 判定依据」已于 OSD-116 c50658 向 Kent 申请（批次 A 第 1 项），待建」：已建，「HR判定依据 · HR Decision Basis」customfield_18326（Kent c50725；editmeta 回读见「主单专属 Screen」行 2026-09-29 补）。N10／N14／N17 尚未建件。本行状态不变。

**⑤ §一 配置对应表 N28 执行中止 (`dcef6713-…`): 状态 tetap 进行中, 【补】:**

> 【2026-09-29 补】上条「「取消原因」为主单侧字段、尚未建」：已建，「取消原因（纪律处置） · Disciplinary Cancellation Reason」customfield_18331，选项 Duplicate Case (15986)／Withdrawn (15987)／Dismissed (15988)／员工已离职或案件失效 (15989)（Kent c50725，editmeta 回读）。Kent 原文：「The name differs from the OS dev flow's 「取消原因」 cf18151, which is text. Do not mix the two.」本流程尚无任一环节写入该字段。本行状态不变。

**⑥ §二 transisi 3 Reject (`9924efe5-…`) dan 8 Withdraw (`377bc48a-…`), 【补】 yang sama di keduanya:**

> 【2026-09-29 补】上文「该字段尚不存在」「该 Issue Type 现无属于 S-05 的取消原因字段」已不准确：「取消原因（纪律处置）」customfield_18331 已建（Kent OSD-116 c50725，editmeta 回读）。本转换 post function 仍只写 Resolution，未写该字段（上文实跑结果不变）；Spec 增补区 A「取消原因」由 N05／N06／N07／N28 使用，写入方式建造侧尚未配置。

**⑦ §八 「带主体端到端／负向／权限测试」 (`5882ce8b-…`), 【补】:**

> 【2026-09-29 补】上条缺口③「主单回写字段与专属 Screen 未建」：批次 A 字段已建于共用屏（Kent OSD-116 c50725，editmeta 回读）；专属 Screen 已改为共用屏（页首附表对应行 2026-09-29 补）；批次 B 未建。缺口①②不变。

Tidak dimasukkan: C-15 (P-6.7, menunggu Felix soal 到期日期／纪律记录有效期). c50725 menyebut arti nilai kosong 纪律记录有效期, tetapi C-15 adalah pertanyaan ke Felix dan tidak didamaikan sendiri (CLAUDE.md §0-7).


### v59 (2026-09-29T06:51:23Z, akun pribadi Bambang, perintah 「Tulis P-18 ke build sheet」)

Ditulis lewat Atlassian_MCP `updateConfluenceContent` snapshotToken `v:58`, 164 operasi: 附表 41 baris (sel 状态 diganti label baru + 【补】 di akhir sel 解除判据; baris 41 tidak diubah karena sudah di v58), 暗号表 8 + §一 配置对应表 24 + tabel objek 8 (label baru disisipkan sebagai paragraf pertama sel 状态, 【补】 di akhir sel; teks lama tetap), plus dua 【补】 statistik (附表 setelah `b28d0928001f`, §一 setelah `b28d0928003d`). localId baru `b28d09290104`–`b28d0929018e`. dryRun dibandingkan skrip dengan v58 + 164 operasi: identik. Baca ulang v59 penuh: identik dengan hasil dryRun, 164/164 node ada. Evidence E71. Hitungan: 附表 42 = 已验证 6／已完成但未验收 3／进行中 2／待决策 12／被阻塞 13／未开始 6; 暗号表 8 = 进行中 2／未开始 3／待决策 1／被阻塞 1／已验证 1; 配置对应表 24 = 进行中 7／被阻塞 8／未开始 9; tabel objek 8 = 已完成但未验收 4／已验证 3／被阻塞 1.

#### P-18 · Kolom 状态 附表 ikut Anchor 04 §七.6, statistik dihitung ulang (DRAF, 2026-09-29)

- Dasar: Anchor 04 §七.6 「事实只标为：已验证／已完成但未验收／进行中／待决策／被阻塞／未开始；附 Jira、Confluence、回读、测试或团队回复。」 dan aturan Bambang CLAUDE.md §0-13 (build sheet ikut dokumen asli).
- Keadaan v58: hanya baris 「本流程 n8n 件 04.9 登记」 yang memakai label Anchor. Baris lain memakai 阻塞中／待办（…）／已解封（tanggal·dasar）／不适用. Paragraf 统计 menghitung dengan kosakata lama (terakhir: 「共 42 行；阻塞中 5 行；待办 28 行…；已解封 9 行」, 2026-09-28).
- Cara kerja saat draf dibuat:
  1. Baca build sheet versi terbaru, daftar **semua** baris 附表 dengan status sekarang dan 解除判据-nya.
  2. Untuk tiap baris, tentukan label Anchor **dari bukti** (pageId/comment id/hasil API), bukan dari terjemahan kata lama. Kalau bukti tidak cukup untuk memilih label, baris itu ditandai dan ditanyakan ke Bambang, tidak ditebak.
  3. Status lama tidak dihapus tanpa jejak: tiap baris yang diganti dapat 【补】 singkat 「状态由「…」改为「…」，依 Anchor 04 §七.6；证据：…」 (pola v58).
  4. Setelah semua baris final, tambahkan 【补】 统计 baru (hitungan per enam label), paragraf 统计 lama tidak dihapus.
- Tabel 「统计：24 个节点行」 di §五 juga memakai kategori sendiri (已建／可建／阻塞／待对端); apakah ikut diseragamkan ditanyakan ke Bambang saat draf ditunjukkan.
- Draf ditunjukkan dulu ke Bambang sebelum ditulis.

**Draf usulan label (dari bukti yang tercatat di tiap baris build sheet v58, dibaca 2026-09-29).** Nomor # = urutan baris di 附表 v58. ⚠ = bukti di baris sudah lama, cek ulang sumbernya sebelum ditulis. ❓ = label lain juga masuk akal, Bambang yang memilih.

Pegangan yang dipakai (Anchor 04 §七.6 tidak mendefinisikan tiap label; pegangan ini **disetujui Bambang 2026-09-29**: 「Setuju pegangan arti label」):
- 被阻塞: menunggu tindakan/jawaban pihak lain, bukan keputusan.
- 待决策: menunggu keputusan (termasuk 「双签未表态」).
- 未开始: pekerjaan pihak build yang belum dimulai.
- 进行中: sebagian sudah dikerjakan.
- 已完成但未验收: pihak build sudah selesai dan membaca ulang, tapi pemilik belum memeriksa.
- 已验证: sudah terbukti dari jawaban tertulis pihak yang berwenang atau baca ulang, dan tidak menunggu pemeriksaan lagi.

| # | 事项 (singkat) | Status sekarang | Usulan label | Bukti | Catatan |
|---|---|---|---|---|---|
| 0 | 纪律处分记录 Registry Project 无已裁决 key（04.1 §一 该行为「候选｜ | 阻塞中 | **被阻塞** | Dicek 2026-09-29: 04.1 **v47** §一 baris 纪律处分记录 masih 「候选｜待N5」, key dan Owner 🔲; 04.8 **v23** §三 「归属 Project」 masih 「🔲 候选｜待N5」 | ✓ dicek ulang (E69) |
| 1 | NTP 岗位受控清单待标准化（T-5：「前两项已具备，岗位待标准化」）。技术签 c49696／c | 阻塞中 | **被阻塞** | Alden c50695: field posisi NTP belum dibuat (v57 【补】) |  |
| 2 | 模式九组件扩展（N07 审批交互）。技术签 c49696 已定案：v5 已于 2026-08-2 | 已解封 | **已验证** | Alden c50576 (1A live), c50689 (1B live); N07 diuji SSCSD-435, 437–442 (§八) | sisa field/Screen dilacak di baris 13 dan c50658 |
| 3 | 邮件收信与归档件未具备（T-5：「专用信箱＋收信件｜未具备（新平台件）」）。技术签列为冻结前须立 | 阻塞中 | **被阻塞** | Dicek 2026-09-29: 04.4 **v35** §十一 共享组件索引 (7 komponen) tidak memuat komponen email, bahkan sebagai 「在建」; Spec v67 (T-5) tidak berubah sejak 9/24; OSD-116 (salinan s.d. 9/26 + c50558–c50705) tidak ada jawaban soal kotak surat | ✓ dicek ulang (E69) |
| 4 | 两个 Request Type 双语名称未确认（04.7 RT-HR-DISCIPLINARY- | 阻塞中 | **被阻塞** | Dicek 2026-09-29: 04.7 **v51** (tidak berubah sejak 9/24): SUBMIT masih 「双语Request Type／Slack展示名称待流程Owner确认」, EVENT belum punya nama dua bahasa (nama dari Felix c50261 belum masuk 04.7) | ✓ dicek ulang (E69); juga menjawab P-6.7 C-01 |
| 5 | 七个部门 Collab 频道：bot 入频道与 04.11 登记。频道 ID 已由 Felix  | 待办 | **被阻塞** | Syarat ①③ terpenuhi (9/21); ② registrasi 04.11 menunggu Alden |  |
| 6 | N09 附件回贴端到端未验（技术签列为上线前探针；Grade 通道二在建同形制）。Slack A | 待办 | **未开始** | N09 belum dibangun; e2e belum dijalankan |  |
| 7 | 员工离职 Spec 系统触发接收入口（T-5：「缺口已登记，Owner Kent」）。Kent  | 待办 | **进行中** | Entry qa01CkZBQfx8eLsK sudah dibangun (Geri c50674), belum dipublish | ❓ tumpang tindih dengan baris 35; bisa juga 被阻塞 |
| 8 | S-06（降级＋降薪）与 S-15（扣除薪水／花红处分执行）两份 Spec 均待设计，N22／N | 待办 | **被阻塞** | Dicek 2026-09-29: HR｜盘点与切分 (1745158181) **v40**: S-06 (Low, 「待该体系明确后再排期」) dan S-15 (High) masih kandidat tanpa link Spec; CQL judul 「降级／扣除／花红／S-06／S-15」 di NOSM = 0 halaman (probe pembanding: judul 「纪律」 menemukan Spec S-05, jadi pencarian judul berfungsi) | ✓ dicek ulang (E69) |
| 9 | 测试档案（NTP）待核实 | 待办 | **被阻塞** | 5 dari 6 cek lolos; sisa 1 (Talent Status Kent) harus dibaca Kent sendiri |  |
| 10 | 部门值→Team Project 对照表与兜底。技术签 c49696 明写「部门值→板 key  | 待办 | **待决策** | Dua 🔲 di tabel perlu konfirmasi Felix |  |
| 11 | Inz9／Marketing 两个 Collab 频道是否仍使用。两部门已并入 CRM（Alde | 待办 | **被阻塞** | Felix c50261 ④ sudah memutuskan; registrasi 04.11 menunggu Alden |  |
| 12 | 测试期不得向 sscos-hr 发送 | 待办 | **未开始** | Notifikasi D (ke sscos-hr) belum dibangun; aturan uji mode belum dipasang | ❓ kalau dianggap aturan yang sudah diterapkan di N07 (DM), bisa 进行中 |
| 13 | 主单专属 Screen 未建 | 待办 | **被阻塞** (Bambang 2026-09-29: 「Baris 13 ikut arah layar bersama」; sisa pekerjaan = field di layar bersama, menunggu Kent c50658) | Dicek 2026-09-29: sumber terbaru mengarah ke **layar bersama**, bukan layar khusus: #nos-bo 1790228926.781229 butir 5 (dikutip di c50658) 「挂 Disciplinary Case 那张共用屏时，设成选填直接做」; Alden c50647 (a) ① Approved By 「already on the Disciplinary Case edit screen」, ② field harus ada di 「Disciplinary Case edit screen」; field tiket utama lewat 04.10/Kent (c50647 (a)). 04.10 **v22** (hari ini) masih 「主单字段归 SSCSD/V1」 (K-15). Syarat ①–② baris ini (tempat daftar Screen + layar khusus) tidak dijawab langsung | ✓ diputuskan Bambang: ikut layar bersama; 【补】 khusus di bawah |
| 14 | Kayden 两项提点未见 Felix 回复（c49740「提点」段，不构成退回）：①直属上级缺 | 待办 | **待决策** | Poin ① gugur (Kayden c50461); poin ② (Raymond) belum dijawab Felix |  |
| 15 | 《Nexmax WFH工作规章制度（正式版）》无可追溯版本 | 待办 | **被阻塞** | Felix belum memberi lokasi dan versi resmi |  |
| 16 | 请求级整单时限未定（04.7 两行 SLA 列均为「请求级整单时限 🔲 未定占位」）。04.7  | 待办 | **待决策** | Nilai SLA per request belum ditetapkan Felix |  |
| 17 | 形状 C 是否须配「已改道」出口 | 待办 | **待决策** | 双签未表态 |  |
| 18 | N28 案件失效中止的执行人 | 已解封 | **已验证** | Kayden c50445; 04.3 v35 §六 dibaca (sisa dipindah ke baris 34) |  |
| 19 | 现网 Resolution 值与 04.3 §7.1 不符（本轮实测）。04.3 §7.1 只允 | 待办 | **待决策** | 双签未表态 |  |
| 20 | JSM 原生 SLA 未按 Spec C 表配置（本轮实测）。SSCSD-411 建成即挂上 J | 待办 | **未开始** | Arah sudah jelas (04.4 §8.1); konfigurasi belum dimulai |  |
| 21 | 两个 scheme 的 id 本轮未核实 | 待办 | **待决策** | 双签未表态 (id scheme belum dikonfirmasi Alden) |  |
| 22 | 主体标识 marker 是否跨流程共用同一 token。员工离职在 SSCSD 主单审计 com | 待办 | **待决策** | 双签未表态 |  |
| 23 | 跨流程 link 源两份 Spec 写法不一致 | 已解封 | **已验证** | 04.2 §三 dikutip (2026-09-19) |  |
| 24 | Notify 调用契约 §9.14 与 04.4.1 记载不一致 | 已解封 | **已验证** | Notify kontrak v14 dibaca (2026-09-28) |  |
| 25 | SSCSD 主单侧建设与验收分工（谁建、谁验收） | 已解封 | **已验证** | Kent c50198, c50073 |  |
| 26 | 本流程暗号／marker 精确语法（07.06 §三 (b) 六件套第 2 项） | 已解封 | **已完成但未验收** | Sintaks diputuskan pihak build mengikuti preseden, tercatat di 暗号表; belum ada pemeriksaan pemilik | ❓ bisa juga 已验证 |
| 27 | 主单载体（Issue Type＋Workflow） | 已解封 | **已完成但未验收** | Dibangun dan dibaca ulang lewat API; verifikasi Alden ditunda; readback 3 transisi dan uji Abort Case belum |  |
| 28 | N03 的 Slack 表单分派钩子 flow 值未登记 | 待办 | **未开始** | Menunggu N03 dipublish (N03 belum dibangun) | ❓ bisa juga 被阻塞 |
| 29 | 四条原地转换使模式九重复裁决主锁失效 | 已解封 | **未开始** | Pihak build memutuskan tidak membangun sendiri; uji negatif klik ganda belum dijalankan (digabung ke e2e N07) | ❓ |
| 30 | 本流程未登记为 B6 与 NTP 实体字段的消费方 | 待办 | **待决策** | 双签未表态 |  |
| 31 | N03 是否须复用身份件未定 | 待办 | **待决策** | 双签未表态 |  |
| 32 | 主单 Issue Type 命名与 04.0 §二／04.2 §一 的登记名不一致 | 待办 | **待决策** | 双签未表态 |  |
| 33 | S-05 各 n8n 件切 active 的次序；Kayden 已裁「N14 通过之后、N15  | 待办 | **被阻塞** | Kayden sudah memutuskan, tapi belum ditulis ke OS 开发流 Spec (v40) |  |
| 34 | Abort Case（id 11）转态权限配给 HR Ops & Data 角色组，N07「确认 | 待办 | **未开始** | Kent c50705 memutuskan grup; condition 9/11 belum dipasang | → kalau Bambang sudah memasang sebelum ditulis: ganti sesuai hasil baca ulang |
| 35 | 离职侧「系统触发入口」qa01CkZBQfx8eLsK 发布 | 阻塞中 | **被阻塞** | Entry belum dipublish (Alden) |  |
| 36 | upstreamSource 取值待 Geri 确认 | 已解封 | **已验证** | Geri c50507; enam input N20 ↔ entry dicocokkan lewat API |  |
| 37 | 离职侧入口 Trigger link 的 inwardIssue／outwardIssue 方向 | 待办 | **被阻塞** | Geri c50507 setuju arah; cek visual menunggu run nyata pertama (entry belum dipublish) | ❓ bisa juga 进行中 |
| 38 | 本件后续须建：D-10 通知 Direct Supervisor、经 B6 解析直属上级、挂 e | 待办 | **进行中** | errorWorkflow sudah; D-10 dan B6 belum |  |
| 39 | Spec 增补区 A 表「离职单关联状态」由 N20／N21 系统写入 | 待办 | **待决策** | Pemetaan 3 nilai ↔ cf18140 tidak ada di Spec/build sheet |  |
| 40 | 本件与本页暗号接口契约表「先认领后动作」约束的适用 | 待办 | **待决策** | 双签未表态 |  |
| 41 | 本流程 n8n 件 04.9 登记（索引行＋04.9.7 详情块） | 已完成但未验收 | **已完成但未验收** | v58 |  |

Hitungan (setelah cek ⚠, keputusan baris 13, dan baris ❓ memakai usulan — Bambang 2026-09-29; baris 34 masih bergantung pada jawaban condition P-17): 共 42 行——被阻塞 13；待决策 12；已验证 6；未开始 6；已完成但未验收 3；进行中 2。

**【补】 khusus baris 13 (sel 解除判据, paragraf terakhir; menggantikan pola umum untuk baris ini):**

> 【2026-09-29 补】建造人决定：本行不再建本流程专属 Screen，改依平台方向用 Disciplinary Case 共用屏——#nos-bo 1790228926.781229 第 5 点「挂 Disciplinary Case 那张共用屏时，设成选填直接做」；Alden OSD-116 c50647 (a)：①「Approved By … is already on the Disciplinary Case edit screen」②「Any field the card writes back must be on the Disciplinary Case edit screen first, otherwise Jira rejects the whole write」，主单字段按 04.10 三格交 Kent 建（已于 c50658 申请批次 A 八项，均请设为选填）。原解除判据①②（Screen 登记处、专属 Screen 与 Screen Scheme）自此不再追；③挂 Scheme 一项随之不发生；④createmeta 回读字段齐仍适用于共用屏。上文「他流程字段留在单上会误导填写人」这一后果在共用屏下仍存在，如实保留。04.10 v22 仍载「主单字段归 SSCSD/V1」（与 c50647 (a) 并存，建造侧不调和）。本行状态由「待办」改为「被阻塞」，依 Anchor 04 §七.6；证据：OSD-116 c50658（Kent 未答，字段未建）。

**Pola 【补】 per baris (sel 解除判据, paragraf terakhir), contoh baris 1:**

> 【2026-09-29 补】本行状态由「阻塞中」改为「被阻塞」，依 Anchor 04 §七.6；证据：Alden OSD-116 c50695（岗位字段未建，见上条）。

**Paragraf 统计 baru (setelah paragraf 统计 lama, teks lama tidak dihapus):**

> 【2026-09-29 补】自本版起本表「状态」列依 Anchor 04 §七.6 六个标签（已验证／已完成但未验收／进行中／待决策／被阻塞／未开始）登记，原「阻塞中／待办／已解封」各行改标依据见各行 2026-09-29 补。逐行机读：共 {n} 行——{hitungan final}。上方各段旧统计为当时口径，原文保留。

- Baris ⚠ (0, 3, 4, 8, 13) **sudah dicek ulang 2026-09-29** (E69). 0, 3, 4, 8 tetap 被阻塞. 13: Bambang memutuskan ikut layar bersama (2026-09-29) → 被阻塞 (menunggu Kent c50658), 【补】 khusus di atas.
- Baris ❓ (7, 12, 26, 28, 29, 37): **memakai usulan di tabel** (Bambang 2026-09-29: 「baris ❓ pakai usulanmu」) — 7 进行中, 12 未开始, 26 已完成但未验收, 28 未开始, 29 未开始, 37 被阻塞.
- Baris 34 (Abort Case) mengikuti jawaban P-17: condition belum dipasang → 未开始; sudah dipasang dan dibaca ulang → label ditentukan dari hasil baca ulang.
- **Cakupan diperluas (Bambang 2026-09-29: 「Intinya semua ikut aturan dan source yang ada」):** bukan hanya 附表. Semua kolom 「状态」 dan paragraf statistik di build sheet yang menilai keadaan (termasuk paragraf 「统计：24 个节点行」 di §一 配置对应表: 已建 4／可建或部分可建 13／阻塞 6／待对端 2, dan tabel lain yang punya kolom 状态) ikut enam label Anchor 04 §七.6 dengan pegangan yang sama. Inventaris tabel dan draf per baris dibuat berikutnya, ditunjukkan dulu sebelum ditulis.

##### P-18 lanjutan · Tabel status lain di build sheet v58 (DRAF, 2026-09-29; divalidasi E70)

Sudah dicek (2026-09-29): build sheet **v58** (masih versi terbaru, dicek `listConfluenceContentVersions`), semua 14 tabel di halaman diinventaris. Tabel yang punya kolom 「状态」: 附表 (42 baris, draf di atas), **暗号接口契约表** (8), **§一 配置对应表** (24), **§一 tabel objek** (8). Tabel lain tidak diubah: §二 状态链表 (kolom Jira status/ID, fakta konfigurasi), §八 测试单 「末态」 (nama status Jira tiket), §八 NTP-187 「结论」 (hasil cek per syarat), dan tabel lain tanpa kolom status. Bukti per baris diambil dari isi baris itu sendiri plus sumber yang sudah dibaca hari ini (04.9.7 v2, E59–E69, OSD-116 s.d. c50705). Pegangan label = yang disetujui Bambang.

**A. 暗号接口契约表 (8 baris)**

| Marker | Status sekarang | Usulan | Bukti |
|---|---|---|---|
| 主体标识 `nos-s05-subject` | 拟定·未建 (+补 9/28: sisi baca sudah di N05) | **进行中** | Sisi baca dibangun di N05 `LJwiAZFfnuq6tmju` (04.9.7 v2, E63); sisi tulis (N01/N03) belum |
| 主单建单认领 `nos-s05-case` | 拟定·未建 | **未开始** | Belum ada件 yang menulis/membaca (P-6.8 B-5 tetap terbuka) |
| 疑似重复标记 `nos-s05-dup` | 拟定·未建 | **进行中** | N05 punya node 「Write Duplicate Marker Comment (internal)」 (04.9.7 v2); jalur utama N05 belum diuji (E63). Ini sekaligus menjawab P-6.8 B-2 |
| 子单编排认领 `nos-s05-sub` | 拟定·未建 | **未开始** | Belum dibangun |
| 文书发出认领 `nos-s05-doc` | 拟定·未建 | **未开始** | Belum dibangun (N08/N12 belum) |
| 离职交接认领与审计 `nos-s05-term` | 拟定·未建 (+订正 9/28) | **待决策** | Node penulis marker ini sudah ada di N20 (04.9.7 v2), tapi di dry-run 17373 langkah tulisnya di-pin, jadi marker belum pernah benar-benar ditulis ke Jira; waktu penulisannya masih menunggu 双签 (附表 baris 40) |
| 下游触发认领 `nos-s05-trigger` | 拟定·未建 | **被阻塞** | Pihak penerima S-06/S-15 belum punya Spec (HR 部门页 v40, E69) |
| N07 审批动作认领 `nos-s05-review` | 拟定·未建 (+补 9/28: 不建) | **已验证** | Diputuskan tidak dibangun; fungsinya diganti 「已处理检查」 platform yang sudah live (Alden c50576: 1A termasuk 「已处理检查」; c50689: 1B live, dan 「Bambang's tests … on SSCSD-437 to SSCSD-442 ran on the new version」 — klaim Alden, belum dicocokkan dengan catatan eksekusi). Uji klik ganda sendiri belum dijalankan, tetap di 附表 baris 29 |

Hitungan: 进行中 2, 未开始 3, 待决策 1, 被阻塞 1, 已验证 1.

**B. §一 配置对应表 (24 baris node)**

| Node | Status sekarang (ringkas) | Usulan | Bukti |
|---|---|---|---|
| N01 | 阻塞 (nama RT, link) | **被阻塞** | 04.7 v51 belum diisi nama dua bahasa (E69) |
| N03 | 阻塞 (nama RT; hook) | **被阻塞** | Sama dengan N01 (04.7 v51); hook menunggu N03 dibangun dan dipublish |
| N04 | 未建（可建） | **进行中** | Dibangun, inactive, terdaftar 04.9 v130/04.9.7 v2; 0 eksekusi; pemanggil N01/N03 belum (E63–E65) |
| N05 | 未建（可建） | **进行中** | Dibangun, inactive, terdaftar; hanya jalur error yang diuji (17564/17565) (E63) |
| N06 | 已建；权限待配 | **进行中** | Transisi dibangun dan dijalankan SSCSD-421; izin transisi belum dipasang |
| N07 | Jira 侧已建；卡片件已建… | **进行中** | Kartu dibangun dan diuji SSCSD-435, 437–442; field tulis-balik menunggu Kent (c50658) |
| N08 | 未建（可建） | **未开始** | — |
| N09 | 部分可建；邮件路径阻塞 | **被阻塞** | Komponen email tidak ada di 04.4 v35 §十一 (E69) |
| N10 | 未建（可建） | **未开始** | Field sub-ticket sudah ada (c50345), node belum |
| N12 | 未建（可建） | **未开始** | Sama |
| N13 | 阻塞 | **被阻塞** | Registry masih 「候选｜待N5」 (04.1 v47, 04.8 v23; E69) |
| N25 | 未建（可建） | **未开始** | — |
| N26 | 阻塞 | **被阻塞** | Sama dengan N13 |
| N27 | 阻塞 | **被阻塞** | Sama dengan N13 |
| N14 | 未建（可建） | **未开始** | — |
| N15 | 未建（可建） | **未开始** | — |
| N16 | 未建（可建）；兜底待 Felix | **未开始** | Keputusan Felix dilacak di 附表 baris 10 (待决策) |
| N17 | 未建（可建） | **未开始** | — |
| N20 | 未建（可建）(+补: 件已建) | **进行中** | Dibangun, inactive, dry-run 17373/17374; entry belum dipublish (E63) |
| N21 | 未建（可建） | **未开始** | — |
| N22 | 待办（S-06 待设计） | **被阻塞** | S-06 belum punya Spec (E69) |
| N23 | 待办（S-15 待设计） | **被阻塞** | S-15 belum punya Spec (E69) |
| N24 | 转换已建并实跑；字段与 automation 待建 | **进行中** | Transisi jalan (Done); field dan automation 模式五 belum |
| N28 | 已建（UI）；未实跑 | **进行中** | Transisi dibangun; belum dijalankan; condition di-hold (P-17) |

Hitungan: 被阻塞 8, 进行中 7, 未开始 9 (total 24).

**C. §一 tabel objek (8 baris)**

| Objek | Status sekarang | Usulan | Bukti |
|---|---|---|---|
| 主单 Issue Type | 已建·API 回读 | **已完成但未验收** | Dibangun dan dibaca ulang; verifikasi Alden ditunda (附表 baris 25/27) |
| 主单 Workflow | 已建·回读 | **已完成但未验收** | Sama |
| SSCSD Issue Type Scheme | 已挂 | **已完成但未验收** | Sama |
| SSCSD Workflow Scheme | 已映射 | **已完成但未验收** | Sama |
| 子单 Issue Type | 复用 | **已验证** | Objek bersama terdaftar 「生效」 di 04.10 v22 (Sub-ticket 14316) |
| 任务卡 Issue Type | 复用 | **已验证** | 04.10 v22 (Task 10004, 生效) |
| 执行卡 Workflow Scheme | 复用 | **已验证** | 04.10 v22 (scheme 13093, 生效, 已挂 HR) |
| 主单专属 Screen | 待建 | **被阻塞** | Keputusan Bambang: ikut layar bersama; field menunggu Kent c50658 (sama dengan 附表 baris 13) |

Hitungan: 已完成但未验收 4, 已验证 3, 被阻塞 1.

**D. Paragraf statistik**
- 附表: paragraf 统计 baru (draf di atas).
- §一 「统计：24 个节点行…」: tambah 【补】 baru setelah paragraf lama (teks lama tidak dihapus):

> 【2026-09-29 补】自本版起本表「状态」列依 Anchor 04 §七.6 六个标签登记，各行改标依据见各行 2026-09-29 补。逐行机读：24 个节点行——被阻塞 8（N01／N03／N09／N13／N26／N27／N22／N23）；进行中 7（N04／N05／N06／N07／N20／N24／N28）；未开始 9（N08／N10／N12／N25／N14／N15／N16／N17／N21）。上段「已建 4／可建或部分可建 13／阻塞 6／待对端 2」为 2026-09-18 口径，原文保留。

**Pola 【补】 per baris** sama dengan 附表: 「【2026-09-29 补】本行状态由「…」改为「…」，依 Anchor 04 §七.6；证据：…」, ditaruh di akhir sel 状态 (untuk tiga tabel ini, sel 状态 sendiri yang memuat catatan) dan label baru ditulis di awal sel sebagai paragraf pertama. Teks lama tidak dihapus.

Catatan: P-6.8 B-2 (status `nos-s05-dup`) terjawab oleh baris A-3 di atas.



### v58 (2026-09-29T06:08:12Z, akun pribadi Bambang, perintah 「Ganti status baris 04.9 登记 ke 已完成但未验收」)

附表 baris 「本流程 n8n 件 04.9 登记」: sel 状态 `b28d0928001d` 「待办（建造侧提出）」 → 「已完成但未验收（04.9 v130／04.9.7 v2 已回读；Alden 未验收）」; sel 解除判据 ditambah 【2026-09-29 补】 `b28d0929008c` (status lama, dasar Anchor 04 §七.6 dikutip, bukti, catatan bahwa baris lain dan 统计 belum diseragamkan). dryRun dibandingkan skrip (hanya dua node berubah); baca ulang diff v57→v58: 1 tambah / 1 hapus. Evidence E68.

### v57 (2026-09-29T05:59:25Z, akun pribadi Bambang, perintah 「Tulis P-14, P-15, P-16 ke build sheet」)

Ditulis lewat Atlassian_MCP `updateConfluenceContent` snapshotToken `v:56`: dryRun (dibandingkan skrip dengan v56 + 12 sisipan: identik), tulis, lalu baca ulang `diffConfluenceContentVersions` v56→v57 (18 tambah, 6 hapus = 6 baris 附表 yang diperpanjang + 6 paragraf baru di §五; teks lama utuh; kolom status tidak berubah). Evidence E66, E67. localId baru: `b28d09290080`–`b28d0929008b`.

Perubahan terhadap draf di bawah sebelum ditulis (berdasarkan cek ulang 2026-09-29, E66):
- P-15 ③: kalimat 「c50632 截至 2026-09-29 仍未见 Kent 答复」 diganti kutipan **Kent c50705** (jawaban c50632) + 「按此配置转态条件并回读前，本行状态不变。」
- P-14 ③: 「versionId 5a66fd9c 未变」 → 「时 versionId 5a66fd9c；其后仅订正注记与改名，见本区 N07 全名段下之补」 (versionId N07 sudah berubah ke 3ecb5c28 setelah koreksi catatan).
- P-14 ②: disisipkan di sel 事项 setelah `b28d09280013` (mengikuti 【补】 sebelumnya di baris itu); P-14 ①: setelah `b28d0928000e`; P-14 ③: setelah `b28d0929000a` (paragraf terakhir blok N07).

#### P-14 · Temuan skill harian 2026-09-29 (nos-check, nos-gate, prebuild-scan, build)

Sudah dicek (2026-09-29): build sheet v56 (附表 baris 「离职侧「系统触发入口」…发布」 `cecfddc9c86e`, 「…『先认领后动作』约束的适用」, 「员工离职 Spec 系统触发接收入口」 `2383136a7379`, 「Trigger link 方向」 `15b49457487d`); OSD-116 s.d. c50695; NSE-1137 s.d. c50674 (c50673, c50674 dibaca penuh); OSD-116 c50689 (Alden, dibaca penuh, evidence E57); 04.9 v127, 04.9.3 v30, 04.4.1 v16, Notify 契约 v16, 04.9.1 v22, 04.5 v81 (diff dibaca penuh, evidence E52); n8n N07 (E56). #nos-bo: tidak ada pesan utama baru setelah 2026-09-26.

**① 页首附表 baris 「离职侧「系统触发入口」qa01CkZBQfx8eLsK 发布」, sel 「解除判据」: ditambahkan**

> 【2026-09-29 补】入口已补登：04.9 v127 索引行与 04.9.3 v30 详情块（Geri，「本行属补登」）。Geri NSE-1137 c50674 回读：「entry qa01CkZBQfx8eLsK · versionId 5e3ff7f7 · activeVersionId null · active false · 18 nodes · pinData empty · errorWorkflow VUIgv9Ujj1KEoIne · callerPolicy workflowsFromSameOwner · 6 write nodes disabled」。前半「入口经 Alden 放行发布」仍未成立，本行仍阻塞中。

**② 页首附表 baris 「本件与本页暗号接口契约表『先认领后动作』约束的适用」: ditambahkan**

> 【2026-09-29 补】Geri NSE-1137 c50668 答 c50631：认领 marker「[[nos-resign-claim:<S-05 case key>]]」，以 internal comment 写在 S-05 主单上，「before anything is created」；claim 在而离职单在→ok:true, created:false, issueKey；claim 在而离职单不在→ok:false、无 issueKey、送 nos-ops。本侧 c50672 接受 ok:false，Geri c50674「Bare ok:false it is」。04.9.3 v30（Geri）：「★ 未闭：claim-before-create 尚未实施」，Claim Check 的 JQL comment ~「上线前须实测能否精确命中」；Geri c50668 第 4 点：marker 形状实测后可能改。该 marker 暂不登入本页暗号表。N20 自身 nos-s05-term 的写入时点仍待双签，本行状态不变。

**③ §五 N07 块: ditambahkan**

> 【2026-09-29 补】Alden OSD-116 c50689：「batch 1B is live (ahead of 10/1)」——需弹表单的按钮先开「Loading」表单再换真表单；不弹表单的按钮先显示「Processing」；「When a button has decisionLabel, the "Decision" line of the approval record shows only that label (e.g. 打回补件), with no 通过／不通过 in front」（契约：04.4.1 v16、Notify 契约 v16「v7」）。同条：「S-05 does not need to change anything… N07 is ready on the platform side. Bambang's tests last night on SSCSD-437 to SSCSD-442 ran on the new version and all worked.」（Alden 所述，建造侧未另核执行记录）。N07 各按钮均已带 decisionLabel（API 回读 2026-09-29，versionId 5a66fd9c 未变），打回补件显示「打回补件 · Return for info」。

- Sebelum ditulis: ambil versi terbaru build sheet; cek ulang NSE-1137, OSD-116 dan 04.9/04.9.3. P-7④ (v56) masih menulis 「10/1 后回读实际记录格式」; setelah c50689 kalimat itu basi, dan ③ di atas yang mencatat keadaan barunya.

#### P-15 · Jawaban Alden OSD-116 c50692 dan c50695, platform NSE-1137 c50691 ① (2026-09-29 siang)

Sudah dicek (2026-09-29): OSD-116 s.d. **c50695** (c50689, c50692, c50695 dibaca penuh); NSE-1137 s.d. **c50693** (c50691 dan c50693 dibaca penuh; c50693 hanya soal N5/N6/N7 离职, tidak dipakai); 04.9 **v129** (diff v127→v129 dibaca penuh, evidence E58); build sheet v56 (baris 附表 yang dituju). #nos-bo tidak dicek ulang.

**① 页首附表 baris 「本流程 n8n 件 04.9 登记」, sel 「解除判据」 (setelah `b28d09290072`): ditambahkan**

> 【2026-09-29 补】Alden OSD-116 c50692 答 c50670：①件名「follow 04.6 §2 item 3 — {flow name}｜{node ID}｜n8n-{action}, e.g. 纪律与绩效改进处置｜N04｜n8n-路由分发. Please rename the four S-05 workflows in n8n first, then register them」；04.9 v129 §一「名称一致」同步改为「命名格式按 04.6 第二节第 3 条（{流程名}｜{节点 ID}｜n8n-{动作}，与 04.4 第十节同构）」。②索引「Owner 部门」：「HR」。③「The two items on the 04.9 main page are done」——04.9 v129 实读：Notify 索引行已含「纪律与绩效改进处置」，§三 导航已有 04.9.7 行。四件已于 2026-09-29 在 n8n 改名（建造人批准，Claude 经 n8n MCP，只改名称；回读 versionId 未变），现名：「纪律与绩效改进处置｜N04｜n8n-路由分发」「…｜N05｜n8n-重复案件与历史记录检查」「…｜N07｜n8n-HR三层审核」「…｜N20｜n8n-解雇自动开单与交接」（N07 先改为「…｜N07｜n8n-审批卡发送」，同日再依 Spec 节点名改定，见第五区 N07 块）。2026-09-29 已登记（建造人批准，Claude 经 Atlassian_MCP 以建造人个人账号写入）：04.9.7 v2 加四个 H2 详情块；04.9 v130 索引加四行（Owner 部门 HR、建设归属 Bambang）、§三 04.9.7 块数 0→4、§四 审批卡库读者 N07 改现名；两页均已回读（v129→v130 diff 仅此三处）。

**② 页首附表 baris 「NTP 岗位受控清单待标准化」, sel 「解除判据」 (setelah `807487b7caef`): ditambahkan**

> 【2026-09-29 补】Alden OSD-116 c50695「Controlled position list: data source for S-05 role resolution and recusal — decided」：NTP 新增下拉岗位字段，选项取自岗位清单页；系统以该字段识别 HR Ops & Data、Head of HR 与管理层并判回避；现 Job Title（cf17999）「has a value for only 2 of the 161 active staff and will no longer be used」。分工：Felix 建岗位清单页并定字段名；Kent 建字段、挂 NTP 屏、登记 04.8 §5，并撤旧 Job Title（Alden 确认）；HR（Yuki）先填 HR 团队与管理层；建造人「switch N07/N14 recusal and the HR Ops & Data resolution to read this field」。字段建成并回读前本行仍阻塞中。

**③ 页首附表 baris 「Abort Case（id 11）转态权限配给 HR Ops & Data 角色组…」, sel 「解除判据」 (setelah `b28d0928000d`): ditambahkan**

> 【2026-09-29 补】Alden OSD-116 c50695 第 3 点：「Jira transition conditions only accept user groups, so transition permissions use a group as proposed in c50632; the system identifies people by the position field. The two must list the same people; Kent will settle the group in c50632.」c50632 截至 2026-09-29 仍未见 Kent 答复，本行状态不变。

**④ 页首附表 baris 「S-05 各 n8n 件切 active 的次序…」, sel 「解除判据」 (setelah `b28d0928000c`): ditambahkan**

> 【2026-09-29 补】平台事实（Alden NSE-1137 c50691 第 1 点，离职 N7／N12 发布申请）：「On this instance, publishing a piece activates it; there is no "published but active: false" state」。本流程四件现均未发布（activeVersionId null）；发布即启用，故发布时点同受本行次序约束。本行状态不变。

- Sebelum ditulis: ambil versi terbaru build sheet; cek ulang OSD-116 (Kent c50632/c50658) dan 04.9 (registrasi sudah ditulis 2026-09-29: 04.9 v130, 04.9.7 v2; kalimat 「下一步…」 di ① sudah diganti dengan hasilnya, E64/E65). Status baris 「04.9 登记」 di 附表 diputuskan Bambang saat menulis.

#### P-16 · Nama, catatan, dan folder 4 workflow (2026-09-29 siang)

Sudah dicek (2026-09-29): 04.6 v23 (§二-3, §3.2, §3.5, §3.9, dibaca penuh), 04.5.3 v18 (§一, dibaca penuh), 04.9 v129 §一, Spec S-05 v67 (tabel node), n8n `search_folders` dan `get_workflow_details` keempat workflow (evidence E59–E62); build sheet v56 §五 paragraf 「全名」 keempat workflow.

**① §五, setelah paragraf 「全名」 masing-masing workflow: ditambahkan (4 【补】)**

- setelah `2e76b79f037e` (N04):
> 【2026-09-29 补】件名依 04.6 §二-3（`{流程名}｜{Spec 节点 ID}｜n8n-{动作}`，Alden OSD-116 c50692）改为「纪律与绩效改进处置｜N04｜n8n-路由分发」（建造人批准，Claude 经 n8n MCP，只改名称；2026-09-29T05:20:42Z；回读 versionId `0aad8ecb-e97e-4297-9908-b6c15559fdca` 未变，settings 未变，active false）。

- setelah `2b95937564f9` (N05):
> 【2026-09-29 补】件名依 04.6 §二-3 改为「纪律与绩效改进处置｜N05｜n8n-重复案件与历史记录检查」（2026-09-29T05:24:15Z，只改名称，versionId 未变）。同日订正过时注记（只改件说明与 sticky 文字，逻辑未改）：件说明原写「needs dry-run + errorWorkflow + Alden approval」（errorWorkflow 已挂）、sticky 原写「Spec S-05 v62」→ 改为现状与 v67；现 versionId `30b14fd2-370b-43ef-b360-2086a05da9b8`（2026-09-29T05:30:22Z），其余节点、连线、settings 未变，active false。

- setelah `5e0726a1c002` (N07):
> 【2026-09-29 补】件名依 04.6 §二-3 先改为「纪律与绩效改进处置｜N07｜n8n-审批卡发送」（05:24:24Z），再依同条「命名对不上 Spec 行视为登记未完成」对齐 Spec v67 节点表「N07 HR三层审核」，改定为「纪律与绩效改进处置｜N07｜n8n-HR三层审核」（建造人指示，05:34:52Z）。同日订正过时注记（只改文字）：件说明与 sticky「Pattern-9 batch 1A」「Notify contract … v6」→「batches 1A and 1B live」「contract v7」，并补 Alden c50689 决定行一句。现 versionId `3ecb5c28-2a8c-47a4-9141-906d3da3d584`（05:30:27Z；改名不改 versionId），其余节点、连线、settings 未变，active false。

- setelah `c5cf66408cfa` (N20):
> 【2026-09-29 补】件名依 04.6 §二-3 改为「纪律与绩效改进处置｜N20｜n8n-解雇自动开单与交接」（2026-09-29T05:24:27Z，只改名称；回读 versionId `6971acbc-2413-4b1c-b3b7-2a501c1c9ea7` 未变，settings 未变，active false）。

**② §五, setelah 【补】 N20 di atas: ditambahkan (folder)**

> 【2026-09-29 补】folder：04.6 §3.9「每流程一个 folder…新 workflow 直接建在所属流程 folder」（04.5.3 §一-1 同）。2026-09-29 实读 n8n 项目内 11 个 folder，无本流程 folder；四件均不在任何 folder（parentFolderId null）。建 folder 与移件须经 UI（MCP 无此操作）；folder 名按 04.6 §3.9「中文｜English」，待定。

- Nama folder tidak ada di source mana pun. Claude tidak mengusulkan nama sendiri. Kalau folder sudah dibuat sebelum P-16 ditulis, ganti 【补】 ② dengan nama folder dan hasil baca ulangnya.
- Paragraf lama 「全名 …」 tidak diubah (teks lama tidak dihapus); 【补】 di bawahnya yang mencatat nama baru.


### v56 (2026-09-28T16:12:01Z, akun pribadi Bambang, perintah 「Tulis P-7 dan P-8 ke build sheet」)
P-7 (①②③④, termasuk P-4③) dan P-8 (①③④; ② dibuang). 7 operasi `insertNodeAfter` (node baru `b28d09290070`～`0076`); teks lama tidak diubah. Bukti: `docs/evidence/2026-09-28-live-checks.md` E49.

Syarat sebelum tulis, dicek 2026-09-28 sesaat sebelum menulis: OSD-116 terakhir masih c50670 (Alden belum menjawab, jadi P-7③ tetap 「待答」); #nos-bo tidak ada pesan baru setelah 16:30, thread 1790242043.098949 tanpa keputusan Kayden, thread 1789704362.435989 tanpa balasan setelah 16:36 (P-8③ tetap); keempat workflow `active: false` (P-8④ tetap).

Teks lengkap yang sudah ditulis (arsip, jangan ditulis ulang):

#### P-7 · Jawaban Alden OSD-116 c50647 (2026-09-28 15:11 +07)

Dasar: OSD-116 c50647, dibaca penuh 2026-09-28. Sudah dicek: OSD-116 s.d. c50670 (tidak ada comment baru setelah c50670), NSE-1137 s.d. c50672, build sheet v55; semua 2026-09-28.

Revisi 2026-09-28 (setelah dicek terhadap v55): ① dan ② dipangkas karena sebagian sudah tertulis lewat P-9① dan P-10①; ③ ditambah status c50670; ④ kalimat terakhir diganti karena Alden sudah menjawab di c50648.

**① 页首附表, baris 「主单专属 Screen 未建」, sel 「依赖谁」: ditambahkan setelah 【补】 P-9① (`b28d09290001`)**

> 【2026-09-28 补】上条出处：Alden OSD-116 c50647 (a)「since 9/24, SSCSD main-ticket fields go through the same 04.10 process — Kent approves and builds them; only the risk categories (making a field required on the shared screen, changing a shared object others already rely on, and the like) come to me. So please file the field list to @Kent as a 04.10 three-cell request.」同条：「Right now Jira has no Return Count, HR Decision Basis, Cancellation Reason, Final Outcome or Warning Level, and no fields yet for the initial PIP parameters.」c50647 (a) 所答为主单字段由谁审批与建；本行所记「本流程专属 Screen」是否另建、由谁建，c50647 未提及。本行状态不变。

**② §五 N07 块: ditambahkan setelah 【补】 P-10① (`b28d09290009`)**

> 【2026-09-28 补】Alden OSD-116 c50647 (a) 平台侧另三点（第 1 点 approverFieldId 已落实，见上条）：②「Any field the card writes back must be on the Disciplinary Case edit screen first, otherwise Jira rejects the whole write. Keep `noWrite` until then.」③「Pick the write shape by field type: dropdown → `option` (the value must match the Jira option exactly), multi-line → `adf`, number → `number`, person → `user`.」④「Return count needs +1: the card can only write constants or values typed in the modal, not increments, so please have S-05 add one itself after the return transition.」打回次数 +1 属本流程新增建设项，承载件未定。

**③ 页首附表, baris 「本流程 n8n 件 04.9 登记」: ditambahkan di akhir sel 「解除判据」 (`b28d09280018`)**

> 【2026-09-28 补】Alden OSD-116 c50647 (b)：「a 7th volume is open for S-05 — 04.9.7｜详情：纪律与绩效改进处置. Please register N04, N05, N07 and N20 per 04.9 §一: a row in the main-page index and a block in 04.9.7.」登记由本侧执行（建造单外页面，由建造人本人写入）。登记前三点已于 OSD-116 c50670（2026-09-28）询 Alden：件名格式（04.9 §一／04.4 §十 与 04.6 §二-3「n8n-」两式）、索引「Owner 部门」列取值、04.9 主页 Notify 索引行调用方与 §三 导航缺 04.9.7；待答。

- Catatan untuk Bambang: menulis 04.9 / 04.9.7 bukan wewenang Claude (CLAUDE.md §3). Claude hanya bisa menyiapkan draf isinya (`docs/pending-0409-registration.md`).
- Sebelum ditulis: cek apakah Alden sudah menjawab c50670; kalau sudah, ganti 「待答」.

**④ §八 N07 实跑 「观察（不改）」 (`5def9a821733`): ditambahkan (menutup P-4③)**

> 【2026-09-28 补】上文「不通过 Rejected｜打回补件」措辞：Felix OSD-116 c50639 请改；Alden c50647：「the Decision line of the approval record will show only the button's own label when one is set — e.g. 「打回补件 · Return for info」 instead of 「不通过 Rejected｜打回补件」. This ships with batch 1B on 10/1.」本侧不改件，10/1 后回读实际记录格式。Felix c50639 所附两项条件已由 Alden c50648 答复（见页首附表「模式九组件扩展（N07 审批交互）」行 2026-09-28 补）。

- Kalimat terakhir bergantung pada P-8①. Tulis keduanya dalam versi yang sama.

#### P-8 · Alden OSD-116 c50648, 04.4.1 v15, 04.6 §四, 07.06.1 D1 (2026-09-28 sore)

Sudah dicek: OSD-116 s.d. c50670, NSE-1137 s.d. c50672, build sheet v55, 04.6 v22 dan 07.06.1 v41 (versi dicek ulang 2026-09-28, tidak berubah); sebelumnya #nos-bo s.d. 16:36 (thread 1789704362), 04.4.1 v15, Notify v15, 04.10 v21, 04.8 v23, 04.9 v124. **#nos-bo belum dibaca ulang setelah 16:36.**

Revisi 2026-09-28 (setelah dicek terhadap v55): ① diperbarui (「HR 判定依据」 sudah diajukan di c50658) dan dipindah ke setelah paragraf yang masih menulis 「截至 c50644 未答」; ② **dibuang**, karena sudah tertutup P-10① (approverFieldId terpasang, versionId `c02dba29`/`5c304eb6`) dan P-10② (cf18061 berhasil ditulis di SSCSD-437～442); ③ dan ④ tetap.

**① 页首附表, baris 「模式九组件扩展（N07 审批交互）」, sel 「解除判据」: ditambahkan setelah `b28d09280001`**

> 【2026-09-28 补】上条「②问 Alden，截至 c50644 未答」已答：Alden OSD-116 c50648 ①「已写进平台规则（04.4.1「判定依据」一节）：在审批卡以外作出的判定（S-05 的 N10、N14、N17），由流程在主单按审批记录同一格式写一条评论，写明节点、时间、实际做判断的人、决定和判定依据。」②「「不能编辑或删除」做不到：……所以按你给的退路，以字段修改历史为准，并补强一点：每次判定同时写两个主单字段——「HR 判定依据」（这次的依据）和「Approved By」（这次是谁判的）。」建造侧据此：N10／N14／N17 建件时每次判定写一条主单评论，并同时写「HR 判定依据」与 `customfield_18061`；评论可见性拟同 N07 审批记录 internal（建造侧拟，依 Felix c50639 (2)）。「HR 判定依据」已于 OSD-116 c50658 向 Kent 申请（批次 A 第 1 项），待建。本行状态不变。

**② (dibuang)**

**③ §七: ditambahkan setelah 2026-09-28 补 yang sudah ada (`b28d09280053`, C-26)**

> 【2026-09-28 补】04.6 v22 §四（2026-09-28）已定部分口径：「SLA 时限数值：权威＝各流程 Spec 增补区 C 表；建设时照 C 表写进件，并在建造单登记所依据的 Spec 版本…机器不直接读取 C 表」；值类内容「权威定义＝Confluence 对应页面…n8n Data Table＝机读副本。流程件运行时只读表，不直接解析 Confluence 页面」。本流程非 SLA 类参数（纪律记录有效期、PIP 周期等）落哪一页，仍待 Kayden 03 条文（#nos-bo 1790242043.098949）。

- Sebelum ditulis: baca #nos-bo setelah 16:36 (2026-09-28). Kalau Kayden sudah memutuskan (dijadwalkan sebelum 9/29), kalimat terakhir harus diganti.

**④ 建设备注 07.06.1 命中条目: ditambahkan**

> 【2026-09-28 补】07.06.1 v41 D1：「写入已发布的件，可能当场生效，也可能只存成草稿、线上仍跑旧版…事后以回读为准——versionId 等于 activeVersionId 才算已生效」（04.6 v22 §3.2 第 4 条同）。本流程四件均未发布，现不适用；发布后改件按此回读。

- Sebelum ditulis: pastikan keempat workflow masih belum dipublikasikan.

### v55 (2026-09-28T16:02:46Z, akun pribadi Bambang, perintah 「Tulis P-13 ke build sheet」)
P-13. Satu operasi `insertNodeAfter` setelah `b28d0928005c` (node baru `b28d09290060`); teks lama tidak diubah. JQL dijalankan ulang tepat sebelum tulis, hasilnya tetap 10 tiket dengan status yang sama. Bukti: `docs/evidence/2026-09-28-live-checks.md` E48.

Teks lengkap yang sudah ditulis (arsip, jangan ditulis ulang):

#### P-13 · Koreksi paragraf §八 「现共 5 张」 (2026-09-28 malam)

Sudah dicek: build sheet v54 (paragraf `b28d0928005c` dan tabel 测试单登记 di atasnya), JQL Atlassian_Rovo akun Backend Operations `project = SSCSD AND issuetype = "Disciplinary Case"` (totalCount 10, tanpa halaman berikut; evidence E47), E37/E39; semua 2026-09-28.

**§八, setelah paragraf `b28d0928005c` (teks lama tidak diubah): ditambahkan**

> 【2026-09-28 补】上条「现共 5 张」已过时：同一查询（`project = SSCSD AND issuetype = "Disciplinary Case"`，Backend Operations 账号，2026-09-28 实读）现读出 10 张，均为 TEST 单：SSCSD-411／421／422／423／435／437／438／439／441／442。全部 statusCategory＝Done 且 resolution 非空（Done／Cancelled／Cancelled／Rejected／Rejected／Done／Done／Cancelled／Done／Done）。新增 5 张（437～442）见上方测试单登记。同一查询读出 10 张即为对照，非「看不见」。

- Sengaja tidak ditulis: SSCSD-440 tidak ada di hasil. E37 mencatatnya sebagai persetujuan cuti F2, tetapi itu belum dicek langsung di Jira.
- Sebelum ditulis: ambil versi terbaru build sheet dan jalankan ulang JQL; kalau jumlahnya berubah, perbarui teks.

### v54 (2026-09-28T15:58:28Z, akun pribadi Bambang, perintah 「Tulis P-9 sampai P-12 ke build sheet」)
P-9 (①②③), P-10 (①②③④), P-11 (①②), P-12 (①②). 18 operasi `insertNodeAfter`, semuanya tambahan; tidak ada teks lama yang diganti atau dihapus. Bukti: `docs/evidence/2026-09-28-live-checks.md` E46.

Penyimpangan dari draf di bawah (diputuskan saat menyusun operasi, isi teks tidak berubah):
- P-9②: draf menyebut 第三区, tetapi paragraf 「N07 卡 modal 与 Spec 增补区 A 表之差」 yang dituju ada di §五 (blok N07). Ditulis setelah paragraf itu (`b28d0928004d`).
- P-10④: ditulis sekali sebagai paragraf di bawah tabel transisi §二, setelah paragraf 证据边界 (`9f5d66ab-…`), bukan di dalam sel baris 10 dan 11.
- P-12①: teks gabungan dipecah jadi tiga 【补】, satu per workflow (N05, N07, N20), masing-masing dengan daftar nilai luar, nama node, versionId, dan waktunya sendiri.
- Catatan: P-11② menyebut versionId N05 `ad14f33e` 「未变」. Itu benar saat settings disimpan; 【补】 P-12 tepat di bawahnya memuat versionId baru `9b2ea463`.
- Belum ditangani (di luar P-9～P-12): paragraf §八 `b28d0928005c` 「SSCSD 内 Disciplinary Case 现共 5 张」 sekarang sudah basi (tiket tes bertambah SSCSD-437～442).

Teks lengkap yang sudah ditulis (arsip, jangan ditulis ulang):

#### P-9 · Pengajuan field tiket utama ke Kent, OSD-116 c50658 (2026-09-28)

Sudah dicek: OSD-116 s.d. c50658, NSE-1137 s.d. c50645, NSE-1126 c48074, Spec v67 (tabel A, ⓪区 六/十, N07, D-8), 04.10 v21, 04.4.1 v15, Notify v15 §9.14, createmeta SSCSD/14357, Canvas F0C32N7MYR1 v3; semua dibaca 2026-09-28.

**① 页首附表, baris 「主单专属 Screen 未建」 (atau baris field tiket utama): ditambahkan**

> 【2026-09-28 补】依 Alden c50647 (a)，主单字段三格申请已提交 Kent：OSD-116 c50658（批次 A，N07 审批卡回写的 8 项：HR判定依据、打回次数、打回原因与补件要求、取消原因、HR 确认处置工具、Warning 等级／结果、纪律记录有效期、PIP 参数）。复用不申请：Approved By `customfield_18061`。挂 Disciplinary Case 编辑屏、选填、不进任何 Request Type（#nos-bo 1790228926.781229 第 5 点）。去重候选交 Kent 定：Rejection Reason `customfield_18143`（同屏、无流程读写，NSE-1137 Geri）。批次 B（Final Outcome、离职单关联状态、下游流程触发状态、Show Cause回复截止日期、入口字段）另提。待 Kent 回字段与选项 id。

**② 第三区 (字段) 「N07 卡 modal 与 Spec 增补区 A 表之差」 2026-09-28 补 之后: ditambahkan**

> 【2026-09-28 补】上条①中「负责跟进人」：Spec ⓪区 十 将 PIP 参数该项写作「Direct Supervisor（无法解析→系统拦截并告警，转 HR 修正档案后重新解析）」，N16 Owner 亦为 Direct Supervisor——由系统解析，非 HR 录入，不设主单字段（c50658 已注明）。「到期日期」「纪律记录有效期」两项的卡上收集方式仍待 Felix。

**③ 第三区 「select 类主单字段…Warning 等级＝Verbal／Written／Final Written」 2026-09-28 补 之后: ditambahkan**

> 【2026-09-28 补】Warning 等级字段值按 Spec 增补区 A 表申请为「Verbal Warning／Written Warning／Final Written Warning」（与 Final Outcome 枚举、D-6 同；⓪区 为简写）。字段建成后，卡上 `o` 的 `v` 值改为与 Jira option 逐字一致（改件前经建造人批准）。

- Sebelum ditulis: cek apakah Kent sudah menjawab c50658; kalau sudah, tambahkan id field dan option.
- Catatan antrean: P-6.7 baris C-15 (「负责跟进人」 ke Felix) sudah dijawab Spec ⓪区 十; yang tersisa untuk Felix hanya 到期日期 dan 纪律记录有效期.

#### P-10 · N07: approverFieldId, label Warning, penanda tes, dan tes SSCSD-437～442 (2026-09-28 malam)

Sumber: evidence E36–E39; Alden OSD-116 c50647 ①／c50648; Spec v67 tabel A; 04.5.3 v17 §三／§五; Notify v15 §9.13／§9.14.

**① §五 N07 块: ditambahkan**

> 【2026-09-28 补】N07 件改件两次（均经建造人批准，改后 API 回读）：①`approval.approverFieldId`＝`customfield_18061`（Approved By，Alden c50647 ①／c50648）；Warning 等级下拉值改为 Spec 增补区 A 表写法「Verbal Warning／Written Warning／Final Written Warning」——versionId `c02dba29-a445-4baf-ab09-171dff5753ae`。②04.5.3 §三「注入 blocks 首个 section block（加粗），压在卡片正文之上」：Notify 以 `'*' + title + '*'` 起首，原卡将测试标识放在正文、未加粗；改为测试单（标题 TEST｜ 起头）时 title＝统一测试标识、原卡标题移至正文首行并加粗，生产卡不变——versionId `5c304eb6-de09-4783-ad61-8f98e10a7d30`（2026-09-28T14:09:03Z），active false。上文「卡首行加 🧪」自此版起与实物一致。modal 字段仍全部 noWrite（主单字段待 Kent，OSD-116 c50658）。

**② §八 测试记录: ditambahkan**

> 【2026-09-28 N07 审批卡实跑（二）】（test_workflow，Trigger 与「Read Case」以该单实读值 pin，其余真跑；卡发建造人 DM，白名单甲）
> ①SSCSD-437「通过·Warning」：发卡 17506，回调 17549；审批记录 comment 50662（jsdPublic false，含「Written Warning（Written Warning）」）；转换 Approve (2)→Pending Sub-tickets；cf18061＝建造人。
> ②SSCSD-438「通过·PIP」：发卡 17508，回调 17551；comment 50663（jsdPublic false，七项全记）；同上。
> ③SSCSD-439「确认重复」（matchedCaseKey＝SSCSD-435）：发卡 17510，回调 17552；Cancel as Duplicate (9)→Cancelled／Cancelled；comment 50664（jsdPublic false）；cf18061＝建造人（终态后写入成功）。
> ④改测试标识后：SSCSD-441 第 3 轮卡（无打回补件按钮，17554）点「通过·Show Cause」（回调 17558，comment 50665）；SSCSD-442 点「通过·严重违纪」（17556／17559，comment 50666）；两单 cf18061＝建造人。建造人截图（21:11）核对：首行测试标识加粗、次行卡标题加粗、第 3 轮卡无打回补件——作 04.5.3 §五判据 1 真信核对记录。
> ⑤437／438／441／442 于 Pending Sub-tickets 读可用转换：Complete (10)、Abort Case (11) 均 hasScreen false、isConditional false；随后以 Backend Operations 执行 Complete (10)→Completed／Done。
> 边界：「Read Case」仍为 pin（测试工具强制），Bot_SSC 实读未测；modal 回写未测（noWrite）；打回次数 +1 未建。

**③ §八 测试单登记: ditambahkan 5 baris**

> SSCSD-437｜N07 通过·Warning＋approverFieldId｜末态 Completed / Done｜留存不删（04.5.3 §四）。建单时显式 assignee＝Backend Operations。
> SSCSD-438｜N07 通过·PIP｜末态 Completed / Done｜同前。
> SSCSD-439｜N07 确认重复｜末态 Cancelled / Cancelled｜同前。
> SSCSD-441｜N07 第 3 轮卡＋通过·Show Cause＋测试标识加粗｜末态 Completed / Done｜同前。
> SSCSD-442｜N07 通过·严重违纪｜末态 Completed / Done｜同前。

**④ 第二区 转换表 行 10 与行 11: ditambahkan**

> 【2026-09-28 补】API 回读（SSCSD-437 于 Pending Sub-tickets）：hasScreen false、isConditional false。行 10 另经 SSCSD-437／438／441／442 以 Backend Operations 实跑，Resolution 自动写 Done；执行者非「仅服务账号」所拟之 automation，转态权限仍未配置。

- Sebelum ditulis: ambil versi terbaru build sheet; cek apakah Kent sudah menjawab c50658.

---

#### P-11 · Settings N04 dan N05 (2026-09-28 malam)

Sumber: evidence E40; 04.6 v22 §3.5 (「挂接有效的判据＝目标平台件已发布」).

**① §五 N04 块, setelah 【2026-09-28 补·API 回读】: ditambahkan**

> 【2026-09-28 补】上句「settings 未挂 errorWorkflow、未设 callerPolicy」已不成立：errorWorkflow＝`VUIgv9Ujj1KEoIne`（NOS | Platform | Error Handler (nos-ops)，active），callerPolicy＝workflowsFromSameOwner。两项经 UI 设置，人：Bambang。API 回读：updatedAt 2026-09-28T14:54:46Z，versionId 未变（`0aad8ecb-e97e-4297-9908-b6c15559fdca`），active false，节点 2 个未变。同次保存另带入 `binaryMode: separate`、`timeSavedMode: fixed`，为 UI 默认值。

**② §五 N05 块, setelah 【2026-09-28 补·API 回读】: ditambahkan**

> 【2026-09-28 补】上句「settings 未挂 errorWorkflow、未设 callerPolicy」已不成立：errorWorkflow＝`VUIgv9Ujj1KEoIne`，callerPolicy＝workflowsFromSameOwner。两项经 UI 设置，人：Bambang。API 回读：updatedAt 2026-09-28T14:53:41Z，versionId 未变（`ad14f33e-0434-4788-95cd-542abf56bd5d`），active false，节点 17 个未变。

- Sebelum ditulis: baca ulang N04/N05 lewat API; kalau versionId berubah, pakai nilai terbaru.

#### P-12 · Teks error tanpa titik dua ASCII: N05, N07, N20 (2026-09-28 malam)

Sumber: evidence E44; 04.4.4 §五; open-issues K-17.

**① §五, setelah blok N05, N07, dan N20 masing-masing: ditambahkan (satu 【补】 per件)**

> 【2026-09-28 补】依 04.4.4 §五「抛错文本一律不含半角冒号」改件（建造人批准，Claude 经 n8n MCP）：抛错文案中的半角冒号改全角「：」，外来值（入参、status、reason、idempotencyKey、JSON）经 `noColon` 转全角后再拼入。逻辑未改。N05 `Extract Subject AccountId`／`Alert Visibility Broken` → versionId `9b2ea463-f6be-476e-88a5-b62c074af375`；N07 `Validate Input`／`Build N07 Card`／`Check Notify Result` → `5a66fd9c-2630-4cae-8422-7d1099dbddc7`；N20 `Map Judgment To Dismissal Category`／`Check Entry Result` → `6971acbc-2413-4b1c-b3b7-2a501c1c9ea7`。三件 settings 未变、active false。

**② §八 测试记录: ditambahkan**

> 【2026-09-28 抛错文案去半角冒号·干跑】（test_workflow，Jira／HTTP／Notify 节点 pin）17562 N20（judgmentType「BAD:VALUE」）／17563 N07（issueKey「SSCSD:1」）／17564 N05（无 marker）：三例 `description` 为 null，全文落 `message`，外来值冒号显示为全角；均止于抛错节点，零写入零外发。对照 17235（N7 离职，改前形态）：冒号前后分入 `description`／`message`。其余 8 处续跑 17565–17572（N05 可见性探针；N07 入参三处、控制探针、状态、Notify 未送达；N20 入口 `ok:false`），结果相同；`Call Notify`、`Call Resignation Upstream Trigger Entry` 均为 pin（耗时 0／1 ms）。11 处抛错全部跑过。边界：nos-ops 告警正文未验（Error Handler 不可经 MCP 读取，手动执行不触发）。

- Sebelum ditulis: baca ulang ketiga workflow lewat API; kalau versionId berubah, pakai nilai terbaru.


### v53 (2026-09-28T07:07:32Z, akun pribadi Bambang, perintah 「Tulis halaman」)
P-1 (①②③④), P-2, P-3, P-4 (①②; ② digabung ke catatan baris 模式九 A-04), P-5 (①②), dan P-6.1 sampai P-6.6. Item P-6.7 yang ditulis hanya catatan keadaan: A-14, C-10 dan D-2 mencatat 「Kent 未答」, C-01 memakai 04.7 v51 yang dibaca agen audit hari ini. Rincian: 92 operasi (87 tambahan, 5 ganti status), bukti `docs/evidence/2026-09-28-live-checks.md` E31–E32.

Teks lengkap yang sudah ditulis (arsip, jangan ditulis ulang):

#### P-1 · `nos-s05-review` tidak dibangun (keputusan Bambang, 2026-09-28)

Dasar: dibaca pada 2026-09-28.
- Notify 1603633175: baris v6 dan §9.4, §9.9.
- 04.4.1 1729888419: bagian 已处理检查 dan 配置方式 langkah 3.
- OSD-116 c50558 二② (Alden).

**① 附表, baris 「四条原地转换使模式九重复裁决主锁失效」: ditambahkan di akhir sel 「解除判据」**

> 【2026-09-28 补·建造侧决定：不自建 nos-s05-review】建造人 Bambang 决定：本侧不建 `nos-s05-review` 认领。依据：①本行成立前提「副锁（marker 回扫）…未实现」已不成立——Notify 契约版本表 v6：「§9.4 副锁改为已实现（已处理检查）」，状态「已上线」；§9.4：「已处理检查（v6 起生效）：入站执行任何决定之前，读主单最近 100 条评论，找 `[[nos-approval:<idempotencyKey>:` 标记；找到即落「已决」分支（不转态、不写记录、不回写字段…）」。②分工：Notify §9.9「每流程供给＝…idempotencyKey、round；平台通用＝…幂等/竞态…」；04.4.1 配置方式第 3 步「调用方流程不需要自己实现验签、身份校验或转态逻辑，回调 workflow 统一处理」。③Alden OSD-116 c50558 二②：「S-05 自建的 nos-s05-review 认领对 N07 路径不再是必需。」本侧须做的只有每轮换 idempotencyKey：N07 发卡件已按 `<主单key>:r<轮次>` 实建（v50）。④N07 的转态由平台回调件 `6wdHhygWmyRFQAoX` 执行（SSCSD-435 执行 17293／17294、17297／17298），S-05 无自有回调件；本侧认领无法插入平台「已处理检查→转态→写记录」之间，故也补不上下述边界①③（推断，未实测）。
> 已知残余（04.4.1「已处理检查」边界原文）：①「两次点击在第一次写完记录之前（约 3 秒内）先后进入，仍可能各处理一次…原地转换与不转态按钮会多出一条相同的审批记录，看得见、不静默」；②「读评论失败时本次照常处理（不挡审批），并告警 nos-ops」；③「主单评论超过 100 条且标记更早时，退回只靠 transition 锁」——对 ID 4／5／6／7 原地转换，transition 锁不成立。③ 的实际发生概率未有数据（N07 位于 Case 早段，推断评论数少，未证实）。
> 连点负向用例（同 idempotencyKey 第二张卡点击应只回「已处理」）**暂缓**：理由①N07 正式给 HR 用须第一批 A、B 与回写字段／Screen 均到位（c50558）；②第一批 B（10/1）改造审批入口前段（c50558 二③），现测的是即将替换的路径。并入 N07 端到端测试执行。

**① 附表, baris yang sama: sel 「状态」**
- Diganti: 「待办（建造侧提出·双签未表态）」 → **「已解封（2026-09-28·建造侧决定不自建；连点用例并入 N07 端到端）」**.
- **Disetujui Bambang** (2026-09-28, 「Perbaiki」 sebagai jawaban atas pertanyaan status ini). Label status yang dipakai di 附表: 阻塞中／待办／已解封.

**② 暗号接口契约表, baris 「N07 审批动作认领」: ditambahkan di akhir sel status 「拟定·未建」**

> 【2026-09-28 补】不建。平台「已处理检查」（Notify v6 §9.4，已上线）以卡片 idempotencyKey 的审批记录标记 `[[nos-approval:<idempotencyKey>:<decision>]]` 承担本行作用；依据与残余边界见页首附表「四条原地转换使模式九重复裁决主锁失效」行 2026-09-28 补。

**③ §一 配置对应表, baris N07: ditambahkan di akhir sel status**

> 【2026-09-28 补】上文「四条原地转换的重复裁决主锁失效，须自建幂等闸」已由平台「已处理检查」（Notify v6）承担，本侧不自建（见页首附表对应行 2026-09-28 补）。

**④ §二 状态链表, paragraf 「四条原地转换分轮次命名的理由」 (kalimat 「故四条原地转换的防重复必须由调用方自建幂等闸」 ada di sini, v52 baris ±365; bukan di 建设备注): ditambahkan setelah paragraf itu**

- Lokasi dikoreksi 2026-09-28 dari hasil audit (C-12, disetujui Bambang). Sebelumnya tertulis 「建设备注」, dan kalimat itu tidak ada di sana.

> 【2026-09-28 补｜原文保留不删】上段「副锁…均登记「未实现」」为 v5 口径。Notify 契约 v6 起副锁已实现（已处理检查，已上线），防重复改由平台承担，本侧不自建幂等闸；见页首附表对应行 2026-09-28 补。

#### P-2 · Catatan transition 11 (Abort Case): konfirmasi Owner 04.3 sudah ada

Dasar: OSD-116 c50445 (Kayden, 2026-09-24): 「04.3 §六 已改好并复检通过（04.3 现 v35…）」, 「Abort Case（id 11）转态权限配给 HR Ops & Data 角色组；N07「确认重复」同口径…建造单登记依据 04.3 v35 §六」. 04.3 dibaca ulang 2026-09-28: baris 「主单转入「已取消」（执行中止）」 memuat 「该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」.

**§二 transition 表, baris id 11: ditambahkan di akhir sel 「允许执行者」**

> 【2026-09-28 补】上文「配置前须经 04.3 Owner（Kayden Lee）确认」已由 Kayden OSD-116 c50445 给出：04.3 v35 §六 执行中止行已加「该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」；执行顺序「先把主单转「已取消」，再取消未关子单」。HR Ops & Data 对应的 Jira 组无任何来源点名；现存唯一 HR 组为 SSCOS｜HR（成员 Felix_HR、Yuki Liew_HR，SSCSD 角色 Service Desk Team），已于 OSD-116 c50632 请 Kent 确认。确认前 condition 不配。

- Sebelum ditulis: cek apakah Kent sudah menjawab c50632. Kalau sudah, isi paragraf ini disesuaikan dengan jawabannya.

#### P-3 · Koreksi catatan build sheet soal siapa yang membangun field tiket utama N07

Dasar: lihat `docs/open-issues.md` K-11.

**§一 配置对应表, baris N07: ditambahkan di akhir sel status**

> 【2026-09-28 订正｜原文保留不删】上文 2026-09-26 补「回写主单字段仍待 Alden／V1 建字段与 Screen」与 #nos-bo 1790228926.781229 第 5 点（Alden，2026-09-24）不一致：「纪律处置那 5 个主单字段加屏幕…现在就请 Kent 按五类判、走第五节流程建；挂 Disciplinary Case 那张共用屏时，设成选填直接做，要设必填再找我」。Alden OSD-116 c50558（2026-09-26）另写「这件我另外回复」。两说并存，建造侧不调和，见 open-issues K-11。

- Sebelum ditulis: cek apakah Alden atau Kent sudah menjawab, dan apakah field atau Screen sudah dibangun.

#### P-4 · Keputusan Felix OSD-116 c50639: visibilitas internal (N07) dan syarat pencatat keputusan (N10/N14/N17)

Dasar: OSD-116 c50639 (Felix_HR, 2026-09-28 10:59 +07, kepada Alden), dibaca penuh.

**① §五, blok 【2026-09-26 补·N07 审批卡发送】: ditambahkan setelah butir 「卡形（依 c50558）…」**

> 【2026-09-28 补】auditVisibility＝internal 已由流程 Owner 定案：Felix OSD-116 c50639 (2)「审批记录可见性：选 internal。记录里是 HR 的内部判断过程，主管该知道的结果已通过 D-2、D-16 等通知送达，案件对外状态他仍看得到。」上文「Felix 定前按 internal」为定案前口径，现行值不变。

**② 页首附表: baris baru (建造侧待办), atau catatan di baris N10／N14／N17 §一 — letak dipilih saat penulisan setelah membaca versi terbaru**

> 【2026-09-28 补】Felix OSD-116 c50639 (1) 接受「字段留最新一次、连续记录放主单评论流」，附两个条件：①「N10/N14/N17 由 S-05 代写的记录，要和 N07 一样带上实际做判断的人。History 作者只显示 Bot_SSC，谁判的只能靠这条记录。」②「请确认这些记录普通用户（含 HR）不能编辑或删除；如果做不到，请写明以字段修改历史为准。」①为建造侧在 N10／N14／N17 建件时的必做项；②问的是 Alden，待其答复。记录格式依 Alden c50558「格式写进平台契约 04.4.1」。

**③ Terkait U-8 (kata 「打回补件」): tidak ditulis ke build sheet sekarang.** Felix di c50639 meminta Alden mengganti 「不通过 Rejected｜打回补件」 menjadi 「打回补件 Return for info」. Tunggu jawaban Alden, lalu perbarui catatan 「观察（不改）」 di §八 N07 实跑.

- Sebelum ditulis: baca ulang OSD-116 setelah c50644 untuk jawaban Alden atas syarat ② dan soal kata 打回补件.

#### P-5 · Keputusan Alden NSE-1137 c50645: status 14315 dan penanda "menunggu dilengkapi"

Dasar: NSE-1137 c50645 (Alden, 2026-09-28 12:36 +07, kepada Geri, cc Kent dan Bambang), dibaca penuh.

**① 页首附表, baris 「离职侧「系统触发入口」`qa01CkZBQfx8eLsK` 发布」: ditambahkan di akhir sel 「解除判据」 (status tetap 阻塞中)**

> 【2026-09-28 补】解除判据后半「「待资料补齐」状态口径已定」已成立：Alden NSE-1137 c50645「no new status on 14315 — use the fallback, but mark "awaiting completion" with a field, not an internal marker」；「tickets created by the upstream entry land directly in Pending Sub-tickets. "Awaiting completion" = the actual last working day (`cf18140`) is empty; no separate internal marker.」前半「入口经 Alden 放行发布」尚未成立，本行仍阻塞中。

**② 页首附表, baris 「Spec 增补区 A 表「离职单关联状态」由 N20／N21 系统写入」: ditambahkan di akhir sel 「解除判据」**

> 【2026-09-28 补】Alden NSE-1137 c50645 点名：「@Bambang S-05 N21 reads the same field to tell whether completion is done.」即 N21 以离职主单 `cf18140`（实际离职日）是否已填判断资料是否补齐。「离职单关联状态」三值（已建单并关联／信息待补齐／信息已补齐）与 `cf18140` 的对应关系，Spec 与本页均未写明，建造侧不自拟，见 open-issues U-9。

- Sebelum ditulis: baca ulang NSE-1137 setelah c50645 (jawaban Geri/Kent) dan cek apakah entry sudah diperbarui atau di-publish.

#### P-6 · Hasil audit baris per baris build sheet v52 (2026-09-28)

Asal: audit atas permintaan Bambang 「audit dengan teliti row per row… masuk list biar sekali update」. Disetujui masuk antrean: 「Ya, commit dan push」 (2026-09-28).
Nomor audit: A = baris 1–128, B = 129–276, C = 277–467, D = 468–565 (nomor baris mengacu salinan markdown v52). Item yang dobel sudah digabung; nomor lain dicantumkan dalam kurung.

Sudah dicek: build sheet v52 (dibaca penuh); OSD-116 s.d. c50644 dan NSE-1137 s.d. c50645 (dicek live 2026-09-28 setelah audit, tidak ada comment baru); #nos-bo s.d. 1790567167.378069 (dicek live, tidak ada pesan baru); Confluence live 2026-09-28: 04.3 v35, 04.4 v34, 04.9 v121, 04.9.1 v21, 04.9.7 (2117435433), versi halaman lain lewat API versi. Sumber yang **belum** dibaca penuh ditulis sebagai syarat di item masing-masing.

Aturan tulis tambahan untuk P-6:
- Nomor versi halaman lain dan angka statistik **diambil ulang saat menulis**, karena beberapa halaman berubah pada 2026-09-28.
- Kalau teks P-6 menyentuh baris yang sama dengan P-1…P-5, gabungkan dalam satu 【补】 supaya sumber yang sama tidak dikutip dua kali.

##### P-6.1 · Fakta yang salah (订正)

**A-05 · 附表 「离职 Spec 系统触发接收入口」, kolom 依赖谁**
> 【2026-09-28 订正｜原文保留不删】本行「依赖谁」所记「Kent（入口）」已由 Kent OSD-116 c50381 订正：「the entry is on the resignation side and is built by Geri (NSE-1137), defined in the resignation Spec. Bambang builds only the S-05 side: N20 calls the entry, N21 tracks completion. No interim manual path to design.」入口即 `qa01CkZBQfx8eLsK`，其发布另见本表「离职侧「系统触发入口」`qa01CkZBQfx8eLsK` 发布」行（阻塞中）；两行指向同一对象，本行状态不改，跟踪以该行为准。

**B-1 · 约束 JQL 探针 (v52 L139)**
> 【2026-09-28 订正｜原文保留不删】本条括注「或查 `/rest/api/3/mypermissions` 的 BROWSE_PROJECTS」已不成立。07.06.1 E16 现行原文：「不要用「查该身份对这个 project 的浏览权限」（/rest/api/3/mypermissions 的 BROWSE_PROJECTS）代替」。对照探针只认「同一执行身份查一张已知存在的单」。
- Sebelum ditulis: kutipan E16 berasal dari salinan 07.06.1 09-26. Cocokkan kata per kata dengan v40.

**B-15 · 07.06.1 v34 / E6 (v52 L271)**
> 【2026-09-28 订正｜原文保留不删】①07.06.1 现行为 v40（2026-09-26），非 v34。②上文「并核该次执行 pinData 是否为空」与 E6 现行验收相反：「执行记录顶层的 pinData 字段不作判据——显式 pin 了节点，它也可能为空」。干测判据改为逐个核会写、会发节点是否回真包，耗时为 0 即被 pin 或停用，并回读目标对象；第八区 2026-09-28 N20 干跑已按此登记。v34→v40 其余变动未逐版比对。

**B-4 · 暗号 `nos-s05-term` (v52 L150) dan 建设备注 「跨流程 link」 (L223)**
> 【2026-09-28 订正｜原文保留不删】本行与建设备注「跨流程 link」段「审计 comment 两边都写…（对应 `nos-s05-term` marker）」按现行分工订正：`nos-s05-term` 仅为 N20 防重复调用的内部 marker，不是审计文字（Bambang NSE-1137 c50575：「It is not an audit text」）。两侧审计 comment 均由离职侧入口 `qa01CkZBQfx8eLsK` 写入——S-05 Case 上由入口节点 `Write Audit Comment (Upstream Case)` 写（c50575：「the only audit comment on the S-05 case」），离职主单上由入口写审计备注。离职侧入口自身的防重复 marker 为 `[[nos-upstream:<upstream key>]]`，住离职主单内部审计 comment（Kent c50539 ③；Geri c50585）。Geri c50585 另提「S-05 Case 上先认领再建单」，其 marker 语法未公布（Bambang c50631 已请其公布），见页首附表对应行 2026-09-28 补。
- K-10 tetap 待决策.

**A-10 · 附表 「主单载体」 baris, 补 09-22 (kata 「baris 19」)** — juga v52 L455 「baris 32」 (= baris 「身份件」)
> 【2026-09-28 补｜原文保留不删】上文 2026-09-22 补所记「待 04.3 Owner 答复页首附表 baris 19 的互斥条口径」：「baris 19」系误植，指本表「N28 案件失效中止的执行人」行。该口径已由 Kayden OSD-116 c50445 给出（04.3 v35 §六，见该行 2026-09-28 补）。`Abort Case`(11) 实跑与 `Create`(1)／`Complete`(10)／`Abort Case`(11) 三条转换属性 API 回读仍未做；原暂缓系使用者指示，是否恢复由建造人定。本行状态不变。
- Untuk L455: tambahkan 【2026-09-28 补】「上文「建造单 baris 32」系误植，指页首附表「身份件」行。」 Periksa isi baris itu saat menulis.

##### P-6.2 · Perubahan status 附表 (disetujui Bambang 2026-09-28)

| Baris 附表 | Status baru | Dasar | Syarat sebelum ditulis |
|---|---|---|---|
| N28 案件失效中止的执行人 (v52 L47) | 已解封（2026-09-24·04.3 v35 §六）; urusan grup pindah ke baris 「Abort Case（id 11）转态权限配给 HR Ops & Data 角色组」 | A-08 (C-07, C-08) | — |
| Notify §9.14 与 04.4.1 不一致 (L53) | 已解封（2026-09-26·Notify 页 v14） | A-09 | **Baca isi §9.14 Notify dulu** (audit hanya membaca outline). Kalau isinya tidak cocok, status tidak diubah dan dilaporkan ke Bambang |
| N03 分派钩子 flow 值 (L57) | 待办 (hapus 「双签未表态」) | A-11 (C-02) | — |
| 四条原地转换主锁 (L58) | sudah di P-1 | P-1 | — |
| upstreamSource (L65) | 已解封（2026-09-25·Geri c50507） | A-16 | — |
| **Baris baru:** 本流程 n8n 件 04.9 登记 | 待办 (建造侧提出) | C-16 | Isi di bawah; pembagian siapa yang menulis ke 04.9 ikut 04.9 §一, tidak diisi sendiri |

Setelah semua status ditulis, **hitung ulang** statistik 附表 (A-03).

**A-08 · N28 (L47), sel 解除判据**
> 【2026-09-28 补｜原文保留不删】本行解除判据两半均已由 04.3 Owner 给出：Kayden OSD-116 c50445：「04.3 §六 已改好并复检通过（04.3 现 v35…）」——①转态权限表执行中止行加「该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」；②互斥句加例外：「失效类中止（主单完成条件已不可能达成——当事人离职、对象被另一流程终结、命中重复案件、岗位撤销等）不受模式五互斥约束，仍转「已取消」并在同一动作把未关子单转「已取消」」；并指示建造侧：「执行顺序请写死：先把主单转「已取消」，再取消未关子单」「建造单登记依据 04.3 v35 §六」。2026-09-28 实读 04.3 v35 §六 该行原文：「仅服务账号、该主单所在 Project 的 Owner，与该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」。上文所引「04.3 v33」为当时版本。余下事项（HR Ops & Data 对应的 Jira 组、condition 配置）转由本表「Abort Case（id 11）转态权限配给 HR Ops & Data 角色组」行跟踪。另：c50445 请 Alden 在 04.4 模式五与模式四第 5 条镜像该例外与执行顺序；04.4 v33→v34（2026-09-27）差异仅 §四 一段，未见镜像。

**A-09 · Notify §9.14 (L53)**
> 【2026-09-28 补｜原文保留不删】Notify 调用契约页 v14（2026-09-26，Alden）§9.14 标题现为「9.14 审批当下补数据：声明式 modal 与字段回写（v5 · 已上线；v6 增下拉）」，该版修订说明：「v6：审批记录新格式（流程声明启用）、已处理检查、不转态出口、弹窗下拉、按钮长度闸；v5 已上线；旧格式框按实建订正」。本行所记与 04.4.1 的不一致已由页面 Owner 订正。

**A-11 · N03 flow 值 (L57)** (digabung dengan C-02)
> 【2026-09-28 补｜原文保留不删】Alden OSD-116 c50558 已答复 c50279 附加 (a)：「N03 入口接钩子（c50279 附加 (a)，flow 值 disciplinary-n03）：你们发布 N03 入口件后在本卡说一声，我 1 个工作日内接上。」建造人 c50595：「N03 is not published yet, so I am not asking for the disciplinary-n03 hook wiring now. I will tell you here once it is.」本行剩余前置＝N03 入口件发布（次序依 04.4.1「先发布 N03 入口件，再接钩子出口」）。钩子接上并回读前，Slack 表单提交仍落 `__reject__`。

**A-16 · upstreamSource (L65)**
> 【2026-09-28 补｜原文保留不删】Geri NSE-1137 c50507 已确认：「upstreamSource — keep S-05 N20, but I added a sixth field.」第六项 upstreamEvent 已接；N20 与入口触发节点六项入参逐名比对一致（见第五区 2026-09-28 补，API 实读）。

**C-16 · baris baru 附表 「本流程 n8n 件 04.9 登记」 + §五 补 09-20 ①** (teks dikoreksi: 04.9.7 sudah ada)
> 【2026-09-28 补｜原文保留不删】上文「现阶段无 n8n 件在建，未成阻塞」已不成立：N04／N05／N20／N07 四件已建（均 inactive）。平台侧已于 2026-09-28 建 04.9.7｜详情：纪律与绩效改进处置（pageId 2117435433，Alden；2026-09-28 实读仅导语「本页承载纪律与绩效改进处置族（S-05）全部详情块；新增本族件按主页 §一铁律登记：主页索引表加行＋本页加 H2 块」，无 H2 详情块），即 OSD-116 c50595 (b) 所问册落点。04.9 主页索引表本流程各件行与 04.9.7 各件详情块尚未加。依 04.9 §一「先登记后启用」，四件在登记前不得 active。
- Baris 附表 baru: 事项 「本流程 n8n 件 04.9 登记（索引行＋04.9.7 详情块）」; 依赖谁 dan cara menulis ikut 04.9 §一 (baca saat menulis); status 待办.

##### P-6.3 · Bagian atas halaman dan 附表: data basi / sudah terjawab

**A-01 · Header L1/L3 (versi Spec)**
> 【2026-09-28 补｜原文保留不删】Spec 页现行为页面 v67（2026-09-24T09:40Z，Felix），即 Spec「自然语言版本迭代」表 v28（现行版）；上两段所记 v61／v62 为当时值，v63～v67 逐版差异本侧未比对。Felix OSD-116 c50486 原文：「S-05 Spec 已完成对应修订，页面现 v67（内部版本 v28）」「Spec 已冻结进开发，本轮修订按建设期注记处理，不重走结构审计（与 c50445 处理原则一致）」。Spec 页冻结状态行未变：「已冻结｜…｜冻结时间：2026-09-15」。此系流程 Owner 自述，建造侧照录、不代为背书。

**A-02 · Daftar baca L7–L21 (versi dan jumlah comment)** — ambil ulang semua angka saat menulis
> 【2026-09-28 补｜原文保留不删】上列各段为当日实读记录，按本页体例不追改。2026-09-28 以版本 API 核对现行版：04.3 v35｜04.4 v34（v33→v34 仅 §四 一段）｜04.4.1 v14｜Notify 调用契约 v14｜04.5.3 v17｜04.7 v51｜04.8 v21｜04.10 v21｜04.11 v4｜04.1 v46（未动）｜07.06.1 v40｜OS 开发流 Spec v40｜04.9 v121｜04.9.1 v21；04.0／04.2／04.5 末次修订仍为 2026-09-19。OSD-116 现 194 条（至 c50644），NSE-1137 现 274 条（至 c50645）。凡因版本移动而改变的判断，已分别在对应行登记。

**A-03 · Statistik 附表 (L71–L85)** — hitung ulang setelah P-6.2 ditulis
> 【2026-09-28 订正｜原文保留不删】上段「阻塞中 6 行」「已解封 4 行」为 2026-09-24 计数。2026-09-26「模式九组件扩展（N07 审批交互）」行由「阻塞中」转「已解封（2026-09-26·建设面）」后，现逐行机读本表「状态」列所得：共 〔N〕 行；阻塞中 〔N〕 行；待办 〔N〕 行（其中「建造侧提出·双签未表态」〔N〕 行）；已解封 〔N〕 行。
- Hitungan audit sebelum P-6.2: 41 / 阻塞中 5 / 待办 31 (双签未表态 12) / 已解封 5. 〔N〕 diisi dari hitungan ulang, bukan dari angka ini.

**A-04 · 模式九 (L31), 「③Felix 待答两问」** — gabung dengan P-4 supaya c50639 tidak dikutip dua kali
> 【2026-09-28 补｜原文保留不删】上文「③Felix 待答两问」已由 Felix OSD-116 c50639 答复：(1)「可以接受。字段留最新一次、连续记录放主单评论流」，附两条件「① N10/N14/N17 由 S-05 代写的记录，要和 N07 一样带上实际做判断的人」「② 请确认这些记录普通用户（含 HR）不能编辑或删除；如果做不到，请写明以字段修改历史为准」（②问 Alden，截至 c50644 未答）；(2)「审批记录可见性：选 internal」。余①第一批 B（c50558 定 10/1）与②主单字段与 Screen（见本表「主单专属 Screen 未建」行 2026-09-28 补）未变。本行状态不变。

**A-06 · 主单专属 Screen (L42), 依赖谁** — gabung dengan P-3 (K-11)
> 【2026-09-28 补｜原文保留不删】本行「依赖谁」所记「建造侧（建与挂）」与其后来源不一致，三说并存，建造侧不调和：①Kent OSD-116 c50234 第 2 点：「…and the Screen (Disciplinary Case inherits the SSCSD default) → Alden / V1 domain — route these to Alden, don't file them yourself.」②Alden #nos-bo 1790228926.781229 第 5 点（2026-09-24）：「纪律处置那 5 个主单字段加屏幕（c50234 第 2 点转给我、至今未答）：不用等落页，现在就请 Kent 按五类判、走第五节流程建；挂 Disciplinary Case 那张共用屏时，设成选填直接做，要设必填再找我。」同条第 1 点：「SSCSD 主单侧（字段、屏幕、workflow、scheme）也进 04.10」——该范围调整系草案，截至 04.10 v21（2026-09-26）未见落页。③Alden OSD-116 c50558：「审批卡回写的主单字段与 Screen（c50234 第 2 项）是前置，这件我另外回复」。截至 2026-09-28 读 OSD-116（至 c50644）与 #nos-bo，未见该屏或主单字段建成的回报。本行状态不变。

**A-07 · Dua butir Kayden (L43)** — lihat juga open-issues K-12
> 【2026-09-28 补｜原文保留不删】提点①已失去前提：Kayden OSD-116 c50461 撤回「直属上级缺位时由 HR Ops & Data 代为受理提交，代提交的案件首层审核自动升至 Head of HR」一句；Felix c50486：「S-05 Spec 已完成对应修订，页面现 v67（内部版本 v28）」（另见本表下方 2026-09-24 补）。提点②（HR Team 知会是否含 Raymond、含则拉入 sscos-hr）截至 2026-09-28 读 OSD-116（至 c50644）未见 Felix 答复。另记：04.7 v51（2026-09-24）RT-HR-DISCIPLINARY-SUBMIT 行仍载「缺位由HR Ops & Data代为受理」，与 Spec v67 不一致；候选行语义写权在流程 Owner 侧，建造侧不改、不调和。本行状态不变。

**A-13 · 切 active 次序 (L62), sumber**
> 【2026-09-28 补｜原文保留不删】本行「Kayden 已裁」出处：#nos-bo thread 1789704362.435989 第 3 条回复（1789812242.936089，Kayden，2026-09-19）原文：「切 active 仍是 Alden 的动作，但他拨开关时只核 04.9 登记和守护配置，不再另审一套标准。还有一点现在 Spec 没写：切 active 放在 N14 通过之后、N15 上线之前。这个顺序我会写进 OS 开发流 Spec，走我这边的执行链。」OS 开发流 Spec 现为 v40（2026-09-26）；v39→v40 差异仅治理频道回填，仍无该次序条款。本行状态不变。

**A-15 · 离职入口 (L64) → pakai P-5 ①. Tambahan untuk catatan L87:**
> 【2026-09-28 补｜原文保留不删】上条「建为骨架」之后，Geri NSE-1137 c50590 原文：「the status transition is a disabled placeholder node until this is answered; everything else in the piece is built」；c50645 之后未见入口改建或发布的回报（截至 NSE-1137 c50645）。

**A-17 · Arah link (L66)**
> 【2026-09-28 补｜原文保留不删】Geri NSE-1137 c50507 答复：「Link direction — yours is what we want」「Link type 10075 reads inward: "is triggered by", outward: "triggers" (read live today)」，并注明：「I will confirm it visually on the first real run and correct it if Jira renders it the other way; I would rather not call that verified from the field definition alone.」本侧 Trigger link 节点已停用，由入口建 link（c50501）。本行余首次真跑后目视确认一项，状态不变。

**A-18 · D-10 / B6 / errorWorkflow (L67)** (C-21)
> 【2026-09-28 补｜原文保留不删】三项中「挂 errorWorkflow」已完成：N20 settings.errorWorkflow＝`VUIgv9Ujj1KEoIne`，API 回读 2026-09-28T00:52:29Z（见第五区 2026-09-28 补）。余 D-10 通知与 B6 解析两项未建，本行状态不变。

**A-19 · 离职单关联状态 (L68) → pakai P-5 ②.**

**A-20 · claim-before-create (L69)**
> 【2026-09-28 补｜原文保留不删】建造人 NSE-1137 c50631（2026-09-28）答 c50585：「No objection. It matches our own build sheet rule for this seam (claim on the S-05 side before the resignation ticket is created).」并请 Geri 建前提供两项：「the exact marker you will write on the S-05 case」与「what the entry returns when your claim already exists on the S-05 case but no resignation ticket was created」。截至 2026-09-28 读 NSE-1137（至 c50645），Geri 未答。本件自身 `nos-s05-term` 的写入时点仍待定。本行状态不变。

**A-21 · L89, sumber**
> 【2026-09-28 补｜原文保留不删】上条所引 Kent 原文出处为 OSD-116 c50472（2026-09-24）：「@Bambang the build-sheet note asking which error codes count as "vacancy" no longer applies — any resolution failure = stop + alert.」

**A-22 · L91, sumber**
> 【2026-09-28 补｜原文保留不删】上条出处：Kayden 撤回＝OSD-116 c50461（【变更记录】2026-09-24）；Felix 原文＝OSD-116 c50486。

**A-23 · 对照表 Collab, catatan Inz9 dan Marketing (di bawah tabel)**
> 【2026-09-28 补｜原文保留不删】上表 Inz9、Marketing 两行备注「频道是否续用待确认」已由 Felix OSD-116 c50261 答复：「keeping both collab-hr-inz9 and collab-hr-marketing active, not merging into collab-hr-crm」；同条：「Seven department channels (CRM/Finance/FOZ/Inz9/Marketing/WealthPlus/Xloop): @sscos-bot has been added.」（页首附表对应行 2026-09-21 补已记）。04.11 登记仍待 Alden。

##### P-6.4 · 暗号表, 偏差登记, 建设备注 (baris 129–276)

**B-3 · `nos-s05-subject` (L145)**
> 【2026-09-28 补｜原文保留不删】本行读侧已实建于 N05 `LJwiAZFfnuq6tmju`（inactive）：节点 "Extract Subject AccountId" 与 "Mark Candidate Match Result" 按本行语法取 accountId；本单查无该 marker 即抛错中止（不静默当作「无重复」）。写侧（N01／N03 建单件）未建，故 N05 在其建成并写入本 marker 之前无法真跑。

**B-7 · L154 「待 N5 裁决」** (C-06 sama; untuk §一 N13/N26/N27 pakai teks C-06 di P-6.5)
> 【2026-09-28 补｜原文保留不删】上句「待 N5 裁决」：N5 已由 Kayden c50244 裁定（选 C，独立 Registry）；现待的是建库与 04.1 §一／04.8 §三 两行转正式登记（2026-09-28 读 04.1 仍 v46，该行仍「候选｜待N5」）。本段结论不变。
- Sebelum ditulis: baca isi baris 04.1 (audit hanya membaca nomor versi).

**B-8 · Pembagian versi per akun (L194)** — ambil ulang riwayat versi saat menulis (versi baru juga dari akun pribadi)
> 【2026-09-28 补｜原文保留不删】上文逐版归属为 2026-09-19 回读值。2026-09-28 以页面版本历史 API 复读：个人账号＝v3／v10／v13～v52；Backend Operations＝v1／v2／v4～v9／v11／v12（未变）。

**B-10 · 取消原因四值 (L212)** (C-13 digabung: tulis di sini saja, §三 cukup merujuk)
> 【2026-09-28 补｜原文保留不删】Spec v67（内部 v28，Felix OSD-116 c50486）已为四值逐值标类别：Duplicate Case＝失效类、员工已离职或案件失效＝失效类、Withdrawn＝撤回类、Dismissed＝撤回类；依据 04.3 v35 §六「中止分撤回类／失效类」（Kayden c50445 ③），该节原文：「机器与建设方按该标注判定走哪条路，不按原因文字猜」。建字段时 option 与类别须照 Spec A 表逐字。该字段属主单侧（未建）。

**B-11 · round (L229)**
> 【2026-09-28 补｜原文保留不删】上段「旧轮次卡片点击不会被拒」为 v5 口径。Notify 契约 v6（页面 v14）§9.4 原文：「旧轮次卡片由两把锁挡住：已处理检查（同键已有记录）与主锁（transition 失效）；前提是每轮换键」。04.4.1 v14 仍将「轮次防过期」标 🔲 待定。本流程 N07 发卡件 idempotencyKey＝`<主单key>:r<轮次>`，已按每轮换键实建（SSCSD-435 r1／r2）；四条原地转换分名配置照旧保留。

**B-12 · B6 error.code / HR Ops & Data (L240)**
> 【2026-09-28 补｜原文保留不删】本条已不适用：①「缺位由 HR Ops & Data 承接」已由 Spec v67（内部 v28）删除，改为「若系统无法解析出该员工的 Direct Supervisor，系统拦截并告警，转 HR 修正档案后重新提交／解析」（Felix OSD-116 c50486；Kayden 撤回见 c50461）；②「哪些码计为缺位」由 Kent OSD-116 c50472 答复：「no longer applies — any resolution failure = stop + alert」。故六码不再分类处置，任何 `ok:false` 一律拦截并告警。本页页首 2026-09-24 补 已记同一结论，此处补来源 comment id。

**B-13 · errorWorkflow (L242)** (C-18, C-19)
> 【2026-09-28 补】进度：N07 `77PepnEWGqTOCI61`、N20 `ToIGnEJmksSPhC85` 已挂；N04 `UBLsvYaSlCI3pLWs`、N05 `LJwiAZFfnuq6tmju` 尚未挂（2026-09-28 API 回读）。

**B-16 · c50279 dan 04.10 v20 (L273)**
> 【2026-09-28 补｜原文保留不删】上文两处「仍待 Alden 模式九扩展（c50279）」：Alden 已于 OSD-116 c50558 答复，c50576「第一批 A 已提前上线」；页首附表该行已转「已解封（2026-09-26·建设面）」，N07 发卡件已建并实测（SSCSD-435）。第一批 B（10/1）与主单回写字段／Screen 仍未具备，见该行。另：04.10 现行 v21，上文「v20」为当时值。

##### P-6.5 · §一 sampai §七 (baris 277–467)

**C-03 · §一 「统计」 dan status N04/N05**
> 【2026-09-28 订正｜原文保留不删】上段「统计」为 2026-09-18 口径。其后：N04（`UBLsvYaSlCI3pLWs`）、N05（`LJwiAZFfnuq6tmju`）、N20（`ToIGnEJmksSPhC85`）已建骨架（见本区 2026-09-24 补），N07 审批卡发送件（`77PepnEWGqTOCI61`）已建并以 SSCSD-435 实跑（见 N07 行 2026-09-26 补）；四件均 inactive，均未在 04.9 登记为件（见第五区）。「阻塞 6」所含「N07 审批卡部分」之模式九阻塞已于 2026-09-26 解封（建设面；页首附表模式九行）。N04／N05 两行「状态」格原文未改，以本段为准。各类计数不在此重算。

**C-04 · §一 N07** (tulis dalam satu 【补】 bersama P-1③ dan P-3)
> 【2026-09-28 补｜原文保留不删】①上文「审批卡交互阻塞（模式九扩展）」为 2026-09-26 之前口径：第一批 A 已上线（Alden OSD-116 c50576），页首附表模式九行已记「已解封（2026-09-26·建设面）」。②本节点除上列六条外，另用转换 9 `Cancel as Duplicate`（审批卡「确认重复」按钮，c50558；见第二区转换 9 行）。③HR 正式使用条件依 c50558：「N07 正式给 HR 用，需要 A、B 都上线；另外审批卡回写的主单字段与 Screen（c50234 第 2 项）是前置」——第一批 B 定 10/1，主单字段与 Screen 见本行 2026-09-28 订正。

**C-05 · §一 N09** (prioritas rendah)
> 【2026-09-28 补】Kent #nos-bo 1790408077.181699（2026-09-26）「共用零件单独成批、先建先发」提案所列待建共用件含「专用邮箱收信件（S-05 N09）」，请 Alden 9/30 前回复；截至 2026-09-28 该帖无回复。本行阻塞状态不变。

**C-06 · §一 N13/N26/N27 kolom Project** — baca 04.1 dulu
> 【2026-09-28 补｜原文保留不删】上文「待 N5 裁决」：N5 已由 Kayden c50244 裁「选 C」（见页首附表 Registry 行）；现余 04.1 §一 该行转正式登记（key、Issue Type、可见性），本侧未见完成，三行仍阻塞。

**C-07 · §一 N28** (fakta 04.3 v35; bagian grup menunggu Kent → tulis bersama P-2)
> 【2026-09-28 补｜原文保留不删】本行两项待确认均已由 04.3 v35（Kayden OSD-116 c50445，变更日志 C-320）作出规定：①执行身份——§六「主单转入已取消（执行中止）」允许执行者加「该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」；②模式五互斥——§六 撤回规则原文「例外：失效类中止不受此互斥约束…即使已有子单「已完成」，仍由上表允许执行者把主单转「已取消」，并在同一动作范围内把未关子单转「已取消」…Resolution 一律 Cancelled」；Spec A 表「取消原因」已标「员工已离职或案件失效（失效类）」。执行顺序依 c50445「先把主单转「已取消」，再取消未关子单」。余项：HR Ops & Data 对应的 Jira 组待 Kent 答 OSD-116 c50632；「取消原因」为主单侧字段、尚未建；`hasScreen`／`isConditional` 回读与实跑仍待补。
- Juga §二 transition 11 「与模式五互斥口径待确认」: rujuk ke 【补】 ini.

**C-09 · §二 Rejected/Cancelled 「本轮回读路径」**
> 【2026-09-28 补｜原文保留不删】上两行括注「单据未进入该态」为 2026-09-18 状态。其后实单已进入：Rejected——SSCSD-423（2026-09-22，转换 3）、SSCSD-435（2026-09-26，经 Slack 审批卡转换 3，执行 17297／17298）；Cancelled——SSCSD-421（转换 8）、SSCSD-422（转换 9），均 2026-09-22。证据见第八区。

**C-11 · §二 transisi 3/4 「本轮回读」** (prioritas rendah)
> 【2026-09-28 补】另经 Slack 审批卡回调路径实跑：转换 4（SSCSD-435，执行 17293／17294）与转换 3（SSCSD-435，执行 17297／17298），执行身份为平台回调件 `6wdHhygWmyRFQAoX`。见第八区 2026-09-26 N07 实跑。

**C-13 · §三 取消原因** → cukup rujuk B-10: 「【2026-09-28 补】类别标注见建设备注「取消原因四值」2026-09-28 补。」

**C-14 · §三 syarat nilai option** (hanya pencatatan; pilihan nilai menunggu Felix)
> 【2026-09-28 补】select 类主单字段（Warning 等级、PIP 周期等）建成后，其 Jira option 值须与 N07 审批卡 modal 的 `o` 值逐字一致，方可去掉 `noWrite`（Notify v6；Alden c50558）。现卡上取值：Warning 等级＝Verbal／Written／Final Written；PIP 周期＝15 天／30 天／60 天／90 天。Spec A 表 Warning 行写「Verbal Warning／Written Warning／Final Written Warning」，⓪ 区写「Verbal/Written/Final Written」，两处写法不同，建造侧不自选，待字段建成时与字段 Owner、流程 Owner 一并确认。

**C-15 · §五 N07 bentuk kartu vs Spec** (hanya pencatatan; mengubah kartu menunggu Felix + izin Bambang)
> 【2026-09-28 补】N07 卡 modal 与 Spec 增补区 A 表之差，如实登记、不自拟：①Spec「PIP 参数」列八项（改善问题、改善目标、衡量标准、PIP 周期、开始日期、到期日期、负责跟进人、Check-in 安排），现卡收六项，缺「到期日期」「负责跟进人」；「六个字段」出自 Alden c50558，未说明另两项由谁、如何取得。②Spec「纪律记录有效期」行载「N07／N10／N14（确定Warning等级的同一时刻设定）」，现「通过·Warning」modal 未含该项。两项是否由件推导或另处收集，待流程 Owner（Felix）确认后再改卡；现全部 noWrite，不影响已测路径。

**C-16 · §五 补 09-20 ①** → teks ada di P-6.2 (baris baru 附表).

**C-17 · §五 N07 「04.9 三位一体」 dan §六 Notify** — ambil nomor versi 04.9/04.9.1 saat menulis
> 【2026-09-28 补】OSD-116 c50595 (c) 所请两项已在平台侧登记（2026-09-28 实读）：04.9 Data Table 登记区「NOS Platform Approval Cards」（`jdF8S9cV7ZIZowvw`）消费方列已含「纪律与绩效改进处置｜N07｜审批卡发送（读：按 idempotency_key＋flow_key 查同一轮是否已发；未上线）」；04.9.1 Notify 区块「被哪些流程调用」已含「纪律与绩效改进处置（1 件：N07，未上线）」。本件自身的索引行与 04.9.7 详情块仍未加（见页首附表「本流程 n8n 件 04.9 登记」行）。

**C-18 · §五 N04, baca ulang API**
> 【2026-09-28 补·API 回读】N04 现行版本：versionId `0aad8ecb-e97e-4297-9908-b6c15559fdca`，updatedAt 2026-09-23T09:38:03.808Z，active false，节点 2 个（N04 Trigger → Call N05）。settings 未挂 errorWorkflow、未设 callerPolicy——本区「全部件上线前须挂 `settings.errorWorkflow`」尚未对本件执行。

**C-19 · §五 N05, baca ulang API**
> 【2026-09-28 补·API 回读】N05 现行版本：versionId `ad14f33e-0434-4788-95cd-542abf56bd5d`，updatedAt 2026-09-24T10:06:48.597Z，active false，节点 17 个（含 sticky 3）。settings 未挂 errorWorkflow、未设 callerPolicy。历史纪律记录一半为占位：固定输出 `historicalDisciplinaryRecords: []` 与 `historicalRecordsStatus`（Registry 未建，见 N13 行）。本件尚无干跑记录。
- Sebelum ditulis (C-18, C-19): baca ulang N04/N05 lewat API; kalau versionId berubah, pakai nilai terbaru.

**C-20 · §五 N05 atau §八 尚未测试: risiko belum diuji** (inferensi; mengubah n8n butuh izin Bambang)
> 【2026-09-28 补·待验】按 07.06.1 E9 推断（未实测）：N05 "Read Subject Marker Comments" 与 "Search Open S-05 Cases" 未开 `alwaysOutputData`；零评论或零候选（即「无重复」常态）时下游或不执行，缺 marker 不抛错、"N05 Result" 无输出。须以干跑覆盖零结果两例后定是否改件（先例：N20 v52「Read S-05 Case Comments」）。

**C-22 · §六 Notify**
> 【2026-09-28 补】Notify 契约现行 v6「已上线」（页 lastModified 2026-09-26）：modal 下拉、`auditVisibility`、`noTransition`、`decisionLabel`、已处理检查（详见建设备注 2026-09-26 补·v6）。04.9.1 Notify 区块（2026-09-28 实读）已登记本流程为调用方（N07，未上线），并载「组→频道映射硬编码在 Resolve Recipients」（HR→`C0BHL8AE68G` sscos-hr）；本行原记「映射住 04.11」，04.11 无本流程领域行。两处记载并存，建造侧不调和；HR 频道属 04.5.3 测试红线。

**C-23 · §六 Slack Approval**
> 【2026-09-28 订正｜原文保留不删】上文「v5 在产…缺下拉／不转态出口／重复确认」为 v5 口径，已过期：第一批 A 已上线（Alden OSD-116 c50576）；04.9.1 本件状态（2026-09-28 实读）载「已处理检查、审批记录新格式（流程声明启用）、不转态出口、弹窗下拉」。疑似重复确认依 c50558 以现有能力实现（`Cancel as Duplicate` 按钮）。第一批 B（弹表单改造）定 10/1，未上线。

**C-24 · §六 B6**
> 【2026-09-28 补】①错误码处置口径：Kayden #nos-bo 1790231960.408669 起草 04.5 §五 通用规则「②解析失败一律视为档案问题：该节点拦住不执行，按调用方要求告警 nos-ops，由 HR 修正档案后重新提交或重新解析」；04.5 lastModified 2026-09-19，未见落页，属草案。离职侧同口径见 Kent NSE-1137 c50539「any resolution failure means block and alert」。②消费方登记：04.9.1 B6 区块（2026-09-28 实读）「被调用」栏仍无本流程，页首附表对应行仍待办。

**C-25 · §六 baris baru di luar tabel: Data Table Approval Cards**
> 【2026-09-28 补·表外补登（表格原行不动）】另复用平台 Data Table：NOS Platform Approval Cards `jdF8S9cV7ZIZowvw`（04.9 Data Table 登记区）——N07 发卡件发卡前按 `idempotency_key`＋`flow_key` 查同一轮是否已发（A2）；本表按 flow_key 分区，查询一律带 flow_key 过滤（04.9 该行原文）。04.9 消费方列已含本件（2026-09-28 实读）。

**C-26 · §七 (catatan celah; isi menunggu keputusan Kayden 9/29)**
> 【2026-09-28 补】本区仍待填。相关标准缺口：Kent #nos-bo 1790242043.098949（口径／参数页放哪、机器怎么读），Alden 1790407310.843309 提「机器只读数据表，不直接解析 Confluence 页面」、转写走 GOV 维护单、数据表登 04.9；Kayden 1790401062.118569 载「还没有做任何决定」、9/29 前给结论。本流程 Spec 含参考值（纪律记录有效期 Verbal 3 个月／Written 6 个月；PIP 周期 15／30／60／90 天），现 N07 卡 modal 直接写有 PIP 周期选项。哪些属政策参数、落何处，待该标准裁定后再填，建造侧不先行。
- Sebelum ditulis: cek apakah Kayden sudah memutuskan.

##### P-6.6 · §八 dan §九 (baris 468–565)

**D-1 · §八 尚未测试 baris 1** (D-14 untuk §九)
> 【2026-09-28 补｜原文保留不删】本行 3／8／9 三条已于 2026-09-22 实跑（SSCSD-423／421／422，见上表 2026-09-22 行）；转换 3 另于 2026-09-26 经平台回调以 Bot_SSC 执行一次（SSCSD-435，执行 17298）。2026-09-28 以 Backend Operations 回读五张 TEST 单末态与上表一致。本行仅余 `Abort Case`(11)：转态权限 condition 待 Kent 答复 OSD-116 c50632（组 `SSCOS｜HR`）后配置，配置前不实跑。

**D-3 · 真信验收 「无发信件」**
> 【2026-09-28 补｜原文保留不删】「无发信件」已不成立：N07 审批卡发送件 `77PepnEWGqTOCI61` 已建，2026-09-26 两次发卡至建造人本人 DM（白名单甲，执行 17290／17295，Slack ts `1790428207.178839`／`1790428675.102999`）。04.5.3 §五 判据 1 要求「真信核对记录」（打开逐项核对内容与格式），本页尚未登记该核对记录；Notify `ok:true` 不算。其余发信类节点（D 表各通知）未建。

**D-5 · 幂等验收 「无写入件」**
> 【2026-09-28 补｜原文保留不删】「无写入件」已不成立：①N07 首发消息：执行 17292 以同入参重发，A2 闸命中共享卡表行 258，未调 Notify（见上「N07 实跑」）。04.5.3 §五 判据 2 的通过证据为「回读断言目标数据仍只有一行」，本页未登记对共享卡表 `SSCSD-435:r1` 行数的回读。②N20：执行 17374 为 pinData 干跑（Call／Write Marker 未真跑），不构成判据 2 的证据。其余写入口未建。

**D-6 · 带主体测试 「测试档案未到位」**
> 【2026-09-28 补｜原文保留不删】「测试档案未到位」已不准确：本流程复用 NTP-187（Kent c50227 第 6 点），2026-09-19 建造侧已自验 04.5.3 §二 第 3～5 项（见下「测试档案」段）。2026-09-28 回读 NTP-187 各项值未变。本行现存缺口为：①上司档案 Talent Status 待 Kent 自读（附表对应行）；②Work Email 空、Department 无 Team Project（见下实读结论①②）；③主单回写字段与专属 Screen 未建。

**D-7 · Tabel NTP-187 (Talent ID)**
> 【2026-09-28 补】2026-09-28 以 Backend Operations 回读 NTP-187：上表各项值与 2026-09-19 一致（cf17994「TEST｜Ali」、cf17993「TEST Ali」、cf18002 Test、cf17995 Backend Operations、cf17996 Kent、cf18051 空、cf17998 GENERAL SERVICES）。另：Talent ID（cf17992）已于 2026-09-24 16:53 由 Felix_HR 从 `TAL-184` 改为 `TAL-TEST-001`（changelog 1376150），与 04.5.3 §三「自动组装标题的例外」示例一致。本流程主单标题由自动化拼装（第四区「标题格式」），带主体测试时标题侧标识如何满足，依 04.5.3 §三 该例外，建造侧不另拟。

**D-8 · 实读结论 ③ (jumlah DM)**
> 【2026-09-28 补｜原文保留不删】按 Spec（2026-09-24 版）D 表复核：以 Direct Supervisor 为接收方、经 Slack 私信者另有 D-16（N07 已拒绝，「Direct Supervisor（发起人）」，「Slack私信（发起人）」），上文「九条」未含。经部门 Collab 频道者除 D-17 外另有 D-7、D-14、D-15。NTP-187 部门为 GENERAL SERVICES，其 Collab 频道落点见附表「部门值→Team Project 对照表与兜底」。

**D-10 · 守护登记与演练 (versi)**
> 【2026-09-28 补】上文所引两页已移版：04.3 现行 v35（Kayden OSD-116 c50445），§五「待子单完成→处理中」映射原文仍在；04.8 现行 v21（见页首「⑤」2026-09-22 订正），cf18029 四值原文未变。建造侧落地读法仍「待确认」。私信接收方「HR Ops & Data」对应的 Jira 组／人员尚无来源点名（已于 OSD-116 c50632 就 `SSCOS｜HR` 请 Kent 确认，Felix c50644 补充说明），确认前本件接收方不定。

**D-11 · 守护 「全局报错」**
> 【2026-09-28 补】挂载进度：N07 审批卡发送 `77PepnEWGqTOCI61`（2026-09-26 回读，2026-09-28 复读一致）与 N20 `ToIGnEJmksSPhC85`（2026-09-28T00:52:29Z 回读）均已挂 `settings.errorWorkflow`＝`VUIgv9Ujj1KEoIne`。演练证据仍 🔲。

**D-12 · L557 「本件上线前须挂 errorWorkflow」**
> 【2026-09-28 补】上句「上线前须挂 errorWorkflow」已完成：N20 `ToIGnEJmksSPhC85` settings.errorWorkflow＝`VUIgv9Ujj1KEoIne`、callerPolicy＝workflowsFromSameOwner，经 UI 设置（Bambang），API 回读 2026-09-28T00:52:29Z（见第五区 2026-09-28 补）。入口仍为骨架、未发布，本件试跑仍止于 "Check Entry Result"（2026-09-28 干跑 Call 节点为 pin）。

**D-14 · §九 「四条终态转换」**
> 【2026-09-28 补｜原文保留不删】「四条终态转换」中 3／8／9 已于 2026-09-22 实跑（见第八区），现余 `Abort Case`(11) 一条实跑，与 1／10／11 三条属性回读；转换 9、11 配 condition 后须重读（见第八区「尚未测试」2026-09-28 补）。

**D-15 · §九 「四条原地转换幂等闸」** (bersama P-1)
> 【2026-09-28 补】上列「四条原地转换幂等闸」：建造侧决定不自建，由平台「已处理检查」（Notify v6 §9.4，已上线）承担；依据与残余边界见页首附表对应行 2026-09-28 补。连点负向用例并入 N07 端到端测试，仍为上线前必测项。

**D-17 · Versi 04.5.3**
> 【2026-09-28 补】04.5.3 于 2026-09-28 再次修订（2026-09-28 实读）。与 2026-09-25 版对照，仅第二节「例外｜收件人就是主体」条件 2 改写（标题由流程自动组装时，可在主体标识的 Talent ID 之后嵌入 TEST）；本区所引 §二 第 3～5 项、§三 双标识、§四、§五 四判据原文未变。本流程测试未使用该例外。

**D-18 · Resolution 全覆盖 复核** (opsional)
> 【2026-09-28 补】复核：SSCSD 内 `Disciplinary Case` 现共 5 张（SSCSD-411／421／422／423／435，均为 TEST 单），全部 statusCategory＝Done 且 resolution 非空（Done／Cancelled／Cancelled／Rejected／Rejected）。同一查询读出 5 张即为对照，非「看不见」。

##### P-6.7 · Menunggu orang lain (jangan ditulis sebelum syaratnya terpenuhi)

(2026-09-29: A-14 (C-10, D-2) dipindah ke **P-17** karena Kent sudah menjawab c50632 di c50705.)

| Item | Isi | Menunggu |
|---|---|---|
| C-01 + §四 标题格式 | Nama Request Type dua bahasa dari Felix c50261 butir 1; yang tersisa: backfill 04.7 | Baca ulang 04.7 |
| C-15 (keputusan) | Isi kartu: 到期日期, 纪律记录有效期 (负责跟进人 sudah dijawab Spec ⓪区 十, lihat P-9②) | Felix |
| C-26 (isi) | Isi §七 | Keputusan Kayden (9/29) |
| D-13 | Marker patroli 卡死／漏账 | Geri c50631 dan K-10 |

##### P-6.8 · Belum diputuskan Bambang (tidak masuk antrean tulis)
- **B-2:** teks 「写入侧已实建」 untuk `nos-s05-dup`, dan perubahan status 「拟定·未建」→「已建·inactive」.
- **B-5:** `nos-s05-case` 「事件入口取 S-19 侧主单 key」 vs baris 附表 「S-19 侧建在绩效卡」. Inferensi, belum dikonfirmasi. Usul: diperiksa saat prebuild-scan N01.
- **B-14:** tiga syarat E16 v40 dan penilaian probe N05. Kutipan harus dicocokkan dengan v40 dulu.
- ~~**D-4:**~~ Dipindah ke antrean **P-22** (2026-10-02).
- **D-9:** 实读结论 ④ supervisor. Belum ada teks.
- **D-16:** kutipan 「留存不删（04.5.3 §四）」 mungkin kurang tepat.
- ~~**C-27:**~~ **Selesai 2026-09-29**: sticky note dan description N07 dikoreksi di n8n (evidence E61, perintah Bambang 「Perbaiki catatan basi di N05 dan N07」), tercatat di build sheet v57 (P-16 ①, 【补】 `b28d09290089`).
- **Catatan A-01:** apakah Spec v67 memicu kriteria 04.5 §6.1 「基线版本 ≠ 页面当前版本」? Inferensi, belum dikonfirmasi. Belum dijadikan item K.



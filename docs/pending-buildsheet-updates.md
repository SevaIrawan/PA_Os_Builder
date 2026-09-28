# Antrean update build sheet S-05 (2096463922)

Draf untuk build sheet dikumpulkan di sini supaya nanti ditulis **sekaligus dalam satu versi**. Tujuannya menghindari naik versi hanya untuk perubahan kecil (permintaan Bambang, 2026-09-28).

Aturan:
- **Isi file ini hanya draf, bukan izin menulis.** Penulisan ke Confluence menunggu perintah eksplisit Bambang (CLAUDE.md §3).
- Sebelum menulis, ambil versi terbaru halaman dulu (07 §二「先查后写」). Jalankan dryRun, lalu tulis. Setelah itu baca ulang dan bandingkan per tag.
- Semua perubahan bersifat **menambah** (【补】). Teks lama tidak dihapus.
- Bahasa: Mandarin, mengikuti isi halaman.
- Kalau item sudah ditulis ke build sheet, pindahkan ke bagian "Sudah ditulis" dan cantumkan versi halamannya.

Versi build sheet terakhir yang dibaca: **v53** (2026-09-28T07:07:32Z).

---

## Antre

Sisa yang **belum** ditulis setelah v53:
- **P-4③** (kata 「打回补件」): Alden sudah menjawab di c50647, teksnya ada di P-7④.
- **P-6.7**: D-13 (marker patroli, tunggu Geri c50631 dan K-10). Isi keputusan C-15 (Felix) dan isi §七 (C-26, keputusan Kayden 9/29) juga belum; yang sudah ditulis hanya catatan keadaannya.
- **P-6.8**: semua item di sana masih menunggu keputusan Bambang (B-2, B-5, B-14, D-4, D-9, D-16, C-27, catatan versi dasar Spec v67).
- Setelah Kent menjawab c50632: tambahkan 【补】 baru untuk transisi 9/11 dan baris Abort Case, lalu hitung ulang statistik 附表.


### P-7 · Jawaban Alden OSD-116 c50647 (2026-09-28 15:11 +07)

Dasar: OSD-116 c50647, dibaca penuh 2026-09-28. Sudah dicek: OSD-116 s.d. c50647, NSE-1137 s.d. c50645, build sheet v53.

**① 页首附表, baris 「主单专属 Screen 未建」: ditambahkan di akhir sel 「依赖谁」 (atau 「解除判据」, dipilih saat menulis)**

> 【2026-09-28 补】上文三说已由 Alden OSD-116 c50647 (a) 定：「since 9/24, SSCSD main-ticket fields go through the same 04.10 process — Kent approves and builds them; only the risk categories (making a field required on the shared screen, changing a shared object others already rely on, and the like) come to me. So please file the field list to @Kent as a 04.10 three-cell request.」建造侧下一步：按 04.10 格式向 Kent 提交字段清单（未提交）。同条：「Right now Jira has no Return Count, HR Decision Basis, Cancellation Reason, Final Outcome or Warning Level, and no fields yet for the initial PIP parameters.」

**② §一 N07 (atau §五 blok N07): ditambahkan**

> 【2026-09-28 补】Alden OSD-116 c50647 (a) 平台侧四点：①「No new approver field: use the existing Approved By (`customfield_18061`). It is already on the Disciplinary Case edit screen, so you can set `approverFieldId` now.」②「Any field the card writes back must be on the Disciplinary Case edit screen first, otherwise Jira rejects the whole write. Keep `noWrite` until then.」③写回形状：dropdown → `option`、multi-line → `adf`、number → `number`、person → `user`。④「Return count needs +1: the card can only write constants or values typed in the modal, not increments, so please have S-05 add one itself after the return transition.」现 N07 件未设 `approverFieldId`；打回次数 +1 属本流程新增建设项，承载件未定。

- Sebelum ditulis: kalau `approverFieldId` sudah dipasang di N07, sesuaikan kalimat terakhir. Posisi `customfield_18061` di edit screen belum dicek sendiri, **inferensi, belum dikonfirmasi** (Alden yang menyatakan).

**③ 页首附表, baris 「本流程 n8n 件 04.9 登记」: ditambahkan di akhir sel 「解除判据」**

> 【2026-09-28 补】Alden OSD-116 c50647 (b)：「a 7th volume is open for S-05 — 04.9.7｜详情：纪律与绩效改进处置. Please register N04, N05, N07 and N20 per 04.9 §一: a row in the main-page index and a block in 04.9.7.」登记由本侧执行（建造单外页面，由建造人本人写入）。

- Catatan untuk Bambang: menulis 04.9 / 04.9.7 bukan wewenang Claude (CLAUDE.md §3). Claude hanya bisa menyiapkan draf isinya.

**④ §八 N07 实跑 「观察（不改）」: ditambahkan (menutup P-4③)**

> 【2026-09-28 补】上文「不通过 Rejected｜打回补件」措辞：Felix OSD-116 c50639 请改；Alden c50647：「the Decision line of the approval record will show only the button's own label when one is set — e.g. 「打回补件 · Return for info」 instead of 「不通过 Rejected｜打回补件」. This ships with batch 1B on 10/1.」本侧不改件，10/1 后回读实际记录格式。Felix c50639 两项条件（记录带实际判断人；记录能否被编辑或删除），Alden c50647：「I will answer separately once I have checked the permissions.」

---

## Sudah ditulis

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

| Item | Isi | Menunggu |
|---|---|---|
| A-14 (C-10, D-2) | Baris 附表 Abort Case: sumber c50445, c50632, Felix c50644; transisi 9 「仅服务账号」 vs Kayden 「N07「确认重复」同口径」 (K-13); condition 9/11 dan baca ulang `isConditional` | Kent, jawaban c50632 (tulis bersama P-2) |
| C-01 + §四 标题格式 | Nama Request Type dua bahasa dari Felix c50261 butir 1; yang tersisa: backfill 04.7 | Baca ulang 04.7 |
| C-15 (keputusan) | Isi kartu: 到期日期, 负责跟进人, 纪律记录有效期 | Felix |
| C-26 (isi) | Isi §七 | Keputusan Kayden (9/29) |
| D-13 | Marker patroli 卡死／漏账 | Geri c50631 dan K-10 |

##### P-6.8 · Belum diputuskan Bambang (tidak masuk antrean tulis)
- **B-2:** teks 「写入侧已实建」 untuk `nos-s05-dup`, dan perubahan status 「拟定·未建」→「已建·inactive」.
- **B-5:** `nos-s05-case` 「事件入口取 S-19 侧主单 key」 vs baris 附表 「S-19 侧建在绩效卡」. Inferensi, belum dikonfirmasi. Usul: diperiksa saat prebuild-scan N01.
- **B-14:** tiga syarat E16 v40 dan penilaian probe N05. Kutipan harus dicocokkan dengan v40 dulu.
- **D-4:** catatan penyimpangan: exec 17290 tanpa penanda TEST.
- **D-9:** 实读结论 ④ supervisor. Belum ada teks.
- **D-16:** kutipan 「留存不删（04.5.3 §四）」 mungkin kurang tepat.
- **C-27:** sticky note dan description N07 di n8n sudah basi (Felix c50639, K-11). Menulis ke n8n butuh izin terpisah.
- **Catatan A-01:** apakah Spec v67 memicu kriteria 04.5 §6.1 「基线版本 ≠ 页面当前版本」? Inferensi, belum dikonfirmasi. Belum dijadikan item K.



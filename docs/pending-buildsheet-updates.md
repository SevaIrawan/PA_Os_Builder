# Antrean update build sheet S-05 (2096463922)

Draf untuk build sheet dikumpulkan di sini supaya nanti ditulis **sekaligus dalam satu versi**. Tujuannya menghindari naik versi hanya untuk perubahan kecil (permintaan Bambang, 2026-09-28).

Aturan:
- **Isi file ini hanya draf, bukan izin menulis.** Penulisan ke Confluence menunggu perintah eksplisit Bambang (CLAUDE.md §3).
- Sebelum menulis, ambil versi terbaru halaman dulu (07 §二「先查后写」). Jalankan dryRun, lalu tulis. Setelah itu baca ulang dan bandingkan per tag.
- Semua perubahan bersifat **menambah** (【补】). Teks lama tidak dihapus.
- Bahasa: Mandarin, mengikuti isi halaman.
- Kalau item sudah ditulis ke build sheet, pindahkan ke bagian "Sudah ditulis" dan cantumkan versi halamannya.

Versi build sheet terakhir yang dibaca: **v52** (2026-09-28T01:14:41Z).

---

## Antre

### P-1 · `nos-s05-review` tidak dibangun (keputusan Bambang, 2026-09-28)

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

**④ 建设备注, paragraf yang memuat 「故四条原地转换的防重复必须由调用方自建幂等闸」: ditambahkan setelah paragraf itu**

> 【2026-09-28 补｜原文保留不删】上段「副锁…均登记「未实现」」为 v5 口径。Notify 契约 v6 起副锁已实现（已处理检查，已上线），防重复改由平台承担，本侧不自建幂等闸；见页首附表对应行 2026-09-28 补。

### P-2 · Catatan transition 11 (Abort Case): konfirmasi Owner 04.3 sudah ada

Dasar: OSD-116 c50445 (Kayden, 2026-09-24): 「04.3 §六 已改好并复检通过（04.3 现 v35…）」, 「Abort Case（id 11）转态权限配给 HR Ops & Data 角色组；N07「确认重复」同口径…建造单登记依据 04.3 v35 §六」. 04.3 dibaca ulang 2026-09-28: baris 「主单转入「已取消」（执行中止）」 memuat 「该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」.

**§二 transition 表, baris id 11: ditambahkan di akhir sel 「允许执行者」**

> 【2026-09-28 补】上文「配置前须经 04.3 Owner（Kayden Lee）确认」已由 Kayden OSD-116 c50445 给出：04.3 v35 §六 执行中止行已加「该 Spec 增补区 B 登记的处置角色组（如 S-05 的 HR Ops & Data）」；执行顺序「先把主单转「已取消」，再取消未关子单」。HR Ops & Data 对应的 Jira 组无任何来源点名；现存唯一 HR 组为 SSCOS｜HR（成员 Felix_HR、Yuki Liew_HR，SSCSD 角色 Service Desk Team），已于 OSD-116 c50632 请 Kent 确认。确认前 condition 不配。

- Sebelum ditulis: cek apakah Kent sudah menjawab c50632. Kalau sudah, isi paragraf ini disesuaikan dengan jawabannya.

### P-3 · Koreksi catatan build sheet soal siapa yang membangun field tiket utama N07

Dasar: lihat `docs/open-issues.md` K-11.

**§一 配置对应表, baris N07: ditambahkan di akhir sel status**

> 【2026-09-28 订正｜原文保留不删】上文 2026-09-26 补「回写主单字段仍待 Alden／V1 建字段与 Screen」与 #nos-bo 1790228926.781229 第 5 点（Alden，2026-09-24）不一致：「纪律处置那 5 个主单字段加屏幕…现在就请 Kent 按五类判、走第五节流程建；挂 Disciplinary Case 那张共用屏时，设成选填直接做，要设必填再找我」。Alden OSD-116 c50558（2026-09-26）另写「这件我另外回复」。两说并存，建造侧不调和，见 open-issues K-11。

- Sebelum ditulis: cek apakah Alden atau Kent sudah menjawab, dan apakah field atau Screen sudah dibangun.

### P-4 · Keputusan Felix OSD-116 c50639: visibilitas internal (N07) dan syarat pencatat keputusan (N10/N14/N17)

Dasar: OSD-116 c50639 (Felix_HR, 2026-09-28 10:59 +07, kepada Alden), dibaca penuh.

**① §五, blok 【2026-09-26 补·N07 审批卡发送】: ditambahkan setelah butir 「卡形（依 c50558）…」**

> 【2026-09-28 补】auditVisibility＝internal 已由流程 Owner 定案：Felix OSD-116 c50639 (2)「审批记录可见性：选 internal。记录里是 HR 的内部判断过程，主管该知道的结果已通过 D-2、D-16 等通知送达，案件对外状态他仍看得到。」上文「Felix 定前按 internal」为定案前口径，现行值不变。

**② 页首附表: baris baru (建造侧待办), atau catatan di baris N10／N14／N17 §一 — letak dipilih saat penulisan setelah membaca versi terbaru**

> 【2026-09-28 补】Felix OSD-116 c50639 (1) 接受「字段留最新一次、连续记录放主单评论流」，附两个条件：①「N10/N14/N17 由 S-05 代写的记录，要和 N07 一样带上实际做判断的人。History 作者只显示 Bot_SSC，谁判的只能靠这条记录。」②「请确认这些记录普通用户（含 HR）不能编辑或删除；如果做不到，请写明以字段修改历史为准。」①为建造侧在 N10／N14／N17 建件时的必做项；②问的是 Alden，待其答复。记录格式依 Alden c50558「格式写进平台契约 04.4.1」。

**③ Terkait U-8 (kata 「打回补件」): tidak ditulis ke build sheet sekarang.** Felix di c50639 meminta Alden mengganti 「不通过 Rejected｜打回补件」 menjadi 「打回补件 Return for info」. Tunggu jawaban Alden, lalu perbarui catatan 「观察（不改）」 di §八 N07 实跑.

- Sebelum ditulis: baca ulang OSD-116 setelah c50644 untuk jawaban Alden atas syarat ② dan soal kata 打回补件.

---

## Sudah ditulis
(belum ada)

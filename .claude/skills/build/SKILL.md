---
name: build
description: Skill 流程建设 NOS untuk builder BO (tahap 开发 / OS开发流Spec｜N12). Pakai saat Bambang bilang "Build | S-xx", mau mulai atau melanjutkan build suatu alur, menyusun 开工对齐清单, atau mengerjakan item build sheet. Ini salinan terkendali dari 07.06 §「流程建设 Skill（正式原文）」, jadi wajib cek drift dan membaca halaman terbaru setiap kali dijalankan.
---

# build: 流程建设 Skill (salinan terkendali)

## Status salinan ini
- **Sumber resmi satu-satunya:** 07.06｜建设指南, pageId **1730347066**, bagian berjudul 「流程建设 Skill（正式原文）」 dan sub-bagian 「流程建设 skill｜适用者：BO 建设团队」.
- Isi halaman itu tentang dirinya sendiri: 「BO 建设团队使用的 Project Instruction 是受控部署副本，不得反向覆盖本节。每次启动必须先读取本页当前版本执行；副本与本页不一致时，停止执行并报告『部署漂移』。不得把章节号或步骤正文写死在 Project Instruction——按语义标题定位。」
- Salinan diambil 2026-09-26. Saat itu 07.06 lastModified Sep 15, 2026.
- Skill lokal tim BO (disebut Kent di OSD-116 c50071 dan #nos-bo 1789549825.279199) **tidak digunakan** di sini karena isinya tidak terlihat (lihat `docs/open-issues.md` U-3). Skill ini dibangun **hanya** dari halaman 07.06.

## Langkah 0: cek drift (wajib, sebelum langkah lain)
1. Baca 07.06 (1730347066) terbaru lewat **Atlassian_Rovo** `getConfluencePage` (markdown).
2. Cari bagian berdasarkan **judul**, bukan nomor: 「流程建设 Skill（正式原文）」 → 「流程建设 skill｜适用者：BO 建设团队」.
3. Bandingkan setiap butir di sana dengan bagian **"Salinan butir Skill"** di bawah.
   - **Sama** → lanjut.
   - **Berbeda** → **BERHENTI**. Laporkan 「部署漂移」 ke Bambang: sebutkan butir yang berbeda (lama vs baru) dan tanggal lastModified halaman. Jangan jalankan versi lama, dan jangan memperbarui salinan ini tanpa persetujuan Bambang.
   - **Halaman tidak bisa dibuka** → BERHENTI (Anchor 04 强制停止条件「权威页打不开」).

## Langkah 1: jalankan sesuai halaman terbaru
Setelah drift lolos, **ikuti isi halaman saat ini**, bukan ringkasan di file ini. Minimal:
1. **Jira dulu** (Anchor 04, bagian 「AI 机器执行合同」 butir pertama). Baca Feature alur ini (contoh S-05 = OSD-116): status, Parent Epic, link, dan comment terbaru. Tentukan comment terakhir yang sudah dibaca. Jangan pakai ringkasan lama.
2. Baca **07｜指南** (1704362028) bagian 「通用纪律」 dan 「标准缺口回报格式」, lalu **07.06 penuh**.
3. Baca **07.06.1** (1712226375) 「主题速查」, lalu buka entri yang cocok dengan pekerjaan ini.
4. Baca **Spec yang sudah dibekukan** beserta bukti freeze-nya (marker freeze di Feature Comment) dan **build sheet** alur ini. Keduanya versi terbaru.
5. Jalankan 「开工前置四动作」 dari 07.06, lalu susun **开工对齐清单** dengan empat kolom tetap: 动作｜结果｜需流程 Owner 确认的问题｜建设者建议答案.
6. Cek **tabel blocker build sheet** (建设待办／阻塞表) baris demi baris. Untuk setiap baris, nyatakan apakah 「解除判据」-nya sudah terpenuhi. Sertakan bukti (pageId/comment id/hasil API). Kalau tidak ada bukti, statusnya tetap seperti di tabel.

## Aturan akun (dari CLAUDE.md §2)
- Konfigurasi dan tes Jira (SSCSD dan lainnya) → **Atlassian_Rovo** (Backend Operations). Assignee ditulis eksplisit.
- Comment Feature (contoh OSD-116) dan edit build sheet → **Atlassian_MCP** (akun pribadi Bambang).
- **Setiap penulisan** (comment, edit halaman, transisi, membuat tiket, mengubah n8n) → tunjukkan draf, akun, dan dampaknya, lalu **tunggu persetujuan Bambang**. Setelah menulis, **baca ulang**.
- Tindakan yang tidak bisa dibatalkan dan lima kelas Alden (04.10 §2.1) → CLAUDE.md §3 dan `docs/open-issues.md` K-1.

## Keluaran standar
- Status setiap item hanya boleh memakai enam label dari Anchor 04 「AI 机器执行合同」, dan setiap item menyebut sumbernya.
- Kutipan dalam 「」. Inferensi diberi label "inferensi, belum dikonfirmasi".
- Kalau berhenti, sebutkan 阻塞对象, 阻塞人, dan 恢复条件 (Anchor 04 「强制停止条件」).

---

## Salinan butir Skill (deployment copy, 07.06, diambil 2026-09-26)
> Teks di bawah ini disalin apa adanya, **kecuali markup link markdown** (`[teks](url)` ditulis sebagai `teks` saja). Karena itu, bandingkan teksnya dengan mengabaikan URL. Perbedaan yang dihitung drift hanyalah perbedaan kata, bukan perbedaan link. Bagian ini **hanya dipakai untuk membandingkan drift**. Untuk menjalankan skill, selalu ikuti halaman terbaru.

- 每次开发前，先读 07｜指南 **第二、三节**（通用纪律与缺口回报格式，每次动作前的通用前提，不因熟练而跳过）与 07.06｜建设指南 **全文**（第三节、或新增 n8n workflow 对应第四节，是本次任务对应的具体步骤；执行路径与 API 覆盖分流见第六节）。按当下版本执行，不依赖记忆，指南会更新。
- **动手前按** 07.06.1｜开发规则与避坑指南 **第三节主题速查表命中本次任务相关条目并实际读取**——本次要动的是数据写入、通知外发、共享对象还是发布上线，对应条目在动手前读，不是出事后才查。
- **页面中出现的链接必须实际用工具打开读取，不能仅凭链接文字或以往认知判断其内容**——04｜流程建设与执行治理总纲本身也是「指路牌」而非规则本体，导航表命中哪个子页，就要点开那一页实际读取，不能停在导航表这一层，也不能假设自己记得该页内容。
- 涉及任何标准配置判断，从 04｜流程建设与执行治理总纲 出发按其导航表定位对应标准页，不凭记忆或旧对话直接跳转具体页面或章节。
- 唯一开发依据是流程 Owner 发布的已完成结构审计通过、对齐并冻结的 Spec；**Spec 存在不替代切分审计证据；建设者须读取对应 Epic 的切分审计通过证据**——本 skill 不重新评估流程边界该怎么切、该不该与别的流程合并；若发现切分明显不合理，按 07 第三节格式退回，不自行改切分、不合并或拆分 Spec。整部门盘点与切分属 07.01 范畴。
- **不得修改 Spec 的语义内容**（04.5 第五节写权分离）。建设期对 Spec 页只有两类例行合法动作：①状态区生命周期更新；②引用区“对应建造单”链接回填。节点表与增补区的节点、分支、契约、文案、角色定义一律不得单方改动——发现歧义或 Spec 内部口径冲突（如两处写法不一致），走白话对齐或按 07 第三节退回，**禁止现场调和后静默改写**。
- 看不懂业务背景不影响开发。
- 遇歧义、技术限制或取舍，必须暂停并把问题翻译成业务选择题（不出现 API、字段、webhook 等技术词），不得把技术问题原样抛给流程 Owner；如答案导致实质语义修改，完成重新结构审计、对齐与冻结后才能继续。
- Spec 修订后须重新生成投影图并自检三项标注齐全（模块类型／主单子单归属／知会对象）；若为实质语义修改，还须重新结构审计、对齐与冻结，规则以 04.5 当下版本为准。
- 查不到标准的事项，按 07 第三节「标准缺口回报」格式输出报告，交使用者**原封不动**转交流程 Owner／标准维护方；禁止现场发明标准、禁止把判断规则写死进配置。上报前须完成格式要求的分流判断（标准缺口 vs 业务歧义），业务歧义走白话对齐，不走缺口回报。
- 配置调整必须以有效冻结 Spec 为依据；发现线上配置与 Spec 不一致，以 Spec 为准回滚或停止。需要实质修改 Spec 时退回结构审计、对齐并重新冻结，不得静默保留分歧。
- 建设开始前必须确认并消费 04.7 Candidate：AI 将 Route ID／Candidate 链接登记至建造单第一区，配置回读证据登记至第八区；BO 建造 Owner 最终确认。N13 才执行实际配置与 Candidate 的逐项校准和端到端验收；Candidate 只在 N14 上线原子动作中转为正式，不得提前激活。
- 端到端测试通过后、正式上线前必须完成使用者指南 Gate。07.08｜使用者指南设计 skill 未生效期间，由搭建 Task 建人工文档事项承载；指南完成、流程 Owner 验收且 Portal／入口链接后才可上线。
- 机读契约包六件套（冻结 Spec、建造单暗号／marker 精确语法、所调用共享件契约页、第六节 API 覆盖清单、07.06.1 已知坑清单、Spec 引用区外部平台依赖清单含 T-5 结论）不齐不开工；依赖清单中探针待实测项先实测回写、未具备按阻塞处理。
- 开工前先扫一遍建造单阻塞行，逐条核对「解除判据」是否已成立，已解封的立即恢复推进。
- 开工前置四动作完成后，按第三节 (e) 汇成开工对齐清单发建造单 Comment（四列固定、列已签共享件；无待确认项也须发出）；流程 Owner 回应时限以 OS 开发流 Spec 增补区 C 表当前版为准。
- 涉及跨流程通用能力（查人／发卡／解析类）先查 04.4 共享组件索引；准备自建共享能力时先登记「在建」行；引用 Registry 实体字段先查 04.8 实体字段登记表，未登记先补登、变更先看消费列。
- 每完成一个建设单元须当场完成收口三件套（建造单行登记／契约页状态更新／Comment 结论回写文档），三者未齐不得报告该单元完成。
- 消费 04.9 时只读主页＋本流程分册＋所调用共享件对应行，不得全量扫描他人分册。

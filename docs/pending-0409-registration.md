# Draf registrasi 04.9 untuk S-05 (N04, N05, N07, N20)

Diminta Alden OSD-116 c50647 (b): 「Please register N04, N05, N07 and N20 per 04.9 §一: a row in the main-page index and a block in 04.9.7.」

**Status: draf, bukan izin menulis.** Registrasi ditulis Bambang sendiri ke 04.9 (1693089805) dan 04.9.7 (2117435433). Claude tidak menulis ke halaman itu.

**Jawaban Alden OSD-116 c50692 (2026-09-29, evidence E58):**
1. Format nama (K-3): 「follow 04.6 §2 item 3 — `{flow name}｜{node ID}｜n8n-{action}`, e.g. `纪律与绩效改进处置｜N04｜n8n-路由分发`. Please rename the four S-05 workflows in n8n first, then register them」. Nama di draf ini sudah diganti ke format itu, dan **sudah diterapkan di n8n 2026-09-29** (evidence E59; versionId keempatnya tidak berubah). Bagian `{动作}` sama dengan nama lama; yang ditambah hanya awalan `n8n-`. Hanya contoh N04 yang ditulis Alden; untuk tiga lainnya format yang sama diterapkan oleh Claude atas perintah Bambang. Bagian `{动作}` = nama node di tabel node Spec v67 (04.6 §二-3 「命名对不上 Spec 行视为登记未完成」): N04 「路由分发」, N05 「重复案件与历史记录检查」, N07 「HR三层审核」 (diganti dari 「审批卡发送」 2026-09-29 05:34Z, E62), N20 「解雇自动开单与交接」.
2. Kolom 「Owner 部门」 (K-16): 「HR」.
3. Baris Notify dan navigasi §三 04.9.7: sudah dikerjakan Alden (04.9 v129).

**Urutan:** ganti nama di n8n **sudah dilakukan** (E59). Berikutnya registrasi ditulis Bambang.

**Link indeks:** tulis blok H2 di 04.9.7 dulu, baru baris indeks. Format link sama dengan baris lain: `https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2117435433/04.9.7#<judul H2 yang di-encode>` (contoh bentuknya ada di baris 员工离职 yang menuju 04.9.3).

**Sebelum ditulis:** baca ulang keempat workflow lewat API. Kalau versionId, settings, atau jumlah node berubah, perbarui kolom 状态. Catatan: versionId hanya berubah kalau node/koneksi berubah; settings dibaca terpisah (E40; Geri NSE-1137 c50669). Di halaman, judul blok ditulis sebagai **H2** (di file ini H3 supaya struktur file tetap rapi). Link indeks diarahkan ke anchor H2 masing-masing di 04.9.7.

Sudah dicek (validasi ulang 2026-09-29 siang): 04.9 **v129** penuh (§一 铁律, §1.1–1.4, header indeks §二, §三 navigasi, §四 baris `jdF8S9cV7ZIZowvw`), 04.9.7 v1 (hanya pengantar), 04.6 v23 §二-3, Spec S-05 v67 tabel node (nama N04/N05/N07/N20), n8n `get_workflow_details` + `search_executions` keempat workflow (evidence E63), OSD-116 s.d. c50695.

Sudah dicek (draf awal): 04.9 v124 (§一, §1.3, §1.4, indeks, §三), 04.9.7 v1 (hanya pengantar), 04.9.3 v28 (format blok H2), 04.5 v79, 04.6 v22, Spec S-05 v67 (baris N04/N05/N07/N20), build sheet v53 (§五, baris 附表 「04.9 登记」), n8n get_workflow_details keempat件, OSD-116 s.d. c50658, #nos-bo s.d. 16:36 (thread 1789704362.435989 balasan 16/16, thread 1789817804.263189 3/3, search after:2026-09-27). Settings N04/N05 dibaca ulang setelah disimpan di UI (E40).

## A. 04.9 主页 §二 索引表：加 4 行

| Workflow 名 | 类目 | 所属流程 Spec ／ 被哪些流程调用 | Owner 部门 | 建设归属 | 状态 |
| --- | --- | --- | --- | --- | --- |
| [纪律与绩效改进处置｜N04｜n8n-路由分发](04.9.7 对应 H2 锚点) | 业务件（主链） | [纪律与绩效改进处置｜流程 Spec](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2036858900/Spec)·N04（路由分发） | HR | Bambang | inactive（骨架；调用方 N01／N03 未建） |
| [纪律与绩效改进处置｜N05｜n8n-重复案件与历史记录检查](04.9.7 对应 H2 锚点) | 业务件（主链） | [纪律与绩效改进处置｜流程 Spec](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2036858900/Spec)·N05（重复案件与历史记录检查） | HR | Bambang | inactive（仅抛错路径干跑 17564／17565；主路径与零评论／零候选未验；历史纪律记录一半为占位，Registry 未建） |
| [纪律与绩效改进处置｜N07｜n8n-HR三层审核](04.9.7 对应 H2 锚点) | 业务件（主链） | [纪律与绩效改进处置｜流程 Spec](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2036858900/Spec)·N07（HR三层审核） | HR | Bambang | inactive（测试单实跑 SSCSD-435／437–439／441／442；抛错路径 17563／17566–17571；modal 回写待主单字段） |
| [纪律与绩效改进处置｜N20｜n8n-解雇自动开单与交接](04.9.7 对应 H2 锚点) | 业务件（主链） | [纪律与绩效改进处置｜流程 Spec](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2036858900/Spec)·N20（解雇自动开单与交接） | HR | Bambang | inactive（干跑 17373／17374，抛错路径 17562／17572；所调离职入口未发布） |

## B. 04.9.7：加 4 个 H2 块

Setiap blok di bawah = satu H2 di 04.9.7 (format mengikuti 04.9.3 v28).

### 纪律与绩效改进处置｜N04｜n8n-路由分发

|  |  |
| --- | --- |
| n8n ID / URL | UBLsvYaSlCI3pLWs ｜ [直达](https://n8n2.ohmediaa.com/workflow/UBLsvYaSlCI3pLWs) |
| 类目 | 业务件（主链） |
| 所属流程 Spec + 节点 ID | [纪律与绩效改进处置｜流程 Spec](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2036858900/Spec)｜**N04**（路由分发：两条入口汇合，不做业务判断） |
| 触发方式 | 被调用（`executeWorkflowTrigger`，入参 `issueKey`）。设计调用方为 N01／N03（均未建） |
| 读取数据源 | 无 |
| 输出动作 | 调 N05 并等待其返回，原样返回 N05 输出；本件不写任何 Jira 对象 |
| 调用关系 | 调用 **纪律与绩效改进处置｜N05｜n8n-重复案件与历史记录检查**（`LJwiAZFfnuq6tmju`）。N07 由谁调用尚未接（见建造单第五区 N07 行「已知未做③」）。错误出口 **NOS \| Platform \| Error Handler (nos-ops)**（`VUIgv9Ujj1KEoIne`） |
| 状态 | inactive｜`versionId 0aad8ecb-e97e-4297-9908-b6c15559fdca`，2 节点；`errorWorkflow`＝`VUIgv9Ujj1KEoIne`，`callerPolicy`＝workflowsFromSameOwner（2026-09-28 经 UI 设置，人：Bambang；API 回读 updatedAt 2026-09-28T14:54:46Z）；n8n 无执行记录（2026-09-29 `search_executions` 回读 0 条）。｜登记人：Bambang |

### 纪律与绩效改进处置｜N05｜n8n-重复案件与历史记录检查

|  |  |
| --- | --- |
| n8n ID / URL | LJwiAZFfnuq6tmju ｜ [直达](https://n8n2.ohmediaa.com/workflow/LJwiAZFfnuq6tmju) |
| 类目 | 业务件（主链） |
| 所属流程 Spec + 节点 ID | [纪律与绩效改进处置｜流程 Spec](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2036858900/Spec)｜**N05**（重复案件与历史记录检查） |
| 触发方式 | 被 N04 调用（`executeWorkflowTrigger`，入参 `issueKey`） |
| 读取数据源 | Jira：本主单（对照探针，07.06.1 E16——读不到即抛错，不信任其后的 0 条结果）；本主单 comment 取 `[[nos-s05-subject:<accountId>]]`（由 N01／N03 写入，缺即抛错）；JQL `project = SSCSD AND issuetype = "Disciplinary Case" AND status in ("Pending Approval","Pending Sub-tickets") AND key != <本单>`；各候选单 comment 比对主体 accountId |
| 输出动作 | 命中疑似重复 → 在本主单写 internal comment `[[nos-s05-dup:<本单 key>:<疑似原单 key>]]`（`sd.public.comment` internal）；不判定、不转态。返回 `issueKey`／`subjectAccountId`／`duplicateFound`／`matchedCaseKey`／`historicalDisciplinaryRecords`／`historicalRecordsStatus`。**历史纪律记录为占位**：固定输出 `[]`，Registry（N13）未建 |
| 调用关系 | 被 N04 调用；不调用下游；写入经 Bot_SSC（`Write Duplicate Marker Comment (internal)`，UI 手工挂，UI 目视确认人 Bambang）；错误出口 **NOS \| Platform \| Error Handler (nos-ops)**（`VUIgv9Ujj1KEoIne`） |
| 状态 | inactive｜`versionId 30b14fd2-370b-43ef-b360-2086a05da9b8`（2026-09-29T05:30:22Z，过时注记订正；逻辑同 2026-09-28 抛错文案去半角冒号版），17 节点（含 sticky 3）；`errorWorkflow`＝`VUIgv9Ujj1KEoIne`，`callerPolicy`＝workflowsFromSameOwner（2026-09-28 经 UI 设置，人：Bambang；API 回读 updatedAt 2026-09-28T14:53:41Z）。执行记录：16341（2026-09-23，入参 issueKey 为空，止于对照探针 404）；17564／17565（2026-09-28，抛错路径：无主体 marker、探针不可见）。主路径（查重命中／未命中）与零评论／零候选两例未验（建造单第五区 2026-09-28 待验）。｜登记人：Bambang |

### 纪律与绩效改进处置｜N07｜n8n-HR三层审核

|  |  |
| --- | --- |
| n8n ID / URL | 77PepnEWGqTOCI61 ｜ [直达](https://n8n2.ohmediaa.com/workflow/77PepnEWGqTOCI61) |
| 类目 | 业务件（主链） |
| 所属流程 Spec + 节点 ID | [纪律与绩效改进处置｜流程 Spec](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2036858900/Spec)｜**N07**（HR三层审核；本 workflow 承担发卡侧） |
| 触发方式 | 被调用（`executeWorkflowTrigger`，入参 `issueKey`／`approverAccountId`／`round`（1–3）／`duplicateFound`／`matchedCaseKey`）。调用方与审核人解析未接 |
| 读取数据源 | Jira：本主单 `status`／`issuetype`／`summary`（对照探针；非「Pending Approval」即抛错不发卡）；Data Table「NOS Platform Approval Cards」（`jdF8S9cV7ZIZowvw`）按 `idempotency_key`＋`flow_key` 查同一轮是否已发 |
| 输出动作 | 构造审批卡交 Notify 发给审核人：通过·Show Cause／通过·Warning（等级＋判定依据）／通过·PIP（六参数＋判定依据）／通过·严重违纪／打回补件（第 1、2 轮）／确认重复（仅 N05 标记时）／拒绝（判定依据必填）。`flowKey`＝纪律与绩效改进处置，`idempotencyKey`＝`<主单>:r<轮次>`，`approverFieldId`＝`customfield_18061`，`auditVisibility`＝internal，`rejectNotice`＝none。标题以 `TEST｜` 起头时，卡首为 04.5.3 统一测试标识（加粗）。modal 字段全部 `noWrite`（主单字段待建，OSD-116 c50658）。本件自身不写 Jira |
| 调用关系 | 调用 **NOS \| Platform \| Notify**（`eYOFfHfGUwpfg6ss`）；卡片回调由 **NOS \| Platform \| Slack Approval**（`6wdHhygWmyRFQAoX`）承接；读 Data Table `jdF8S9cV7ZIZowvw`；错误出口 **NOS \| Platform \| Error Handler (nos-ops)**（`VUIgv9Ujj1KEoIne`）。所调平台件只读未改 |
| 状态 | inactive｜`versionId 3ecb5c28-2a8c-47a4-9141-906d3da3d584`（2026-09-29T05:30:27Z，过时注记订正；逻辑同 2026-09-28 抛错文案去半角冒号版），11 节点；`errorWorkflow`＝`VUIgv9Ujj1KEoIne`，`callerPolicy`＝workflowsFromSameOwner。测试单实跑 SSCSD-435（2026-09-26）、SSCSD-437／438／439／441／442（2026-09-28），逐次记录见建造单第八区；抛错路径 17563、17566–17571（2026-09-28）。未证：「Read Case」以 Bot_SSC 真读（测试工具强制 pin）、modal 回写、打回次数 +1（未建）。｜登记人：Bambang |

### 纪律与绩效改进处置｜N20｜n8n-解雇自动开单与交接

|  |  |
| --- | --- |
| n8n ID / URL | ToIGnEJmksSPhC85 ｜ [直达](https://n8n2.ohmediaa.com/workflow/ToIGnEJmksSPhC85) |
| 类目 | 业务件（主链） |
| 所属流程 Spec + 节点 ID | [纪律与绩效改进处置｜流程 Spec](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/2036858900/Spec)｜**N20**（解雇自动开单与交接） |
| 触发方式 | 被调用（`executeWorkflowTrigger`，入参 `caseKey`／`employeeAccountId`／`judgmentType`／`judgmentRef`／`upstreamEvent`）。设计调用方 N14／N17（均未建） |
| 读取数据源 | Jira：本主单 comment 查 `[[nos-s05-term:<本单>:…]]`（幂等；`alwaysOutputData` 开，0 条＝尚未触发） |
| 输出动作 | `judgmentType` 映射 `cf18199` 辞退分类（纪律违规→15846、PIP未改善→15847，其余抛错）→ 调离职侧入口，六项交接（`upstreamSource`＝`S-05 N20`／`upstreamEvent`／`upstreamCaseKey`／`employeeAccountId`／`dismissalCategoryId`／`judgmentRef`，NSE-1137 c50494／c50507）→ 入口未回 `ok:true`＋`issueKey` 即抛错 → 本主单写 internal comment `[[nos-s05-term:<S-05 主单 key>:<离职主单 key>]]`。Trigger link 由入口建，本件 `Create Trigger Link` 节点停用 |
| 调用关系 | 调用 **员工离职｜上游触发入口（S-05 等上游解雇 → 自动开单）**（`qa01CkZBQfx8eLsK`，04.9 v127 已补登，未发布）；写入经 Bot_SSC（httpRequest 节点 UI 手工挂，UI 目视确认人 Bambang）；错误出口 **NOS \| Platform \| Error Handler (nos-ops)**（`VUIgv9Ujj1KEoIne`） |
| 状态 | inactive｜`versionId 6971acbc-2413-4b1c-b3b7-2a501c1c9ea7`（2026-09-28T15:42:00Z，抛错文案去半角冒号），10 节点；`errorWorkflow`＝`VUIgv9Ujj1KEoIne`，`callerPolicy`＝workflowsFromSameOwner。干跑 exec 17373（未触发→走到写 marker，调用与写入 pin）／17374（已有 marker→止于闸门）；抛错路径 17562（judgmentType 不识别）／17572（入口 ok:false）。未建：D-10 知会直属上级、B6 上级解析、「离职单关联状态」写入；入口未发布前不能端到端。｜登记人：Bambang |

## C. Perubahan lain di halaman utama 04.9 yang ikut registrasi

1. **§三 详情分册导航**, baris 04.9.7: kolom 「详情块数」 `0` → `4` (sekarang tertulis 「纪律与绩效改进处置（主链） | 0」).
2. **§四 Data Table 登记区**, baris `NOS Platform Approval Cards` (`jdF8S9cV7ZIZowvw`), kolom 「被哪些 workflow 引用」: masih tertulis 「纪律与绩效改进处置｜N07｜审批卡发送（读：按 idempotency_key＋flow_key 查同一轮是否已发；未上线）」 → ganti nama menjadi 「纪律与绩效改进处置｜N07｜n8n-HR三层审核」. Dasar: 04.9 §一 「名称一致」. Baris ini dulu ditulis Alden (c50647 (c)).

## D. Catatan untuk Bambang (tidak ditulis ke 04.9)

- Baris indeks **NOS | Platform | Slack Approval** di 04.9 v129 menulis 「被调用：请假、调薪（审批卡点击回调）…」 tanpa 纪律与绩效改进处置, padahal kartu N07 diproses oleh workflow itu. 04.9 §1.4: 「调用方增减时本行必须同步」. Alden hanya menambahkan S-05 ke baris Notify (c50647 (c), c50692). Baris ini milik platform (Alden); belum ditanyakan.


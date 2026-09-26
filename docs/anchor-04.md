<!--
SNAPSHOT (salinan lengkap, bukan sumber berlaku)
- Halaman  : 04｜流程建设与执行治理总纲
- pageId   : 1676804100 (space NOSM)
- URL      : https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676804100/04
- lastModified (dilaporkan Rovo): Sep 05, 2026 · author: Kayden Lee
- Nomor versi: tidak dikembalikan oleh Rovo. Build sheet S-05 (pageId 2096463922) mencatat "04 v25" saat dibaca 2026-09-20; tidak diverifikasi ulang di sini.
- Diambil  : 2026-09-26 via Atlassian_Rovo getConfluencePage (markdown), disalin tanpa perubahan isi.
- Yang BERLAKU selalu halaman Confluence saat ini. Sebelum dipakai untuk keputusan, jalankan skill `nos-check` (drift) atau buka halamannya langsung.
  Anchor 04 §七.2: "读取本页当前版本" · 07 §二「先查后写」.
-->

**性质：流程／执行层家族锚点＋建设执行合同**｜当前主要使用者：流程 Owner／HOD、Kayden、Alden／BO 建设团队及协助 AI。同一个人可以兼任多个责任角色；本页按“当前要执行的动作”分流，不假设公司已经配置专职设计、审计或验收岗位。回答：流程从盘点到上线时，当前动作由谁负责、交付物放哪里、何时登记到哪个 SSOT、缺什么必须停止。

**权威使用原则**｜任何人或 AI 不得只读本页就执行对象级判断。本页负责路由；命中 04.x 子页后，必须实际打开并读取其当前版本。Jira 是进度事实，Confluence 当前权威页是规则事实；评论、旧任务描述、记忆或既有配置与权威页冲突时，不得自行调和。

# 一、先判断当前动作：按工作读取

| 当前动作 | 现阶段主要执行人 | 先读取 | 责任边界 |
| --- | --- | --- | --- |
| 盘点、切分与流程设计 | 部门 HOD／流程 Owner＋协助 AI | 第二、三节＋04.5＋07.01／07.02 | Owner 决定业务语义；AI 只翻译、检查和提问，不代替裁决。 |
| 三个审计 Gate 与对齐 | 审计：切分审计与验收审计由 Kayden 或 Alden 任一人（OR）裁决，结构审计为业务签（Kayden）＋技术签（Alden）双签（AND）；对齐：流程 Owner及相关 HOD／管理层 | 第二节 Gate＋Spec／建造单＋对应 Jira 证据 | n8n 只做机械审计与不通过自动退回；裁决人按上列裁决模式以自己的 AI 辅助复核，明确裁决后由该 AI 留言、更新权威文档、执行获授权转态并回读。对齐负责白话签收与冻结，不替代审计。 |
| 平台建设 | Alden／BO 建设者＋协助 AI | 第二、四、五节＋04.5／04.6／07.04 | 按冻结 Spec 建造并维护建造单；不得擅改业务语义。 |
| 验收与上线 | 验收裁决：Kayden 或 Alden；上线：流程 Owner＋BO 建造 Owner | 第二、三、五节＋Spec＋建造单＋测试证据 | 验收先由 n8n 机械审计，不通过自动退回开发；机器通过后由 Kayden 或 Alden 单人裁决。业务验收与工程证据必须分开。 |

# 二、唯一开发流：八个工作阶段不得跳过

**阶段顺序固定为：盘点与切分 → 切分审计 → 设计 → 结构审计 → 对齐 → 开发 → 验收审计 → 上线。三个审计阶段均先由 n8n 在进入审计态时执行机械审计：不通过则在对应 Jira Epic／Feature Comment 留言并自动退回上一工作态；通过则留言并停留在审计态，等待人工裁决——切分审计与验收审计由 Kayden 或 Alden 任一人（OR）裁决，结构审计为业务签（Kayden）＋技术签（Alden）双签（AND），两签均通过才可转态（规则见 **[**07.04**](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1744896004/07.04)**）。机器通过不等于 Gate 通过。上线完成后进入“完成”终态；完成不是另一项建设工作。已有草案、页面、配置、机器通过或口头同意，都不等于相应 Gate 已通过。**

| 阶段 | 主责 Owner | 交付物 | Gate／验收证据 | 下一步 |
| --- | --- | --- | --- | --- |
| 1｜盘点与切分 | 部门 HOD／Function Lead | 部门事实、流程清单、候选 Spec 边界、Project 载体与依赖 | 事实来源可追溯；Function 盲区、待裁决点与观察建议分开登记 | 提交切分审计 |
| 2｜切分审计 | n8n（机械）＋Kayden 或 Alden（裁决） | 完整性、一致性、防重复与自洽性的机器报告及人工裁决 | 进入审计态即机械审计；不通过在 Epic Comment 留言并自动退回盘点与切分；通过停留审计态。Kayden 或 Alden 使用自己的 AI 复核并把最终裁决追加到同一 Epic Comment | 人工通过后产生／放行单条流程设计工作 |
| 3｜设计 | 流程 Owner／HOD＋协助 AI | Spec 自然语言、节点表、增补表、投影图与 04.7 Candidate | 语义与六区完整；跨流程触发两端一致；Candidate 回链同一 Spec。设计者不执行正式结构审计 | 提交结构审计 |
| 4｜结构审计 | n8n（机械）＋业务签 Kayden＋技术签 Alden（双签 AND） | 入口、节点、终点、边界、Owner、例外、契约及 SSOT 的机器报告与人工裁决 | 进入审计态即按 04.5 当前版机械审计；不通过在 Feature Comment 留言并自动退回设计；通过停留审计态。业务签与技术签均明确通过后，由后完成一方的 AI 追加最终 Comment、更新 Spec 状态区并执行转态；任一签退回即退回设计（07.04） | 人工通过后进入对齐 |
| 5｜对齐 | 流程 Owner；跨部门时含相关 HOD／管理层 | 结构已通过的 Spec、白话对齐包与显式签收证据 | 业务结论回写 Spec；签收人、日期和决定留在 Jira Feature Comment。无实质修改时冻结当前 Spec 基线；有实质修改时回到设计，原结构审计与对齐证据失效 | 冻结后交 BO 开发 |
| 6｜开发 | Alden／BO 建造 Owner | Spec 子页下的建造单、实际平台配置与所需登记行 | 建造单第 1–8 区按适用性完成；实际对象、ID、回读和 Candidate 消费证据齐全 | 提交验收审计 |
| 7｜验收审计 | n8n（机械）＋Kayden 或 Alden（裁决） | 配置回读、业务、端到端、负向、权限、守护与校准记录 | 进入审计态即机械审计；不通过在 Feature Comment 留言并自动退回开发；通过停留审计态。Kayden 或 Alden 使用自己的 AI 复核，最终裁决进 Feature Comment，工程证据进建造单第 8 区 | 人工通过且使用者指南 Gate 齐全后进入上线 |
| 8｜上线 | 流程 Owner＋BO 建造 Owner | 可用指南、启用记录、Route 正式状态与上线三合一证据 | 入口、权限、监控、回滚与指南可读取；建造单第 9 区完整；三合一动作完成 | 进入完成终态与运行治理 |

# 三、过程产出放哪里：不为留痕而重复建页

| 产出 | 唯一承载点 | 何时建立／更新 | 禁止 |
| --- | --- | --- | --- |
| 部门盘点 Workshop 与切分成果 | 07.01 下的「{部门名}｜盘点与切分」页；Jira Epic Comment 按实质事件触发记录过程沟通与 Gate 事件，不复制部门页事实 | 部门首次接入或流程清单批量变化时；整部门处理 | 不得逐条孤立盘点，也不得只留会议聊天而不回写部门页 |
| 切分审计记录 | 机器报告与人工最终裁决住 Jira Epic Comment；部门页只同步状态摘要与待修改项 | 每次进入切分审计 Gate 时 | 不得发 Slack 代替；机器通过不得替代 Kayden 或 Alden 的人工裁决 |
| 流程 Spec | 流程 Owner 所属部门 Space；「{流程名}｜流程 Spec」 | 设计开始建立；对齐修改直接迭代现行自然语言与正式结构 | 不得写工程 ID、workflow 名与测试记录 |
| 建造单 | 对应 Spec 的直接子页；「{流程名}｜建造单」 | 进入开发 Gate 时建立并与 Spec 双向互链 | 不得在设计期凭推测填写工程实况 |
| 投影图／泳道图 | Spec 的投影图区 | 随节点表生成并同步校准 | 默认不独立成页；图不是第二份规则 |
| 单流程白话对齐 | 业务现行结论回写 Spec；签收人、日期、决定与来源证据住 Jira Feature Comment，Spec 状态／引用区链接该 Comment | 结构审计人工通过后发起；每轮对齐后立即更新。无实质修改则冻结，实质修改则回设计并使原结构审计与对齐证据失效 | 不得另建会与 Spec 漂移的“最终结论页”，也不得只在聊天中口头通过 |
| 结构审计记录 | n8n 机器报告与业务签（Kayden）＋技术签（Alden）双签裁决住 Jira Feature Comment；人工通过后的审计基线、结果与证据链接住 Spec 状态区 | 每次进入结构审计 Gate 时 | 不得发 Slack；机器通过不得写成 Gate 通过；不得只转 Jira 状态而不更新证据 |
| 验收审计与上线记录 | n8n 机器报告与 Kayden／Alden 最终裁决住 Jira Feature Comment；测试、配置回读与守护证据住建造单第 8 区；上线三合一住第 9 区 | 每次进入验收审计 Gate，以及上线时 | 不得发 Slack 代替审计留痕；不得把工程明细写回 Spec |
| 使用者指南 | 文档／知识层指定落点，由 07.05／NW 规则决定，并与 Spec／建造单互链 | 测试通过且最终入口、权限和实际行为可读取后 | 不得在测试前把设计推测写成正式指南 |

## Jira Comment｜使用者 AI 与管理者 AI 的过程沟通层

Jira Comment 是流程建设期间的 append-only 过程沟通与决策留痕层，也是使用者 AI 与管理者 AI 的异步沟通接口。部门页、Spec、建造单及专项 SSOT 承载正式事实；Comment 不复制这些正文，而是让未参与现场的人或 AI 读懂过程判断、决策请求、管理回复、偏离、阻塞、标准缺口、Gate 提交／裁决以及下一步。

- 事件触发才留言：出现新事实、判断变化、决策请求或回复、异议、偏离、阻塞、标准缺口、Gate 提交／打回／通过、Owner 或下一行动变化时追加；普通问答、重复汇报或没有新事实的进度不留言。
- 不规定固定模板或字段顺序；自然语言留言须自足，能说明发生了什么、依据与影响、是否需要谁决定或协助、下一步与责任人，以及正式事实最终落在哪个权威载体。
- AI 写前先读目标 Issue 与最近相关 Comment，避免重复并说明本次回应或取代哪项旧判断；写后回读确认落在正确 Epic／Feature。找不到唯一 Jira 对象时才询问使用者，不要求每次重复提供 URL。
- 正式决定形成后须回写部门页、Spec 或建造单等对应 SSOT，并在 Comment 链接；Comment 与正式载体冲突时以正式载体当前版本为准。三个审计 Gate 不使用 Slack：机器报告与人工裁决只追加到对应 Jira Epic／Feature Comment。其他讨论可使用 Slack／Huddle，但关键结论不得只留在聊天中。

**例外：**外部会议纪要、法规文件或原始证据可独立存在，但流程页面只引用，不复制全文；独立证据不能取代 Spec／建造单内的结论登记。

# 四、建页、命名与层级的原子规则

| Confluence 对象 | 标准命名 | 层级／父页 | 原子动作 |
| --- | --- | --- | --- |
| 部门盘点页 | {部门名}｜盘点与切分 | 07.01 子页 | 建页时同步登记来源 Jira Epic、Owner 与当前 Gate |
| 流程 Spec | {流程名}｜流程 Spec | 流程 Owner 所属部门 Space 的流程 Index 之下 | 建页与部门 Index 行同次完成；Index 链接实名页面 |
| 建造单 | {流程名}｜建造单 | 该流程 Spec 的直接子页 | 建页、Spec 双向链接、BO Owner 与来源 Jira Feature 同次登记 |
| 试点／临时页面 | 正式命名＋顶部注明临时落点与迁移条件 | 仅在目标部门 Space 尚不可用时暂放 NOSM | 必须有迁移 Owner、触发条件和目标落点；不得因暂存成为永久默认 |

**原子绑定**｜建页和登记 Index／互链不是可分开的两项工作。页面已创建但无 Owner、来源任务、父级关系或反向入口，状态仍是“未完成”，不得以“稍后补登记”放行。

# 五、登记集：何时必须写入哪个 SSOT

登记用于定位真实对象，不重复描述流程。每个事实只在专项 SSOT 存值，Spec／建造单只保留链接与本流程消费关系。

| 触发对象／事件 | 权威落点 | 触发时点 | 放行条件 |
| --- | --- | --- | --- |
| 新流程／执行术语 | [04.0｜词汇表](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676640265/04.0+SSOT) | 第一次进入 Spec 或规则页前 | 已有则引用；无定义先裁决再登记，AI 不自造 |
| 新开或登记 Project | [04.1｜Project 类型与开设判定](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676738564/04.1+Project) | Project 创建／消费前 | 类型、命名、Key、Owner 与证据完整 |
| 具体 Request Type／Route | [04.7｜Router SSOT](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1691254793/04.7+Router+SSOT) | 设计可校验时先登记 Candidate；上线时再转正式 | 同一 Spec 链接、Route ID、业务与实际配置校准证据齐全 |
| 持续存在的实体／档案 | [04.8｜Registry SSOT](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1690140756/04.8+Registry+SSOT) | 设计确定实体边界后，最迟上线前 | 实体 Owner、Project、状态列与来源规则可读取 |
| 创建或修改 n8n workflow | [04.9｜n8n Workflow 登记表](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1693089805/04.9+n8n+Workflow+SSOT) | 建成当场、启用之前 | ID、Owner、对应 Spec／节点或辅助职责、测试证据完整 |
| 创建、复用或修改 Jira 共享对象 | [04.10｜Jira 共享配置登记表](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1738735636/04.10+Jira+SSOT) | 配置建成当场、任何流程启用之前 | 实际 ID、Owner、范围、使用方与回读／实测证据完整；先登记后启用 |

# 六、04 子页地图：本页路由，子页裁决

| 子页 | 唯一职责 | Owner | 当前状态 |
| --- | --- | --- | --- |
| [04.0｜流程／执行层词汇表](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676640265/04.0+SSOT) | 术语与枚举值的唯一权威定义 | Kayden | 生效 |
| [04.1｜Project 类型与开设判定](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676738564/04.1+Project) | Project 判定、命名、Key 与实例登记 | Kayden | 生效 |
| [04.2｜单据体系](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676607500/04.2) | 主单、子单、维护单等 Issue Type 的语义、触发与阻塞 | Kayden | 生效 |
| [04.3｜状态词汇表与 Workflow 配置规范](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676771343/04.3+Workflow) | 状态语义、流程形状与 Workflow 逻辑标准 | Kayden | 生效 |
| [04.4｜自动化配置模式库](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1677066244/04.4) | 跨部门／跨系统自动化模式与命名 | Alden | 生效（模式持续扩充） |
| [04.4.1｜模式九：Slack 审批卡回调（共享地基）](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1729888419/04.4.1+Slack) | Slack 审批卡回调模式的配置与验收规则（候选新增章节，待 Alden 核收并入 04.4 正文） | Alden | 候选模式／待并入 04.4 |
| [04.5｜流程 Spec 与建造单规范](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1678573617/04.5+Spec) | 双文档架构、Schema、交接与验收 | Kayden | 生效 |
| [04.5.1｜流程 Spec 模板](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1685979182/04.5.1+Spec) | Spec 可复制模板与填写示例 | Kayden | 生效 |
| [04.5.2｜建造单模板](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1729626775/04.5.2) | 建造单九区模板与字段结构 | Alden | 生效 |
| [04.5.3｜Sandbox 与测试策略](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1729626578/04.5.3+Sandbox) | 测试环境、数据与通过判据 | Alden | 生效 |
| [04.6｜n8n 使用规范与环境需求](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1690927120/04.6+n8n) | n8n 环境、部署、权限与使用治理 | Alden | 草拟（待平台侧收口） |
| [04.7｜Router SSOT](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1691254793/04.7+Router+SSOT) | Request Type／Route 实例与生命周期 | Alden | 生效 |
| [04.8｜Registry SSOT](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1690140756/04.8+Registry+SSOT) | 持续实体 Owner、Project 与状态结构 | Alden | 草拟 |
| [04.9｜n8n Workflow SSOT](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1693089805/04.9+n8n+Workflow+SSOT) | workflow 身份、Owner、消费关系与证据 | Alden | 生效 |
| [04.10｜Jira 共享配置治理](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1738735636/04.10+Jira+SSOT) | 共享对象实例、变更权限、影响与证据 | Kent | 生效 v1 |

**边界铁律：**04.0 管词义；04.1–04.6 管判定与配置方法；04.7–04.9、04.10 管对应实例；本页管跨页顺序、Owner、当前状态和停止条件。任何页面不得复制另一个 SSOT 的值。Owner／状态发生变化时更新本表；对象级细节仍只改对应子页。

# 七、AI 机器执行合同

1. 读取 Jira 当前任务、Parent、上下游 Issue、状态、Owner、评论与依赖；Jira 未登记的进度不视为事实。
2. 读取本页当前版本，按任务阶段命中第二节 Gate；再实际打开第六节所指专项页。只看到链接但未打开，等于未读取规则。
3. 识别行动的 Owner、触发条件、前置依赖、交付物、验收证据、下一步和阻塞人；缺任一项先回报，不用百分比掩盖。
4. 读取 Spec 与建造单当前版本，验证双向链接、层级和写权；建设侧不得替业务 Owner 修改语义。
5. 按第五节判断登记触发。命中而未登记时停止启用或转 Gate。
6. 事实只标为：已验证／已完成但未验收／进行中／待决策／被阻塞／未开始；附 Jira、Confluence、回读、测试或团队回复。
7. 涉及语义、跨部门责任、权限或结构性影响时，生成白话决策请求；写清决定、成本、截止点及沉默不等于同意。
8. 完成后重读权威页和实际配置，核对页面版本、登记行、测试证据与 Jira Gate；没有回读证据不得报告完成。

**强制停止条件**｜权威页打不开；规则冲突；业务语义未裁决；Owner 不明；前置未齐；登记触发命中但无行；测试／回读证据缺失；实际配置与 Spec／建造单不一致。停止时必须指出阻塞对象、阻塞人和恢复条件。

# 八、与 03／05／06／07 的关系

| 页面家族 | 负责什么 | 与 04 的接口 |
| --- | --- | --- |
| [03｜文档／知识层](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1677000718/03) | 知识住哪里、如何面向读者维护 | 04 提供已验证事实；测试后由知识层产出指南，不复制工程 SSOT |
| [05｜权责／治理层](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676902411/05) | 谁有权决定、谁负责、升级给谁 | 04 引用正式 Owner／RACI，不另造权责定义 |
| [06｜流程全貌与成熟度模型](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1676935183/06) | 汇编已定稿流程的组织全景 | 04 管单条流程建设；06 后置汇编，不与 Spec 双写 |
| [07｜指南](https://nexmax.atlassian.net/wiki/spaces/NOSM/pages/1704362028/07) | 按阶段编排人的步骤和 Skills | 04 定义必须满足什么；07 定义怎样做到，只引用不复制 |

# 九、04.x 子页统一骨架

全部 04.x 子页面向人和 AI 双受众，采用同页分层，不维护人版／机器版两份正文。

| 固定区块 | 承载内容 | 顺序 |
| --- | --- | --- |
| 1｜Info panel | 性质、读者、问题、权威边界与引用页 | 固定置顶 |
| 2｜规则本体 | 速查、映射、判定步骤、配置或登记清单 | 高频优先 |
| 3｜配置细则／模式 | 落地方式、字段或证据要求 | 紧随规则本体 |
| 4｜背景与理由 | 论证、案例与非配置依据 | 页面末段，明确“供理解” |
| 5｜Note panel | Owner、权限、更新触发、审计与升级线 | 固定置底 |

子页新增、废弃、改名、权威边界改变或跨页结构重排时，必须同步核对本页路由与全部指针。一般正文更新无需复制到本页。

# 十、背景与理由（供理解，非配置依据）

单条流程在没有本页时仍可开发，因为 Epic Owner、评论和参与者会临时补足跨页判断。本页不是让第一条流程“能做”，而是让第二十条流程仍能被不同的人和 AI 以同一方式切分、设计、登记、验收、接手和变更。它把散落在人脑、Session 与 Jira Comment 的家族级协调规则固化为执行合同；对象级事实仍留在专项 SSOT，避免本页成为第二份配置数据库。

---

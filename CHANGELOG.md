# Changelog

本文件记录 otp-target-assessment skill 的版本更新。版本号遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)（MAJOR.MINOR.PATCH）。

本 skill 由 WorkBuddy 在 MRGPRX2 × 慢性自发性荨麻疹（CSU）评估项目中创建并持续迭代，版本演进即反映该项目实战沉淀的评估纪律。所有版本均通过 skill-creator 校验并重新打包（`otp-target-assessment.zip`）。

## [1.4.0] - 2026-08-18

### Added（新增）
- `references/framework.md` §8 新增两条实战教训：
  - **区分"官方口径"与"外部推演"并强制标注**：竞争分子状态以官方新闻稿/电话会/ClinicalTrials.gov 为准；分析师推测必须标注"非官方推演"；注意材料时间锚点（失败前 vs 失败后）。（来源：AB102 案例——EVO-756 失败后 Arcus Q2-2026 财报仍保留 CSU POC mid-2027、无书面调整，而"Ⅰ期数据作为 POC 适应症选择 gatekeeper"为外部推演）
  - **机制表型差异是竞争分析关键变量**：surmountable（可逾越）/ insurmountable（不可逾越）/ 变构 NAM 表型差异需逐项目注明，但表型差异 ≠ 疗效差异，需临床验证。
- `SKILL.md` 核心纪律从 7 条扩充至 10 条，新增/强化：毒理情报边界、靶点占用 ≠ 疗效、官方口径 vs 外部推演、机制表型差异标注。

### Changed（修改）
- `SKILL.md` 纪律 5 补充"人体 Ⅰ期安全性良好 ≠ 免于动物长期毒理风险；毒理信号可能不公开"。
- `SKILL.md` 纪律 6、7、8 新增（原纪律 6、7 顺延为 9、10）。

## [1.3.0] - 2026-08-18

### Changed（修改）
- `references/framework.md` §5 毒理教训强化：**人体 Ⅰ期安全性良好（AE 率低于安慰剂）≠ 免于动物长期毒理风险**；毒理信号可能不公开（公司仅表述 "preclinical toxicology findings"），情报上只能依赖公司公告、试验状态变更（ClinicalTrials.gov）与媒体追踪。（来源：EP262 终止原因澄清——失败源为 GLP 动物长期毒理新发现，非人体临床 SAE，毒理靶器官与数据未公开，全部适应症一并终止）

## [1.2.0] - 2026-08-18

### Added（新增）
- `references/framework.md` §8 新增教训：**"靶点占用 ≠ 疗效"是最易犯的乐观陷阱**——PD 生物标志物（如 icatibant 风团抑制）与相邻适应症疗效（如 CIndU 阳性）不能外推为目标适应症疗效；证据层级：靶点占用（弱）< 相邻适应症疗效（中）< 目标适应症疗效读出（强）；"机制已验证"表述必须注明验证层级，且"方向正确 ≠ 适应症有效"。（来源：EVO756 CSU Ⅱb 阴性——N=160 未达 UAS7 主要终点，Evommune 终止 CSU 开发）

### Changed（修改）
- `references/framework.md` §8 竞争反转教训更新：增加 EVO756 CSU Ⅱb 失败案例（2026-06-29）；要求核查竞争反转的时间关联（SEP-631 撤 CSU Ⅱb 发生在 EVO756 失败公布后 6 周，大概率是直接回应）。

## [1.1.0] - 2026-08-18

### Added（新增）
- `references/framework.md` §8 新增教训：**机制分类必须注明实验体系**——"反向激动剂/拮抗剂/NAM"等分类若来自高过表达细胞体系（易组成型激活），须标注"仅限过表达体系，生理表达/原代细胞未验证"，禁止过度外推；引用机制结论时给出原始证据出处（正文 vs 补充材料）。（来源：EP262 反向激动剂分类仅出自 JACI 2024 补充材料 Fig E3 的过表达 CHO 体系；"长期抑制本底活性致毒理失败"为未验证假说）

## [1.0.0] - 2026-08-14

### Added（新增）
- 初始版本，基于 MRGPRX2 × CSU 完整评估流程（OTP 数据查询 + PDB 核实 + 现实管线交叉验证 + 五步合成 + 概率粗估 + HTML 报告）固化：
  - `SKILL.md` — 8 步工作流 + 7 条核心纪律
  - `scripts/otp_query.py` — 一键执行 OTP GraphQL 全部查询（search/靶标/疾病/证据/遗传/表达/meta），JSON 落盘 + 精简摘要
  - `scripts/rcsb_check.py` — 按 UniProt AC 列出 PDB 条目（RCSB Search API + entry API）
  - `scripts/europepmc_titles.py` — PMID → 文献标题查询
  - `references/otp-queries.md` — GraphQL 查询模板全集 + 参数陷阱（`Bs` 参数名、entityNames 字符串、meta.dataVersion 嵌套、introspection 自检）
  - `references/framework.md` — 五步合成法、概率粗估（做法 A/B）、报告章节规范、交通灯解读、实战教训清单
  - `assets/report-skeleton.html` — 中文评估报告 HTML 骨架（CSS + 章节结构 + 占位标记）
- 通过 skill-creator 校验并打包为 `otp-target-assessment.zip`（用户级安装于 `~/.workbuddy/skills/`）。

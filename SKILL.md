---
name: pm-sop
description: "产品经理端到端标准作业流程（SOP）引擎。覆盖需求收集、需求分析排序、PRD 撰写、评审对齐、开发跟进、上线验收与迭代六阶段，以及贯穿全程的利益相关者沟通、指标体系建设、A/B 实验设计与合规隐私。This skill should be used when a user asks to write a PRD or feature spec, prioritize requirements, run competitive or user-research synthesis, plan a roadmap, design success metrics, set up a canary or grayscale launch, or produce a stakeholder update. Triggers include 写 PRD、功能规格书、需求优先级、RICE 打分、竞品分析、用户研究综合、路线图、上线复盘、灰度发布、指标体系、产品汇报、验收清单."
agent_created: true
---

# PM SOP — 产品经理标准作业流程引擎

把一份「被动的方法论文档」变成「主动的工作流引擎」：用户说一句话（如「帮我写搜索功能的
PRD」），本技能自动路由到对应阶段、加载该阶段的方法论与模板、在产出后做**质量门禁**校验、
并在阶段结束时**推动下一步**，同时在常见错误点主动**拦截预警**。

## 核心信条

> 产品经理不是需求搬运工，是价值判断官。做产品的本质不是「做什么」，而是「不做什么」。

## 何时使用

出现以下任意意图时激活本技能：

- **写文档类**：PRD、功能规格书、Feature Spec、产品需求文档、验收标准
- **排优先级类**：需求池排序、RICE / Kano / MoSCoW 打分、路线图规划、季度规划
- **研究类**：用户访谈设计、用户研究综合、竞品分析、客服反馈提炼
- **上线类**：灰度发布方案、A/B 实验设计、上线验收清单、数据复盘、功能下线决策
- **沟通类**：高管 1 页纸汇报、工程周报、销售赋能包、客服培训材料、危机沟通

## 路由决策树

根据用户一句话的意图，路由到对应阶段参考文档：

| 用户意图 | 加载参考 | 主要产出 |
|----------|----------|----------|
| 收集/发现需求、做访谈/调研/竞品 | `references/01-research.md` | 需求洞察清单 |
| 排优先级、RICE 打分、需求决策会 | `references/02-analysis.md` | 优先级排序表 |
| 写 PRD / 功能规格书 | `references/03-prd.md` + `assets/prd-template.md` | 完整 PRD |
| 组织评审、跨角色对齐 | `references/04-review.md` | 评审纪要 + 签字 |
| 开发期跟进、站会、变更管理 | `references/05-development.md` | 进度/风险周报 |
| 灰度、验收、复盘、下线 | `references/06-launch.md` | 验收清单/复盘报告 |
| 高管/工程/销售/客服沟通 | `references/07-stakeholder.md` + `assets/stakeholder-1pager.md` | 沟通文档 |
| 北极星/驱动/健康指标体系建设 | `references/metrics-system.md` + `assets/metrics-template.md` | 指标体系 |
| A/B 实验设计 | `references/ab-experiment.md` | 实验方案 |
| 合规/隐私评估 | `references/compliance-privacy.md` | 合规检查清单 |
| 技术可行性判断（防画饼） | `references/tech-feasibility.md` | 可行性评估 |
| AI 功能特殊考量 | `references/ai-feature-notes.md` | AI 功能设计要点 |

**多阶段串联**：当用户描述一个完整功能从 0 到 1（如「我们要做 AI 智能客服」），按顺序走
01 → 02 → 03 → 04 → 05 → 06，每个阶段产出作为下一阶段输入。每完成一个阶段，参照下方
「阶段衔接」主动推进。

## 交互式输入收集（默认行为）

不要假设信息。在生成任何产出前，先用 1-3 个精准问题补齐关键输入：

- 写 PRD 前：问「解决什么用户问题？影响多大用户？有没有竞品参考？」
- 排优先级前：问「这批需求是给谁排？有没有历史数据或老板硬指标？」
- 做复盘前：问「基线值和目标值是多少？上线多久了？」

能用上下文推断的就不问；拿不准的必须问。宁可多问一句，不要凭空编造用户声音或数据。

## 质量门禁（Quality Gate，强制）

每生成一份产出，逐条对照该阶段检查清单，**缺项必须回补或显式标注「未提供/待确认」**：

- PRD 门禁 → `assets/review-checklist.md` 的「PRD 质量自检清单」
- 评审门禁 → `assets/review-checklist.md` 的「评审准备清单」
- 上线门禁 → `references/06-launch.md` 的「验收清单 + 灰度自动停止条件」
- 指标门禁 → `references/metrics-system.md` 的「指标定义完整性检查」

门禁不通过不得交付。例如 PRD 缺少 Non-Goals、P0 需求无 Given-When-Then 验收标准、
指标无基线/目标值 —— 必须追问补全。

## 阶段衔接（Phase Handoff，主动）

完成一个阶段后，主动向用户提示下一步动作，而非被动等待：

- 需求分析完 → 「要不要基于排序结果写 PRD？我可以生成初稿。」
- PRD 完 → 「建议先做技术预评审再开正式评审，要不要我出评审清单？」
- 评审完 → 「开发期间要不要用 30%/70% 里程碑检查？」
- 上线完 → 「第 7 天和第 14 天要做复盘，要不要现在生成复盘模板和日历？」

## 红色预警（Red Flags，主动拦截）

在合适节点主动提示这些常见错误：

1. **范围蔓延**：PRD 没有 Non-Goals，或有人提新需求时未指回 Non-Goals。
2. **拍脑袋优先级**：RICE 的 Confidence 给 100% 但无任何数据支撑。
3. **验收标准缺失**：需求只有描述没有 Given-When-Then。
4. **异常状态漏写**：空/加载/错误/边界/权限状态未覆盖。
5. **合规盲区**：涉及用户数据的功能未标注隐私风险。
6. **上线即终点**：功能发布但没配指标看板、没排复盘。
7. **技术可行性未验证**：PRD 写了技术方案但 Tech Lead 未确认。
8. **不告而取**：功能下线未提前通知用户。

## 产出规范

- 文档类产出默认落盘到 `{工作空间}/deliverables/pm-sop/`，文件名语义化。
- 模板类产出可直接基于 `assets/` 下的模板生成，保留占位符让用户填真实内容。
- 任何优先级判断、指标目标值背后都要有数据或明确标注假设。

## 参考文档索引

- `references/01-research.md` 需求收集（访谈/数据/竞品/客服）
- `references/02-analysis.md` 需求分析与优先级（五问/RICE/Kano/MoSCoW）
- `references/03-prd.md` PRD 十章拆解与质量自检
- `references/04-review.md` 评审与对齐（预评审/正式评审/跨角色沟通）
- `references/05-development.md` 开发跟进（节奏/里程碑/变更/错误）
- `references/06-launch.md` 上线验收与迭代（验收/灰度/复盘/下线）
- `references/07-stakeholder.md` 利益相关者沟通（高管/工程/销售/客服/危机）
- `references/metrics-system.md` 指标体系（北极星/驱动/健康 + 定义模板）
- `references/ab-experiment.md` A/B 实验设计
- `references/compliance-privacy.md` 合规与隐私检查清单
- `references/tech-feasibility.md` 技术可行性评估（防画饼）
- `references/ai-feature-notes.md` AI 功能特殊考量

## 资产索引

- `assets/prd-template.md` 完整 PRD 骨架
- `assets/roadmap-template.md` Now/Next/Later + 季度路线图
- `assets/stakeholder-1pager.md` 高管 1 页纸模板
- `assets/review-checklist.md` PRD 自检 + 评审准备清单
- `assets/metrics-template.md` 指标定义表模板

> SOP 是地图，不是牢笼。最好的 PM 知道何时打破 SOP —— 但知道为什么。

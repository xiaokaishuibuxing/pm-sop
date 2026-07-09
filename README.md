# pm-sop

> 产品经理端到端标准作业流程（SOP）引擎 —— 把「写 PRD / 排优先级 / 做路线图 / 设计指标 / 灰度发布 / 向上汇报」从一份文档变成可触发、可校验、带质量门禁的工作伙伴。

## 它解决什么

一份 SOP 文档躺在文件夹里，记得翻才用得上；`pm-sop` 是一个 WorkBuddy Skill，说一句意图就激活，并在每个节点主动推下一步、做缺项校验：

- **不靠记忆**：说「帮我写搜索功能的 PRD」即加载十章结构、用户故事格式、验收标准模板
- **质量门禁**：PRD 生成后自动校验 Non-Goals / Given-When-Then / 异常状态 / 指标基线是否齐备
- **决策引导**：排优先级时逐项引导 RICE 四维打分，必须走完流程才出结果
- **阶段衔接**：到「开发跟进」「上线复盘」节点自动提醒，不再靠想起才做

## 覆盖六阶段 + 贯穿能力

| 阶段 | 关键产出 |
|------|----------|
| 1. 需求收集 | 访谈 SOP、数据分析层次、竞品调研模板 |
| 2. 需求分析与排序 | RICE / Kano / MoSCoW、五问深度拆解 |
| 3. PRD 撰写 | 十章结构 + 好/差对比案例 + 验收标准范例 |
| 4. 评审与对齐 | 预评审链路、跨角色沟通准则、签字流程 |
| 5. 开发跟进 | 30%/70% 里程碑、变更评估、PM 易错点 |
| 6. 上线验收与迭代 | 验收清单、灰度策略、复盘模板、功能下线 |
| 贯穿：利益相关者沟通 | 高管 1 页纸 / 工程周报 / 销售赋能 / 客服培训 |
| 贯穿：新增能力 | 指标体系、A/B 实验、合规隐私、技术可行性、AI 功能 |

## 目录结构

```
pm-sop/
├── SKILL.md                 # 路由决策树 + 质量门禁 + 阶段衔接 + 红色预警
├── references/              # 12 个阶段与能力详解
│   ├── 01-research.md
│   ├── 02-analysis.md
│   ├── 03-prd.md
│   ├── 04-review.md
│   ├── 05-development.md
│   ├── 06-launch.md
│   ├── 07-stakeholder.md
│   ├── metrics-system.md
│   ├── ab-experiment.md
│   ├── compliance-privacy.md
│   ├── tech-feasibility.md
│   └── ai-feature-notes.md
├── assets/                  # 5 个可直接复制的模板
│   ├── prd-template.md
│   ├── roadmap-template.md
│   ├── stakeholder-1pager.md
│   ├── review-checklist.md
│   └── metrics-template.md
└── LICENSE
```

## 安装

把整个目录放到 WorkBuddy 的技能目录即可（无需解压、无需额外依赖）：

```bash
# 方式一：从 GitHub 克隆
git clone git@github.com:xiaokaishuibuxing/pm-sop.git ~/.workbuddy/skills/pm-sop

# 方式二：下载 zip 后解压到 ~/.workbuddy/skills/pm-sop/
```

放好后，在 WorkBuddy 对话里用意图触发即可，例如：

- 「帮我写搜索功能的 PRD」
- 「给这 10 个需求按 RICE 排优先级」
- 「设计一个灰度发布方案」
- 「为这个功能建一套指标体系」
- 「给 CEO 写一页纸产品汇报」

## 使用约定

- Skill 是**工作伙伴**而非自动执行器：它给半成品、做校验、推流程，最终判断仍由你（产品经理）拍板。
- 涉及用户数据的功能，默认按《个人信息保护法》/ GDPR 标注合规风险（见 `compliance-privacy.md`）。
- AI 类功能额外关注幻觉、人机边界、AI 专属指标与成本（见 `ai-feature-notes.md`）。

## License

[MIT](./LICENSE) © 2026 xiaokaishuibuxing

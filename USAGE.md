# pm-sop 调用指南（USAGE）

本文件说明如何准确触发 `pm-sop` 这个 Skill、有哪些可用的「指令」（本质是意图短语），以及它加载后的行为特点。

---

## 一、怎么触发：没有命令语法

`pm-sop` 是**意图触发型** Skill，不需要记任何斜杠命令或特殊语法。在 WorkBuddy 对话里说出你的产品意图即可：

1. **自然语言直接说**（最常用）：系统根据 `SKILL.md` 的 description 自动匹配并加载。
   - 例：「帮我写搜索功能的 PRD」→ 自动触发
2. **显式指定**（想保险时）：在句首加「用 pm-sop」「调用 pm-sop」。
   - 例：「用 pm-sop 给我排一下需求优先级」

> 不需要安装额外依赖，只要 `pm-sop` 目录在 `~/.workbuddy/skills/` 下即可被识别。

---

## 二、指令清单（按路由表整理）

| 你想做的事 | 直接这么说（示例） | Skill 加载 | 产出 |
|-----------|------------------|-----------|------|
| 写 PRD | 「帮我写『搜索模糊匹配』功能的 PRD」 | `references/03-prd.md` + `assets/prd-template.md` | 完整 PRD + 质量校验 |
| 排优先级 | 「给这 10 个需求按 RICE 排优先级」 | `references/02-analysis.md` | RICE 排序表 + P0/P1/P2 |
| 收集需求 | 「设计一个用户访谈方案」 | `references/01-research.md` | 访谈 SOP / 调研模板 |
| 组织评审 | 「帮我出技术评审清单」 | `references/04-review.md` | 评审纪要 + 签字项 |
| 开发跟进 | 「生成这周的开发进度周报」 | `references/05-development.md` | 进度/风险周报 |
| 灰度发布 | 「设计灰度发布方案」 | `references/06-launch.md` | 灰度策略 + 停止条件 |
| 上线复盘 | 「XX 功能上线了，做复盘」 | `references/06-launch.md` | 复盘模板 + 日历 |
| 路线图 | 「做下半年路线图」 | `references/02-analysis.md` + `assets/roadmap-template.md` | Now/Next/Later 路线图 |
| 指标体系 | 「建一套北极星指标体系」 | `references/metrics-system.md` + `assets/metrics-template.md` | 指标定义表 |
| A/B 实验 | 「设计 A/B 实验」 | `references/ab-experiment.md` | 实验方案（样本量/MDE/显著性） |
| 合规评估 | 「这功能涉及用户数据，做合规检查」 | `references/compliance-privacy.md` | 合规检查清单 |
| 技术可行性 | 「评估这个方案的技术可行性」 | `references/tech-feasibility.md` | 可行性评估 |
| 向上汇报 | 「给 CEO 写一页纸产品汇报」 | `references/07-stakeholder.md` + `assets/stakeholder-1pager.md` | 高管 1 页纸 |
| 竞品分析 | 「做竞品 A/B/C 对比」 | `references/01-research.md` + `references/07-stakeholder.md` | 竞品对比报告 |
| 用户研究 | 「综合这 20 份访谈找规律」 | `references/01-research.md` | 洞察清单 |
| AI 功能 | 「我们要做 AI 客服，评估要点」 | `references/ai-feature-notes.md` | AI 设计要点 |

---

## 三、高级玩法：0→1 串联

如果你描述的是一个**完整功能从 0 到 1**，它会**自动按顺序走完全流程**：

```
需求收集 → 需求分析 → PRD → 评审对齐 → 开发跟进 → 上线验收与迭代
(01)      (02)       (03)   (04)       (05)         (06)
```

每个阶段产出作为下一阶段输入，且每完成一步会**主动推你做下一步**（而不是等你想起）。
例：「我们要做 AI 智能客服」→ 走完六阶段，期间主动提示评审、里程碑、复盘。

---

## 四、加载后的行为特点（脾气）

1. **先问再写**：写 PRD 前会问「解决什么用户问题？影响多大？有竞品参考吗？」——拿不准必问，不瞎编数据。
2. **质量门禁**：PRD 缺 Non-Goals、P0 需求没 Given-When-Then、指标没基线/目标值 → 会**追问补全才交付**。
3. **主动预警**：RICE 的 Confidence 拍 100% 却没数据、PRD 没写异常状态等 8 类常见错误，会在合适节点拦截。
4. **阶段衔接**：完成一个阶段主动提示下一步，不被动等待。

---

## 五、一句话总结

把它当成一个「产品搭档」，用大白话告诉它你想做哪块产品工作就行，路由、模板、校验它自己搞定。

> SOP 是地图，不是牢笼。最好的 PM 知道何时打破 SOP —— 但知道为什么。

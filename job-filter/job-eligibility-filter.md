---
name: job-eligibility-filter
description: Screen archived job postings for work shape, hard eligibility, and career development before clustering; write eligible or verify-needed screening notes linked to their Raw sources.
---

# 岗位准入与职业发展筛选

此 skill 是聚类前的第一道门：筛选 `/Users/jinx/Library/Mobile Documents/iCloud~md~obsidian/Documents/CV/1.岗位/Raw` 中的岗位，决定其是否应保留在可行求职池。它不做职业路径聚类、个人简历匹配、投递排序或简历修改。

## 输入与输出

- 输入：`Raw/Strong` 和 `Raw/Weak` 内的岗位笔记。
- 输出：只为 `ELIGIBLE` 与 `TO_VERIFY` 的岗位在 `/Users/jinx/Library/Mobile Documents/iCloud~md~obsidian/Documents/CV/1.岗位/Filter` 创建独立筛选笔记，并保留指向 Raw 原笔记的 Obsidian 链接。
- `REJECT` 不复制岗位笔记到 `Filter`；在同目录的当日筛选汇总中记录原笔记链接、状态和一句拒绝理由。
- 不修改 Raw 原笔记，不改变其 Strong/Weak 分类。

使用 [输出模板](https://github.com/Vivace98/FindAJob/blob/main/job-filter/output-template.md)。每个结论必须遵循“证据 → 规则 → 状态”，只采用 Raw 笔记中转录的 JD 或明确的结构化字段；不能用职位名称、公司名、行业声誉或印象补证据。

## 筛选顺序

按以下顺序逐篇判断，任一步明确 `REJECT` 即停止后续评分：

1. 工作形态门槛
2. 硬条件：固定月薪、双休、班次、候选资格
3. Career Development（仅工作形态未拒绝时）
4. 汇总状态

未知硬条件不推断为有利条件，除薪资的特定情形外均标为 `TO_VERIFY`。

## 1. 工作形态门槛

这是聚类前的强制筛选，防止“数据开发与治理”岗位因工具要求多而进入职业池。

- `PRIORITIZE`：主要工作包括理解或定义业务／研究问题、指标设计与探索、统计分析与建模、假设检验／回归／预测／分群、解释机制、形成报告或洞察、支持决策，以及与业务或研究团队沟通。
- `LOWER_PRIORITY`：以 SQL 取数、固定报表、BI 看板维护、成熟模型的常规使用或高比例清洗为主，但公开 JD 仍明确要求专题分析、解释结果、诊断问题或支持决策。该状态不是硬拒绝，应继续完成后续筛选，并在输出中保留其优先级。
- `REJECT`：主要工作是数据开发、数仓／ETL、大数据平台、算法工程、后端开发、MLOps／模型部署、系统建设、接口开发或生产环境维护；或主要考察复杂软件工程／算法能力。此类岗位不因出现 Python、SQL、AI、报表或“数据分析”字样而保留。

岗位名称可用于发现线索，但必须以职责的主导工作验证。名称为“数据开发工程师”等通常应拒绝；只有 JD 明确显示开发为次要、分析与解释为主时，才可例外写为 `LOWER_PRIORITY`，并解释证据。

## 2. 硬条件

### 薪资

固定税前月薪下限须为 **7,000 元**：

- `PASS`：固定月薪下限 ≥ 7,000 元。
- `TO_VERIFY`：区间跨过 7,000 元，例如 6K–10K。
- `REJECT`：固定月薪上限 < 7,000 元，或仅写面议、年包、底薪加绩效／提成但固定部分不明。

奖金、补贴、股票、绩效和提成不能凑足门槛。

### 双休

- `PASS`：明确“周末双休／双休／五天工作制／周一至周五／five-day workweek”。
- `REJECT`：明确“单休／大小周／六天工作制”或常规周末工作。
- `TO_VERIFY`：未公开作息。

### 班次与夜班

- `PASS`：明确白班、日班、正常办公时间，且无冲突安排。
- `REJECT`：明确夜班、倒班、轮班、两班倒、三班倒、24 小时轮转或常规夜间值班。
- `TO_VERIFY`：未公开班次。

偶发加班不等同于轮班；可记录 `work_intensity_risk`，但不单独拒绝。

### 候选资格

- `PASS`：明确本科、本科及以上、硕士，或本科／硕士；“本科及以上”不因候选人学历更高而拒绝。
- `REJECT`：明确仅大专／高中／中专，或明确博士／PhD 为必须条件。
- `TO_VERIFY`：学历、博士限制或校招届别与候选人届别的关系无法判断。

若用户另行提供个人毕业届别或其他不可变条件，将其写入筛选汇总的 `candidate_profile_used`；未提供时不得猜测。

## 3. Career Development

对未被工作形态或硬条件拒绝的岗位，按五项各 0–2 分评分：分析深度（AD）、技能积累（SA）、决策暴露（DE）、问题所有权（PO）、职业可迁移性（CT）。总分 `CD = AD + SA + DE + PO + CT`。

- 8–10：`STRONG`
- 6–7：`ACCEPTABLE`
- 4–5：`CAUTION`
- 0–3：`WEAK`

`CD >= 6` 为 `PASS`；低于 6 为 `REJECT`。纯录入、纯固定报表、纯客服、纯销售、纯行政或纯执行岗位，即使文字表面分数较高，也以 `career_development_override: REJECT` 处理。工具名本身不能证明分析深度；每一项都要引用职责或要求中的工作产出。

## 4. 最终状态

- `REJECT`：工作形态为 `REJECT`，或任一硬条件／Career Development 为 `REJECT`。
- `TO_VERIFY`：不存在 `REJECT`，但一个或多个硬条件为 `TO_VERIFY`。
- `ELIGIBLE`：所有硬条件和 Career Development 均为 `PASS`。

`LOWER_PRIORITY` 是工作形态标签，不改变上述状态机；它在 Filter 笔记和筛选汇总中单独显示。

## 批量交付

先创建或更新 `Filter/YYYY-MM-DD_岗位筛选汇总.md`，用表格列出岗位、Raw 链接、工作形态、四项硬条件、CD 分数、最终状态与待核验事项。然后仅写入符合输出条件的筛选笔记。报告 Strong/Weak 输入数、`ELIGIBLE`／`TO_VERIFY`／`REJECT` 数量及拒绝的主要原因。

只有完成本 skill 的 `ELIGIBLE` 与 `TO_VERIFY` 岗位才进入后续 `job-clustering-profile`。后者不得重新纳入本阶段拒绝的岗位。

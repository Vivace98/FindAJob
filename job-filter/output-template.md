# Filter 筛选笔记模板

每份筛选笔记使用与 Raw 原文件相同的文件名，存放在 `1.岗位/Filter/`。这是筛选派生笔记，不复制完整 JD；必须保留原笔记链接。

```markdown
---
type: job-eligibility-screen
company: "公司全称"
position: "岗位名称"
screened_at: "YYYY-MM-DD"
raw_note_path: "1.岗位/Raw/Strong/YYYY-MM-DD_公司_岗位.md"
raw_classification: "Strong / Weak"
work_shape: "PRIORITIZE / LOWER_PRIORITY"
overall_status: "ELIGIBLE / TO_VERIFY"
salary_status: "PASS / TO_VERIFY"
weekends_off_status: "PASS / TO_VERIFY"
shift_status: "PASS / TO_VERIFY"
candidate_eligibility_status: "PASS / TO_VERIFY"
career_development_score: 0
career_development_classification: "STRONG / ACCEPTABLE"
work_intensity_risk: "true / false / unknown"
verification_needed: []
---

# 公司｜岗位｜筛选结果

## 原始岗位

- [[1.岗位/Raw/Strong/YYYY-MM-DD_公司_岗位|查看 Raw 原始岗位笔记]]

## 工作形态门槛

- 状态：PRIORITIZE / LOWER_PRIORITY
- 证据：JD 中的职责原文或其 Raw 笔记定位。
- 判断：说明为什么分析、解释和决策支持是主导工作，或为什么它只是次要但仍值得保留。

## 硬条件

| 条件 | 状态 | 证据 | 规则判断 |
| --- | --- | --- | --- |
| 固定税前月薪 ≥ 7,000 | PASS / TO_VERIFY | | |
| 五天工作制／双休 | PASS / TO_VERIFY | | |
| 无常规夜班／轮班 | PASS / TO_VERIFY | | |
| 候选资格 | PASS / TO_VERIFY | | |

## Career Development

| 维度 | 0–2 分 | JD 证据 |
| --- | ---: | --- |
| Analytical Depth | | |
| Skill Accumulation | | |
| Decision Exposure | | |
| Problem Ownership | | |
| Career Transferability | | |

- 总分：`n/10`（STRONG / ACCEPTABLE）
- 结论：说明保留的职业发展理由；不得使用公司声誉、薪资或岗位名称代替证据。

## 最终结论

- 总体状态：ELIGIBLE / TO_VERIFY
- 工作形态优先级：PRIORITIZE / LOWER_PRIORITY
- 待核验：没有则写“无”；否则逐项说明待问 HR 的事实。
- 工作强度风险：true / false / unknown；说明证据。
```

筛选汇总中的 `REJECT` 行必须包含：Raw 原始笔记链接、拒绝步骤（工作形态／硬条件／Career Development）和最短证据理由；不要在 Filter 中另建被拒绝岗位的派生笔记。

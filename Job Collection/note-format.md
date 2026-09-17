# Obsidian 岗位笔记格式

对每个已保存岗位使用此模板。未知值写 `未公开` 或 `待核实`，不得空置或推断补全。

```markdown
---
type: job-posting
company: "公司全称"
position: "岗位名称"
location: "苏州｜具体区县/办公地点"
classification: Strong # Strong：直接数据职责且明确要求 Python/R/Stata/Office/Excel；否则 Weak
eligibility_status: 待核实 # 已满足 / 待核实
eligibility_gaps: [] # 如 [固定双休未公开, 发布日期未公开]
company_ownership: "外商独资 / 中外合资 / 国企 / 民营 / 其他 / 待核实"
is_foreign_enterprise: "是 / 否 / 待核实"
ownership_evidence: "公司官网 About Us，第 N 段 / 待核实"
source_platform: "企业官网 / BOSS直聘 / …"
source_url: "https://…"
alternate_sources: []
posted_or_updated: "YYYY-MM-DD / 未公开"
deadline: "YYYY-MM-DD / 未公开"
accessed: "YYYY-MM-DD"
first_seen: "YYYY-MM-DD"
last_checked: "YYYY-MM-DD"
posting_status: "活跃 / 疑似过期 / 已下线 / 待核实"
education: "本科及以上 / 待核实"
phd_eligibility: "不招博士 / 博士可投 / 待核实"
salary: "JD 原文"
after_social_insurance_housing_fund_over_5000: "是 / 否 / 待核实"
income_tax_included_in_estimate: "是 / 否 / 待核实"
weekends_off: "是 / 否 / 待核实"
verification: "已公开核验 / 部分公开 / 待核实"
business_domain: [] # 如 制造、电商、医疗、金融、教育、物流、互联网、消费品
business_function: [] # 如 用户运营、市场研究、供应链、财务、风控、销售、产品、质量管理
business_object: [] # 如 用户、订单、销售、库存、设备、风险客户、问卷受访者
business_problem: "未明确" # 例如 识别流失用户并提升留存
data_tasks: [] # 如 数据清洗、指标监控、经营报表、异常归因、建模、实验分析
methods: []
tools: []
data_sources: [] # 如 用户行为数据、交易数据、问卷数据、财务数据、设备传感器数据
seniority: "未明确"
work_mode: "未明确"
clustering_confidence: "高 / 中 / 低"
english_requirement: "低 / 中 / 高"
english_requirement_basis: "JD 未提及，按低处理"
english_evidence: "未提及"
tags: [求职, 苏州, 数据分析]
---

# 公司｜岗位

## 来源

- [岗位原始页面](https://example.com)
- 访问日期：YYYY-MM-DD
- 来源平台：平台名称
- 首次发现：YYYY-MM-DD
- 最近复核：YYYY-MM-DD
- 职位状态：活跃 / 疑似过期 / 已下线 / 待核实
- 备用来源：没有则写“无”；同一职位的其他公开链接列于此处。

## 分类与筛选判断

- 分类：Strong / Weak。Strong 须同时满足“直接数据职责”与“明确要求 Python、R、Stata 或 Office/Excel”；仅 SQL 或无上述工具证据的相关岗位归 Weak。
- 分类理由：引用职责或要求中的具体证据。
- 资格核验：`eligibility_status` 填“已满足”或“待核实”；`eligibility_gaps` 列出地点、日期、学历/博士、薪资或双休等未核实项。资格待核实不改变 `classification` 或文件夹。
- 公司性质与外企：`company_ownership`、`is_foreign_enterprise` 和 `ownership_evidence`；转录核验来源及原文位置。
- 地点：原文；判断：满足 / 待核实。
- 时间：发布日期、更新日期或截止日期；判断：满足 / 待核实。
- 学历与博士：原文；判断：满足 / 排除 / 待核实。
- 薪资：原文；扣除五险一金后 > 5,000：是 / 否 / 待核实；写明估算口径、来源和日期。
- 作息与福利：原文；双休：是 / 否 / 待核实。

## 职位描述（原文）

> 按页面的岗位职责、任职要求、技能、薪酬和福利分段转录全部公开可见原文。保留页面标题或分段，以便摘要定位。

## 岗位摘要

- 核心职责：从职责中摘取“做什么 + 产出什么”。〔原文：岗位职责，第 N 条〕
- 方法/工具：仅列 JD 明确写出的工具、语言、方法或数据源；无则“未明确”。〔原文：任职要求，第 N 条〕
- 关键要求：学历、专业、经验、必要方法或行业背景。〔原文：任职要求，第 N 条〕

## 聚类标签

- 业务领域：`business_domain`；只使用稳定行业标签。
- 业务环节：`business_function`；如用户运营、供应链或风控。
- 分析对象与问题：`business_object`、`business_problem`；业务问题用一句短句概括，不能超出 JD 可支持的范围。
- 数据工作：`data_tasks`；方法、工具和数据源分别写入 `methods`、`tools`、`data_sources`，不与业务环节混写。
- 聚类置信度：业务场景和数据工作都有直接原文证据为“高”；部分信息来自职责概括为“中”；关键场景不明为“低”。
- 英语要求：`english_requirement` 填低 / 中 / 高；`english_requirement_basis` 写判定依据，`english_evidence` 转录原文并附位置。未提及英语时，三项分别写“低”“JD 未提及，按低处理”“未提及”。

英语分级规则：大学英语四/六级、基础读写或一般英语能力要求为“中”；雅思/托福等明确成绩、英语作为工作语言、流利商务沟通，或明确要求优秀英语听说读写能力为“高”。

外企判定规则：外商独资或跨国公司在华子公司填“外商独资 / 是”；中外合资填“中外合资 / 是”；国企、民营或其他非外资主体填“否”。优先引用企业官网、全球集团官网或公开法定登记信息；招聘平台企业性质仅为初步依据。英文名称、英语要求或外籍员工不能作为外企证据，无法核验则填“待核实”。

## 核验备注

记录页面访问限制、日期缺失、薪资估算的假设、重复来源、过期风险或仍待确认的条件。
```

“扣除五险一金后”默认不等于扣除个税后的到手收入。使用税前月薪估算时，除非用户明确要求，`income_tax_included_in_estimate` 填 `否`；只要缴费基数、比例或固定薪资不明确，薪资状态必须为“待核实”。

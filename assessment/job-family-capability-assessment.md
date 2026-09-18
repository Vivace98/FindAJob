---
name: job-family-capability-assessment
description: Aggregate current Job Fit Reports for one selected job family into an evidence-backed capability assessment, prioritized learnable gaps, structural boundaries, and next evidence-building targets. Use after matching jobs in a Class; do not re-match jobs, alter upstream evidence, or write CV content.
---

# Job Family Capability Assessment

Create a job-family-level diagnosis of the candidate's evidenced position in a market category. It answers what is directly demonstrated, what can transfer, what is worth building next, and what is not a short-term learning problem.

## Scope and authority

Run only for a user-selected job family or an explicitly requested batch. Read:

- the relevant `1.岗位/Classes/` profile and Retrieval Lens;
- current Job Fit Reports and the Match Registry under `5.岗位匹配/` as the job-level classification record;
- linked Raw JD notes for exact requirement wording and locators;
- `4.个人能力画像/` as an index, then linked Evidence Units in `3.个人证据库/` as the authority for demonstrated behavior.

Do not reclassify a requirement differently from its current Job Fit Report. If reports disagree or are stale, record the inconsistency and request a matcher refresh rather than silently resolving it. Do not modify Raw, Filter, Classes, Ontology, Retrieval Lenses, Evidence Units, Personal Capability Profile, or Job Fit Reports.

Read [the assessment schema](references/assessment-schema.md) before writing.

## Aggregation rules

Organize the assessment into five mutually distinct sections:

- `DIRECT`: demonstrated behaviors that satisfy equivalent sub-behaviors in one or more JDs. Preserve original project context.
- `TRANSFERABLE`: structurally comparable source and target behaviors. Include source behavior, target behavior, transfer basis, and transfer boundary.
- `LEARNABLE_GAP`: a bounded missing tool, workflow, technique, or limited domain knowledge with documented adjacent evidence. Link every occurrence to the original Raw JD and its matcher classification.
- `STRUCTURAL_GAP`: an accumulated experience, regulated process, credential, ownership, or material domain-practice barrier. Do not give it a learning priority; state a current stance and, where useful, a long-term route.
- `UNVERIFIED`: missing facts that cannot be represented as either a gap or a match.

Never treat absence of evidence as inability. Do not turn a research outcome into commercial impact, a course tool into professional proficiency, or a transferable behavior into target-domain ownership.

## Learnable-gap priority

Use `CRITICAL`, `HIGH`, `MEDIUM`, `LOW` only for learnable gaps. State the rationale descriptively from four factors:

1. **JD coverage:** exact count of in-scope jobs and required/preferred status.
2. **Workflow centrality:** whether the Class and Lens identify it as core/common/extension.
3. **Adjacent evidence:** demonstrated behavior that lowers the transition distance.
4. **Evidence-building leverage:** whether one bounded project can credibly create reusable evidence across multiple JDs.

Do not calculate a numerical score. For a family with few jobs, state the denominator (for example, `2/2 current JD sample`) and mark findings provisional rather than claiming a stable market pattern.

## Development order

For the highest-priority learnable items, specify an evidence-building sequence:

`current evidenced behavior → nearest missing behavior → bounded new artifact/project → new Evidence Unit`

Recommend evidence creation, not a generic course list. Do not promise that learning produces evidence before an artifact exists.

## Output

Write only to `6.岗位族能力评估/<family-folder>/Capability_Assessment.md` using the reference schema. Include versions, in-scope jobs, and report snapshots so it can be marked stale when its inputs change.

Every JD-derived statement must link to a Raw note and locator; every candidate claim must link to Evidence Units. Use the Job Fit Report only as the link between them, not as a substitute for either source.

## Completion checks

Ensure Direct and Transferable sections contain detailed demonstrated behavior and boundaries. Each learnable gap has at least one linked Raw JD occurrence, adjacent evidence, priority rationale, and proposed evidence form. Each structural gap names its JD requirement and explains why short-term learning is non-equivalent. Each unverified item identifies the missing fact.

Do not create job rankings, CV bullets, fit scores, or learning priorities for structural gaps.

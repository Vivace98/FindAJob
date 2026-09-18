---
name: job-fit-evidence-matcher
description: Match a user-selected filtered job posting to an evidence-backed Personal Capability Profile and Evidence Library, producing a bounded Job Fit Report and application priority. Use after job clustering, ontology/profile creation, and evidence extraction; do not generate CV content or automatically match every job.
---

# Job Fit Evidence Matcher

Build a Job Fit Report that answers how the current evidence relates to a specified JD. It is a relationship record, not a new personal profile, a self-rating, or CV content.

## Scope and trigger

Run only for a job the user names, a named set of jobs, or an explicitly requested batch. Do not automatically match every new filtered JD.

Read:

- the linked `1.岗位/Raw/`, `1.岗位/Filter/`, `1.岗位/Classes/`, active `1.岗位/Ontology/`, and the job family's Retrieval Lens;
- `4.个人能力画像/` as a retrieval index;
- source-linked Evidence Units in `3.个人证据库/` as the authority for every final claim.

Do not rerun a current match whose JD, ontology, and profile snapshot are unchanged unless the user asks. If any has materially changed, mark the existing report `stale`; refresh only when requested.

Read [the report schema](https://github.com/Vivace98/FindAJob/blob/main/matcher/job-fit-report-schema.md) before creating or refreshing an output.

## Evidence rule

Follow this route for every match:

`JD requirement → ontology mapping → Capability Profile retrieval → Evidence Unit verification → match classification`

Match demonstrated behavior, not keyword overlap. A Profile is an index; an Evidence Unit and its source reference are authoritative. If they conflict, follow the Evidence Unit.

Never infer proficiency from a tool name, treat missing evidence as evidence of absence, relabel academic work as commercial ownership, or create a capability because a JD requests it.

## Requirement decomposition

Split the JD into the smallest independently assessable units. If a sentence combines a capability, tool, domain, and credential, create separate units rather than assigning one combined verdict.

For each unit record the raw JD wording and locator, its type (`capability`, `method`, `tool`, `domain_knowledge`, `experience`, `credential`, `delivery`, `communication`, or `other`), workflow stage, ontology label where supported, explicitness, and JD-derived criticality (`required`, `preferred`, or `unclear`). Do not upgrade criticality by judgement.

When no ontology label fits, retain the JD wording as `ontology_mapping: unmapped`; do not modify the ontology in this skill.

## Classification

Give every in-scope requirement exactly one primary result:

- `DIRECT`: Evidence shows substantially the same behavior within its supported-claim boundary. Industry need not be identical unless it is explicit in the requirement.
- `TRANSFERABLE`: The source and target behavior are structurally comparable, but target context or ownership is not directly evidenced. State source behavior, target behavior, transfer basis, and boundary.
- `LEARNABLE_GAP`: No sufficient direct/transferable evidence, but a bounded missing tool, platform, adjacent technique, or limited domain knowledge has documented adjacent evidence. State what would count as post-learning proof.
- `STRUCTURAL_GAP`: The missing requirement depends on years of direct practice, regulated workflow, required credential, material domain practice, or ownership that short-term learning cannot replace. State why, related evidence, and whether it is required or preferred.
- `UNVERIFIED`: Existing material is insufficient to decide. State the missing fact and required source; it is not a gap verdict.

Before labelling a gap, check in this order: direct evidence, bounded transferable evidence, missing information, learnable adjacency, structural barrier. Do not lower a required structural barrier to learnable; do not call all industry differences structural.

Keep Filter's eligibility, salary, schedule, and work-shape decisions separate from requirement matching. Cite them as upstream context, without re-deciding them.

## Outputs and preservation

Write only under `5.岗位匹配/` using the current job family folder and the report schema. Use a lightweight `matcher` record in the corresponding Filter note only to link the report and its status/snapshot; never put substantive match reasoning into Filter and never alter its screening judgement.

Maintain `5.岗位匹配/_Match_Registry.md` as the source of truth for report status. Group storage by job family; use the Overview to group and order reports by evidence-based application priority. The four priority groups are `MOST_SUITABLE`, `SUITABLE`, `WORTH_CONSIDERING`, and `LOW_PRIORITY`; they are ordinal groups, not numerical scores.

Report application readiness separately: `ready_to_apply`, `verify_then_apply`, or `do_not_prioritize`. A strong evidence match may still be `verify_then_apply` because Filter conditions are unresolved.

Do not modify Raw, Filter's substantive screening results, Classes, Ontology, Retrieval Lenses, Evidence Units, Capability Profile, or create CV bullets.

## Completion checks

Every direct result links an existing Evidence Unit with a source reference. Every transferable result names source/target behavior and a boundary. Every learnable gap has adjacent evidence. Every structural gap explains why it cannot be short-term-equivalently learned. Every unverified result names missing information.

Include all material negative, unresolved, and positive requirements in the Coverage Matrix. Derive job priority only after completing that matrix, without keyword percentages or numeric fit scores.

---
name: personal-capability-profile
description: Build or refresh an evidence-backed Personal Capability Profile from an Obsidian Personal Evidence Library and the current market Capability Ontology. Use after new Evidence Units or ontology changes; do not match specific jobs or write CV content.
---

# Personal Capability Profile

Create a transparent capability index: every capability statement must point back to the Evidence Units that demonstrate it. The profile is an index over facts, not a self-rating and not a claim of job fit.

## Inputs and boundaries

Read the current notes in `3.个人证据库/` and the active ontology under `1.岗位/Ontology/`. Read source-linked Evidence Units, not only project overview notes. Use the active ontology version shown in its home or changelog.

Do not alter source materials, Evidence Units, Raw/Filter/Classes job notes, the ontology, or Retrieval Lenses. Do not turn missing evidence into a capability gap, infer proficiency from a tool name, match a specific JD, rank jobs, or create CV language.

Read [profile rules](https://github.com/Vivace98/FindAJob/blob/main/personal-evidence/profile-rules.md) before writing or refreshing a profile.

## Outputs

Write under `4.个人能力画像/`:

- `_Global_Capability_Profile.md`: human-readable overview grouped by ontology family.
- `Capability_Index/<capability_id>.md`: one evidence-backed index note per demonstrated capability, when separate detail is useful.
- `_Profile_Update_Log.md`: date, source scope, ontology version, added/changed/removed index entries, and unresolved evidence.

If no valid Evidence Units exist, report that profile creation is deferred. Do not manufacture an empty-looking capability profile.

## Rebuild behavior

On an Evidence Library update, incorporate only newly valid or changed Evidence Units and refresh affected capability entries. On an ontology update, re-evaluate mappings against the new definitions while preserving historical evidence IDs. If an ontology label is deprecated, retain its trace in the log and remap only when the evidence supports the successor definition.

Each profile entry must list evidence IDs, project context, demonstrated behaviors, source quality, and evidence dimensions. A capability with only a thin or ambiguous source may appear as `provisional` with its uncertainty; it must not be represented as strong evidence.

## Completion checks

Before finishing, ensure every profile capability links to at least one Evidence Unit, every linked unit exists and records a source reference, and no profile wording exceeds the unit's `supported_claims`. Summarize omitted or unmapped evidence separately.

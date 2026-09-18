# Job Fit Report schema

Use this schema for a new or refreshed report. Keep Raw JD and Evidence Unit text in their authoritative notes; link and quote only the minimum required locator.

```yaml
---
type: job-fit-report
status: current                       # current | stale | superseded
job_id: <stable Raw/Filter basename>
job_title: <title>
company: <company>
job_family: <class id/name>
filter_note: "[[...]]"
raw_jd_note: "[[...]]"
filter_status: TO_VERIFY
ontology_version: v0.1
profile_last_refreshed: YYYY-MM-DD
matched_at: YYYY-MM-DD
application_priority: SUITABLE
application_readiness: verify_then_apply
evidence_ids_used: [THESIS_E01]
---
```

# Job identity and upstream context

State Filter status, work-shape/eligibility constraints, Class family, and Retrieval Lens. Preserve them as upstream context; do not revise them.

## Core workflow

Describe the JD's actual workflow in plain terms, linked to requirement IDs.

## Requirement Coverage Matrix

| ID | Requirement | Type | Criticality | Result | Evidence / adjacent evidence | Boundary, gap, or required verification |
| --- | --- | --- | --- | --- | --- | --- |

For `TRANSFERABLE`, add below the table:

```text
Source behavior:
Target behavior:
Transfer basis:
Transfer boundary:
```

For gaps and unverified items, state the classification-specific fields required by the skill.

## Job-level assessment

- Core capability coverage: direct evidence for the core workflow, with limits.
- Transferability: what is reasonably transferable and what is not.
- Gap burden: material learnable, structural, and unresolved items.
- Filter constraints: decision-relevant `PASS` / `TO_VERIFY` items.

## Application priority and readiness

State the ordinal priority and the separate readiness status, followed by a short evidence-based rationale. Do not calculate a numerical fit score.

## Verification before application

List only actionable external or personal facts that remain to be checked.

## Registry and Filter pointer

When a report is written, maintain the registry row:

| Job | Family | Filter status | Priority | Readiness | Report | Match status | Matched at | Refresh trigger |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

Add this narrow pointer to the relevant Filter note's frontmatter, preserving all existing fields:

```yaml
matcher:
  status: current
  report: "[[../../5.岗位匹配/<job-family>/<report-name>]]"
  last_matched: YYYY-MM-DD
  ontology_version: v0.1
  profile_last_refreshed: YYYY-MM-DD
  priority: SUITABLE
```

If a source snapshot changes, set `matcher.status: stale` and update the registry. Do not refresh the substantive report automatically.

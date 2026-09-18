# Job-family capability assessment schema

```yaml
---
type: job-family-capability-assessment
status: current                    # current | stale
job_family: <Class name>
class_profile: "[[...]]"
retrieval_lens: "[[...]]"
job_fit_reports: [<report paths>]
raw_jd_notes: [<Raw note paths>]
ontology_version: v0.1
profile_last_refreshed: YYYY-MM-DD
assessed_at: YYYY-MM-DD
sample_size: 0
sample_note: "Current matched JD sample; provisional where small."
---
```

# Job family overview

State the Class definition, core workflow, sample size, source snapshots, and whether the sample is provisional.

## Current position

Briefly summarize the demonstrated analytical base and the main transition required. This is not a score or a job-fit verdict.

## Directly demonstrated capabilities

| Capability / sub-behavior | JD requirement and Raw locator | Evidence | Demonstrated behavior | Context boundary |
| --- | --- | --- | --- | --- |

## Transferable capabilities

For each item include the JD requirement and Raw locator, Evidence IDs, source behavior, target behavior, transfer basis, and transfer boundary.

## Learnable gaps and evidence-building order

| Priority | Gap | JD occurrences | Workflow role | Adjacent evidence | Why this priority | Bounded artifact → intended new Evidence Unit |
| --- | --- | --- | --- | --- | --- | --- |

Use exact `required/preferred` counts, such as `required in 3/5 current matched JDs`; do not replace them with percentages.

## Structural / temporarily non-crossable gaps

| Gap | JD requirement and Raw locator | Current related evidence | Why structural | Current stance / long-term route |
| --- | --- | --- | --- | --- |

## Unverified requirements

| Requirement | JD occurrence | Existing clue | Missing fact / source needed |
| --- | --- | --- | --- |

## Summary

| Capability area | Status | Evidence | Priority or stance |
| --- | --- | --- | --- |

## Refresh conditions

List the Class, JD report, Ontology, Profile, or Evidence changes that make this assessment stale. Do not rewrite upstream notes.

# Personal Evidence Library Schema v0.1

This schema stores facts at a reusable grain. Empty fields mean the source does not establish the fact; do not fill them with assumptions.

```yaml
---
type: evidence-unit
evidence_id: THESIS_E06
project_or_experience: Master's thesis
source_refs:
  - path: /absolute/path/to/source.pdf
    locator: "Chapter 4, Table 4.3"
source_type: report                    # file | obsidian_note | user_statement | voice_transcript
source_quality: primary_artifact       # user_statement | primary_artifact | assessed_record | external_review
verification_status: source-linked     # source-linked | user-confirmed | externally-reviewed | needs-clarification
ontology_version: v0.1
---

# Context and problem

context:
problem:
objective:

# Data and work performed

data_source:
data_type:
sample_or_scope:
workflow_stages: []                    # e.g. data_cleaning, statistical_modeling, validation
task:
action:
methods: []
tools: []
validation_or_rigor: []

# Observable outputs; distinguish findings from claimed impact

outputs: []
findings: []
decision_relevance:

# Ontology labels apply only to evidenced behavior
capabilities: []
supported_claims: []
unsupported_claims: []

# Strength is multidimensional, not a star score
independence:                           # observed | course_guided | partly_independent | independent | led_designed
complexity:                             # basic | intermediate | advanced
evidence_available: []                 # code | dataset | table | report | grade | supervisor_review | external_outcome

# Preserve uncertainty rather than resolving it by guesswork
open_questions: []
```

## Source-quality meanings

- `user_statement`: a direct account supplied or confirmed by the user. It is not inferior, but cannot substantiate claims that require an external record.
- `primary_artifact`: original report, project file, code, notebook, presentation, work product, or official material that directly shows the activity.
- `assessed_record`: transcript, grade record, supervisor feedback, or other formal assessment.
- `external_review`: a published, client-accepted, employer-verified, or otherwise independent outcome.

## ID convention

Use an uppercase project prefix and a two-digit sequence: `THESIS_E01`, `SPARCS_E04`, `INTERNSHIP_E02`, `VOLUNTEER_E01`. IDs are immutable once referenced elsewhere.

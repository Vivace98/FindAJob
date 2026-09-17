---
name: market-capability-ontology
description: Maintain an evidence-grounded Capability Ontology and job-family Retrieval Lenses from filtered and clustered job postings in an Obsidian vault. Use after job clustering to evolve market capability language; do not extract personal evidence, assess a candidate, or generate CV content.
---

# Market Capability Ontology

Build a stable vocabulary for observing personal evidence from the target job market. The ontology represents repeated market patterns, not a list of the candidate's abilities and not an exhaustive map of all jobs in China.

## Inputs and boundaries

Read `1.岗位/Classes/` and follow links back to `1.岗位/Filter/` and `1.岗位/Raw/` when checking JD evidence. Treat Raw job notes as the source of JD facts. Use only `ELIGIBLE` and `TO_VERIFY` jobs already included in the clustering input.

Do not alter Raw, Filter, or Classes notes. Do not infer personal capabilities, create Evidence Units, rank a candidate, write CV bullets, or treat the number of current sample postings as a market-share estimate.

Read [ontology governance](https://github.com/Vivace98/FindAJob/blob/main/ontology/ontology-governance.md) before creating or revising ontology notes.

## Outputs

Write under `1.岗位/Ontology/`:

- `_Capability_Ontology_v<version>.md`: the hierarchy, definitions, aliases, boundaries, and JD evidence links.
- `Capabilities/<capability_id>.md`: optional notes for capabilities that need definitions, confusing near-neighbours, or multiple supporting sources.
- `Retrieval_Lenses/<job-family>.md`: a ranked, explainable retrieval rule for each current career class.
- `_Ontology_Changelog.md`: version, date, input scope, changed items, reason, and evidence.

Use lowercase snake_case IDs. Keep methods, tools, domain knowledge, workflow stages, and capabilities distinct. A method such as `survey_weighted_logistic_regression` can evidence a behavior but is not automatically a capability.

## Ontology update rule

Prefer existing labels and aliases. Add or split a capability only when the existing ontology cannot accurately express a repeated, materially distinct JD demand or a cross-job pattern. A single unusual JD requirement normally belongs in a job-family extension, not the core ontology.

Each capability needs a plain-language definition, inclusion/exclusion boundary, and at least one linked JD source. When evidence is thin, mark the concept `provisional` rather than presenting it as stable. Version the ontology only for a meaningful structural change; otherwise update evidence links or the changelog without renaming the model.

## Retrieval Lenses

Each lens converts one job family into a selection rule; it never edits Personal Evidence Library facts. It must include:

- job family and linked cluster profile;
- Priority 1, Priority 2, and lower-priority capabilities;
- critical workflow stages, tools, and domain constraints distinguished from capability labels;
- likely evidence forms to seek;
- explicit exclusions or claim boundaries; and
- the current input size and any tentative classification caveat.

The lens may say that `model_diagnostics` is highly relevant to a job family. It must not say that the user possesses it.

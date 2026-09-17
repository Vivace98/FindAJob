---
name: personal-evidence-extract
description: Extract verifiable, reusable Evidence Units from a person's project files, transcripts, academic records, work reports, volunteer work, or self-described experience into an Obsidian Personal Evidence Library. Use when building or expanding a personal evidence library; do not use to tailor a CV or match a job description.
---

# Personal Evidence Extract

Turn personal materials into atomic, traceable facts that can later support capability claims. The library is a fact layer, not a CV and not a claim that the person meets a job requirement.

## Scope and inputs

Accept source material supplied as file paths, pasted text, a user-written Obsidian note, a spoken account/transcript, or a direct typed account in chat. Examples include theses, project code and reports, transcripts, degree records, internships, paid freelance work, volunteering, social practice, and online part-time work.

Use only facts supported by the supplied source. Do not infer business impact, seniority, tool proficiency, decision ownership, or an outcome from a project title or a target job requirement.

Read [the evidence schema](https://github.com/Vivace98/FindAJob/blob/main/personal-evidence/references/evidence-schema.md) before writing or revising Evidence Units.

## Source provenance

Every Evidence Unit must link to one or more source records and state the source type.

- For a file, preserve its absolute path and a precise internal locator when possible: page, heading, table, figure, sheet, slide, repository path, or code function.
- For an existing Obsidian note, link the note and its heading or block.
- For a direct typed or spoken account, first create a dated source note under `2.个人材料/口述与手动记录/`. Preserve the user’s wording in a `原始陈述` section; label it `user_statement` or `voice_transcript`. Do not present it as independently verified.
- A user-confirmed statement is valid personal evidence, but `source_quality` must distinguish it from a report, code, grades, or external review.

If an assertion is ambiguous, retain it as an uncertainty or ask a focused question. Do not manufacture missing dates, sample sizes, tools, results, or responsibility level.

## Extraction and storage

Default vault locations, unless the user names a different location:

- source materials / intake records: `2.个人材料/<project-or-experience>/`
- Evidence Units: `3.个人证据库/<project-or-experience>/`

Create one Evidence Unit for one independently describable contribution or analytical action. A project normally produces multiple units; do not create one unit per project or one unit for every trivial command. Use stable IDs such as `THESIS_E06` or `VOLUNTEER_E02`. Never overwrite an existing unit with a different fact.

Record facts in their original context first. Then attach controlled capability tags only when the current ontology can accurately name the demonstrated behavior. Methods and tools are supporting fields, never substitutes for capabilities. A skill may update neither the ontology nor Retrieval Lenses.

Use `supported_claims` and `unsupported_claims` to set truthful transfer boundaries. Do not create CV bullets, commercial metaphors, or job-family rankings.

## Completion checks

Before finishing, check that every new unit has: an ID, project/experience context, at least one source reference, a source type, a specific contribution or action, and a verification status. Report uncertainties and source gaps separately from demonstrated evidence.

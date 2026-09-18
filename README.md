# FindAJob

> An evidence-first, human-in-the-loop job-search research system.

`FindAJob` is not an auto-apply bot and does not treat a CV as a bag of keywords. It is a structured workflow for answering four questions honestly:

1. What does the target job market actually ask for?
2. What can I already demonstrate with source-backed evidence?
3. For a specific role, which capabilities are direct, transferable, learnable, structural, or still unverified?
4. What should I build or learn next, and why?

The system is designed around an Obsidian vault, reusable skills, and source-linked records. Human review remains required at every consequential decision.

## Core principles

- **Evidence before claims.** A capability is not asserted merely because a course, keyword, or tool appears somewhere in a CV.
- **Market language and personal facts are separate.** Job descriptions define the market's capability language; personal materials supply the evidence.
- **No silent inference.** Missing information stays `UNVERIFIED`; a transferable capability is not treated as direct experience.
- **No automatic application.** The repository supports research and prioritisation, not automatic CV submission or job application.
- **Traceability.** Job requirements should link back to archived raw JDs; capability claims should link back to a source document, artefact, or clearly marked user statement.

## System map

```text
MARKET
Raw JDs
  → eligibility filter
  → job-family clustering
  → capability ontology + retrieval lenses

PERSON
Source materials
  → personal evidence extraction
  → evidence library
  → personal capability profile

MATCHING
Selected filtered JD + profile + evidence library
  → Job Fit Report
  → job-family capability assessment
  → learning / evidence-building priorities
```

## Repository structure

| Directory | What it contains |
| --- | --- |
| [`job-collection/`](job-collection/) | Rules and note format for collecting and archiving job postings as Raw JD records. |
| [`job-filter/`](job-filter/) | Eligibility screening: work shape, hard requirements, and career-development value. |
| [`career-classification/`](career-classification/) | Clusters filtered JDs into preparation-oriented job families. |
| [`ontology/`](ontology/) | Maintains the market Capability Ontology and job-family Retrieval Lenses. |
| [`personal-evidence/`](personal-evidence/) | Extracts reusable, bounded Evidence Units from projects, education, work, and self-described experience; builds the Capability Profile. |
| [`matcher/`](matcher/) | Matches one user-selected JD to current evidence and produces a bounded Job Fit Report. |
| [`assessment/`](assessment/) | Aggregates Job Fit Reports within a job family into learnable gaps, structural boundaries, and evidence-building priorities. |

## Workflow

### 1. Build the market side

1. Archive a job posting as a Raw JD.
2. Screen it for eligibility and practical value.
3. Cluster eligible JDs into job families.
4. Update the Capability Ontology only when repeated market evidence cannot be expressed well by the current vocabulary.
5. Maintain one Retrieval Lens per job family to define how evidence should be retrieved and ranked later.

### 2. Build the personal evidence side

1. Provide a primary source: thesis, project report, transcript, certificate, internship material, portfolio artefact, or a clearly marked self-description.
2. Extract atomic Evidence Units with source locators, actions, methods, tools, outputs, results, and claim boundaries.
3. Map an Evidence Unit to the market ontology only when the evidence supports that label.
4. Refresh the Personal Capability Profile after material changes to evidence or ontology.

### 3. Make a job-specific decision

For a selected filtered job only, create a Job Fit Report. Each requirement is classified as one of:

| Classification | Meaning |
| --- | --- |
| `DIRECT` | Explicitly demonstrated in an appropriate context. |
| `TRANSFERABLE` | A supported adjacent capability; the source and target contexts remain distinct. |
| `LEARNABLE_GAP` | A specific skill, tool, or workflow that can plausibly be built with scoped learning and a new artefact. |
| `STRUCTURAL_GAP` | Experience tenure, regulated practice, domain ownership, or other boundary not honestly closed by a short course. |
| `UNVERIFIED` | The current library does not establish it; this is neither a positive nor a negative claim. |

Then aggregate current Job Fit Reports for a chosen job family. This identifies which learnable gaps recur, what evidence would have the highest leverage, and which routes should be treated as longer-term rather than immediate targets.

## What this repository does not do

- It does not fabricate experience, tools, results, or years of experience.
- It does not equate academic analysis with production, commercial, clinical, or regulated ownership.
- It does not automatically match every JD or revise an existing match without a user-triggered refresh.
- It does not make application decisions on the user's behalf.
- It does not yet generate a targeted CV or cover letter. A future CV assembly layer should consume Job Fit Reports and enforce the same evidence boundaries.

## Status

The current repository contains the research and matching layers. The next intended layer is a truthfulness-checked CV assembly workflow, to be added only after the evidence library and matching records are sufficiently mature.

## License and reuse

This repository currently documents a personal workflow. Before reuse or redistribution, add an explicit license and remove or anonymise personal documents, job-posting archives, private links, and identifiable evidence.

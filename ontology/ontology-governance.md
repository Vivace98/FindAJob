# Ontology governance

## Minimum capability record

```yaml
---
type: market-capability
capability_id: model_diagnostics
family: validation_and_rigor
status: provisional                    # provisional | stable | deprecated
ontology_version: v0.1
aliases: [模型诊断, 假设检验与诊断]
jd_evidence:
  - "[[../Classes/.../job-note|JD note]] — responsibility/requirement locator"
---

definition: Assess whether an analytical model is adequate for its intended use and identify material limitations.
includes:
  - assumption checking
  - residual or performance assessment
excludes:
  - generic data cleaning
  - deploying a model to production
```

## Versioning

- Patch evidence only: add source links or clarifications; preserve the version.
- Minor version: add a capability, alias, lens, or documented boundary.
- Major version: alter the hierarchy or redefine a broad capability family.

Never delete an existing ID that has been used by Personal Evidence Library notes. Mark it `deprecated`, point to a successor, and preserve its history.

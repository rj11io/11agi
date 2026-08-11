---
name: 11agi-core-reporting-best-practices
description: "Reference general best practices for evidence-backed reporting, including data collection, coverage, provenance, flexible schemas, structure, metrics, uncertainty, privacy, artifact strategy, and verification. Use when Codex needs advisory guidance, tradeoff analysis, or a read-only review of how a report should be designed. This skill is advisory and does not create, edit, render, manage, or enforce report artifacts."
---

# 11agi Core Reporting Best Practices

Consult these practices when designing or reviewing a report. Treat them as
context-sensitive advice, not as rules or a completion gate.

## Advisory boundary

- Explain useful defaults, tradeoffs, alternatives, and anti-patterns.
- Review a proposed or existing approach read-only when asked.
- Prefer language such as `prefer`, `consider`, `usually`, and `when useful`.
- Do not create, edit, render, validate, or manage report artifacts.
- Do not declare a report invalid merely because it departs from a practice.
- Do not impose one schema, section order, artifact package, or report format.
- Defer report operations to
  [`11agi-core-reports-manager`](../11agi-core-reports-manager/SKILL.md).
- Defer tables and other visual encodings to
  [`11agi-core-datavis-best-practices`](../11agi-core-datavis-best-practices/SKILL.md).
- Defer house presentation mechanics to
  [`11agi-core-reports-styleguide`](../11agi-core-reports-styleguide/SKILL.md).

## Reference map

Read each relevant reference completely before advising:

- [references/data-and-evidence.md](references/data-and-evidence.md): scope,
  maximal relevant collection, provenance, coverage, privacy, and evidence
  states.
- [references/structure-and-metrics.md](references/structure-and-metrics.md):
  flexible schemas, report structure, metrics, uncertainty, formats, and
  cross-format parity.
- [references/verification-practices.md](references/verification-practices.md):
  factual, numerical, structural, privacy, artifact, and regression checks.

## Core position

- Prefer collecting and preserving as many relevant, available, authorized,
  and practical datapoints as possible.
- Preserve granular evidence before aggregating it. Presentation constraints
  are not a reason to discard collected dimensions.
- Expand schemas and report structures around each report's subject, evidence,
  audience, and analytical needs.
- Distinguish observed, source-reported, calculated, estimated, inferred, and
  unavailable information.
- Keep claims traceable to sources and disclose assumptions, exclusions,
  conflicts, freshness, coverage, and limitations.
- Prefer the smallest artifact set that serves the user. A formal multi-format
  package is useful, not universally necessary.
- Let explicit user requirements, existing artifact contracts, and applicable
  domain requirements take precedence over these practices.

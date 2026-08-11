---
name: 11agi-core-reports-manager
description: "Create, generate, update, extend, rerender, and verify evidence-backed report artifacts across technical, operational, audit, research, and analytical topics. Use when Codex must produce or modify Markdown, self-contained HTML, machine-readable, or multi-format reports; collect and model report data; preserve an existing report while extending it; or validate report artifacts. Consults the reporting best practices, datavis best practices, and reports styleguide while keeping schemas and structures specific to each report."
---

# 11agi Core Reports Manager

Own the report artifact lifecycle. Create or modify report files only when the
user requests report work; keep consulted source evidence read-only unless the
user separately authorizes changes.

## Required consultations

Before creating, updating, or rerendering a report:

1. Read
   [`11agi-core-reporting-best-practices`](../11agi-core-reporting-best-practices/SKILL.md)
   and every reference relevant to the task.
2. When the report contains tables, charts, diagrams, maps, scorecards, or
   other repeated-field displays, read
   [`11agi-core-datavis-best-practices`](../11agi-core-datavis-best-practices/SKILL.md)
   and its relevant references.
3. When producing or changing the house Markdown or self-contained HTML report
   presentation, read
   [`11agi-core-reports-styleguide`](../11agi-core-reports-styleguide/SKILL.md)
   and the references it routes for the requested output.
4. Do not consult or apply optional report-format skills unless the user
   explicitly selects that format. When the user explicitly requests collapsed,
   collapsible, disclosure, or accordion report sections, read
   [`11agi-core-reports-collapsed-format`](../11agi-core-reports-collapsed-format/SKILL.md).

Apply this precedence:

1. Explicit user requirements
2. Existing artifact and domain contracts
3. Requested output-format requirements
4. House report styleguide
5. Reporting and datavis best practices

Treat best practices as advisory defaults. Adapt or depart from them when the
report's evidence, audience, domain, or user requirements justify it.

## Workflow

### 1. Frame the report

- Establish the objective, audience, scope, reporting period, timezone,
  evidence boundary, requested formats, destination, and privacy constraints.
- Inspect an existing report and its generator before updating it.
- Preserve useful content, provenance, structure, and attribution unless a
  deliberate change improves the requested result.
- Ask only when an unresolved choice would materially change the report.

### 2. Collect evidence

- Collect and preserve as many relevant, available, authorized, and practical
  datapoints as possible.
- Capture useful dimensions before aggregation. Do not omit a field because it
  complicates a table, schema, or presentation.
- Keep source evidence read-only and record provenance, dates, methods, units,
  confidence, coverage, exclusions, conflicts, and unavailable inputs.
- Distinguish observed, source-reported, calculated, estimated, inferred, and
  unavailable information.
- Never invent a value or reinterpret missing evidence as zero.

### 3. Model the report

- Design and expand the schema around this report's subject and analytical
  needs. Do not force it into a universal report schema.
- Preserve granular evidence separately from normalized and derived values.
- Keep values typed and attach units, provenance, methods, confidence, and
  coverage where needed.
- Add a versioned machine-readable dataset when validation, recomputation,
  comparison, or rerendering benefits from it. Skip it when it adds no value.

### 4. Structure the narrative

- Lead with the result that changes the reader's next action.
- Follow with evidence, comparisons, uncertainty, and limitations.
- Choose sections for the report rather than copying a universal sequence.
- Include methodology sufficient to reproduce material calculations.
- Include recommendations only when requested or clearly part of the report's
  purpose.
- Omit empty sections.

### 5. Render or update artifacts

- Respect the requested formats and produce the smallest useful artifact set.
- Prefer Markdown for a portable readable report, self-contained HTML for rich
  navigation or interaction, and structured data for recomputation or
  rerendering.
- Render multiple presentation formats from one evidence model when practical.
- Keep facts, values, ordering, limitations, and provenance aligned across
  formats. Let HTML add interaction, not exclusive information.
- Prefer timestamped, immutable packages for recurring or auditable reports.
- Do not silently overwrite an existing report. Require an explicit output or
  replacement request.

### 6. Verify

- Trace material claims to evidence and independently recompute derived values.
- Check units, denominators, periods, timezone boundaries, rounding, nulls,
  totals, coverage, citations, and privacy.
- Confirm every requested artifact exists, opens, and agrees with its siblings.
- Rerender saved data when promised and confirm scope, provenance, limitations,
  and analytical meaning survive.
- Render HTML in a real browser and exercise relevant presentation interactions.
- Compare old and new artifacts for generator changes; explain every intentional
  content difference.

### 7. Hand off

- Link the exact artifact paths.
- State the main result, important limitations, evidence gaps, and validation
  performed.
- Name the sections, tables, rows, or visible states the operator should inspect.
- Provide a detailed conventional commit message when repository files changed.

## Ownership boundary

- Own report creation, updates, rerendering, packaging, and verification.
- Do not turn advisory best practices into universal validity rules.
- Do not move domain-specific schemas, formulas, thresholds, or policies into
  this skill; keep them with the report generator or domain skill that owns
  them.
- Do not duplicate styleguide CSS, fonts, templates, or interaction code.
- Do not infer an optional format from report length, density, section count,
  HTML output, or an available format skill.
- Do not execute recommendations or mutate external systems unless the user
  separately requests and authorizes that work.

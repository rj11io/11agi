---
name: 11agi-core-datavis-best-practices
description: "Reference general data-visualization best practices for clear, accurate, accessible tables and visual encodings. Use when Codex needs advisory guidance, tradeoff analysis, or a read-only review of how data should be selected, compared, formatted, or presented in a report or interface. The current bundled reference focuses on tables. This skill is advisory and does not create visualizations, manage reports, enforce a library, or own house styling."
---

# 11agi Core Datavis Best Practices

Consult these practices when choosing or reviewing a data presentation. Treat
them as context-sensitive advice, not as rules or a completion gate.

## Advisory boundary

- Explain useful defaults, tradeoffs, alternatives, and misleading patterns.
- Review a proposed or existing visualization read-only when asked.
- Do not create or edit visualizations or report artifacts.
- Do not require a visualization when prose or a compact table is clearer.
- Do not enforce one charting library, schema, or interaction model.
- Do not own report structure, evidence collection, CSS, fonts, themes, or
  rendering code.
- Defer report operations to
  [`11agi-core-reports-manager`](../11agi-core-reports-manager/SKILL.md).
- Defer visual presentation mechanics to
  [`11agi-core-reports-styleguide`](../11agi-core-reports-styleguide/SKILL.md)
  for house reports.

## General practices

- Use a visualization only when it makes a material relationship easier to
  understand than prose.
- Match the encoding to the analytical question: lookup, comparison, change,
  distribution, relationship, composition, geography, flow, or hierarchy.
- Preserve semantic fidelity. Do not distort baselines, scales, areas,
  ordering, aggregation, or uncertainty to make a result look stronger.
- Collect and preserve broad relevant data before deciding what a summary view
  should display.
- Show units, scope, period, source, coverage, and uncertainty when they affect
  interpretation.
- Prefer accessible labels and direct explanation over color-only meaning.
- Keep visual complexity proportional to the reader's task.

## Table guidance

Read [references/tables.md](references/tables.md) completely for any request
that involves tables, matrices, scorecards, rankings, or repeated-field
comparisons.

Keep the current reference set focused on tables. Add chart, diagram, map,
dashboard, color, and interaction references later as stable practices are
defined. Keep every future reference directly linked from this file.

---
name: 11agi-core-reports-styleguide
description: "Apply the house presentation contract for generated, self-contained HTML reports: canonical design tokens, embedded fonts, dark default with a light toggle, collapsed disclosures, and deterministic table interactions that reset on reload. Ships copyable CSS, a working HTML template, an interaction contract, and a regression checklist. Use when building, styling, restyling, or reviewing house Markdown and HTML reports. Owns presentation mechanics, not report semantics, data collection, schema design, or visualization choice."
---

# 11agi Core Reports Styleguide

The house presentation contract for generated reports. Reports are immutable
artifacts: styled once at generation, self-contained forever, identical on
every open.

## Ownership boundary

- Own report tokens, typography, layout, disclosures, table presentation
  mechanics, interaction behavior, and presentation verification.
- Do not decide which evidence, metrics, fields, totals, or visual encodings a
  report should contain.
- Consult
  [`11agi-core-datavis-best-practices`](../11agi-core-datavis-best-practices/SKILL.md)
  for table semantics and other data-presentation choices.
- Consult
  [`11agi-core-reporting-best-practices`](../11agi-core-reporting-best-practices/SKILL.md)
  for report evidence, structure, metrics, uncertainty, and artifact strategy.
- Let
  [`11agi-core-reports-manager`](../11agi-core-reports-manager/SKILL.md)
  compose those concerns when creating or updating report artifacts.

Copy from the bundled references instead of reimplementing:

- [references/tokens.css](references/tokens.css): the design tokens and base rules.
- [references/fonts.css](references/fonts.css): embedded font faces, ready to inline.
- [references/report-template.html](references/report-template.html): a complete
  working page demonstrating every directive; open it in a browser.
- [references/interaction-contract.md](references/interaction-contract.md): the
  table behavior spec and the failure modes it prevents.
- [references/verification-checklist.md](references/verification-checklist.md):
  the regression gate to run before shipping any report change.

## Directives

Self-containment:

- One HTML file, zero network requests. Styles inline, fonts as data URIs.
- Everything deterministic: identical input yields byte-identical output
  except the generation-timestamp line.

Tokens and theme:

- Use the tokens in tokens.css; never hardcode a color beside them.
- Square corners everywhere. Straight lines and hairline `--border` rules; no
  `border-radius`, no shadows.
- Dark by default: `class="dark"` on the root element, an icon toggle in a
  flex header row opposite the title switches modes, `color-scheme` declared
  per mode.

Typography:

- Inter for text, Geist Mono for code and identifiers, both embedded per
  fonts.css with full system stacks behind them for other platforms and
  glyph ranges.
- Body 14px/1.45. Tables .82rem. Title `clamp(1.3rem, 2.3vw, 1.8rem)` with
  tight tracking. Headings weight 750, table headers 700.
- `font-variant-numeric: tabular-nums` on every data cell so digits align.

Structure:

- Every report section is a native `<details>` disclosure, collapsed by
  default; the title, generation message, and signature stay outside.
- Tables live inside a `.table-wrap` that scrolls horizontally; the page body
  never scrolls sideways.

Table presentation and interaction:

- Apply the selected table schema and semantic formatting without removing
  fields for layout convenience.
- Sorting, row highlighting, and column resizing follow
  [references/interaction-contract.md](references/interaction-contract.md)
  exactly, including the node-identity rule for sorting and the two fixed
  failure modes for resizing.
- Interactive state never persists: no storage of theme, highlights, or
  widths; a reload always yields the pristine dark report.

Markdown sibling:

- When a markdown report accompanies the HTML, both render from the same data
  with the same section order, table columns, and values; the HTML adds
  interaction, never information.

## Verification

Run [references/verification-checklist.md](references/verification-checklist.md)
before shipping any change: structural comparison against the previous
generation, a determinism double-render, and the functional browser pass.

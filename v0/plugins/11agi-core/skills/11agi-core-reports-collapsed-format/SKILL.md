---
name: 11agi-core-reports-collapsed-format
description: "Apply an opt-in collapsed-section presentation to self-contained HTML reports using native details and summary disclosures. Use only when the user explicitly invokes this skill or explicitly requests collapsed, collapsible, disclosure, or accordion report sections. Do not use merely because a report is long, dense, interactive, or divided into sections."
---

# 11agi Core Reports Collapsed Format

Layer collapsed disclosure sections onto an HTML report only after the user
selects this format. Keep report semantics, evidence, tables, and house styling
owned by their existing skills.

## Activation boundary

- Require an explicit user request for collapsed, collapsible, disclosure, or
  accordion report sections.
- Do not infer this format from report length, density, section count, HTML
  output, or the availability of native disclosure controls.
- When creating or updating the full report, consult
  [`11agi-core-reports-manager`](../11agi-core-reports-manager/SKILL.md).
- When applying the house presentation, consult
  [`11agi-core-reports-styleguide`](../11agi-core-reports-styleguide/SKILL.md)
  and layer this format on top without duplicating its tokens, fonts, theme, or
  table interactions.

## Format contract

- Render each user-selected collapsible section as a native `<details>` element
  with a direct `<summary>` child.
- Omit the `open` attribute so selected sections load collapsed.
- Keep the report title, generation message, and signature outside disclosures.
- Preserve the report's heading hierarchy with `level-*` classes rather than
  changing its semantic structure or section order.
- Put the section content in `.section-body` and use the rules from
  [references/collapsed-format.css](references/collapsed-format.css).
- Keep summary labels short, descriptive, and unique within their parent.
- Do not put links, buttons, form controls, or other interactive elements inside
  a summary.
- Use native disclosure behavior. Do not replace it with custom JavaScript.

Use this shape:

```html
<details class="report-section level-2">
  <summary><span class="section-title">Section title</span></summary>
  <div class="section-body">
    <!-- section content -->
  </div>
</details>
```

## Verification

- Confirm only the requested sections use the collapsed format.
- Confirm every disclosure has one direct summary and valid closing markup.
- Confirm selected disclosures omit `open` and load collapsed.
- Confirm keyboard and pointer activation work without JavaScript.
- Confirm visible labels still communicate the hidden content's purpose.
- Confirm removing the disclosure wrappers would not change report facts,
  values, ordering, provenance, or limitations.

# Report verification practices

Select checks in proportion to the report's risk, complexity, and reuse.

## Evidence and calculation

- Trace every material claim to supporting evidence.
- Recompute derived metrics independently from their source values.
- Check units, denominators, periods, timezone boundaries, signs, rounding, and
  null handling.
- Confirm that missing values were not converted to zero.
- Confirm totals include only additive, non-overlapping values.
- Review conflicts, exclusions, assumptions, and material coverage gaps.

## Structure and presentation

- Confirm the title, objective, audience, scope, and reporting period agree.
- Confirm headings, tables, labels, units, citations, and recommendations match
  the underlying evidence.
- Confirm unfamiliar acronyms are expanded, glossary definitions match actual
  usage, and terminology stays consistent across the report.
- Confirm summaries do not overstate detailed findings.
- Confirm limitations remain visible and specific.
- Check that every requested artifact exists and opens successfully.
- For HTML, inspect the rendered artifact and exercise relevant interactions.

## Cross-format and rerendering

- Compare facts, section order, table values, terminology, limitations, and
  provenance across formats.
- Rerender saved data without rescanning when the workflow promises it.
- Confirm rerendering preserves scope, sources, scan limitations, and the data's
  original analytical meaning.
- Render identical data twice when deterministic output matters. Normalize only
  explicitly variable metadata such as the generation timestamp.

## Privacy and handoff

- Search outputs for secrets, credentials, raw private content, and unintended
  absolute paths.
- Report what was verified, what could not be verified, and the residual risk.
- Link exact artifact paths and name the sections or rows that deserve operator
  attention.

## Generator changes

- Compare old and new reports from equivalent inputs.
- Preserve machine-readable data and Markdown for presentation-only changes.
- Compare extracted headings and table cells when HTML chrome changes.
- Name and explain every intentional content difference.
- Combine automated checks with direct artifact inspection.

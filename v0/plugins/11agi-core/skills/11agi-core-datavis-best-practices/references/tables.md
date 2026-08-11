# Table best practices

## Choose a table deliberately

- Use a table for exact lookup, repeated-field comparison, dense multi-metric
  evidence, or data that readers may sort and inspect row by row.
- Prefer prose for a handful of facts and a chart for a pattern that exact cells
  obscure.
- Keep the full evidence table available when a smaller summary serves the
  opening narrative.

## Preserve datapoints

- Collect and preserve as many relevant, available, authorized, and practical
  fields as possible before designing the view.
- Do not drop a useful field only because the table becomes wide.
- Separate collection completeness from display priority. Put secondary fields
  later, in a detail table, or in a separate detail view instead of losing them.
- Include source, method, confidence, coverage, or status columns when those
  qualifiers differ by row.

## Order columns consistently

A useful default order is:

1. Row identity and grouping fields
2. Primary outcome or decision metric
3. Supporting inputs and component values
4. Units, rates, ratios, or normalized metrics
5. Counts and coverage
6. Time, provenance, confidence, status, and notes

Keep the same order across comparable tables. Put units in headers when one
unit applies to the whole column.

## Represent values honestly

- Render unavailable data as `n/a`, `unknown`, or a precise status, never zero.
- Reserve zero for an observed or calculated zero.
- Distinguish not applicable from not measured.
- Use precision supported by the evidence and consistent within a column.
- Align numbers by decimal place and use tabular figures where available.
- Keep raw values available when displayed values are rounded.
- State denominators for percentages and ratios when they are not obvious.

## Aggregate only valid data

- Include a `Total` row only for additive, non-overlapping values.
- Do not total percentages, ratios, averages, percentiles, ranks, or overlapping
  groups.
- Use weighted calculations when the metric requires them and disclose the
  weight.
- Show coverage beside aggregates when missing rows can bias the result.
- Label subtotals and grand totals distinctly.

## Support comparison

- Use stable row and column ordering before interaction.
- Choose a meaningful default sort, then preserve deterministic ties.
- Keep totals and unavailable values outside the ordinary sort order when that
  improves interpretation.
- Avoid mixing incompatible populations, periods, units, or methods in one
  comparison without explicit qualification.
- Use deltas only when the baseline and direction are clear.

## Handle width and density

- Prefer a compact full-width table over dropping useful columns.
- Keep identity columns understandable when readers scroll horizontally.
- Use wrapping for explanatory text and controlled truncation only when the
  complete value remains accessible.
- Use grouping, nested headings, or separate detail tables when one flat table
  becomes harder to interpret than the underlying data.
- Avoid decorative cells, excessive icons, and repeated units that reduce data
  density without improving meaning.

## Preserve accessibility

- Use real table semantics with explicit header relationships.
- Provide text labels for status, direction, and meaning conveyed by color.
- Maintain sufficient contrast and visible keyboard focus.
- Make sortable headers announce their state.
- Keep interaction optional so the initial table remains understandable.
- Provide a nonvisual equivalent for meaningful icons or sparklines.

## Avoid misleading tables

- Do not hide unfavorable rows, missing coverage, or incompatible methods.
- Do not rank values whose differences are smaller than their uncertainty.
- Do not imply causation through adjacency or ordering.
- Do not use conditional color without a defined scale and neutral midpoint.
- Do not let formatting precision imply measurement precision.
- Explain material exclusions immediately beside the table.

House report styling, scrolling, sorting implementation, row highlighting, and
column resizing belong to `11agi-core-reports-styleguide`; these practices own
the table's semantic content and honest interpretation.

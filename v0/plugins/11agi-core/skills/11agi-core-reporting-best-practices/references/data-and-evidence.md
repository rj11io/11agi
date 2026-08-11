# Data and evidence practices

## Frame collection

- Define the report objective, audience, scope, reporting period, timezone,
  evidence boundary, requested outputs, and material privacy constraints.
- Prefer primary and authoritative sources. Record source identity, date, and
  retrieval context when freshness matters.
- Keep source material read-only unless the user separately authorizes edits.
- Separate evidence collection from report presentation. A concise summary may
  display fewer values while the evidence model preserves full useful detail.

## Maximize relevant coverage

- Collect and preserve as many relevant, available, authorized, and practical
  datapoints as possible.
- Capture useful dimensions before aggregation: entity, category, period,
  location, source, method, unit, status, confidence, and coverage where they
  apply.
- Do not omit a field only because it makes a table wide or a schema larger.
- Preserve raw granularity so later groupings and calculations remain possible.
- Record unavailable, unreadable, excluded, malformed, conflicting, and
  inapplicable evidence explicitly.
- Stop collecting when added data is out of scope, unauthorized, duplicative,
  disproportionately expensive, or immaterial to the report's decisions.

## Preserve provenance

- Keep every material claim traceable to one or more sources.
- Distinguish source-reported facts from independently measured values.
- Record transformations from source values to normalized values.
- Retain identifiers needed to audit a calculation without copying sensitive
  source content into the report.
- Preserve conflicting evidence. Explain the conflict and any resolution rule.
- Never silently drop evidence that weakens the report's conclusion.

## Express evidence states

Use explicit states rather than blending unlike evidence:

- `observed`: directly inspected or measured.
- `source-reported`: stated by a source but not independently measured.
- `calculated`: derived by a disclosed deterministic formula.
- `estimated`: approximated through a disclosed method.
- `inferred`: reasoned from evidence rather than directly present.
- `unavailable`: expected but not obtainable.
- `not applicable`: not meaningful for this row or scope.

Render a missing value as `n/a`, `unknown`, or another explicit state. Reserve
zero for a real measured or calculated zero.

## Report coverage

- State the intended population and the measured population.
- Show coverage counts or percentages for important metrics.
- Explain whether incomplete coverage can understate or overstate aggregates.
- Keep measured totals numeric when other data is unavailable, then state what
  those totals exclude.
- Never reinterpret unreadable or undetected evidence as zero activity.

## Protect sensitive data

- Collect only sensitive data that is necessary, authorized, and proportionate.
- Exclude secrets, credentials, authentication material, and unnecessary
  personal data from report datasets and artifacts.
- Prefer citations, identifiers, hashes, or sanitized excerpts over copying raw
  private records.
- Avoid exposing private absolute paths in externally shared reports.
- Record a sensitive-data exclusion without revealing the excluded value.

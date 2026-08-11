# Structure and metric practices

## Keep schemas flexible

- Design the schema around the report's subject, evidence, audience, and
  analytical questions.
- Expand it when new relevant dimensions, relationships, metrics, provenance,
  uncertainty, or limitations appear.
- Prefer additive expansion over forcing evidence into a smaller generic model.
- Keep values typed and store units, methods, sources, confidence, and coverage
  beside values when needed.
- Separate raw evidence, normalized values, and derived metrics.
- Version a schema when saved data must support validation, migration, or
  deterministic rerendering.
- Skip machine-readable data for a simple narrative report when it adds no
  practical value.

A useful optional envelope is:

```json
{
  "schemaVersion": 1,
  "generator": {},
  "generatedAt": "ISO-8601 timestamp",
  "title": "Report title",
  "scope": {},
  "sources": [],
  "limitations": []
}
```

Add report-specific entities, metrics, periods, relationships, findings,
recommendations, sections, or other fields only when useful.

## Structure around the reader

- Lead with the result that changes the reader's next decision.
- Follow with the strongest supporting evidence.
- Make scope, coverage, uncertainty, and limitations easy to find.
- Keep methodology reproducible without making it the opening burden.
- Include recommendations only when the request calls for them.
- Omit empty sections.
- Preserve an existing report's useful structure when updating it unless a
  deliberate change improves the result.

A common starting sequence is:

1. Title and provenance
2. Executive summary
3. Scope and coverage
4. Findings and evidence
5. Metrics, comparisons, or visualizations
6. Risks, uncertainty, and limitations
7. Recommendations when requested
8. Methodology and sources
9. Generation metadata and attribution

Adapt or replace this sequence for the report at hand.

## Explain terminology for the audience

- Prefer defining unfamiliar domain terms and acronyms on first use.
- Consider a report-specific glossary when terminology is specialized,
  ambiguous, extensive, or likely to vary across the intended audience.
- Prefer one canonical term for each concept. Include useful aliases or legacy
  terms when readers may encounter them in the evidence.
- Keep definitions consistent across narrative, tables, charts, diagrams, and
  machine-readable data.
- Prefer authoritative definitions when the report depends on a formal domain
  standard, policy, methodology, or source vocabulary.
- Omit a glossary when ordinary inline definitions are sufficient. Omit empty
  glossary sections.

## Define metrics precisely

- Define the population, numerator, denominator, unit, period, timezone, and
  calculation method for every material metric.
- Distinguish raw, normalized, calculated, estimated, and source-reported
  values.
- Use precision supported by the evidence. Avoid decorative decimal places.
- Preserve source precision internally when later calculations need it.
- State whether time windows are rolling or calendar-based.
- Use totals only for additive, non-overlapping values.
- Do not sum percentages, ratios, percentiles, averages, or overlapping groups.
- Explain when partial coverage can bias a rate or average.
- Show both the value and its coverage when coverage is material.

## Choose artifacts intentionally

- Respect the formats the user requests.
- Prefer Markdown for portable readable reports.
- Add self-contained HTML when navigation, tables, or interaction improve use.
- Add machine-readable data when validation, recomputation, comparison, or
  rerendering matters.
- Prefer timestamped immutable packages for recurring or auditable reports.
- Do not silently overwrite prior artifacts.
- Render every presentation format from the same evidence model when practical.
- Keep facts, values, ordering, limitations, and provenance aligned across
  formats. Let HTML add interaction, not exclusive information.

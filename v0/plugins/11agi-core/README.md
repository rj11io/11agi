# 11agi Core Skills

Skills for building, auditing, and packaging other skills and plugins, plus
general-purpose reporting, compression, reverse-engineering, communication,
and critique utilities.

## Choose a skill

| Skill | Use it for |
| --- | --- |
| [`11agi-core-operator-plugin-creator`](./skills/11agi-core-operator-plugin-creator/SKILL.md) | Scaffolding a new `11agi-operator-TOOL` plugin that matches the house pattern and passes validation |
| [`11agi-core-plugin-faq-manager`](./skills/11agi-core-plugin-faq-manager/SKILL.md) | Creating or updating a plugin's `11agi-*-faq` skill: a validated question router over the plugin's own contracts, references, scripts, and tests |
| [`11agi-core-compression`](./skills/11agi-core-compression/SKILL.md) | Compressing a markdown guidance file (a SKILL.md, CLAUDE.md, prompt, or runbook) locally, without an external LLM call, while preserving headings, code, links, and paths |
| [`11agi-core-reverse-engineering`](./skills/11agi-core-reverse-engineering/SKILL.md) | Reverse engineering a locally cloned repository into a sanitized markdown blueprint for rebuilding it with modern tools |
| [`11agi-pragmatic`](./skills/11agi-pragmatic/SKILL.md) | Answering in a terse, evidence-preserving register: short lines, an example per claim, a fix beside every problem, and a copyable conventional commit message after repo work |
| [`11agi-core-www-styleguides`](./skills/11agi-core-www-styleguides/SKILL.md) | Theming a Next.js and shadcn application with the house web design language: user tokens and fonts kept, missing pieces derived as balanced equivalents with contrast gates, bundled defaults otherwise |
| [`11agi-core-reports-manager`](./skills/11agi-core-reports-manager/SKILL.md) | Creating, updating, extending, rerendering, and verifying topic-specific reports while consulting the reporting, datavis, and house-style skills |
| [`11agi-core-reporting-best-practices`](./skills/11agi-core-reporting-best-practices/SKILL.md) | Consulting advisory practices for evidence, broad datapoint collection, provenance, flexible report schemas, metrics, uncertainty, privacy, artifacts, and verification |
| [`11agi-core-datavis-best-practices`](./skills/11agi-core-datavis-best-practices/SKILL.md) | Consulting advisory data-visualization practices, currently centered on complete, accurate, accessible tables |
| [`11agi-core-reports-styleguide`](./skills/11agi-core-reports-styleguide/SKILL.md) | Styling, restyling, or reviewing generated HTML reports: canonical tokens, embedded fonts, dark default, and the table interaction contract with its verification checklist |
| [`11agi-core-reports-collapsed-format`](./skills/11agi-core-reports-collapsed-format/SKILL.md) | Applying native collapsed disclosure sections only when explicitly invoked or requested by the user |
| [`11agi-roast`](./skills/11agi-roast/SKILL.md) | Giving a blunt, prioritized, read-only critique of code, documents, designs, or any other work product |

Marketplace and plugin configuration research moved to the
[`11agi-plugins-marketplace`](../11agi-plugins-marketplace/README.md) plugin.

## Communication skills

`11agi-pragmatic` and `11agi-roast` set or critique how an agent communicates.
Both follow the same three-rule contract, stated in their own vocabulary:

1. **Say what changes the reader's next action.** Cut the rest.
2. **Never cut the evidence.** Numbers, file paths, command names, exact error
   text, and stated uncertainty survive every register. Brevity is not
   vagueness.
3. **Pair every problem with a fix.** A finding with no proposed action is
   incomplete, however short the reply.

`11agi-roast` is not a register: it's a one-off critique, and it composes with
whichever register is active.

## Scope

Candidates for this plugin:

- Author a new skill from a description.
- Audit frontmatter and packaging across harnesses.
- Wire a plugin into the marketplace, catalogs, and site.
- Keep counts, manifests, and duplicated helper scripts in sync.
- Retire a skill or plugin cleanly.
- Add a communication register or a one-off critique deliverable.
- Consult general reporting or datavis practices without creating artifacts.
- Create, update, rerender, or verify an evidence-backed report package.

## The authority

`v0/scripts/validate-skills.mjs` is the source of truth for every packaging rule.
A core skill enforces what the validator already checks and closes the gaps it
does not. Read it first. Do not restate its rules from memory.

## Related

`11agi-super-skill-qa` in `11agi-super` also falls in this scope: it audits and
repairs skill packaging across harnesses. Read it before writing a new core
skill here.

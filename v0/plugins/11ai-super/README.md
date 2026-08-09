# 11agi Super

Nine long-running skills that perform a project task repeatedly, verify the result, and stop when material issues are resolved or clearly documented.

## Choose a skill

| Skill | Use it for |
| --- | --- |
| [`11agi-super-bugfixing`](./skills/11agi-super-bugfixing/SKILL.md) | Continuously finding, reproducing, fixing, and verifying software defects until no material bug remains |
| [`11agi-super-code-quality`](./skills/11agi-super-code-quality/SKILL.md) | Repeatedly improving clarity, structure, naming, comments, and test coverage until the code reaches a high bar, without changing behavior |
| [`11agi-super-metadata`](./skills/11agi-super-metadata/SKILL.md) | Auditing and fixing project metadata, technical SEO, structured data, and social preview images |
| [`11agi-super-performance`](./skills/11agi-super-performance/SKILL.md) | Measuring, fixing, and repeatedly optimizing project speed and resource efficiency |
| [`11agi-super-readme`](./skills/11agi-super-readme/SKILL.md) | Auditing a repository's README files and repeatedly improving them until they match the code to a high bar |
| [`11agi-super-security`](./skills/11agi-super-security/SKILL.md) | Auditing, fixing, and repeatedly hardening a project's security |
| [`11agi-super-skill-qa`](./skills/11agi-super-skill-qa/SKILL.md) | Auditing and repairing skill formatting, harness metadata, plugin discovery, packaging, catalogs, creator templates, and validation guardrails |
| [`11agi-super-ux`](./skills/11agi-super-ux/SKILL.md) | Auditing and improving usability, accessibility, responsiveness, visual consistency, and interface polish |
| [`11agi-super-visual-a11y`](./skills/11agi-super-visual-a11y/SKILL.md) | Measuring and fixing contrast, focus visibility, target size, text scaling, and motion so light and dark themes clear the same thresholds |

## Shared workflow

Run these skills from the repository you want to improve. Each one uses repeated implementation, audit, and verification passes instead of stopping after the first fix, keeps a manifest of every file it changes, and stops with a full report when the change set becomes unmanageable or troubleshooting outweighs progress.

The skills preserve unrelated work. `11agi-super-bugfixing` applies the shared workflow to evidence-backed software defects, `11agi-super-code-quality` applies it to the maintainability of the code it touches and keeps behavior unchanged, `11agi-super-skill-qa` repairs skill packaging without rewriting skill routines, `11agi-super-readme` is documentation-only, and the other specialist super skills update the project areas named in their playbooks.

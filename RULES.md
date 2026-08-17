# 11agi Rules

single source of truth for every rule 11agi skills and plugins must follow. when this file and any script, skill, or README disagree, this file wins. the validator (`v0/scripts/validate-skills.mjs`) implements the machine rules; wiring every machine rule into it is tracked in Open decisions below.

cite rule ids (R1-R12, B1-B4) in validator errors, review findings, and commit messages.

## definitions

- skill: one directory under `v0/plugins/<plugin>/skills/<skill>/` with a SKILL.md. the unit of deployment. it must work installed alone.
- plugin: one directory under `v0/plugins/`. organizational only: a folder of skills, a README, manifests. never a unit of behavior.
- reference: any mention of another skill or plugin, in any form: bare name, `$name`, relative path, or URL.
- embed: copy the relevant behavior into the target skill's own files, adapted to its scope, with no mention of the source.
- mesh: a group of skills whose files reference each other so that no member works alone. meshes are the failure mode these rules prevent.

## enforcement tags

- machine: `v0/scripts/validate-skills.mjs` checks it in CI and during release.
- review: humans and agents check it when authoring or reviewing.
- behavior: how agents must act while working in this repo.

## A. standalone contract

- **R1** a skill references no other skill. applies to every file in the skill dir (SKILL.md, references/, scripts/, tests/, agents/) and every form (bare name, `$name`, relative path, URL). a skill naming itself is not a reference. [machine]
- **R2** a skill never reads, writes, or points outside its own directory. no `../` escapes, no repo paths (`v0/scripts/...`, `v0/www/...`), no repo-root file mentions. skills must survive outside this checkout. [machine]
- **R3** a plugin references no other plugin, in any file including README and manifests. [machine]
- **R4** frontmatter descriptions are self-contained. no sibling names, no routing ("use X instead") in the trigger surface. selection must not depend on other skills existing. [machine]
- **R5** relationships between a plugin's own skills (differentiation, when to use which) live only in the plugin README. the README is the plugin's one organizational surface. [review]

## B. behavior

- **B1** embed instead of link. when the operator references another skill while creating or updating a skill, embed the referenced skill's behavior into the target skill instead of linking to it.
  - embed only the relevant part unless told otherwise. adapt it to the target's scope.
  - ownership transfers on embed: the copy belongs to the target, may diverge, and source updates do not propagate.
  - provenance goes in the commit message only ("feat(scope): embed X behavior from Y"), never in the artifact.
  - if the operator explicitly asks for a live link, stop and flag the R1 conflict. an explicit operator exemption is the only way a reference gets written.
  - the same applies when the named skill lives in another plugin or another repo.
  [behavior]
- **B2** backwards test every change before calling it done: diff old vs new so every skill, file, and behavior is accounted for (moved, replaced, or deliberately dropped and noted); run the repo validators; check anything that consumes the change (npm package, marketplace, site); report the result to the operator. [behavior]
- **B3** never run destructive or dangerous actions (such as the cleanup skills) without an explicit operator instruction for that action. [behavior]
- **B4** when planning, brainstorming, or strategising, stay read-only until the operator approves a final action plan. [behavior]

## C. hygiene

- **R6** every skill or plugin name mentioned anywhere must exist in this repo. no stale prefixes (`11agi-operator-*` moved to 11ops), no dead names. [machine]
- **R7** a plugin's manifests (`.claude-plugin/plugin.json`, `.codex-plugin/plugin.json`, per-skill `agents/openai.yaml`) and README must agree with each other. no contradictory claims. [machine]
- **R8** skill dir name equals frontmatter name and follows `11agi-<plugin-short>-<topic>`. [machine]
- **R9** only current domains in URLs (agi.rj11.io). a URL to another skill counts as a reference under R1. [machine]
- **R10** a plugin README lists exactly the skills that exist: no missing rows, no ghosts. [machine]

## D. quality

- **R11** trigger scopes are differentiable: two skill descriptions must not both plausibly fire on the same bare request. [review]
- **R12** a skill carries everything it needs: own references, own scripts, own data. shared data means each skill owns its copy; no skill syncs another skill's files (the file-level breach is caught by R2). [review]

## known violations at adoption (2026-08-17)

baseline for burn-down. counts from the 2026-08-17 full review.

| plugin | violations |
| --- | --- |
| 11agi-ai-analytics | 86 R1 refs; R2 path escapes in pricing-update scripts and tests |
| 11agi-blog-builder | 48 R1 refs ($invoke pipeline); 2 R4 frontmatter; R8 off-pattern names (11agi-blog-ui, 11agi-platform-cta, 11agi-publications-cms) |
| 11agi-agent-automation | 42 R1 refs; 19 R4 frontmatter routing lines |
| 11agi-ai-chat | 36 R1 refs; R8 off-pattern name (11agi-aichat-chatbot-extension) |
| 11agi-core | 17 R1 refs (reports cluster); R2 repo-root refs; 24 R6 stale 11agi-operator-* refs |
| 11agi-security | 10 R3 refs; R7 manifest contradiction with 11agi-audit README; R2 four-level path escape |
| 11agi-xharness | 2 R1 mutual refs |
| 11agi-cleanup | 1 R1 ref; R2 hardcoded repo output path in creator |
| 11agi-plugins-marketplace | R3 README link into 11agi-core |
| cross-plugin | R11 overlaps: super-security vs audit vs security; the three web-design restyle skills; the two directors |

## open decisions

unresolved. rules apply as written until the operator decides; do not improvise exemptions.

1. 11agi-plugins-marketplace structurally violates R3 (its purpose is cataloging plugins). exempt by name or rescope.
2. repo-tooling skills (11agi-core-operator-plugin-creator, 11agi-core-plugin-faq-manager, 11agi-core-reports-manager) cannot satisfy R2 as written. exempt class, relocate, or rewrite repo-agnostic.
3. does R1 govern generated output (reports that advertise another skill by name and URL) or only skill files.
4. validator rollout: warn-with-baseline then flip to error, or fix-first then land strict. machine rules are normative now either way; validator wiring is pending.

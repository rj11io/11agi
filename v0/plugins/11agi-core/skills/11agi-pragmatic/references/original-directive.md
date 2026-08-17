# Original directive

The directive this skill was expanded from. Verbatim, unedited:

```text
always be extremely pragmatic and objective

when speaking be extremely concise. sacrifice grammar for the sake of concision. use lists. never use em dashes. show examples or snippets where applicable. cite sources.

when reviewing, troubleshooting, or find any kind of bug, or issue, always suggest a fix for each problem that you find.

when planning, brainstorming, strategising, go read-only mode (never implement or execute actions, never change or destroy any files) until precisely told to do so after a final action plan review.

when implementing, point to where the changes were made for the operator to verify.

never run destructive or dangerous actions without an explicit operator instruction for that action.

also apply all these principles when writing code comments, content, plans, reports, documentation.

when working in a repo, leave a detailed conventional commit message (include scope) for the operator to copy.
```

Keep it exactly as written. It works standalone, and it is the fallback.

A drop-in copy for an `AGENTS.md` file, wrapped in BEGIN/END markers with a
heading, lives at [11AGI-AGENTS.md](11AGI-AGENTS.md). Same register, paste it
verbatim, markers included.

## When to use the directive instead

- The skill file is not loaded and you want the register in one message.
- Context is tight. The directive costs about 170 tokens. `SKILL.md` costs
  about 1,300.
- You are setting the register in a tool that takes plain instructions, not
  skills: a system prompt, a project rules file, a memory entry, a chat message.
  For an `AGENTS.md`, use [11AGI-AGENTS.md](11AGI-AGENTS.md).
- Something in the expanded skill is fighting you and you want the plain
  original behavior back.

Paste it as-is. No preamble needed.

## What the expansion added

`SKILL.md` maps one to one onto the eight blocks. Nothing was dropped, nothing
was reinterpreted:

| Clause in the original | Where it lives now |
| --- | --- |
| always be extremely pragmatic and objective | `## Rules`, "Always" block, plus an example |
| be extremely concise | `## Rules`, speaking, first bullet |
| sacrifice grammar for the sake of concision | `## Rules`, speaking, second bullet, plus an example |
| use lists | `## Rules`, speaking, third bullet |
| never use em dashes | `## Rules`, speaking, fourth bullet, plus an example |
| show examples or snippets where applicable | `## Rules`, speaking, fifth bullet |
| cite sources | `## Rules`, speaking, sixth bullet, plus an example |
| reviewing: always suggest a fix for each problem found | `## Rules`, reviewing block |
| planning: go read-only mode until precisely told, after a final action plan review | `## Rules`, planning block, expanded in `## Planning freeze` |
| implementing: point to where the changes were made | `## Rules`, implementing block, plus an example |
| never run destructive or dangerous actions without an explicit operator instruction | `## Rules`, "Always" block, second bullet |
| apply all these principles when writing code comments, content, plans, reports, documentation | `## Rules`, writing block |
| repo: detailed conventional commit message with scope, copyable | `## Rules`, repo block, expanded in `## Commit message` |

Two of the blocks needed more than a bullet:

- `## Planning freeze` pins what "go read-only mode" means in tool terms (no
  Edit, no Write, no executed actions, no state changes, nothing destroyed) and
  what counts as approval. The original leaves the approval bar to the reader.
- `## Commit message` pins the format (`type(scope): summary`), the allowed
  types, the scope rule, what "detailed" means (a body whenever the summary
  cannot carry the why), and the placement (own fenced block, last thing in the
  reply).

Two sections in `SKILL.md` are additions, not part of the original:

- `## Cut these` names the specific things to delete. Easier to follow than
  "be extremely concise" on its own.
- `## Keep these` says short is not vague, and that numbers, paths, exact error
  text, and stated uncertainty always survive.

The directive leaves both to the reader's judgment, which is why it stays
short. If the expansion ever drifts from the thirteen clauses above, the
directive wins.

## Revisions

The directive is edited in place, not versioned. Latest form is the one at the
top of this file. What changed, so a fallback lands on the right shape:

| Date | Change |
| --- | --- |
| 2026-08-05 | First recorded form. One line, six clauses, ending at "also suggest a fix." |
| 2026-08-05 | Added the seventh clause: a copyable conventional commit message closing any response that touched code. |
| 2026-08-07 | Reworded "sacrifice grammar" to "sacrifice grammar in favor of simplicity." Added a clause: when making changes, say where to look to verify them. Eight clauses total. |
| 2026-08-07 | Restructured from one line into six blocks: an always rule plus speaking, reviewing, planning, implementing, repo. New: "always be extremely pragmatic and objective", "cite sources", and the planning freeze (no file changes until the action plan is approved). "In favor of simplicity" became "for the sake of concision." Commit scope now required. |
| 2026-08-07 | Typo fix: "king of bug" to "kind of bug". |
| 2026-08-17 | Two new blocks: never run destructive or dangerous actions without an explicit operator instruction, and apply all the principles when writing code comments, content, plans, reports, documentation. Planning reworded to "go read-only mode (never implement or execute actions, never change or destroy any files)". "Show examples or snippets" gained "where applicable". Commit message "good" became "detailed". Eight blocks total. Added the `AGENTS.md` drop-in copy at 11AGI-AGENTS.md. |

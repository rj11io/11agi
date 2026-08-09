# 11agi Cleanup

Five skills for finding abandoned local resources and removing only the items the user explicitly selects.

## Choose a skill

| Skill | Use it for |
| --- | --- |
| [`11agi-cleanup-agent-threads`](./skills/11agi-cleanup-agent-threads/SKILL.md) | Finding old conversations and session scratchpads from coding agents |
| [`11agi-cleanup-agent-worktrees`](./skills/11agi-cleanup-agent-worktrees/SKILL.md) | Finding stale Git worktrees and reporting their branch safety |
| [`11agi-cleanup-idle-ports`](./skills/11agi-cleanup-idle-ports/SKILL.md) | Finding abandoned development servers and processes holding ports |
| [`11agi-cleanup-node-modules`](./skills/11agi-cleanup-node-modules/SKILL.md) | Finding large `node_modules` directories in stale projects |
| [`11agi-cleanup-creator`](./skills/11agi-cleanup-creator/SKILL.md) | Creating another scan, review, select, execute, and verify cleanup skill |

The resource-specific skills include read-only scan scripts. Their shared safety pattern is: scan, judge, report, ask, execute, then verify. A scan never authorizes deletion.

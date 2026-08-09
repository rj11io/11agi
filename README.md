# 11agi

Open source AI-agent skills for building chat products, editorial blogs, and repo-driven project sites; automating agent work; reporting LLM usage, cost, and timing; reverse engineering and maintaining codebases; integrating application services; running repository tasks through disciplined Git workflows; cleaning up local development environments; setting how an agent speaks; and running deep iterative project audits.

Project site: [https://agi.rj11.io/](https://agi.rj11.io/)

Each skill is a self-contained directory led by a `SKILL.md` file. Keep the whole directory together so its references, scripts, assets, and agent metadata remain available.

## Install

Install the collection from GitHub with the [skills CLI](https://skills.sh/docs/cli):

```bash
npx skills add rj11io/11agi --full-depth
```

The CLI runs through `npx`, discovers the repository's skills, and configures the skills you select for your agent. `--full-depth` is required because this collection organizes skills into per-workflow plugins under `v0/plugins/` instead of one top-level `skills/` directory.

The repository follows the open Agent Skills format. Every skill also includes Codex UI metadata in `agents/openai.yaml`, and every plugin is packaged for both Claude Code and Codex.

### Claude Code marketplace

Add the marketplace once, either inside a Claude Code session:

```text
/plugin marketplace add rj11io/11agi
```

or from your shell:

```bash
claude plugin marketplace add rj11io/11agi
```

Then install the plugin you need from the marketplace UI or with `/plugin install <plugin>@11agi`, for example `/plugin install 11agi-benchmarks@11agi`.

### Codex marketplace

Add the marketplace once:

```bash
codex plugin marketplace add rj11io/11agi
```

Then install the plugin you need with `codex plugin add <plugin>@11agi`, for example `codex plugin add 11agi-benchmarks@11agi`, or pick it from the plugins UI.

After installation, ask your agent to use a skill by name. For example:

```text
Use 11agi-ai-chat-stack to add a complete AI chat surface to this application.
```

### Package-only installation

Install the npm package directly when you need a versioned copy of the raw files rather than agent configuration:

```bash
npm install --save-dev @rj11io/11agi
```

The files are installed at `node_modules/@rj11io/11agi/v0/plugins/`. You can also clone this repository and use [`v0/plugins`](./v0/plugins) directly.

## Skill catalog

The repository currently contains 70 skills in 14 plugins.

| Plugin | Skills | Use them for |
| --- | ---: | --- |
| [Agent automation](./v0/plugins/11agi-agent-automation/README.md) | 8 | Scheduled autonomous work using the Ledger + Conductor + Routine pattern |
| [AI chat](./v0/plugins/11agi-ai-chat/README.md) | 9 | End-to-end chat, sessions, tools, models, providers, UI, and messaging-platform extensions |
| [Audit](./v0/plugins/11agi-audit/README.md) | 1 | Read-only dependency vulnerability, malware, supply-chain, and host-computer risk auditing |
| [Benchmarks](./v0/plugins/11agi-benchmarks/README.md) | 5 | Single-thread, project-scoped, and machine-wide LLM cost, effort, and timing reports, provider-verified pricing maintenance, and a FAQ over all of them |
| [Blog builder](./v0/plugins/11agi-blog-builder/README.md) | 10 | Building file-backed editorial blogs with composable CMS, author, Markdown, content, navigation, and UI skills, plus a standalone platform-services page and a publications-and-chapters CMS |
| [Cleanup](./v0/plugins/11agi-cleanup/README.md) | 5 | Safely finding and removing abandoned local resources |
| [Codebase](./v0/plugins/11agi-codebase/README.md) | 4 | Playwright setup, npm publishing, automated releases, and web analytics |
| [Directors](./v0/plugins/11agi-directors/README.md) | 2 | Wrapping a repository task in a disciplined Git workflow, on main or through a reviewed pull request |
| [Core skills](./v0/plugins/11agi-core-skills/README.md) | 8 | Building, auditing, and maintaining other skills and the plugins that package them, plus markdown compression, repository reverse engineering, report and web styleguides, a pragmatic communication register, and a blunt read-only critique |
| [Plugins marketplace](./v0/plugins/11agi-plugins-marketplace/README.md) | 2 | Auditing and researching marketplace, plugin, and skill configuration files across the Claude Code, Claude Cowork, OpenAI Codex, ChatGPT, and Agent Skills ecosystems |
| [Security](./v0/plugins/11agi-security/README.md) | 1 | A reserved plugin for future security skills beyond dependency scanning: threat modeling, secure-coding review, and secrets handling |
| [Super](./v0/plugins/11agi-super/README.md) | 9 | Repeatedly completing general or specialist project tasks to a high evidence-based bar |
| [Web design](./v0/plugins/11agi-web-design/README.md) | 4 | The 11agi visual language, deliberate content-led styling, and repository-driven project sites for accessible web interfaces |
| [Cross-harness](./v0/plugins/11agi-xharness/README.md) | 2 | Delegating work to agents running in other CLI harnesses |

Start with a plugin's README to choose a skill, then name that skill in your request. Skills provide instructions and examples; they do not install the application dependencies used in those examples by themselves.

## Repository layout

```text
.claude-plugin/               Claude marketplace discovery entry point
v0/
  index.js                    CommonJS package entry point
  plugins/
    11agi-agent-automation/     8 automation skills under skills/
    11agi-ai-chat/              9 AI chat skills under skills/
    11agi-audit/                1 evidence-backed dependency-audit skill under skills/
    11agi-benchmarks/           5 LLM cost, effort, timing, and FAQ skills under skills/
    11agi-blog-builder/         10 editorial blog, platform-CTA, and publications-CMS skills under skills/
    11agi-cleanup/              5 cleanup skills under skills/
    11agi-codebase/             4 codebase skills under skills/
    11agi-directors/            2 Git task-director skills under skills/
    11agi-core-skills/          8 skill-authoring, packaging, compression, reverse-engineering, styleguide, and communication-register skills under skills/
    11agi-plugins-marketplace/  2 marketplace-config audit and research skills under skills/
    11agi-security/             1 reserved security skill under skills/
    11agi-super/                9 iterative task and improvement skills under skills/
    11agi-web-design/           4 web design and project-site skills under skills/
    11agi-xharness/             2 cross-harness skills under skills/
  scripts/                    Package validation, release, and publishing helpers
  www/                        Next.js project site
```

`v0` is the current versioned distribution namespace for the plugins, package tooling, and project site. The root marketplace manifest is their stable Claude discovery entry point. Pin the npm package version or a commit when reproducibility matters, because its content can change between releases.

The CommonJS entry point exposes package metadata only:

```js
const elevenAGI = require("@rj11io/11agi")

console.log(elevenAGI.name) // "@rj11io/11agi"
```

The supported consumer surface is the skill content under `v0/plugins/{plugin-name}/skills/{skill-name}`, not a JavaScript runtime API.

## Repository commands

Install root package tooling before running these commands:

```bash
npm install
npm run validate-skills
npm run pack-dry
```

`validate-skills` checks frontmatter, Codex metadata, Claude plugin and marketplace configuration, links, scripts, and catalog coverage. `pack-dry` shows the npm tarball contents without publishing. The manual publishing command and its token requirements are documented in [`v0/scripts/README.md`](./v0/scripts/README.md). The project site has its own dependencies and commands in [`v0/www/README.md`](./v0/www/README.md).

Pushes to `main` run semantic-release, which updates the package version, publishes to npm, creates a GitHub release, and publishes the generated tarball to GitHub Packages.

## License

Apache-2.0. See [`LICENSE`](./LICENSE).

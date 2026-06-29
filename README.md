<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=240&color=0:0d47a1,30:00ff41,70:00ffff,100:ff006e&text=Claude%20Code%20Skills&fontSize=64&fontColor=ffffff&animation=fadeIn&desc=Curated+for+AI+Engineering+%C2%B7+Agent+Dev+%C2%B7+Offensive+Security&descAlignY=80&descSize=17" width="100%" alt="banner"/>
</div>

<div align="center">

![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=for-the-badge&logo=anthropic&logoColor=white)
![MCP](https://img.shields.io/badge/MCP_compatible-0a0a0a?style=for-the-badge&logo=anthropic&logoColor=00ff41)
![Skills](https://img.shields.io/badge/Skills-35-00ff41?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-00ff41?style=for-the-badge)

</div>

> A curated, opinionated collection of [Claude Code](https://docs.claude.com/claude-code) skills I keep installed in my daily workflow. Heavy on **AI agent building**, **offensive-security ops**, and **dev-velocity tooling**. Each skill is a single `SKILL.md` (sometimes with helpers) that Claude Code can invoke directly.

This is a **curation**, not a manifesto — skills here come from my own usage, the open Claude Code ecosystem, and community marketplaces. Attribution is preserved in each `SKILL.md` frontmatter where the upstream author tagged themselves. Skills without a clear upstream are surfaced as-is from my local working set.

## 📦 Install one (Claude Code)

```bash
# From this repo into your local skills directory:
cp -R skills/<skill-name> ~/.claude/skills/

# Then in any Claude Code session:
/<skill-name>
```

Or browse the `skills/` folder and copy what fits.

## 🗂️ What's inside

### 🤖 Skill & agent factories — build more skills, faster

| Skill | What it does |
|---|---|
| [`hook-factory`](skills/hook-factory) | Scaffolds Claude Code hooks (pre-tool, post-tool, prompt-submit) with safe defaults |
| [`slash-command-factory`](skills/slash-command-factory) | Generates new `/slash-command` skills from a one-line description |
| [`prompt-factory`](skills/prompt-factory) | Composable prompt templates for system / tool-use / agent loops |
| [`makeskill`](skills/makeskill) | End-to-end skill generator with rubric, examples, validation |
| [`skill-builder`](skills/skill-builder) | Companion to `makeskill` — interactive skill drafting |
| [`find-skills`](skills/find-skills) | Local search across your installed skills by topic / capability |
| [`claude-md-enhancer`](skills/claude-md-enhancer) | Improves your project `CLAUDE.md` for clarity and agent guidance |

### 🧠 AI agent building

| Skill | What it does |
|---|---|
| [`agent-browser`](skills/agent-browser) | Browser-driving agent patterns (Playwright + Claude) |
| [`agent-factory`](skills/agent-factory) | Spawn and compose specialized sub-agents |
| [`agentcore`](skills/agentcore) | Foundational agent kernel patterns |
| [`langchain`](skills/langchain) | LangChain-specific agent / tool patterns |
| [`langsmith-fetch`](skills/langsmith-fetch) | Pull traces from LangSmith for analysis |
| [`local-llm-router`](skills/local-llm-router) | Multi-provider local LLM routing (Ollama / vLLM / others) |

### 🛡️ Security & offensive ops

| Skill | What it does |
|---|---|
| [`owasp-security`](skills/owasp-security) | OWASP-aligned web app security review |
| [`security-scanner`](skills/security-scanner) | Quick secret / credential scan |

### ⚙️ Dev velocity

| Skill | What it does |
|---|---|
| [`tdd-guide`](skills/tdd-guide) | Test-driven workflow for new features |
| [`tech-stack-evaluator`](skills/tech-stack-evaluator) | Decision-quality stack picks for new projects |
| [`test-generator`](skills/test-generator) | Generate unit / integration tests for given code |
| [`test-scout`](skills/test-scout) | Find untested code paths in a repo |
| [`refactoring-assistant`](skills/refactoring-assistant) | Guided multi-step refactors with checkpoints |
| [`worktree`](skills/worktree) | Safe git worktree workflows |
| [`batch`](skills/batch) | Run the same task across many files in parallel |
| [`loop`](skills/loop) | Repeat a task until a condition or max iterations |
| [`orchestrate`](skills/orchestrate) | Multi-wave parallel agent coordination |
| [`onboard`](skills/onboard) | Quickly orient Claude to a new codebase |
| [`quickstart`](skills/quickstart) | One-shot project scaffolding |
| [`codex-cli-bridge`](skills/codex-cli-bridge) | Bridge to OpenAI Codex CLI for cross-model workflows |

### 🧭 Quality / planning utilities

| Skill | What it does |
|---|---|
| [`honest-agent`](skills/honest-agent) | Anti-fabrication / verification patterns |
| [`change-validator`](skills/change-validator) | Validate changes match the user's intent |
| [`error-analyzer`](skills/error-analyzer) | Triage stack traces and runtime errors |
| [`issue-scoper`](skills/issue-scoper) | Decompose an issue into well-scoped sub-tasks |
| [`knowledge-db`](skills/knowledge-db) | Skill-side persistent knowledge store |
| [`scrum-master-agent`](skills/scrum-master-agent) | Sprint-style task management with status reporting |
| [`arch-map`](skills/arch-map) | Map a codebase's architecture into a queryable graph |
| [`core`](skills/core) | Core skill bundle / shared primitives |

## ✍️ Format

Each skill folder follows the standard Claude Code convention:

```
skills/<name>/
├── SKILL.md          # YAML frontmatter + skill body (required)
├── assets/           # optional supporting files (scripts, templates)
└── ...               # any helpers the skill needs at runtime
```

YAML frontmatter usually contains `name`, `description`, optional `trigger` (slash command), and `metadata.author` for attribution.

## 🤝 Contributing

PRs welcome — especially:

- New skills aligned to **AI security**, **red team workflows**, **agent infrastructure**, or **MCP integrations**
- Hardening / better defaults on existing skills
- Examples of each skill being used in a real session

Open an issue first if you're proposing a sizeable addition so we can discuss scope.

## 📜 License

MIT — see [LICENSE](./LICENSE).

Individual skills retain their upstream attribution where present in their `SKILL.md` frontmatter. If you're the author of a skill here and want a credit / link added or a removal, open an issue.

---

<div align="center"><sub>Part of the <a href="https://github.com/Dhanush-Aries">Dhanush Shankar</a> AI engineering portfolio · <a href="https://github.com/Dhanush-Aries/jarvis">Jarvis</a> · <a href="https://github.com/Dhanush-Aries/breachintel">BreachIntel</a> · <a href="https://github.com/Dhanush-Aries/cve-advisor">CVE Advisor</a></sub></div>

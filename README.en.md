# VibeCoding — Idea to Product

> Full workflow Agent Skill from product idea to shippable delivery  
> **中文:** [README.md](./README.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](./CHANGELOG.md)
[![Multi-Agent](https://img.shields.io/badge/agents-Claude%20Code%20%7C%20Codex%20%7C%20TRAE%20%7C%20Zcode-8A2BE2)](./docs/compatibility.md)

---

## Introduction

**VibeCoding — Idea to Product** is a **production-ready, single-file** Agent Skill ([`SKILL.md`](./SKILL.md)). It steers compatible coding agents through gated phases so an idea becomes a deliverable product:

```text
Phase 0 routing → PRD → UI/design → tech solution → architecture lock
→ small-step dev → system test → ship
```

Built for indie builders, engineers who want guardrails on AI coding, and small teams that need consistent delivery artifacts.

---

## Why this exists

| Common failure | How this Skill helps |
| -------------- | -------------------- |
| Agent drifts off-brief | Phase gates + document-driven development |
| Context loss | Resume from `docs/` artifacts |
| Code before design | Prototypes + design spec |
| Random deps / core rewrites | Architecture constitution + protected logic |
| Happy-path-only testing | State coverage + PRD traceability + test report |
| No handoff docs | Phase 7 doc sync + project README |

---

## Highlights

- **Phase 0 + 7 stages**, artifact-based resume, **Full Flow / Fast Track**
- **Explicit confirmation** before advancing
- **Templates & example** under `docs/`
- **Multi-agent**: Claude Code, Codex, TRAE, Zcode, Cursor, generic agents
- **Bilingual triggers** and dual READMEs

---

## Quick start

```bash
git clone https://github.com/DuXingLang/vibecoding-idea-to-product.git
```

Install for your agent ([installation](./docs/installation.md), [compatibility](./docs/compatibility.md)). Claude Code example:

```bash
mkdir -p ~/.claude/skills/vibecoding-idea-to-product
cp SKILL.md ~/.claude/skills/vibecoding-idea-to-product/SKILL.md
```

In an empty project, say:

```text
I have an idea
# or
我有一个想法
```

Success means the agent starts **Phase 0** (workspace, git, resume inference, Full vs Fast).

---

## Workflow

| Phase | Output |
| ----- | ------ |
| 0 Bootstrap | Routing & mode |
| 1 Product | `docs/prd.md` |
| 2 Design | `docs/design.md`, `docs/ui-prototypes/` |
| 3 Tech | `docs/techsol.md` |
| 4 Prep | `docs/architecture.md` |
| 5 Build | `TODO.md` + code |
| 6 Test | `docs/test-report.md` |
| 7 Ship | Project README, doc sync, optional tag |

See [docs/workflow.md](./docs/workflow.md) and [docs/usage.md](./docs/usage.md).

---

## Repository layout

```text
SKILL.md                 # Core skill (distributable alone)
README.md / README.en.md
docs/installation.md usage.md workflow.md compatibility.md faq.md
docs/templates/
docs/examples/sample-todo-app/
```

---

## Docs index

| Doc | Purpose |
| --- | ------- |
| [SKILL.md](./SKILL.md) | Normative agent workflow |
| [compatibility.md](./docs/compatibility.md) | Multi-agent install notes |
| [templates/](./docs/templates/) | Stage templates |
| [sample-todo-app](./docs/examples/sample-todo-app/) | Sample artifacts |

---

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md).

## License

[MIT](./LICENSE) © DuXingLang

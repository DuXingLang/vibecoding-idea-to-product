# Vibecoding: Idea to Product - Agent Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](./CHANGELOG.md)
[![Multi-Agent](https://img.shields.io/badge/agents-Claude%20Code%20%7C%20Codex%20%7C%20TRAE%20%7C%20Zcode%20%7C%20Cursor-8A2BE2)](./docs/compatibility.md)

**中文:** [README.md](./README.md)

**An end-to-end AI Agent Skill from product idea to shippable delivery.**  
Single-file and agent-agnostic — works with Claude Code, Codex, TRAE, Zcode, Cursor, Windsurf, and other tools that support skills, project rules, or custom system instructions.

When you say *“I have an idea”*, this Skill guides you and the AI through Phase 0 bootstrap, product positioning, UI prototyping, tech design, architecture lock-in, small-step development, testing, and deployment — with clear boundaries, normative outputs, and resumable progress.

---

## What it does

- **Structure fuzzy ideas** → produces a proper PRD  
- **Visualize UX & design** → layout options, Mermaid flows, high-fidelity HTML prototypes (compressible on Fast Track)  
- **Freeze the tech stack** → architecture, data model, deployment, and security notes  
- **Stop AI freelancing** → locks norms into `docs/` as a development “constitution”  
- **Ship in small steps** → one TODO at a time; six-point scope gate before each coding task  
- **Resume anytime** → infers phase from `docs/` artifacts (“Resume progress”)  
- **Handoff-ready** → test report, doc sync, project README, git commit/tag with your approval  

Canonical behavior lives in [`SKILL.md`](./SKILL.md):

```text
Idea → Phase 0 → PRD → Prototype/Design → Tech solution → Architecture lock
→ Build → Test → Ship
```

---

## Quick start

### 1. Get the Skill

```bash
git clone https://github.com/DuXingLang/vibecoding-idea-to-product.git
cd vibecoding-idea-to-product
```

The core file is **`SKILL.md`** at the repo root (distributable alone). Optionally copy `docs/templates/`.

### 2. Load it in your AI tool

**Claude Code**

```bash
mkdir -p ~/.claude/skills/vibecoding-idea-to-product
cp SKILL.md ~/.claude/skills/vibecoding-idea-to-product/SKILL.md
```

Or project-local: `.claude/skills/vibecoding-idea-to-product/SKILL.md`.

**Cursor**

- Paste `SKILL.md` into project rules (e.g. `.cursor/rules`) or Settings → Rules; or `@SKILL.md` in chat.

**Windsurf**

- Follow Windsurf’s official rule/memory conventions and include `SKILL.md`.

**Codex / TRAE / Zcode / others**

- Copy into that product’s skill/rules directory, or reference it from project instructions (e.g. `AGENTS.md`).  
- See [docs/compatibility.md](./docs/compatibility.md) and [docs/installation.md](./docs/installation.md). **Official docs win** if paths differ.

**Generic**

- Use the full `SKILL.md` as system / custom instructions.

### 3. Start the conversation

> “I have an idea — a scheduling tool for fitness coaches. Help me build it from scratch.”

Or short triggers:

```text
I have an idea
I want to build a product
Resume progress
我有一个想法
```

The agent should enter **Phase 0** first (workspace, git, resume inference, Full vs Fast Track), then advance only after your confirmation.

---

## Workflow overview

| Phase | Focus | Output after confirmation |
| ----- | ----- | ------------------------- |
| 0 Bootstrap | Env, resume, Full/Fast mode | Routing decision |
| 1 Product | Structured Q&A | `docs/prd.md` |
| 2 Design | Layouts, Mermaid, colors, HTML prototypes | `docs/design.md` + `docs/ui-prototypes/` |
| 3 Tech | Architecture, stack, data, deploy, security | `docs/techsol.md` |
| 4 Prep | Locked “constitution” | `docs/architecture.md` |
| 5 Build | `TODO.md` + six-point gates | Incremental code |
| 6 Test | Review, security, PRD traceability | `docs/test-report.md` |
| 7 Ship | Doc sync, README, authorized git tag | Handoff-ready repo |

No phase skipping without your explicit gate.  
Details: [docs/workflow.md](./docs/workflow.md) · [docs/usage.md](./docs/usage.md)

**Fast Track (MVP):** opt in at Phase 0 for thinner docs/prototypes and P0-only TODOs; upgrade to Full Flow by backfilling docs anytime.

---

## Why you need it

Vibe coding often drifts: random features, broken core logic, silent stack changes, missing docs, and sessions that cannot resume.

This Skill locks boundaries **before** coding, forces small confirmed steps **during** coding, syncs docs **after** coding, and restores progress from **on-disk artifacts** in a new session.

| Failure mode | Mitigation |
| ------------ | ---------- |
| Off-brief coding | Phase gates + docs-first |
| Lost context | Artifact-based resume |
| Code before design | Prototypes + design spec |
| Rogue deps / core rewrites | Architecture rules + protected logic |
| Happy-path-only tests | State coverage + PRD trace + test report |
| No handoff | Phase 7 sync + project README |

---

## Examples & templates

- **Sample artifacts:** [docs/examples/sample-todo-app/](./docs/examples/sample-todo-app/) (minimal todo, phases 1–4)  
- **Blank templates:** [docs/templates/](./docs/templates/)  

Samples show document shape; they are not a full production app.

---

## Repository layout

```text
SKILL.md
README.md / README.en.md
CONTRIBUTING.md / CHANGELOG.md / LICENSE
docs/  installation · usage · workflow · compatibility · faq
docs/templates/
docs/examples/sample-todo-app/
```

---

## Contributing

Improvements to the workflow, prompts, examples, docs, and multi-agent notes are welcome.

1. Fork  
2. Branch (`git checkout -b feature/amazing-improvement`)  
3. Commit (`git commit -m 'feat: add some amazing improvement'`)  
4. Push and open a Pull Request  

Behavioral changes should update `SKILL.md` first, then `docs/` and templates. See [CONTRIBUTING.md](./CONTRIBUTING.md). Issues are welcome too.

---

## License

[MIT License](./LICENSE) — free to use, modify, and distribute.  
If this helps you, a ⭐️ Star is appreciated.

---

## Who it’s for

- Indies shipping 0→1 products  
- Non-technical founders building an MVP with AI  
- Engineers who want guardrails on AI coding  
- Teams needing consistent PoC docs and quality  
- Teaching how ideas become engineered products  

---

**Let every idea grow into a product — with discipline.**

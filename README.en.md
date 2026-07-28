# 🚀 VibeCoding — Idea to Product

> A full-stack AI development workflow from idea to deployment  
> A Claude Code Agent Skill that guides AI assistants through a 7-stage standardized process to turn your product ideas into shippable products.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.txt)
[![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-8A2BE2)](https://claude.ai/code)

---

## 📖 Introduction

**VibeCoding — Idea to Product** is a Claude Code Agent Skill that defines a complete, production-ready product development workflow:

> **PRD → UI Prototype → Tech Solution → Prep → Iterative Development → System Test → Deployment**

When you have a product idea but don't know where to start — or want AI to help you build it in a structured way — this Skill is for you. Every phase has clear deliverables and confirmation gates, preventing AI from wandering off-track or producing runaway code.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🧩 **7-Stage Standardized Workflow** | Complete lifecycle from product positioning to deployment |
| ✅ **Phase-by-Phase Confirmation** | Developer must confirm each phase before proceeding |
| 📄 **Document-Driven** | Auto-generates PRD, design specs, tech solutions, architecture docs |
| 🎨 **High-Fidelity Prototypes** | Produces interactive HTML/CSS/JS prototypes, previewable in browser |
| 📐 **Mermaid Diagrams** | Auto-generates flowcharts, architecture diagrams, ER diagrams |
| 🔄 **Small-Step Iteration** | One task at a time, with clear scope and acceptance criteria per change |
| 🛡️ **Core Logic Protection** | Prevents AI from modifying critical flows (auth, payments, etc.) |
| 🧪 **Full Test Coverage** | Unit tests + state coverage + requirements traceability |

---

## 🚦 Quick Start

### Prerequisites

- [Claude Code](https://claude.ai/code) installed
- Claude Code can access this project's `SKILL.md`

### Installation

#### Option 1: Direct Use (Recommended)

```bash
# Clone the project
git clone https://github.com/<your-username>/vibecoding-idea-to-product.git

# Launch Claude Code
cd vibecoding-idea-to-product
claude
```

Then tell Claude:

> "I have an idea, I want to build a product"

Claude will automatically detect the trigger and enter the Skill-defined workflow.

#### Option 2: Install as a Global Skill

Copy `SKILL.md` to your Claude Code global Skills directory:

```bash
# Adjust the path as needed
cp SKILL.md ~/.claude/skills/vibecoding-idea-to-product.md
```

Then Claude Code can recognize and invoke this Skill from any project.

---

## 📋 Workflow Overview

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│  Phase 1    │ →   │  Phase 2    │ →   │  Phase 3    │ →   │  Phase 4    │
│  Product    │     │  UI Design  │     │  Tech Arch  │     │  Prep Dev   │
│  → PRD      │     │  → Design   │     │  → Tech Doc │     │  → Arch Doc │
└─────────────┘     └─────────────┘     └─────────────┘     └─────────────┘
                                                              │
                                                              ▼
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│  Phase 7    │ ←   │  Phase 6    │ ←   │  Phase 5    │
│  Deployment │     │  System Test│     │  Development│
│  → Docs Sync│     │  → Test Rep │     │  → Iteration│
└─────────────┘     └─────────────┘     └─────────────┘
```

See [docs/workflow.md](docs/workflow.md) for detailed explanations of each phase.

---

## 🗂️ Deliverables

Each phase generates corresponding documents in the project's `docs/` directory:

| Phase | Output File | Description |
|-------|-------------|-------------|
| 1 | `docs/prd.md` | Product Requirements Document |
| 2 | `docs/design.md` | Design specifications & color scheme |
| 2 | `docs/ui-prototypes/` | High-fidelity interactive prototypes |
| 3 | `docs/techsol.md` | Technical implementation plan |
| 4 | `docs/architecture.md` | Development architecture "constitution" |
| 5 | `TODO.md` | Task list & progress tracking |
| 6 | `docs/test-report.md` | Full test report |
| 7 | `README.md` | Final project README |

---

## 📦 Phase Details

### Phase 0: Pre-flight Check
- Check workspace directory state
- Check Git repository status
- Check for existing docs to resume progress
- Confirm product idea readiness

### Phase 1: Product Positioning
Claude asks structured questions about target users, scenarios, core features, and success metrics, then generates a PRD.

### Phase 2: UI Design
3 layout options → Mermaid workflow diagram → color scheme → interactive HTML prototypes → design spec document.

### Phase 3: Tech Solution
Architecture design, tech stack selection with comparison table, data model, security checklist, performance budget, deployment architecture.

### Phase 4: Development Prep
Lock down `docs/architecture.md` as the development "constitution" — directory structure, constraints, version control strategy, environment variable management.

### Phase 5: Iterative Development
One task at a time. Each iteration outputs: target, scope, protected logic, impact, acceptance criteria, test plan. With rollback and error recovery.

### Phase 6: System Testing
Full code review, security scanning, performance benchmarking, unit tests, requirements traceability, test report generation.

### Phase 7: Deployment
Documentation sync, CI/CD config generation, API docs, deployment verification, README generation, Git tagging.

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## 📄 License

This project is open-sourced under the [MIT License](LICENSE.txt).

---

## 👤 Author

- **DuXingLang** (独行浪)

---

## ⭐ Support

If this project helps you, please give it a Star ⭐ to help others discover it!
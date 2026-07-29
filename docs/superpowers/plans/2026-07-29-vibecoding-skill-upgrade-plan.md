# VibeCoding Idea-to-Product Skill 生产级优化实现计划

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 全面升级 VibeCoding Agent Skill，打造生产级、跨平台兼容、带生态包的完整交付方案。

**Architecture:** 单文件通用 SKILL.md（含 Phase 0、7 阶段、门禁、恢复、Fast Track）；模板/示例/中英 README/贡献规范生态包；兼容策略按平台官方文档 + 通用复制法。

**Tech Stack:** Markdown、Mermaid、Git（commit 风格）。

## Global Constraints

- SKILL.md 单文件通用，兼容 Claude Code / Codex / TRAE / Zcode
- 所有阶段必须有明确用户确认门禁
- Phase 0 自动进度恢复
- 文档统一在 `docs/` 目录
- 中英文 README 对等
- 模板、示例、贡献规范齐全

---

## Task 1: 重写 SKILL.md（核心文件）

**Files:**
- Modify: `SKILL.md` (full rewrite)

**Interfaces:**
- Consumes: 现有 `SKILL.md` 结构、Phase 0/7 阶段逻辑
- Produces: 新 `SKILL.md`（Phase 0 + 7 阶段 + 门禁 + 恢复 + Fast Track + frontmatter）

- [ ] **Step 1: 写当前 SKILL 结构分析**
- [ ] **Step 2: 写 Phase 0 前置检查**
- [ ] **Step 3: 写阶段一产品定位（PRD 草稿）**
- [ ] **Step 4: 写阶段二视觉设计（原型 + design.md）**
- [ ] **Step 5: 写阶段三技术方案（techsol.md）**
- [ ] **Step 6: 写阶段四准备开发（architecture.md）**
- [ ] **Step 7: 写阶段五正式开发（TODO + 六项模板）**
- [ ] **Step 8: 写阶段六系统测试（test-report）**
- [ ] **Step 9: 写阶段七部署交付（README + 版本）**
- [ ] **Step 10: 写 Fast Track 快车道**
- [ ] **Step 11: 写全局规则、回溯、失败处理**
- [ ] **Step 12: 写 frontmatter（兼容 + 中英 triggers）**
- [ ] **Step 13: 写自检清单、确认点**
- [ ] **Step 14: 写术语表**
- [ ] **Step 15: 完整自审 + 提交**

---

## Task 2: 创建 docs/templates/

**Files:**
- Create: `docs/templates/prd.template.md`
- Create: `docs/templates/design.template.md`
- Create: `docs/templates/techsol.template.md`
- Create: `docs/templates/architecture.template.md`
- Create: `docs/templates/test-report.template.md`
- Create: `docs/templates/todo.template.md`

**Interfaces:**
- Consumes: SKILL.md 阶段描述
- Produces: 模板文件（标题、章节、确认清单）

- [ ] **Step 1: 写 prd.template.md**
- [ ] **Step 2: 写 design.template.md**
- [ ] **Step 3: 写 techsol.template.md**
- [ ] **Step 4: 写 architecture.template.md**
- [ ] **Step 5: 写 test-report.template.md**
- [ ] **Step 6: 写 todo.template.md**
- [ ] **Step 7: 写 templates/index.md（可选）**
- [ ] **Step 8: 完整自审**

---

## Task 3: 创建示例项目 `docs/examples/sample-todo-app/`

**Files:**
- Create: `docs/examples/sample-todo-app/README.md`
- Create: `docs/examples/sample-todo-app/prd.md`
- Create: `docs/examples/sample-todo-app/design.md`
- Create: `docs/examples/sample-todo-app/techsol.md`
- Create: `docs/examples/sample-todo-app/architecture.md`

**Interfaces:**
- Consumes: templates
- Produces: 完整示例产物（文档骨架）

- [ ] **Step 1: 写 sample-todo-app README.md**
- [ ] **Step 2: 写 prd.md**
- [ ] **Step 3: 写 design.md**
- [ ] **Step 4: 写 techsol.md**
- [ ] **Step 5: 写 architecture.md**
- [ ] **Step 6: 完整自审**

---

## Task 4: 更新 docs/ 安装与使用文档

**Files:**
- Modify: `docs/installation.md`
- Modify: `docs/usage.md`
- Modify: `docs/workflow.md`
- Create: `docs/compatibility.md` (new)

**Interfaces:**
- Consumes: SKILL.md、templates
- Produces: 安装、用法、兼容文档

- [ ] **Step 1: 写 installation.md**
- [ ] **Step 2: 写 usage.md**
- [ ] **Step 3: 写 compatibility.md**
- [ ] **Step 4: 写 workflow.md**
- [ ] **Step 5: 完整自审**

---

## Task 5: 写中英文 README.md

**Files:**
- Create: `README.md`
- Create: `README.en.md`

**Interfaces:**
- Consumes: SKILL.md、docs/
- Produces: 生产级中英文 README

- [ ] **Step 1: 写 README.md（中文）**
- [ ] **Step 2: 写 README.en.md（英文）**
- [ ] **Step 3: 完整自审**

---

## Task 6: 写 CONTRIBUTING.md + CHANGELOG.md

**Files:**
- Create: `CONTRIBUTING.md`
- Create: `CHANGELOG.md`

**Interfaces:**
- Consumes: SKILL.md
- Produces: 贡献指南 + 变更日志

- [ ] **Step 1: 写 CONTRIBUTING.md**
- [ ] **Step 2: 写 CHANGELOG.md**
- [ ] **Step 3: 完整自审**

---

## Task 7: 调整 .gitignore 和可选 CI

**Files:**
- Modify: `.gitignore`
- Create: `.github/ISSUE_TEMPLATE/bug-report.md` (optional)
- Create: `.github/ISSUE_TEMPLATE/feature-request.md` (optional)

**Interfaces:**
- Consumes: SKILL.md
- Produces: 忽略文件 + issue 模板

- [ ] **Step 1: 写 .gitignore**
- [ ] **Step 2: 写 issue templates**
- [ ] **Step 3: 完整自审**

---

## Task 8: 整体自审 + 交付

**Files:**
- Modify: SKILL.md
- Modify: 所有 docs/
- Modify: README.md / README.en.md
- Modify: CONTRIBUTING.md / CHANGELOG.md

**Interfaces:**
- Consumes: 所有 Task
- Produces: 完整生产级生态包

- [ ] **Step 1: 链接自检**
- [ ] **Step 2: 中英 README 对等性检查**
- [ ] **Step 3: 模板与 SKILL 章节一致性检查**
- [ ] **Step 4: 生产可用性自审**
- [ ] **Step 5: 最终 commit + 版本标记**

---

## Task 9: 运行计划自审

**Files:**
- Review: 所有 plan 文档

**Interfaces:**
- Consumes: 本 plan
- Produces: 无

- [ ] **Step 1: 扫描所有 plan 步骤**
- [ ] **Step 2: 检查是否有 placeholder**
- [ ] **Step 3: 检查文件路径准确性**
- [ ] **Step 4: 完成所有任务**
- [ ] **Step 5: 提交最终 plan 版本**

---

## Post-Plan Handoff

Plan complete and saved to `docs/superpowers/plans/2026-07-29-vibecoding-skill-upgrade-plan.md`. Two execution options:

**1. Subagent-Driven (recommended)** - I dispatch a fresh subagent per task, review between tasks, fast iteration

**2. Inline Execution** - Execute tasks in this session using executing-plans, batch execution with checkpoints

**Which approach?**
# VibeCoding — Idea to Product

> 从产品想法到交付上线的全流程 Agent Skill  
> **English:** [README.en.md](./README.en.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](./CHANGELOG.md)
[![Multi-Agent](https://img.shields.io/badge/agents-Claude%20Code%20%7C%20Codex%20%7C%20TRAE%20%7C%20Zcode-8A2BE2)](./docs/compatibility.md)

---

## 简介

**VibeCoding — Idea to Product** 是一份**生产级、单文件通用**的 Agent Skill（[`SKILL.md`](./SKILL.md)），用结构化门禁把「想法」推到「可交付产品」：

```text
Phase 0 路由 → PRD → UI/设计 → 技术方案 → 架构锁定 → 小步开发 → 系统测试 → 部署交付
```

适合：有想法的独立开发者、希望约束 AI 编程的工程师、需要统一交付质量的小团队。

---

## 为什么需要它？

| 常见问题 | 本 Skill 的应对 |
| -------- | --------------- |
| AI 方向跑偏 | 阶段门禁 + 文档驱动 |
| 上下文丢了需求 | `docs/` 产物可恢复进度 |
| 跳过设计直接码 | 强制/可选原型与 design 规范 |
| 乱引依赖、改核心逻辑 | architecture 宪法 + 禁改清单 |
| 只测快乐路径 | 状态覆盖 + PRD 回溯 + test-report |
| 做完没文档 | 阶段 7 反扫与 README |

---

## 核心特性

- **Phase 0 + 7 阶段**：环境检查、产物推断恢复、Full Flow / Fast Track  
- **逐阶段确认**：未确认不进入下一阶段  
- **文档驱动**：PRD / design / techsol / architecture / test-report  
- **小步开发**：`TODO.md` + 每任务「六项」范围门禁  
- **跨 Agent**：Claude Code、Codex、TRAE、Zcode、Cursor、通用 Agent  
- **中英触发词** + 双语 README  
- **模板与示例**：`docs/templates/`、`docs/examples/sample-todo-app/`

---

## 快速开始

### 1. 获取 Skill

```bash
git clone https://github.com/DuXingLang/vibecoding-idea-to-product.git
```

### 2. 安装到你的 Agent

详见 [docs/installation.md](./docs/installation.md) 与 [docs/compatibility.md](./docs/compatibility.md)。

Claude Code 示例：

```bash
mkdir -p ~/.claude/skills/vibecoding-idea-to-product
cp SKILL.md ~/.claude/skills/vibecoding-idea-to-product/SKILL.md
```

### 3. 在空项目里启动并触发

```text
我有一个想法
# 或
I have an idea
```

若进入 **Phase 0**（目录 / Git / 进度 / Full·Fast），即安装成功。

---

## 流程一览

| 阶段 | 产出 |
| ---- | ---- |
| 0 前置 | 路由与模式 |
| 1 产品定位 | `docs/prd.md` |
| 2 视觉设计 | `docs/design.md`、`docs/ui-prototypes/` |
| 3 技术方案 | `docs/techsol.md` |
| 4 准备开发 | `docs/architecture.md` |
| 5 正式开发 | `TODO.md` + 代码 |
| 6 系统测试 | `docs/test-report.md` |
| 7 部署交付 | 项目 README、文档同步、版本标签（经授权） |

深度说明：[docs/workflow.md](./docs/workflow.md) · 使用：[docs/usage.md](./docs/usage.md)

---

## 仓库结构

```text
SKILL.md                 # 核心 Skill（可单独分发）
README.md / README.en.md
CONTRIBUTING.md / CHANGELOG.md / LICENSE
docs/
  installation.md
  usage.md
  workflow.md
  compatibility.md
  faq.md
  templates/             # 阶段产出模板
  examples/sample-todo-app/
```

---

## 文档索引

| 文档 | 说明 |
| ---- | ---- |
| [SKILL.md](./SKILL.md) | Agent 必须遵循的完整工作流 |
| [installation.md](./docs/installation.md) | 安装 |
| [compatibility.md](./docs/compatibility.md) | 多端兼容 |
| [usage.md](./docs/usage.md) | 使用 |
| [workflow.md](./docs/workflow.md) | 阶段设计理由 |
| [faq.md](./docs/faq.md) | 常见问题 |
| [templates/](./docs/templates/) | PRD 等模板 |
| [sample-todo-app](./docs/examples/sample-todo-app/) | 示例产物 |

---

## 贡献

欢迎改进工作流、文档、模板与示例。请阅读 [CONTRIBUTING.md](./CONTRIBUTING.md)。

## 许可证

[MIT](./LICENSE) © DuXingLang

# 🚀 VibeCoding — Idea to Product

> 从产品想法到交付上线的全流程 AI 开发规范  
> 一套为 Claude Code 设计的 Agent Skill，引导 AI 助手按 7 阶段标准化流程，将你的产品想法落地为可交付的完整产品。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-8A2BE2)](https://claude.ai/code)

---

## 📖 简介

**VibeCoding — Idea to Product** 是一个 Claude Code Agent Skill，它定义了一套完整的、可落地的产品开发工作流：

> **PRD → UI 原型 → 技术方案 → 准备开发 → 小步迭代开发 → 系统测试 → 部署上线**

当你有一个产品想法，但不知道如何开始，或希望 AI 按结构化流程帮助你开发时，这个 Skill 就是为你准备的。它确保每个阶段都有明确的产出物和确认环节，避免 AI 自由发挥、代码失控。

---

## ✨ 核心特性

| 特性 | 说明 |
|------|------|
| 🧩 **7 阶段标准化流程** | 从产品定位到部署上线的完整闭环 |
| ✅ **逐阶段确认机制** | 每阶段结束必须开发者确认，避免方向跑偏 |
| 📄 **文档驱动** | 自动生成 PRD、设计规范、技术方案、架构文档 |
| 🎨 **高保真原型** | 产出可交互的 HTML/CSS/JS 原型，浏览器中直接预览 |
| 📐 **Mermaid 图表** | 自动绘制流程图、架构图、ER 图 |
| 🔄 **小步迭代** | 一次只做一件事，每次修改前明确范围与验收标准 |
| 🛡️ **核心逻辑保护** | 禁止 AI 擅自修改认证、支付等关键流程 |
| 🧪 **全量测试** | 单元测试 + 状态覆盖 + 需求回溯 |

---

## 🚦 快速开始

### 前置条件

- [Claude Code](https://claude.ai/code) 已安装
- Claude Code 能访问本项目的 `SKILL.md`

### 安装

#### 方式一：直接使用（推荐）

```bash
# 克隆项目
git clone https://github.com/<你的用户名>/vibecoding-idea-to-product.git

# 在 Claude Code 中启动项目
cd vibecoding-idea-to-product
claude
```

然后在 Claude Code 中直接说：

> "我有一个想法，我想做一个产品"

Claude 会自动识别并进入本 Skill 定义的工作流。

#### 方式二：作为全局 Skill 安装

将 `SKILL.md` 复制到你的 Claude Code 全局 Skills 目录：

```bash
# 请根据实际路径调整
cp SKILL.md ~/.claude/skills/vibecoding-idea-to-product.md
```

然后在任意项目中，Claude Code 均可识别并调用此 Skill。

---

## 📋 七阶段工作流概览

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│  阶段一      │ →   │  阶段二      │ →   │  阶段三      │ →   │  阶段四      │
│  产品定位    │     │  UI 原型    │     │  技术方案    │     │  准备开发    │
│  → PRD 草稿  │     │  → 设计规范  │     │  → 技术文档  │     │  → 架构文档  │
└─────────────┘     └─────────────┘     └─────────────┘     └─────────────┘
                                                              │
                                                              ▼
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│  阶段七      │ ←   │  阶段六      │ ←   │  阶段五      │
│  部署上线    │     │  系统测试    │     │  正式开发    │
│  → 文档同步  │     │  → 测试报告  │     │  → 小步迭代  │
└─────────────┘     └─────────────┘     └─────────────┘
```

详见 [docs/workflow.md](docs/workflow.md) 了解每个阶段的详细说明。

---

## 🗂️ 项目产出物

每阶段都会在项目 `docs/` 目录下生成对应的文档：

| 阶段 | 产出文件 | 说明 |
|------|----------|------|
| 一 | `docs/prd.md` | 产品需求说明书 |
| 二 | `docs/design.md` | 设计规范与配色方案 |
| 二 | `docs/ui-prototypes/` | 高保真交互原型 |
| 三 | `docs/techsol.md` | 技术实现方案 |
| 四 | `docs/architecture.md` | 开发架构宪法 |
| 五 | `TODO.md` | 任务清单与进度追踪 |
| 六 | `docs/test-report.md` | 全量测试报告 |
| 七 | `README.md` | 项目最终 README |

---

## 🤝 贡献

欢迎参与贡献！请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 了解贡献流程。

---

## 📄 许可证

本项目基于 [MIT 许可证](LICENSE) 开源。

---

## 👤 作者

- **DuXingLang**（独行浪）

---

## ⭐ 支持

如果这个项目对你有帮助，请给一个 Star ⭐，让更多人看到它！

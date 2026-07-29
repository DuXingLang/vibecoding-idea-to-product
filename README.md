# Vibecoding: Idea to Product - Agent Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](./CHANGELOG.md)
[![Multi-Agent](https://img.shields.io/badge/agents-Claude%20Code%20%7C%20Codex%20%7C%20TRAE%20%7C%20Zcode%20%7C%20Cursor-8A2BE2)](./docs/compatibility.md)

**English:** [README.en.md](./README.en.md)

**从产品想法到交付上线的全流程 AI Agent Skill**  
单文件通用，适用于 Claude Code、Codex、TRAE、Zcode、Cursor、Windsurf 等支持 Skills / 自定义规则 / 系统指令的 AI 编程工具。

当你说出「我有一个想法」时，本 Skill 会引导你和 AI 一起，从 Phase 0 前置检查开始，一步步完成产品定位、UI 原型、技术方案、规范锁定、小步迭代开发、测试与部署，确保每一步都边界清晰、输出规范、可回溯、可恢复。

---

## 它能干什么

- **结构化你的模糊想法** → 生成规范 PRD（产品需求文档）
- **可视化交互与设计** → 多种布局方案、Mermaid 流程图、HTML 高保真原型（Fast Track 可压缩）
- **冻结技术选型** → 输出含架构图、数据模型、部署与安全要点的技术方案
- **防止 AI 乱写** → 开发前将规范写入 `docs/`，形成 AI 的约束「宪法」
- **小步安全迭代** → 每次只做一个 TODO；开发前必须确认「六项」范围与验收
- **会话可恢复** → 按 `docs/` 产物推断进度，说「恢复进度」即可接上
- **交付即上线** → 测试报告、文档反扫、项目 README、经你授权的 Git 提交与标签

整个流程严格遵循：

```text
想法 → Phase 0 → PRD → 原型/设计 → 技术方案 → 规范锁定 → 开发 → 测试 → 部署
```

权威行为定义见根目录 [`SKILL.md`](./SKILL.md)。

---

## 快速开始

### 1. 获取 Skill 文件

```bash
git clone https://github.com/DuXingLang/vibecoding-idea-to-product.git
cd vibecoding-idea-to-product
```

核心文件是仓库根目录的 **`SKILL.md`**（可单独复制分发）。流程与产出结构以 `SKILL.md` 为准。

### 2. 在你的 AI 工具中加载

**Claude Code**

```bash
mkdir -p ~/.claude/skills/vibecoding-idea-to-product
cp SKILL.md ~/.claude/skills/vibecoding-idea-to-product/SKILL.md
```

或在项目内使用 `.claude/skills/vibecoding-idea-to-product/SKILL.md`。

**Cursor**

- 将 `SKILL.md` 全文放入项目规则（如 `.cursor/rules`），或 Settings → Rules 中添加；也可在对话中 `@SKILL.md`。

**Windsurf**

- 在项目中按 Windsurf 规则/记忆文件约定引入 `SKILL.md` 内容（以官方文档为准）。

**Codex / TRAE / Zcode / 其它**

- 复制到该产品识别的 Skill / 规则目录，或在项目指令（如 `AGENTS.md`）中声明遵循本 Skill。  
- 详见 [docs/compatibility.md](./docs/compatibility.md)、[docs/installation.md](./docs/installation.md)。路径以各产品**官方文档**为准。

**通用做法**

- 将 `SKILL.md` 作为 system / custom instructions 全文加载。

### 3. 开始对话

在 AI 对话框中输入类似触发语：

> 「我有一个想法，想做一个给健身教练排课的工具，帮我从零开发出来。」

或简短触发：

```text
我有一个想法
我想做一个产品
恢复进度
I have an idea
```

AI 应先进入 **Phase 0**（工作区 / Git / 进度推断 / Full Flow 或 Fast Track），再按门禁推进，不得擅自跨阶段写一堆无关代码。

---

## 工作流程概览

| 阶段 | 核心产出 | 确认后输出 |
| ---- | -------- | ---------- |
| 0、前置检查 | 环境、进度恢复、Full/Fast 模式 | 路由决定 |
| 一、产品定位 | 结构化提问澄清想法 | `docs/prd.md` |
| 二、视觉设计 | 布局、Mermaid 流程、配色、HTML 原型 | `docs/design.md` + `docs/ui-prototypes/` |
| 三、方案设计 | 架构、选型、数据模型、部署与安全 | `docs/techsol.md` |
| 四、准备开发 | 整合规范，形成开发「宪法」 | `docs/architecture.md` |
| 五、正式开发 | 按 `TODO.md` 小步迭代，每步六项确认与验收 | 逐步完成代码 |
| 六、系统测试 | 审查、安全、需求回溯、测试报告 | `docs/test-report.md` |
| 七、部署交付 | 文档同步、README、Git 提交与标签（经授权） | 可交接的项目仓库 |

每一步都需要你确认；AI 不得擅自跨阶段执行。  
深度说明：[docs/workflow.md](./docs/workflow.md) · 使用：[docs/usage.md](./docs/usage.md)

**Fast Track（MVP）**：时间紧、只要验证时，可在 Phase 0 显式选择压缩文档与原型，TODO 仅 P0；可随时补文档升级 Full Flow。

---

## 为什么需要它？

Vibe coding 的最大问题是 AI 容易「跑偏」：  
随便加功能、破坏核心逻辑、架构随意变更、产出无文档、上下文一丢就接不上……

本 Skill 通过在 **开发开始前** 用文档锁定边界，在 **开发过程中** 强制小步确认，在 **开发完成后** 反向同步文档，并在 **新会话** 中按产物恢复进度，让 vibe coding 更接近工程级可交付。

| 常见问题 | 本 Skill 的应对 |
| -------- | --------------- |
| AI 方向跑偏 | 阶段门禁 + 文档驱动 |
| 上下文丢失 | `docs/` 产物推断恢复 |
| 跳过设计直接码 | 原型与 design 规范 |
| 乱引依赖、改核心逻辑 | architecture 宪法 + 禁改清单 |
| 只测快乐路径 | 状态覆盖 + PRD 回溯 + test-report |
| 做完没文档 | 阶段 7 反扫与项目 README |

---

## 示例

- **示意产物**：[docs/examples/sample-todo-app/](./docs/examples/sample-todo-app/)（极简个人待办，阶段 1–4 文档样例）

示例用于对照「文档长什么样」，不是完整可运行业务源码。各阶段空白结构见 [`SKILL.md`](./SKILL.md) 对应章节。

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
  examples/sample-todo-app/
```

---

## 贡献指南

欢迎任何形式的贡献：优化提示词与流程、补充示例、修正文档、改进多端兼容说明。

1. Fork 本仓库  
2. 创建特性分支（`git checkout -b feature/amazing-improvement`）  
3. 提交修改（`git commit -m 'feat: add some amazing improvement'`）  
4. 推送分支并打开 Pull Request  

改行为请先改 `SKILL.md`，再同步 `docs/` 说明文档。详情见 [CONTRIBUTING.md](./CONTRIBUTING.md)。  
Bug 或新想法也可直接开 [Issues](https://github.com/DuXingLang/vibecoding-idea-to-product/issues)。

---

## 许可证

本项目采用 [MIT License](./LICENSE) 开源，可自由使用、修改和分发。  
如果觉得有用，欢迎给个 ⭐️ Star 支持一下。

---

## 适用场景

- 独立开发者从 0 到 1 快速构建产品  
- 非技术背景的创业者与 AI 协作实现 MVP  
- 工程师用 AI 辅助开发时需要约束与可审范围  
- 团队内做 PoC 时统一文档与交付质量  
- 教学：展示如何把模糊想法一步步工程化落地  

---

**让每一个 idea，都能规范地生长为 product。**

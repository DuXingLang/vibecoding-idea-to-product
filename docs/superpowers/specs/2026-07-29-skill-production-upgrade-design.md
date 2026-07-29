# Design: VibeCoding Idea-to-Product Skill 生产级升级

> 日期：2026-07-29  
> 状态：已批准（用户确认方案 B）  
> 范围：单文件通用 Agent Skill + 跨平台兼容 + 中英文 README + 模板/示例/贡献生态

---

## 1. 背景与目标

### 1.1 现状

仓库核心是 `SKILL.md`（约 174 行），定义 7 阶段「想法 → 产品」工作流。已有 `docs/` 安装/使用/FAQ/工作流说明，但：

- README / README.en / CONTRIBUTING / CHANGELOG / CI 等在工作区被删除，需重建
- `SKILL.md` 缺少 Phase 0、进度恢复、失败回退、Fast Track、跨平台 frontmatter
- 无文档模板、无示例、无贡献规范，难以作为生产级生态包发布
- 主要面向 Claude Code，对 Codex / TRAE / Zcode 兼容说明不足

### 1.2 目标

打造**可用于生产**的 Agent Skill 生态包：

1. 优化完善 `SKILL.md`，可在 Claude Code、Codex、TRAE、Zcode 等智能体上使用
2. 生成中英文生产级 `README.md` / `README.en.md`
3. 配套模板、示例、贡献规范、CHANGELOG、安装与多端兼容文档

### 1.3 非目标

- 不实现真实后端/SaaS 产品代码
- 不做成多文件 per-platform Skill（采用单文件通用）
- 不绑定某一家模型 API 或专有插件协议
- 示例仅为文档化产物快照，不要求可运行完整应用

### 1.4 成功标准

| 维度 | 标准 |
|------|------|
| 可安装 | Claude Code / Codex / TRAE / Zcode 安装路径有文档且可照做 |
| 可触发 | 中英触发词明确；description 可被各端 Skill 发现机制识别 |
| 可跑通 | Phase 0 → 7 全流程门禁清晰；可 Fast Track |
| 可恢复 | 根据 `docs/` 产物自动判断阶段并恢复 |
| 可贡献 | CONTRIBUTING + 模板 + 示例齐全 |
| 双语文档 | README 中英完整、结构对等 |

---

## 2. 方案选择

经讨论选定 **方案 B：生产级单文件 + 生态包**：

- 单文件通用 `SKILL.md`（一次维护）
- Phase 0 + 7 阶段 + 门禁 + 恢复 + Fast Track
- 模板 / 示例 / 中英 README / 贡献规范

放弃方案 A（仅轻量增强）与方案 C（平台强分支）。

---

## 3. 仓库架构

```
vibecoding-idea-to-product/
├── SKILL.md                      # 核心：生产级 Agent Skill（单文件通用）
├── README.md                     # 中文主文档
├── README.en.md                  # 英文主文档
├── LICENSE                       # MIT（保留）
├── CHANGELOG.md                  # 版本变更
├── CONTRIBUTING.md               # 贡献指南（中英双语或中文为主+英摘）
├── .gitignore
├── docs/
│   ├── installation.md           # 安装（含多端）
│   ├── usage.md                  # 使用
│   ├── workflow.md               # 工作流深度解析
│   ├── compatibility.md          # 新增：Claude/Codex/TRAE/Zcode 兼容
│   ├── faq.md
│   ├── templates/                # 新增：阶段产出模板
│   │   ├── prd.template.md
│   │   ├── design.template.md
│   │   ├── techsol.template.md
│   │   ├── architecture.template.md
│   │   ├── test-report.template.md
│   │   └── todo.template.md
│   ├── examples/                 # 新增：示例产物
│   │   └── sample-todo-app/
│   │       ├── README.md
│   │       ├── prd.md
│   │       ├── design.md
│   │       ├── techsol.md
│   │       └── architecture.md
│   └── superpowers/specs/        # 设计与计划文档
└── .github/（可选重建）
    ├── ISSUE_TEMPLATE/
    └── workflows/ci.yml          # markdownlint 等轻量 CI
```

**运行时产物**（由 Skill 在用户项目中生成，本仓库 `.gitignore` 忽略）：

- `docs/prd.md` / `design.md` / `techsol.md` / `architecture.md` / `test-report.md`
- `docs/ui-prototypes/`
- `TODO.md`

---

## 4. SKILL.md 设计

### 4.1 Frontmatter（跨平台通用）

```yaml
---
name: vibecoding-idea-to-product
description: >
  End-to-end workflow from product idea to shipped product.
  Covers PRD, UI prototype, tech design, small-step development,
  testing, and deployment. Use when the user wants to build a product
  from scratch, turn an idea into a shippable app, or resume an
  idea-to-product workflow. 从想法到产品的全流程规范。
version: 2.0.0
license: MIT
compatibility: Claude Code, Codex, TRAE, Zcode, Cursor, generic agent
triggers:
  - 我有一个想法
  - 我想做一个产品
  - 帮我从零开发一个
  - 我要从想法到上线
  - 我们一起做个产品吧
  - 从零开始做一个项目
  - 恢复进度
  - I have an idea
  - I want to build a product
  - Build a product from scratch
  - From idea to launch
  - Resume progress
metadata:
  author: DuXingLang
  category: workflow
  tags: [prd, prototype, architecture, iterative-dev, shipping]
---
```

说明：

- `description` 中英混合，兼顾各端语义检索 / 路由
- `triggers` 中英并列；不依赖专有字段的平台可读 description 触发
- `compatibility` 为文档化字段，不强制平台解析

### 4.2 全局行为原则

1. **门禁优先**：每阶段结束必须用户明确确认，方可进入下一阶段
2. **文档驱动**：代码服从 `docs/` 已确认文档；变更先改文档再改代码
3. **单任务聚焦**：开发阶段一次只做一个 TODO 项
4. **平台中立**：不假设特定工具名；用「读取文件 / 写入文件 / 运行命令 / 询问用户」描述动作
5. **双语友好**：用户用中文则中文交互；用英文则英文；文档默认中文，可应要求出英文
6. **安全底线**：禁止硬编码密钥；认证/支付等核心逻辑列入不可擅自修改清单
7. **可恢复**：启动时扫描 `docs/` 与 `TODO.md` 判断进度

### 4.3 Phase 0：前置检查与路由

启动后、进入阶段一之前执行：

| 检查 | 行为 |
|------|------|
| 工作目录 | 空目录 / 已有代码 / 仅有 docs |
| Git | 是否仓库、是否脏工作区；建议初始化但不强制 |
| 进度恢复 | 按产物存在性推断阶段（见下表） |
| 模式 | Full Flow（默认）或 Fast Track（MVP） |
| 想法状态 | 已有明确想法 / 需 brainstorm |

**进度推断规则（优先级从高到低）：**

| 已有产物 | 推断位置 |
|----------|----------|
| `docs/test-report.md` + 完整 docs | 阶段七或已完成 |
| `TODO.md` 且有未勾选项 + architecture | 阶段五进行中 |
| `docs/architecture.md` | 阶段四完成 → 可进五 |
| `docs/techsol.md` | 阶段三完成 → 可进四 |
| `docs/design.md` 或 `ui-prototypes/` | 阶段二完成 → 可进三 |
| `docs/prd.md` | 阶段一完成 → 可进二 |
| 无上述产物 | 从阶段一（或 Phase 0 brainstorm）开始 |

恢复时必须向用户展示推断结果并确认，禁止静默跳阶段。

### 4.4 七阶段（保留并强化）

| 阶段 | 名称 | 关键产出 | 退出门禁 |
|------|------|----------|----------|
| 1 | 产品定位 | `docs/prd.md` | 用户确认 PRD |
| 2 | 视觉设计 | `docs/design.md` + `docs/ui-prototypes/` | 用户确认原型与规范 |
| 3 | 方案设计 | `docs/techsol.md` | 用户确认技术选型 |
| 4 | 准备开发 | `docs/architecture.md` | 用户确认「宪法」锁定 |
| 5 | 正式开发 | `TODO.md` + 代码 | 每任务六项确认 + 验收 |
| 6 | 系统测试 | `docs/test-report.md` | 需求回溯通过 |
| 7 | 部署交付 | 项目 `README.md` + 版本标签建议 | 文档与代码一致 |

各阶段具体步骤以现有 `SKILL.md` 为骨架增强：

- 阶段一：问题清单 + PRD 结构；每次 1–2 问；可引用 `docs/templates/prd.template.md`
- 阶段二：3 布局 → Mermaid 流程 → 2–3 配色 → HTML 原型 → design.md
- 阶段三：先问技术偏好 → 架构/选型/数据模型/部署/集成/外部资源
- 阶段四：锁定 docs，写 architecture（含 AI 引用规则与禁止破坏清单）
- 阶段五：生成 TODO；每轮强制六项模板；验收含主流程/加载/空/错/单测
- 阶段六：审查 + 单测 + PRD 回溯 + 整体验收 + test-report
- 阶段七：反扫代码更新 architecture；写 README；建议 commit + tag（不自动 force push）

### 4.5 Fast Track（MVP 快车道）

适用：用户明确只要 MVP / 原型验证 / 时间紧。

| 阶段 | Fast Track 行为 |
|------|-----------------|
| 1 | 压缩提问（用户/问题/形态/P0 功能/成功标准） |
| 2 | 可跳过完整 HTML 原型，仅 design 要点 + 关键线框描述 |
| 3 | 推荐默认栈，简化部署与集成 |
| 4 | 精简 architecture（栈 + 目录 + 禁改清单 + 验收） |
| 5 | TODO 仅 P0 |
| 6 | 主流程 + 关键异常；可标注已知限制 |
| 7 | 最小 README |

进入 Fast Track 必须用户显式同意；可随时升级回 Full Flow（补文档后继续）。

### 4.6 开发迭代六项模板（阶段五）

每任务开始前必须输出并等待确认：

```
📌 修改目标：
📁 允许修改范围：
🚫 不允许破坏的逻辑：
⚡ 对其它模块的影响：
✅ 验收标准：
🧪 测试计划：
```

用户确认前禁止写业务代码。

### 4.7 回溯与变更

任意阶段若修改更早产物：

1. 更新对应 `docs/*`
2. 重新取得用户确认
3. 评估对下游文档/代码的影响并列出需同步项
4. 再继续当前阶段

### 4.8 失败与降级

| 情况 | 处理 |
|------|------|
| 用户拒绝某阶段方案 | 修订后再次确认，不跳过门禁 |
| 测试失败 | 当前任务内修复；不扩大范围 |
| 环境无法跑测试 | 记录于 test-report，给出手工验收步骤 |
| 缺少外部 Key | 列入外部资源清单，用 mock/跳过策略并文档化 |
| 平台无某工具 | 降级为纯文本步骤（如无法开浏览器则描述预览方式） |

### 4.9 与模板的关系

Skill 正文保留完整结构说明（保证单文件可独立分发）；`docs/templates/*` 为可选详细骨架。Agent 写产物时应优先对齐模板标题层级。

---

## 5. 文档与生态

### 5.1 README.md / README.en.md

对等结构：

1. 标题 + 一句话价值 + Badge（License / Multi-Agent）
2. 简介与流程图
3. 为什么需要（痛点表）
4. 核心特性
5. 支持的智能体（Claude Code / Codex / TRAE / Zcode / 通用）
6. 快速开始（安装 + 触发词 + 验证）
7. 七阶段 + Phase 0 概览
8. 产出物表
9. Fast Track 说明
10. 目录结构
11. 文档索引
12. 贡献 / License

中文为默认主 README；英文为 `README.en.md`，并在文首互相链接。

### 5.2 docs/compatibility.md

按平台说明：

| 平台 | 安装路径建议 | 触发方式 | 注意 |
|------|--------------|----------|------|
| Claude Code | `~/.claude/skills/<name>/SKILL.md` 或项目 skills | description / 触发词 | 官方 Skill 目录约定 |
| Codex | 项目 AGENTS.md 引用或 skills 目录 | 用户指令 + description | 以 OpenAI Codex 习惯为准 |
| TRAE | 项目规则 / Skill 导入 | 触发词 | 按 TRAE 文档放置 |
| Zcode | 项目 Skill / 规则文件 | 触发词 | 按 Zcode 文档放置 |
| 通用 | 将 SKILL.md 内容贴入系统提示或规则 | 手动声明 | 最低兼容保证 |

原则：**不编造未验证的绝对路径**；对不确定路径写「请以该产品官方文档为准」，并给出通用做法（复制 SKILL.md 到 agent skills 目录 / 在规则中 `@` 引用）。

### 5.3 模板

六个模板均含：标题、适用阶段、必填章节、可选章节、确认清单。语言：简体中文（模板内可注英文标题别名）。

### 5.4 示例 `sample-todo-app`

虚构「个人待办 Web 应用」MVP，展示阶段一至四产物样例 + 示例 README，证明文档骨架可落地。不要求含完整应用源码。

### 5.5 CONTRIBUTING / CHANGELOG

- CONTRIBUTING：如何改 SKILL、模板、文档；PR 要求；行为准则简述
- CHANGELOG：Keep a Changelog 格式；先写 `2.0.0` 升级说明

### 5.6 可选 CI

重建轻量 `markdownlint` CI 与 issue 模板；若与「生产 Skill」无强相关，可作实现后期可选任务。

---

## 6. 受众与语气

- **混合受众**：工程师为主、兼顾非技术独立开发者
- Skill 正文：指令式、可执行、短句；关键规则加粗或列表
- README：价值驱动 + 可扫描表格；少行话或行话带解释
- 默认中文交互；英文用户英文交互

---

## 7. 实现顺序（供 writing-plans 使用）

1. 重写 `SKILL.md` v2.0.0
2. 写 `docs/templates/*`
3. 写 `docs/examples/sample-todo-app/*`
4. 更新 `docs/installation.md` / `usage.md` / `workflow.md` / `faq.md`
5. 新增 `docs/compatibility.md`
6. 写 `README.md` + `README.en.md`
7. 写 `CONTRIBUTING.md` + `CHANGELOG.md`
8. 调整 `.gitignore`（如需）
9. 可选：恢复 `.github` 轻量配置
10. 自检：链接有效、中英对等、模板与 Skill 章节一致

---

## 8. 风险与缓解

| 风险 | 缓解 |
|------|------|
| 各 Agent 目录约定变更 | compatibility 写「官方文档优先」+ 通用复制法 |
| SKILL 过长导致上下文压力 | 结构分层、列表化；模板外置；Fast Track 减负 |
| 示例与真实流程漂移 | 示例注明「示意」；与模板同源结构 |
| 工作区已删 README 等 | 实现时重建，不依赖 git 恢复旧内容（可参考 git 历史文案） |

---

## 9. 批准记录

- 优化重点：整体生产级重做
- 目标用户：混合受众
- 阶段结构：7 阶段 + Phase 0
- 兼容策略：单文件通用 Skill
- 成功标准：完整生态包
- 方案：B
- 设计四节：架构 / SKILL / 文档生态 / 质量范围 —— 全部批准（2026-07-29）

# 常见问题（FAQ）

## 基础

### 这个 Skill 是做什么的？

定义 **Phase 0 + 7 阶段** 的标准化工作流，引导兼容的编码智能体从想法走到可交付产品，并生成 PRD、设计、技术方案、架构、测试报告等文档。

### 需要会编程吗？

不必先会写代码；需要能描述想法、做选择、确认门禁。复杂上线与账号/密钥仍需你提供或审批。

### 支持哪些产品形态？

网站、小程序、App、桌面、插件、API、CLI 等。无 UI 产品会跳过或弱化视觉原型，改为交互/接口约定。

### 和「随便跟 AI 聊着做」有何不同？

| 自由对话 | 本 Skill |
| -------- | -------- |
| 易跑偏 | 阶段门禁 |
| 文档常缺失 | 文档驱动 |
| 一次大改 | 小步 TODO + 六项确认 |
| 难恢复 | 按 `docs/` 产物恢复 |

---

## 安装与多端

### 如何安装？

见 [installation.md](./installation.md) 与 [compatibility.md](./compatibility.md)。

### 支持哪些 Agent？

Claude Code、Codex、TRAE、Zcode、Cursor 及能读取 Markdown 规则的通用 Agent。路径以各官方文档为准。

### 触发了但没进 Phase 0？

确认 `SKILL.md` 在 Agent 可读位置；尝试更明确：「请严格按 vibecoding-idea-to-product Skill 从 Phase 0 开始」。

---

## 工作流

### 必须按顺序吗？

默认是。Fast Track 可压缩内容，但仍建议保留阶段门禁。跳过须你显式承担风险。

### 能改上一阶段吗？

能。更新文档 → 确认 → 处理下游影响。

### 能中途加功能吗？

能。先改 `prd.md`（及设计/技术如需要）→ 确认 → 更新 `TODO.md` → 再开发。

### Full Flow 和 Fast Track？

Full Flow 完整文档与原型；Fast Track 面向 MVP，须显式同意，可再升级补文档。

---

## 质量与安全

### 代码质量如何保障？

六项范围门禁、状态覆盖、阶段 6 回溯与 test-report。仍需你做最终确认；Agent 会犯错。

### 密钥怎么办？

只用环境变量与 `.env.example`；不要把真实密钥写进仓库或发给不明第三方。

---

## 其它

### 有英文文档吗？

有 [README.en.md](../README.en.md)。Skill 正文以中文指令为主，含中英触发词与 description。

### 如何贡献？

见 [CONTRIBUTING.md](../CONTRIBUTING.md)。

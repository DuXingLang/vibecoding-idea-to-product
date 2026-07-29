# 安装指南

## 前置条件

- 已安装至少一种兼容的编码智能体（见 [compatibility.md](./compatibility.md)）
- 有一个产品想法（任何形态：网站、小程序、App、CLI 等）

推荐：[Claude Code](https://claude.ai/code)（CLI 或编辑器扩展）。

---

## 安装方式

### 方式一：直接使用本仓库（适合学习 Skill 本身）

```bash
git clone https://github.com/DuXingLang/vibecoding-idea-to-product.git
cd vibecoding-idea-to-product
# 启动你的 Agent（示例为 Claude Code）
claude
```

然后输入触发词，例如：「我有一个想法，我想做一个产品」。

> 注意：若在本仓库内直接跑完整「做产品」流程，运行时 `docs/prd.md` 等可能与仓库说明文档混在一起。**更推荐方式二/三：在你的空项目目录安装 Skill 再开发。**

### 方式二：作为 Claude Code 全局 / 用户 Skill

以官方 Skills 目录约定为准（路径可能随版本变化）。常见做法：

```bash
mkdir -p ~/.claude/skills/vibecoding-idea-to-product
cp SKILL.md ~/.claude/skills/vibecoding-idea-to-product/SKILL.md
```

在任意项目目录启动 Claude Code，使用触发词即可。

### 方式三：项目级安装

```bash
mkdir -p /path/to/your/project/.claude/skills/vibecoding-idea-to-product
cp SKILL.md /path/to/your/project/.claude/skills/vibecoding-idea-to-product/
cd /path/to/your/project
claude
```

部分环境也支持在项目规则中引用：将 `SKILL.md` 放入 Agent 可读取的 rules/skills 路径，或在对话中 `@SKILL.md`。

### 方式四：Codex / TRAE / Zcode / 通用 Agent

见 [compatibility.md](./compatibility.md)。原则：**复制 `SKILL.md` 到该产品识别的 Skill/规则目录**，或以系统提示/项目指令全文引用。路径以各产品**官方文档**为准。

---

## 验证安装

启动 Agent 后输入：

- `我有一个想法` 或 `I have an idea`
- 或 `恢复进度` / `Resume progress`

若 Agent 开始 **Phase 0 前置检查**（目录、Git、进度推断、Full/Fast 模式），即表示 Skill 已被遵循。

---

## 下一步

- [使用指南](./usage.md)
- [工作流说明](./workflow.md)
- [兼容性](./compatibility.md)

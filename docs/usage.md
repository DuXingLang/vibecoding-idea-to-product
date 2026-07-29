# 使用指南

## 基本用法

在已安装本 Skill 的智能体中，使用以下任一触发语（中英均可）：

```text
我有一个想法
我想做一个产品
帮我从零开发一个
我要从想法到上线
我们一起做个产品吧
从零开始做一个项目
恢复进度

I have an idea
I want to build a product
Build a product from scratch
From idea to launch
Resume progress
```

Agent 应进入 **Phase 0**，再按门禁推进 **7 阶段**（或经你同意的 **Fast Track**）。

---

## 工作流概览

| 阶段 | 你要做的事 | 主要产出 |
| ---- | ---------- | -------- |
| 0 前置 | 确认目录/Git/进度/模式 | 路由决定 |
| 1 定位 | 回答 1–2 个一组的问题 | `docs/prd.md` |
| 2 设计 | 选布局、流程、配色，看原型 | `docs/design.md`、`ui-prototypes/` |
| 3 技术 | 确认或拒绝选型 | `docs/techsol.md` |
| 4 准备 | 锁定架构宪法 | `docs/architecture.md` |
| 5 开发 | 每任务确认「六项」 | `TODO.md` + 代码 |
| 6 测试 | 确认测试报告 | `docs/test-report.md` |
| 7 交付 | 确认 README 与发布动作 | 项目 README、标签建议 |

模板见 [templates/](./templates/)。完整行为见根目录 [SKILL.md](../SKILL.md)。

---

## 关键操作

### 改上一阶段内容

直接说要改什么。Agent 应：更新文档 → 再确认 → 评估下游影响 → 再继续。

### 查看进度

可问：「我们现在到哪个阶段了？」「当前进度如何？」

### 恢复会话

新会话中说「恢复进度」。Agent 应根据 `docs/` 产物推断阶段并**请你确认**，禁止静默跳阶段。

### Fast Track

在 Phase 0 选择 MVP 快车道：少文档、可弱化原型、TODO 仅 P0。可随时要求补文档升级 Full Flow。

### 暂停

使用各产品自带的会话暂停/恢复即可；进度以磁盘上 `docs/` 与 `TODO.md` 为准。

---

## 最佳实践

**建议**

- 回答具体；不对就早说
- 确认门禁前花 1–2 分钟读产出
- 一次一个产品方向

**避免**

- 强行跳过阶段门禁
- 开发中途无文档地大幅改栈
- 同时推进多个无关 TODO

---

## 六项开发模板（阶段 5）

每个编码任务开始前，你应看到并确认：

```text
📌 修改目标：
📁 允许修改范围：
🚫 不允许破坏的逻辑：
⚡ 对其它模块的影响：
✅ 验收标准：
🧪 测试计划：
```

---

## 更多

- [FAQ](./faq.md)
- [工作流深度说明](./workflow.md)
- [示例](./examples/sample-todo-app/)

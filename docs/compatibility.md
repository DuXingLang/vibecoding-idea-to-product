# 多 Agent 兼容性说明

本 Skill 以**单文件** [SKILL.md](../SKILL.md) 分发，用通用 frontmatter + 流程正文，避免绑定单一厂商专有协议。

**原则**：安装路径以各产品**当前官方文档**为准；下表为常见做法与建议，若与官方冲突，**以官方为准**。通用保底：把 `SKILL.md` 放进 Agent 能读到的规则/技能目录，或在对话中显式引用。

---

## 总览

| 平台 | 建议做法 | 触发 |
| ---- | -------- | ---- |
| Claude Code | 用户或项目 `skills/<name>/SKILL.md` | description 语义 + 触发词 |
| Codex | 项目 skills / 指令文件中引用 | 用户指令 + description |
| TRAE | 按 TRAE 的 Skill/规则导入方式 | 触发词或 @ 文件 |
| Zcode | 按 Zcode 的 Skill/规则方式 | 触发词或 @ 文件 |
| Cursor | Rules / 项目文档中引用 SKILL | 用户请求相关任务时 |
| 通用 Agent | 系统提示或工作区粘贴全文 | 手动声明「按该 Skill 执行」 |

---

## Claude Code

1. 将本仓库的 `SKILL.md` 复制到 Skills 目录，例如：  
   `~/.claude/skills/vibecoding-idea-to-product/SKILL.md`  
   或项目内 `.claude/skills/vibecoding-idea-to-product/SKILL.md`
2. 可选复制 `docs/templates/` 到同级，便于 Agent 读取模板
3. 使用中英触发词或描述「从想法做产品 / idea to product」

具体目录名以 Claude Code 当前版本说明为准。

---

## Codex

1. 在项目中增加 Agent 可加载的 skill/指令文件，内容为 `SKILL.md` 或对其的引用  
2. 或在项目级 `AGENTS.md` / 官方推荐的指令入口中写明：执行产品开发时遵循 `SKILL.md`  
3. 用自然语言启动：「Build a product from scratch following the idea-to-product skill」

路径与文件名请核对 OpenAI Codex / 所使用工具链文档。

---

## TRAE

1. 使用 TRAE 提供的「技能 / 规则 / 项目知识」导入能力，上传或链接 `SKILL.md`  
2. 若仅支持工作区文件：将 `SKILL.md` 放在仓库根或 `.trae/` 等官方推荐目录  
3. 用触发词或中文说明启动全流程

---

## Zcode

1. 按 Zcode 文档将 Skill 安装到其技能目录，或把 `SKILL.md` 加入项目规则  
2. 启动时声明遵循 VibeCoding idea-to-product 流程  
3. 若工具能力不足（如不能起浏览器），Skill 要求**降级为文本步骤**，仍保持门禁

---

## Cursor 与其它

- **Cursor**：在 Project Rules 或 `.cursor/rules` 中引用本流程要点，或让用户 `@SKILL.md`  
- **其它编码 Agent**：能读工作区 Markdown 即可；将本文件当作强制工作流说明书

---

## 能力降级

| 能力缺失 | 行为 |
| -------- | ---- |
| 不能执行 shell | 给出命令让用户自行运行，并记录结果 |
| 不能开浏览器 | 说明用本地文件打开 HTML 原型的路径 |
| 不能访问网络 | 跳过在线审计/部署，写入 test-report 限制 |
| 无 Git | 跳过 commit/tag，提醒用户手工版本管理 |

---

## 验证清单

- [ ] Agent 能读到 `SKILL.md`
- [ ] 触发后出现 Phase 0 而非直接乱写代码
- [ ] 每阶段结束有确认门禁
- [ ] 恢复进度时展示推断而非静默跳转

# 贡献指南 / Contributing

感谢关注 **VibeCoding — Idea to Product**。

核心交付物是根目录 [`SKILL.md`](./SKILL.md)：跨 Agent 的 idea→product 工作流。贡献应提升其**完整性、可执行性、清晰度与多端可用性**。

English summary: improve the skill, docs, or examples; open an issue for large structural changes first; keep MIT license headers where applicable.

---

## 欢迎的方向

- 工作流边界情况、门禁与恢复逻辑
- 文档（中/英）、[compatibility](./docs/compatibility.md) 勘误
- [sample-todo-app](./docs/examples/sample-todo-app/) 示例
- 错别字、死链、与 SKILL 不一致之处
- 轻量 CI / issue 模板改进

## 不适合的方向

- 与 idea→product 工作流无关的功能
- 未讨论的破坏性流程重写（请先开 Issue）
- 提交真实密钥、隐私数据或侵权内容
- 将本地 `docs/superpowers/`、`docs/templates/` 提交进仓库（已在 `.gitignore`）

---

## 流程

1. **Issue**：说明问题或提案（可用 Bug / Feature 模板）
2. **Fork** 并建立分支：`feat/…`、`fix/…`、`docs/…`
3. **改动**：
   - 改行为 → 先改 `SKILL.md`，再同步 `docs/workflow.md`、`usage.md` 等说明
   - 仅文档 → 保持中英 README 关键部分对等
4. **自检**：链接可点；说明文档与 SKILL 一致；无占位「TBD」残留在用户可见主路径
5. **PR**：说明动机、改动点、如何验证（例如「按 Phase 0 触发词走读」）

---

## 提交信息

建议：`type: 简要说明`（`feat` / `fix` / `docs` / `chore`）。

---

## 行为准则（简）

尊重协作对象；不人身攻击；假设善意；维护者可关闭辱骂或垃圾 PR/Issue。

---

## 许可证

贡献在合并后按仓库 [MIT License](./LICENSE) 授权。

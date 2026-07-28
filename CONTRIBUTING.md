# 贡献指南

感谢你考虑为 **VibeCoding — Idea to Product** 做出贡献！🎉

本项目的核心是一份 `SKILL.md` 文件，它定义了 Claude Code Agent 的 7 阶段工作流。任何贡献都应围绕提升这个工作流的完整性、可用性和清晰度展开。

---

## 🧭 贡献方向

### 欢迎的贡献

- **工作流改进**：完善 7 阶段流程中的细节，增加边界情况处理
- **文档优化**：修正错别字、优化表达、补充示例
- **国际化**：添加英文版本的支持
- **示例补充**：增加更多产品的完整开发案例
- **Bug 修复**：修复流程中的逻辑漏洞或不一致

### 不适合的贡献

- 与产品开发工作流无关的功能
- 破坏现有流程结构的重大改动（建议先开 Issue 讨论）

---

## 🚀 贡献流程

### 1. 开 Issue

在提交代码之前，请先创建一个 Issue 描述你想要做的改动：

- Bug 报告：使用 [Bug Report 模板](.github/ISSUE_TEMPLATE/bug-report.md)
- 功能建议：使用 [Feature Request 模板](.github/ISSUE_TEMPLATE/feature-request.md)

### 2. Fork & Branch

```bash
# Fork 本仓库，然后 clone 你的 fork
git clone https://github.com/<你的用户名>/vibecoding-idea-to-product.git
cd vibecoding-idea-to-product

# 创建功能分支
git checkout -b feat/your-feature-name
```

### 3. 提交改动

```bash
git add .
git commit -m "feat: 简洁描述你的改动"
```

提交信息请遵循 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/) 规范：

| 类型 | 说明 |
|------|------|
| `feat` | 新功能或工作流改进 |
| `fix` | Bug 修复 |
| `docs` | 文档更新 |
| `refactor` | 重构 |
| `test` | 测试相关 |
| `chore` | 构建/工具链相关 |

### 4. 发起 Pull Request

- 确保描述清楚你的改动内容和动机
- 关联相关的 Issue 编号
- 等待维护者 review

---

## 📝 编码规范

### SKILL.md 编辑规范

1. **保持阶段完整性**：7 阶段结构不可随意增减，新增内容应归入合适阶段
2. **Mermaid 图表**：确保所有图表可直接渲染，语法正确
3. **中英文混杂**：技术术语可保留英文，其余使用简体中文
4. **前后一致**：新增规则与现有规则不矛盾

### 文档规范

1. 文件使用 UTF-8 编码
2. Markdown 文件每行不超过 120 字符
3. 代码块标注语言类型

---

## 🙋 常见问题

**Q: 我想修改 SKILL.md 中的某个流程，但不确定是否合适？**  
A: 先开 Issue 讨论，描述你的想法和理由，维护者会给你反馈。

**Q: 发现文档中有错别字，可以直接提 PR 吗？**  
A: 当然可以！小修复不需要先开 Issue，直接提 PR 即可。

---

再次感谢你的贡献！🚀
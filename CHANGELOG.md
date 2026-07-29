# 更新日志

本文件遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.0.0/)，版本号遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)。

## [2.0.0] — 2026-07-29

### Added

- 跨平台 frontmatter：`version`、`compatibility`、`metadata`、中英 `description` / `triggers`
- Phase 0：**产物推断恢复**、Full Flow / **Fast Track**、想法 brainstorm 路由
- `docs/examples/sample-todo-app/` 示意产物
- `docs/compatibility.md` 多 Agent 安装与降级说明
- 生产级中英 `README.md` / `README.en.md`
- 重建 `CONTRIBUTING.md`、本 CHANGELOG、Issue 模板

### Changed

- `SKILL.md` 全面重写为 v2.0.0 生产级单文件工作流
- `docs/installation.md` / `usage.md` / `workflow.md` / `faq.md` 对齐 v2
- 全局规则强化：冲突仲裁、失败降级、平台中立表述

### Removed

- 对单一厂商路径的硬编码依赖（改为「官方文档优先 + 通用复制法」）
- 仓库不再跟踪 `docs/templates/`、`docs/superpowers/`（本地开发用，见 `.gitignore`）

## [1.0.0] — 2026-07-28

### Added

- 初始 7 阶段工作流与基础文档

[2.0.0]: https://github.com/DuXingLang/vibecoding-idea-to-product/releases/tag/v2.0.0
[1.0.0]: https://github.com/DuXingLang/vibecoding-idea-to-product/releases/tag/v1.0.0

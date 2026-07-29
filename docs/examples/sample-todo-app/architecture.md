# 架构规范 — 极简个人待办（示例）

**状态**：已锁定（示例）

## 1. 技术栈清单

| 类别 | 名称 | 版本 |
| ---- | ---- | ---- |
| 构建 | Vite | 5.x |
| UI | React | 18.x |
| 语言 | TypeScript | 5.x |
| 测试 | Vitest | 1.x+ |

## 2. 目录结构

```text
src/
  components/
  domain/todo.ts
  repo/localStorageTodoRepo.ts
  App.tsx
  main.tsx
tests/
docs/
```

## 3. AI 引用规则

- 仅使用上表依赖；新增须先改本文档
- 禁止引入未声明的状态库/UI 套件（本示例刻意保持轻量）

## 4. 禁止破坏的核心逻辑

| 模块 | 原因 |
| ---- | ---- |
| `localStorageTodoRepo` 的序列化格式 | 用户数据兼容 |
| Todo `id` 生成与唯一性 | 列表键与更新正确性 |

## 5. 验收标准（P0）

- 可新增、切换完成、删除
- 刷新后数据仍在
- 空列表有引导
- 核心域逻辑有单元测试

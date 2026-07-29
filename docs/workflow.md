# 七阶段工作流深度解析（v2）

**VibeCoding — Idea to Product** 在 v2 中采用 **Phase 0 + 7 阶段**，并支持 **Full Flow / Fast Track**。权威行为定义见根目录 [SKILL.md](../SKILL.md)。

---

## 整体流程

```text
Phase 0 前置检查与路由
    ↓
阶段1 产品定位 → prd.md
阶段2 视觉设计 → design.md + ui-prototypes/
阶段3 技术方案 → techsol.md
阶段4 准备开发 → architecture.md（锁定）
阶段5 正式开发 → TODO.md + 代码
阶段6 系统测试 → test-report.md
阶段7 部署交付 → README + 文档同步
```

---

## Phase 0

**目标**：环境、进度、模式、想法清晰度。

**进度推断**（高优先匹配在前）：test-report → 进行中 TODO+architecture → architecture → techsol → design/ui → prd → 无则从阶段 1。

必须向用户展示推断并确认。

---

## 阶段 1：产品定位

结构化提问（每次 1–2 问）→ PRD 草稿 → 自检 → 确认 → `docs/prd.md`。

**设计理由**：先锁方向，降低「代码写偏」成本。

---

## 阶段 2：视觉设计

3 布局 → Mermaid 流程 → 2–3 配色 → HTML 原型（或 Fast Track 线框）→ `design.md`。

**设计理由**：先看见再编码，暴露需求漏洞。

---

## 阶段 3：技术方案

偏好收集或推荐 → 架构/数据/部署/安全/性能/外部资源 → 冻结 `techsol.md`。

**设计理由**：选型变更越晚越贵。

---

## 阶段 4：准备开发

`architecture.md` 作为宪法：栈、目录、AI 引用规则、禁改清单、验收。

**设计理由**：约束 Agent 发挥边界。

---

## 阶段 5：正式开发

`TODO.md` + **六项门禁** + 状态覆盖验收 + 小步提交。

**设计理由**：限制单次变更半径，可审可回滚。

---

## 阶段 6：系统测试

审查、安全、性能（量力）、测试、PRD 回溯、`test-report.md`。

**设计理由**：补齐快乐路径之外的真实质量。

---

## 阶段 7：部署交付

反扫文档、README、可选 CI/API 文档、经授权的 tag。

**设计理由**：交付物可交接，而不是「只有对话记录」。

---

## Fast Track

用户显式同意后的 MVP 路径：压缩提问与原型、默认栈、仅 P0、精简测试与 README。可升级回 Full Flow。

---

## 全局规则摘要

- 回溯：改文档 → 确认 → 同步下游  
- 冲突：指出并请用户裁定  
- 恢复：产物推断 + 确认  
- 降级：缺工具/缺 Key 时文档化限制  
- 单任务聚焦、禁止未声明依赖  

细节与确认清单以 SKILL.md 为准。

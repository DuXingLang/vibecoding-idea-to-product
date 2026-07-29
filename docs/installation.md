# 安装指南

## 前置条件

- 已安装 [Claude Code](https://claude.ai/code)（支持 Claude Code 的 CLI 或 VS Code 扩展）
- 拥有一个产品想法（任何形态：网站、小程序、App、CLI 工具等）

---

## 安装方式

### 方式一：直接使用（推荐）

最适合"从零开始"的新项目。

```bash
# 1. 克隆本项目
git clone https://github.com/<你的用户名>/vibecoding-idea-to-product.git
cd vibecoding-idea-to-product

# 2. 进入 Claude Code 交互模式
claude

# 3. 告诉 Claude 你的想法
# 输入："我有一个想法，我想做一个产品"
```

Claude 会自动识别 Trigger 关键词并进入本 Skill 的工作流。

### 方式二：作为全局 Skill 安装

适合在**多个已有项目**中使用本流程。

```bash
# 1. 创建 Claude Code 的 Skills 目录（如不存在）
mkdir -p ~/.claude/skills

# 2. 将 SKILL.md 复制到全局 Skills 目录
cp SKILL.md ~/.claude/skills/vibecoding-idea-to-product.md

# 3. 在任意项目目录中启动 Claude Code
cd /path/to/your/project
claude

# 4. 输入触发词即可启动
# "我有一个想法"
```

### 方式三：项目级安装

适合在**特定项目**中使用本流程。

```bash
# 将 SKILL.md 放置到项目根目录
cp SKILL.md /path/to/your/project/
cd /path/to/your/project
claude
```

---

## 验证安装

启动 Claude Code 后，输入以下任一触发词：

- "我有一个想法"
- "我想做一个产品"
- "帮我从零开发一个"
- "我要从想法到上线"

如果 Claude 回复了阶段一的产品定位需求信息收集，说明安装成功。

---

## 下一步

查看 [使用指南](usage.md) 了解完整的 7 阶段工作流如何使用。

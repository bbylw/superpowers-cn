# Superpowers

> **汉化说明**：本文档由 [https://github.com/obra/superpowers](https://github.com/obra/superpowers) 进行中文翻译。

Superpowers 是一个完整的软件开发工作流程，专为你的编码智能体设计，基于一组可组合的"技能"和一些初始指令构建，确保你的智能体能够正确使用它们。

## 工作原理

从你启动编码智能体的那一刻开始。当它发现你正在构建某些东西时，它*不会*直接跳进去尝试编写代码。相反，它会退后一步，询问你真正想要做什么。

一旦它通过对话梳理出了规范，它会以足够简短的块形式展示给你，让你能够真正阅读和消化。

在你确认设计后，你的智能体会制定一个足够清晰的实现计划，即使是像一位热情但缺乏判断力、没有项目背景且厌恶测试的初级工程师也能遵循。它强调真正的红/绿 TDD、YAGNI（你不会需要它）和 DRY 原则。

接下来，一旦你说"开始"，它就会启动一个*子智能体驱动开发*流程，让智能体完成每个工程任务，检查和审查他们的工作，并继续推进。Claude 通常能够自主工作数小时而不会偏离你制定的计划。

还有更多内容，但这就是系统的核心。而且由于技能会自动触发，你不需要做任何特殊的事情。你的编码智能体天生就拥有 Superpowers。


## 赞助

如果 Superpowers 帮助你完成了一些赚钱的事情，并且你愿意的话，我非常感谢你能考虑[赞助我的开源工作](https://github.com/sponsors/obra)。

谢谢！

- Jesse


## 安装

**注意：** 安装方式因平台而异。Claude Code 或 Cursor 有内置插件市场。Codex 和 OpenCode 需要手动设置。

### Claude Code 官方市场

Superpowers 可通过[官方 Claude 插件市场](https://claude.com/plugins/superpowers)获取

从 Claude 市场安装插件：

```bash
/plugin install superpowers@claude-plugins-official
```

### Claude Code（通过插件市场）

在 Claude Code 中，首先注册市场：

```bash
/plugin marketplace add obra/superpowers-marketplace
```

然后从此市场安装插件：

```bash
/plugin install superpowers@superpowers-marketplace
```

### Cursor（通过插件市场）

在 Cursor Agent 聊天中，从市场安装：

```text
/add-plugin superpowers
```

或在插件市场中搜索"superpowers"。

### Codex

告诉 Codex：

```
Fetch and follow instructions from https://raw.githubusercontent.com/obra/superpowers/refs/heads/main/.codex/INSTALL.md
```

**详细文档：** [docs/README.codex.md](https://github.com/obra/superpowers/blob/main/docs/README.codex.md)

### OpenCode

告诉 OpenCode：

```
Fetch and follow instructions from https://raw.githubusercontent.com/obra/superpowers/refs/heads/main/.opencode/INSTALL.md
```

**详细文档：** [docs/README.opencode.md](https://github.com/obra/superpowers/blob/main/docs/README.opencode.md)

### Gemini CLI

```bash
gemini extensions install https://github.com/obra/superpowers
```

更新：

```bash
gemini extensions update superpowers
```

### 验证安装

在你选择的平台中开始一个新会话，并询问一些应该触发技能的内容（例如，"帮我规划这个功能"或"让我们调试这个问题"）。智能体应该自动调用相关的 superpowers 技能。

## 基本工作流程

1. **头脑风暴（brainstorming）** - 在编写代码前激活。通过提问完善粗略的想法，探索替代方案，分段展示设计以进行验证。保存设计文档。

2. **使用 git worktrees（using-git-worktrees）** - 设计批准后激活。在新分支上创建隔离的工作空间，运行项目设置，验证干净的测试基线。

3. **编写计划（writing-plans）** - 有批准的设计后激活。将工作分解为小任务（每个 2-5 分钟）。每个任务都有确切的文件路径、完整代码、验证步骤。

4. **子智能体驱动开发（subagent-driven-development）或执行计划（executing-plans）** - 有计划后激活。每个任务分派新的子智能体，进行两阶段审查（规范合规性，然后是代码质量），或带人工检查点的批量执行。

5. **测试驱动开发（test-driven-development）** - 实现期间激活。强制执行 RED-GREEN-REFACTOR：编写失败测试，看着它失败，编写最小代码，看着它通过，提交。删除在测试之前编写的代码。

6. **请求代码审查（requesting-code-review）** - 任务之间激活。根据计划审查，按严重程度报告问题。关键问题阻止进度。

7. **完成开发分支（finishing-a-development-branch）** - 任务完成时激活。验证测试，展示选项（合并/PR/保留/丢弃），清理 worktree。

**智能体在任何任务前都会检查相关技能。** 强制性工作流程，而非建议。

## 内容概览

### 技能库

**测试**
- **test-driven-development** - RED-GREEN-REFACTOR 循环（包含测试反模式参考）

**调试**
- **systematic-debugging** - 4 阶段根本原因流程（包含根本原因追踪、纵深防御、基于条件的等待技术）
- **verification-before-completion** - 确保它真正被修复

**协作** 
- **brainstorming** - 苏格拉底式设计精炼
- **writing-plans** - 详细实现计划
- **executing-plans** - 带检查点的批量执行
- **dispatching-parallel-agents** - 并发子智能体工作流
- **requesting-code-review** - 预审查检查清单
- **receiving-code-review** - 响应反馈
- **using-git-worktrees** - 并行开发分支
- **finishing-a-development-branch** - 合并/PR 决策工作流
- **subagent-driven-development** - 带两阶段审查的快速迭代（规范合规性，然后是代码质量）

**元技能**
- **writing-skills** - 遵循最佳实践创建新技能（包含测试方法论）
- **using-superpowers** - 技能系统介绍

## 理念

- **测试驱动开发** - 始终先编写测试
- **系统化优于临时性** - 流程优于猜测
- **复杂性降低** - 简单性作为主要目标
- **证据优于声明** - 在宣布成功前验证

了解更多：[Superpowers for Claude Code](https://blog.fsck.com/2025/10/09/superpowers/)

## 贡献

技能直接存储在此仓库中。要贡献：

1. Fork 本仓库
2. 为你的技能创建分支
3. 遵循 `writing-skills` 技能创建和测试新技能
4. 提交 PR

完整指南请参见 [skills/writing-skills/SKILL.md](https://github.com/obra/superpowers/blob/main/skills/writing-skills/SKILL.md)。

## 更新

更新插件时技能会自动更新：

```bash
/plugin update superpowers
```

## 许可证

MIT 许可证 - 详情请见 LICENSE 文件

## 支持

- **问题反馈**：https://github.com/obra/superpowers/issues
- **市场**：https://github.com/obra/superpowers-marketplace

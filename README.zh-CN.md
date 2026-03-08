# Codex CLI 个人助理初始化提示词合集

[English](./README.md)

这是一组为 Codex CLI 设计的提示词模板，用来把它从一次性问答工具，调整为更稳定、更适合长期协作的本地个人助理工作流。

这些提示词的目标不是“幻想一个完美代理”，而是基于 Codex CLI 的真实行为模型，尽量做到：

- 协作风格更稳定
- 能初始化项目本地记忆结构
- 尽量避免粗暴重写已有内容
- 用轻量 bootstrap 逐步补齐用户偏好

为了适配不同环境，这个仓库提供了三个执行强度不同的版本。

## 这个仓库解决什么问题

很多“个人助理型提示词”写得很完整，但不一定适合 Codex CLI 的真实执行方式。常见问题包括：

- 对全局配置的控制能力估计过高
- 要求每次都读取过多文件
- 过度流程化，容易阻塞正常任务
- 对已有内容的保护不够

这个仓库的提示词就是围绕这些现实约束做的收敛版。

## 仓库内容

- [codex-cli-personal-assistant-prompt-safe.md](./codex-cli-personal-assistant-prompt-safe.md)  
  先审查、后修改。适合第一次试用和已有环境较复杂的情况。

- [codex-cli-personal-assistant-prompt-lite.md](./codex-cli-personal-assistant-prompt-lite.md)  
  平衡版，适合作为大多数场景下的默认版本。

- [codex-cli-personal-assistant-prompt-strong.md](./codex-cli-personal-assistant-prompt-strong.md)  
  更强执行版，适合新项目或你明确希望 Codex 主动推进初始化时使用。

- [codex-cli-personal-assistant-prompt-comparison.md](./codex-cli-personal-assistant-prompt-comparison.md)  
  三个版本的横向对比表。

## 快速开始

1. 打开你要使用的提示词文件。
2. 复制其中完整的 `text` 代码块。
3. 在目标工作区里发给 Codex CLI。
4. 让 Codex 进行工作区检查、配置更新，并在合适时进入轻量 bootstrap。

## 怎么选

| 场景 | 推荐版本 |
| --- | --- |
| 第一次试这套工作流 | `safe` |
| 作为长期默认方案使用 | `lite` |
| 新项目，希望更主动地完成初始化 | `strong` |
| 当前环境里已有较多手写配置 | `safe` |

## 推荐使用顺序

1. 先用 `safe` 观察 Codex 在你环境里的真实行为。
2. 跑顺之后，日常默认切到 `lite`。
3. 明确需要更强推进时，再使用 `strong`。

## 设计原则

- 把全局配置当成默认偏好层，而不是强控制层
- 优先增量编辑，而不是破坏性重写
- 强调项目本地记忆，而不是假设全局“全知”
- 用轻量 bootstrap 代替冗长问卷
- 尽量贴近 Codex CLI 的真实行为边界

## 重要边界

- `~/.codex/AGENTS.md` 更适合被理解为默认偏好层，不是永久强制控制层。
- `.assistant/` 是项目本地记忆约定，不是 Codex CLI 天然内建协议。
- 最终效果仍然取决于当前会话上下文、工具权限和更高优先级指令。

## 适合谁用

如果你希望 Codex CLI 更像下面这些角色，这个仓库会比较有用：

- 可重复使用的项目助理
- 对工作区有感知的协作者
- 能维护轻量本地上下文的工具

如果你只需要偶尔发一个一次性 prompt，不关心本地结构和长期协作，这个仓库的价值会小一些。

## 备注

如果 Codex 在你的环境里表现得过于激进，就退回 `safe`。

如果它推进不足、总是太保守，就切到 `strong`。


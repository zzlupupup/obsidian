---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "Tool 组件"
  - "工具组件"
  - "Tool"
generation_complete: true
---


# Tool

## 定义
Tool 是 Eino ADK 中 Agent 使用的核心组件之一，代表智能体的"执行能力"。在 Agent 架构中，[[concepts/chatmodel|chatmodel]] 提供对话能力，Tool 提供执行能力，二者共同构成 Agent 最核心的组件组合。Agent 可通过添加 tools 来扩展功能，从而支持工具调用、中间件、中断恢复等高级能力。

## 关键特征
- 提供"执行能力"，与 [[concepts/chatmodel|chatmodel]] 的"对话能力"互补，共同构成 Agent 的核心能力
- 可通过添加 tools 扩展 [[concepts/agent|agent]] 的功能边界
- 支持工具调用、中间件、[[concepts/interruptresume|interruptresume]]（中断恢复）等高级能力
- 体现 [[entities/eino|eino]] 中组件可替换、可组合的设计理念
- 是构建复杂智能体应用的关键要素，[[concepts/chatmodelagent|chatmodelagent]] 作为最简单的 Agent 仅使用 ChatModel，后续通过添加 Tool 等能力逐步增强

## 应用
- 为 [[concepts/agent|agent]] 添加工具调用能力，使其能够执行外部操作（如搜索、计算、API 调用等）
- 扩展 [[concepts/chatmodelagent|chatmodelagent]] 的基础功能，构建具备执行能力的智能体
- 配合 [[concepts/interruptresume|interruptresume]] 机制实现可中断恢复的高级交互流程
- 在 [[concepts/react-agent|react-agent]] 等 ReAct 模式智能体中作为"行动"环节的执行单元
- 作为 [[concepts/component|component]] 体系中的一类，体现 Eino 组件化、可组合的架构设计

## 相关概念
- [[concepts/chatmodel|chatmodel]] - 与 Tool 共同构成 Agent 核心组件，提供对话能力
- [[concepts/component|component]] - Tool 是 Eino 组件体系的具体实现
- [[concepts/agent|agent]] - Tool 是 Agent 扩展执行能力的核心组件
- [[concepts/chatmodelagent|chatmodelagent]] - 最简单的 Agent 实现，可通过添加 Tool 增强能力
- [[concepts/interruptresume|interruptresume]] - Tool 支持的高级能力之一
- [[concepts/graph-tool|graph-tool]] - Graph 工具，Tool 的具体实现形式之一
- [[concepts/graphtool-newinvokablegraphtool|graphtool-newinvokablegraphtool]] - 可调用图工具方法

## 相关实体
- [[entities/eino|eino]] - Tool 所属的框架，体现组件可替换、可组合的设计理念

---

## 来源摘录
> "Tool 是 Eino ADK 中 Agent 使用的核心组件之一，代表智能体的'执行能力'。在 Agent 架构中，ChatModel 提供对话能力，Tool 提供执行能力，二者构成 Agent 最核心的组件组合。"
>
> — [[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]

> "Agent 可以通过添加 tools 来扩展功能，包括工具调用、中间件、中断恢复等高级能力。"
>
> — [[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]

> "ChatModelAgent 是最简单的 Agent，内部只使用 ChatModel，后续章节会展示如何添加 Tool 等更多能力。"
>
> — [[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]

## 来源提及

- "**Agent 内部使用 Component** ：最核心的是 `ChatModel` （对话能力）和 `Tool` （执行能力）" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "后续章节会展示如何添加 `Tool` 等更多能力。" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "**可扩展能力** ：可以添加 tools、middleware、interrupt 等" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
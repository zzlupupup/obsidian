---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "Agent 接口"
  - "智能体"
generation_complete: true
---


# Agent

## 定义

Agent 是 [[concepts/adk|adk]] 框架中的核心接口，定义了智能体的基本行为。它包含 `Name()`、`Description()` 和 `Run()` 三个核心方法，其中 `Run()` 接收输入消息并返回 `AsyncIterator[*AgentEvent]` 事件流。Agent 是完整的 AI 应用，封装了完整的业务逻辑，可以直接运行，与 [[concepts/component|Component]] 不同的是，Agent 不再是可复用的单一能力组件，而是面向最终用户的应用实体。

## 关键特征

- **统一抽象**：所有 Agent 类型（如 ChatModelAgent、WorkflowAgent、SupervisorAgent）都实现同一接口，保证一致的调用方式
- **事件驱动**：通过 `AsyncIterator[*AgentEvent]` 事件流输出执行过程，支持流式响应和中间状态追踪
- **可扩展性**：可在不改变接口的前提下添加 tools、middleware、interrupt 等能力
- **完整应用封装**：Agent 封装了完整的业务逻辑，可以直接运行，区别于作为能力组件的 [[concepts/component|Component]]
- **依赖 Component 构建**：Agent 内部使用 Component，最核心的是 [[concepts/chatmodel|chatmodel]]（对话能力）和 Tool（执行能力）

## 应用

- **对话型智能体**：基于 ChatModelAgent 实现多轮对话、问答等场景
- **工作流智能体**：基于 WorkflowAgent 编排复杂的多步骤任务流
- **多智能体协作**：基于 SupervisorAgent 实现多个子 Agent 的调度与协调
- **工具增强型应用**：为 Agent 添加 Tool 能力，实现函数调用、外部系统交互
- **流式响应场景**：通过事件流机制实现实时输出和中间状态反馈

## 相关概念

- [[concepts/adk|adk]] - Agent 所属的开发框架
- [[concepts/component|Component]] - Agent 内部使用的可复用能力组件
- [[concepts/chatmodel|chatmodel]] - Agent 的核心对话能力组件
- [[concepts/chatmodelagent|ChatModelAgent]] - Agent 接口的对话模型实现
- [[concepts/runner|Runner]] - Agent 执行的运行器
- [[concepts/agentevent|AgentEvent]] - Agent 执行过程中输出的事件类型
- [[concepts/asynciterator|AsyncIterator]] - Agent Run() 方法返回的异步迭代器
- [[concepts/react-agent|react-agent]] - 一种常见的 Agent 实现模式

## 相关实体

- [[entities/eino|eino]] - Agent 所属的框架生态

## 来源提及

- "`Agent` 是 ADK 中的核心接口，定义了智能体的基本行为：" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "Agent 是完整的 AI 应用：它封装了完整的业务逻辑，可以直接运行" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "统一抽象：所有 Agent（ChatModelAgent、WorkflowAgent、SupervisorAgent 等）都实现这个接口" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
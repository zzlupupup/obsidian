---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "Agent 输入"
  - "智能体输入"
generation_complete: true
---


# AgentInput

## 定义
AgentInput 是 [[concepts/agent|agent]] 接口中 `Run()` 方法接收的输入参数类型，封装了 Agent 执行所需的输入消息。在 Agent 接口定义中，`Run()` 方法签名为 `Run(ctx context.Context, input *AgentInput, options ...AgentRunOption) *AsyncIterator[*AgentEvent]`，其中 AgentInput 携带了用户输入的消息内容。AgentInput 是 [[concepts/adk|adk]] 事件驱动架构的输入端，与输出端的 [[concepts/agentevent|agentevent]] 形成对应关系。通过 AgentInput，调用方可以向 Agent 传递对话历史、用户消息等信息，启动 Agent 的执行流程。

## 关键特征
- 作为 Agent 接口 `Run()` 方法的核心输入参数类型
- 封装了 Agent 执行所需的输入消息内容
- 是 ADK 事件驱动架构的输入端，与 [[concepts/agentevent|agentevent]] 形成输入输出对应关系
- 通过 AgentInput 可传递对话历史、用户消息等上下文信息
- 作为启动 Agent 执行流程的入口数据结构

## 应用
AgentInput 主要应用于 [[concepts/adk|adk]] 中 Agent 的调用场景。调用方通过构造 AgentInput 对象，将用户输入消息、对话历史等信息传递给 Agent，随后通过 [[concepts/runner|runner]] 触发 Agent 的执行。Agent 执行后返回 `*AsyncIterator[*AgentEvent]` 异步迭代器，实现事件驱动的流式输出处理。在实际开发中，AgentInput 通常在 [[entities/eino|eino]] 框架的 [[concepts/multi-turn dialogue|多轮对话]] 场景中使用，支持将多轮对话上下文传递给 Agent 进行处理。

## 相关概念
- [[concepts/agent|agent]]
- [[concepts/agentevent|agentevent]]
- [[concepts/runner|runner]]
- [[concepts/adk|adk]]
- [[concepts/asynciterator|asynciterator]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "Run(ctx context.Context, input *AgentInput, options ...AgentRunOption) *AsyncIterator[*AgentEvent]" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "`Run()` ：执行 Agent 的核心方法，接收输入消息，返回事件流" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
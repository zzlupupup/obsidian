---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "TypedRunner"
  - "Agent Runner"
generation_complete: true
---


# Runner

## 定义
Runner 是 [[concepts/adk|adk]] 中执行 [[concepts/agent|agent]] 的入口点，负责管理 Agent 的生命周期。Runner 内部持有 Agent 引用、enableStreaming 标志和 [[concepts/checkpoint|checkpoint]] 存储器（CheckPointStore，用于中断恢复的状态存储），将 Agent 的事件流转换为可消费的 [[concepts/asynciterator|asynciterator]]，使 Agent 可以被统一管理并支持 checkpoint、恢复等运行时能力。

## 关键特征
- **生命周期管理**：提供启动、恢复、中断等 Agent 运行时生命周期控制能力
- **Checkpoint 支持**：内部持有 CheckPointStore，支持中断恢复的状态存储
- **统一入口**：通过 `adk.NewTypedRunner[M]` 创建，为 Agent 提供统一的执行入口
- **便捷方法**：提供 `Run()`（传入消息列表）和 `Query()`（传入单个查询字符串）两种便捷调用方式
- **事件流封装**：将 Agent 的事件流转换为可消费的 `AsyncIterator[*TypedAgentEvent[M]]`
- **运行时能力增强**：虽然 Agent 自身提供 `Run()` 方法，但直接调用会缺少 Runner 提供的 checkpoint、恢复等运行时能力

## 应用
- 在需要中断恢复场景中，通过 Runner 管理 [[concepts/chatmodelagent|chatmodelagent]] 的执行，利用 CheckPointStore 保存中间状态
- 在多轮对话应用中，通过 `Run()` 方法传入消息历史列表驱动 Agent 执行
- 在简单查询场景中，通过 `Query()` 方法传入单个查询字符串快速获取 Agent 响应
- 在流式输出场景中，通过 enableStreaming 标志启用流式处理，消费 `TypedAgentEvent` 事件流

## 相关概念
- [[concepts/agent|agent]]
- [[concepts/chatmodelagent|chatmodelagent]]
- [[concepts/agentevent|agentevent]]
- [[concepts/asynciterator|asynciterator]]
- [[concepts/checkpoint|checkpoint]]
- [[concepts/adk|adk]]

## 相关实体
无相关实体。

## 来源提及

- "`Runner` 是执行 Agent 的入口点，负责管理 Agent 的生命周期：" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "Runner 管理 Agent 的启动、恢复、中断等状态" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "Agent 可以被 Runner 统一管理，支持 checkpoint、恢复等运行时能力" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
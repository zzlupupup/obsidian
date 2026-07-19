---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [method]
aliases:
  - "异步迭代器"
  - "流式迭代器"
generation_complete: true
---


# AsyncIterator

## 定义
AsyncIterator 是 [[concepts/adk|adk]] 中用于消费事件流的非阻塞流式迭代器模式。[[concepts/runner|runner]] 的 `Run()` 方法返回 `*AsyncIterator[*AgentEvent]`，消费者通过调用 `Next()` 方法逐个获取事件，该方法会阻塞直到有新事件到达或迭代器关闭。这种设计使得消费者可以实时处理 Agent 执行过程中产生的每个事件，而无需等待整个执行流程完成。

## 关键特征
- **非阻塞流式消费**：通过 `Next()` 方法逐个获取事件，调用时阻塞直到有事件或迭代器关闭，但在等待期间不占用计算资源
- **单次使用**：每次 `runner.Run()` 创建新的迭代器实例，消费一次后不可重复使用
- **事件驱动架构基础**：作为 [[concepts/agent|agent]] 事件驱动架构的核心机制，支持流式响应、中断恢复和状态转移等复杂场景
- **类型安全**：返回 `*AsyncIterator[*AgentEvent]`，明确指定迭代器产出的事件类型为 [[concepts/agentevent|agentevent]]
- **实时性**：允许消费者在模型逐 token 生成回复、Tool 调用穿插执行的过程中实时处理每个事件

## 应用
- **流式响应处理**：在 [[concepts/chatmodelagent|chatmodelagent]] 执行过程中，实时接收并处理模型生成的每个 token 和工具调用事件
- **中断恢复场景**：配合 [[concepts/interruptresume|interruptresume]] 机制，通过事件流捕获中断点，支持后续恢复执行
- **状态转移跟踪**：在复杂 Agent 工作流中，通过事件流实时跟踪 [[concepts/agent|agent]] 的状态变化
- **实时日志与监控**：将事件流导向日志系统或监控面板，实现 Agent 执行过程的可观测性
- **增量结果展示**：在前端界面中逐步展示 Agent 的思考和回复过程，提升用户体验

## 相关概念
- [[concepts/agentevent|agentevent]] - AsyncIterator 产出的基本事件单元
- [[concepts/runner|runner]] - 创建并返回 AsyncIterator 的执行器
- [[concepts/agent|agent]] - 通过 AsyncIterator 暴露流式执行结果的智能体接口
- [[concepts/adk|adk]] - AsyncIterator 所属的 Agent 开发框架
- [[concepts/interruptresume|interruptresume]] - 基于 AsyncIterator 事件流实现的中断恢复机制

## 相关实体
- [[entities/eino|eino]] - AsyncIterator 模式所属的框架实现

## 来源提及

- "`Runner.Run()` 返回的是 `*AsyncIterator[*AgentEvent]`，这是一个非阻塞的流式迭代器。" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "`AsyncIterator` 让你可以实时消费每一个事件。" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "每次 `runner.Run()` 创建新的迭代器，消费一次后不可重复使用。" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
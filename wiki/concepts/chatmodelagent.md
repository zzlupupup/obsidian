---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "ChatModelAgent 实现"
  - "TypedChatModelAgent"
generation_complete: true
---


# ChatModelAgent

## 定义
ChatModelAgent 是 [[concepts/agent|agent]] 接口的最简单实现，基于 [[concepts/chatmodel|chatmodel]] 构建。它通过 `adk.NewChatModelAgent` 或 `adk.NewTypedChatModelAgent[M]` 创建，配置包括 `Name`、`Description`、`Instruction` 和 `Model`。ChatModelAgent 封装了 ChatModel 的调用逻辑，提供统一的 `Run() -> AgentEvent` 输出形态。

## 关键特征
- 最简单的 Agent 实现：直接基于 ChatModel 构建，是 Agent 接口的最基础形态
- 创建方式：通过 [[concepts/adk|adk]] 提供的 `NewChatModelAgent` 或 `NewTypedChatModelAgent[M]` 构造函数创建
- 配置参数：包含 `Name`（名称）、`Description`（描述）、`Instruction`（指令）和 `Model`（模型）四项核心配置
- 统一输出形态：提供 `Run() -> AgentEvent` 的事件驱动输出，与 Runner 编排体系兼容
- 可扩展性：后续可添加 tools、middleware 等能力，支持逐步增强
- 单轮调用特性：在没有 tools 的情况下，一次 `Run()` 只会完成一轮模型调用
- 本质区别于 ChatModel：
  - ChatModel 是 Component（组件），只负责与大语言模型通信并屏蔽不同模型提供商的差异
  - ChatModelAgent 是 Agent（智能体），支持事件驱动、可扩展能力和编排友好（可被 Runner 统一管理）
- 类比关系：ChatModel 类似数据库驱动，ChatModelAgent 类似业务逻辑层

## 应用
- 作为构建自定义智能体的起点，在最简单的 Agent 场景下直接使用
- 作为更复杂 Agent（如带工具调用的 ReAct Agent）的基础形态，后续逐步叠加能力
- 在 Runner 编排框架中作为可被统一管理的智能体节点运行
- 需要统一事件驱动输出形态（AgentEvent）的场景

## 相关概念
- [[concepts/agent|agent]] - ChatModelAgent 实现的接口
- [[concepts/chatmodel|chatmodel]] - ChatModelAgent 构建所依赖的底层模型组件
- [[concepts/adk|adk]] - 提供 ChatModelAgent 构造函数的框架
- [[concepts/runner|runner]] - 可统一管理 ChatModelAgent 的编排器
- [[concepts/agentevent|agentevent]] - ChatModelAgent 的输出事件类型
- [[concepts/component|component]] - ChatModel 所属的组件类型

## 相关实体
无相关实体

## 来源提及

- "`ChatModelAgent` 是最简单的 Agent，它内部只使用了 `ChatModel`，但已经具备了 Agent 的完整能力框架。后续章节会展示如何添加 `Tool` 等更多能力。" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "`ChatModelAgent` 是 Agent 接口的一个实现，基于 ChatModel 构建：" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
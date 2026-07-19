---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "组件"
  - "Eino Component"
generation_complete: true
---


# Component

## 定义
Component（组件）是 Eino 框架中可替换、可组合的能力单元，是构建 AI 应用的基础积木。Component 本身不构成完整的 AI 应用，它仅提供单一能力，需要被组织、编排和执行后才能形成可用的应用逻辑。

## 关键特征
- **可替换性**：Component 作为能力单元，可以在不同实现之间替换，例如 ChatModel 可在 OpenAI、Ark、Claude 等不同模型提供商之间切换
- **可组合性**：多个 Component 可以被组合使用，形成更复杂的功能链路
- **能力单一性**：每个 Component 聚焦于一项具体能力，不封装完整业务逻辑
- **层级关系**：Component 是底层能力单元，[[concepts/agent|Agent]] 是更高层的抽象，Agent 内部使用 Component 并封装完整的业务逻辑
- **屏蔽差异**：Component 负责屏蔽底层实现的差异，例如 [[concepts/chatmodel|ChatModel]] 屏蔽不同大语言模型提供商的接口差异
- **需编排执行**：如果仅有 Component，开发者需要自行管理对话历史、编排调用流程、处理流式输出和实现中断恢复等

## 应用
- **Agent 内部使用**：[[concepts/agent|Agent]] 最核心的 Component 包括 [[concepts/chatmodel|ChatModel]]（对话能力）和 Tool（执行能力）
- **模型通信**：[[concepts/chatmodel|ChatModel]] 作为 Component 的一种，负责与大语言模型通信，屏蔽 OpenAI、Ark、Claude 等提供商的差异
- **应用构建**：通过编排多个 Component 构建完整的 AI 应用，如 [[concepts/rag|RAG]] 场景中组合 Retriever、Embedding 等 Component
- **工作流编排**：在 [[concepts/graph|图编排]] 或 [[concepts/chain|链式编排]] 中，Component 作为节点被组织执行

## 相关概念
- [[concepts/agent|agent]] - Component 的上层抽象，组合多种 Component 并封装完整业务逻辑
- [[concepts/chatmodelagent|chatmodelagent]] - 基于 ChatModel 的 Agent 实现，体现了 Component 与 Agent 的层级关系
- [[concepts/chatmodel|chatmodel]] - Component 的一种核心实现，负责对话能力

## 相关实体
- [[entities/eino|eino]] - Component 所属的框架

## 来源提及

- "第一章我们学习了 **Component**（组件），它是 Eino 中可替换、可组合的能力单元：" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "Component 不构成完整的 AI 应用：它只是能力单元，需要被组织、编排、执行" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "Agent 内部使用 Component：最核心的是 `ChatModel`（对话能力）和 `Tool`（执行能力）" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
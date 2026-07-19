---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources:
  - "[[sources/第八章graph-tool复杂工作流_584c82]]"
  - "[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"
tags:
  - "term"
aliases:
  - "model.BaseChatModel"
  - "model.BaseModel"
generation_complete: true
---

## 关键特征

- **统一调用接口**：通过 `model.BaseChatModel` 定义标准化接口，屏蔽底层不同 LLM 提供商的实现差异
- **核心方法**：提供 `Generate()` 和 `Stream()` 等核心接口，直接返回消息内容，适用于简单对话交互场景
- **多提供商支持**：可通过 [[entities/openai|OpenAI]]、[[entities/ark|Ark]]、Claude 等提供商配置，灵活接入不同的模型服务
- **工作流原生编排**：可作为 [[concepts/workflow|workflow]] 和 [[concepts/graph|graph]] 中的节点被原生编排，参与复杂任务流构建
- **泛型消息支持**：通过泛型接口 `model.BaseModel[M]` 支持不同消息类型，增强类型安全性与扩展性
- **依赖注入友好**：以接口形式作为参数传入 `BuildTool` 等构建函数，实现模型能力与业务逻辑的解耦
- **ADK 核心组件**：在 [[concepts/adk|ADK]] 架构中作为 [[concepts/agent|Agent]] 内部最核心的组件之一，与 Tool（执行能力）共同构成 Agent 的能力基础

## 应用

- 在 [[concepts/graph-tool|graph-tool]] 实现文档问答能力时，用于构建工作流中的评分节点，对检索结果进行相关性打分
- 在答案生成节点中调用 LLM 能力，基于上下文合成最终答案
- 作为 [[concepts/compose|compose]] 工作流的核心节点，参与 [[concepts/rag|rag]]、[[concepts/react-agent|react-agent]] 等复杂场景的编排
- 通过依赖注入方式传入构建函数，使模型实例可在不同工作流间复用
- 作为 [[concepts/chatmodelagent|ChatModelAgent]] 的底层能力支撑，提供最基本的对话交互能力

## 相关概念

- [[concepts/component|component]]
- [[concepts/agent|agent]]
- [[concepts/chatmodelagent|chatmodelagent]]
- [[concepts/adk|adk]]
- [[concepts/workflow|workflow]]
- [[concepts/graph|graph]]
- [[concepts/graph-tool|graph-tool]]
- [[concepts/compose|compose]]
- [[concepts/rag|rag]]
- [[concepts/react-agent|react-agent]]
- [[concepts/node|node]]
- [[concepts/prompt|Prompt]]
- [[concepts/retriever|Retriever]]
- [[concepts/embedding|Embedding]]
- [[concepts/indexer|Indexer]]

## 相关实体

- [[entities/eino|eino]]
- [[entities/eino-ext|eino-ext]]
- [[entities/eino-examples|eino-examples]]
- [[entities/cloudwego|cloudwego]]
- [[entities/openai|openai]]
- [[entities/ark|ark]]

## 来源提及

- "与第一章一致：需要配置一个可用的 ChatModel（OpenAI 或 Ark）。" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "原生编排 Eino 的所有 component （如 ChatModel、Prompt、Tools、Retriever、Embedding、Indexer 等）" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "**Agent 内部使用 Component** ：最核心的是 `ChatModel` （对话能力）和 `Tool` （执行能力）" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
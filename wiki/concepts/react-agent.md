---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/eino_8abb92]]"]
tags: [method]
aliases:
  - "ReAct"
  - "Reasoning and Acting Agent"
generation_complete: true
---


# ReAct Agent

## 定义
ReAct Agent 是一种结合推理（Reasoning）和行动（Acting）的 Agent 设计范式，通过交替执行思考推理与工具调用来完成复杂任务。在 [[entities/eino|eino]] 框架中，ReAct Agent 被列为核心支持的常见应用模式之一，与 [[concepts/rag|rag]] 共同构成框架的典型应用场景。开发者可借助 [[concepts/adk|adk]] 和 [[concepts/compose|compose]] 模块构建 ReAct Agent，实现能够自主推理并调用外部工具的智能体。

## 关键特征
- **推理与行动交替**：Agent 在每一步中先进行推理分析，再决定执行何种行动（如工具调用），形成"思考-行动-观察"的循环
- **工具调用能力**：支持在推理过程中动态调用外部工具，将工具返回结果纳入后续推理
- **框架原生支持**：[[entities/eino|eino]] 框架通过 [[concepts/adk|adk]] 和 [[concepts/compose|compose]] 模块提供开箱即用的 ReAct Agent 构建能力
- **核心应用模式**：与 [[concepts/rag|rag]] 并列为 [[entities/eino|eino]] 框架最常支持的应用模式
- **可扩展性**：可通过 [[entities/eino-ext|eino-ext]] 扩展组件接入更多工具与能力

## 应用
- **智能助手构建**：利用 [[concepts/adk|adk]] 快速搭建具备推理与工具调用能力的 Agent
- **复杂任务编排**：通过 [[concepts/compose|compose]] 模块编排多步骤推理与行动流程
- **示例与原型开发**：在 [[entities/eino-examples|eino-examples]] 中提供 ReAct Agent 的参考实现
- **多 Agent 协作**：可与其他 Agent 模式（如 [[entities/manus-agent|manus-agent]]）结合，构建更复杂的多智能体系统

## 相关概念
- [[concepts/adk|adk]] - Agent Development Kit，提供 Agent 构建的核心能力
- [[concepts/compose|compose]] - eino Compose 模块，支持 Agent 流程编排
- [[concepts/rag|rag]] - 检索增强生成，eino 框架另一核心应用模式

## 相关实体
- [[entities/eino|eino]] - 提供 ReAct Agent 原生支持的框架
- [[entities/manus-agent|manus-agent]] - 可与 ReAct 模式结合的 Agent 示例
- [[entities/eino-ext|eino-ext]] - 为 ReAct Agent 提供扩展组件
- [[entities/eino-examples|eino-examples]] - 提供 ReAct Agent 参考实现

## 来源提及

- "框架支持构建 [[concepts/react-agent|ReAct Agent]] 和 [[concepts/rag|RAG]] 等常见应用模式。" — [[wiki/entities/eino|eino]]
---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "Workflow Agent"
  - "工作流智能体"
generation_complete: true
---


# WorkflowAgent

## 定义
WorkflowAgent 是 [[concepts/adk|adk]] 框架中 [[concepts/agent|agent]] 接口的一种实现类型，与 [[concepts/chatmodelagent|chatmodelagent]] 和 SupervisorAgent 并列。所有 Agent 类型均实现统一的 Agent 接口，体现了"统一抽象"的设计理念。WorkflowAgent 的名称暗示其基于 [[concepts/workflow|workflow]] 编排来构建智能体，是 ADK 框架中比 [[concepts/chatmodelagent|chatmodelagent]] 更复杂的一种 Agent 类型。

## 关键特征
- 实现 [[concepts/agent|agent]] 统一接口，与其他 Agent 类型（如 [[concepts/chatmodelagent|chatmodelagent]]、SupervisorAgent）共享相同的抽象层级
- 基于 [[concepts/workflow|workflow]] 编排机制构建，可能利用 [[concepts/graph|graph]] 或 [[concepts/chain|chain]] 等编排模式
- 作为 ADK 框架中较复杂的 Agent 实现类型，适用于需要多步骤、多节点协同的场景
- 体现 Eino 框架"统一抽象"设计理念，不同复杂度的 Agent 共用同一接口契约

## 应用
适用于需要通过工作流编排来实现复杂逻辑的智能体场景，例如：
- 多步骤任务处理流程，其中各步骤之间存在明确的依赖关系
- 结合 [[concepts/node|node]] 和 [[concepts/edge|edge]] 构建有状态的智能体执行图
- 需要集成多种组件（如 [[concepts/retriever|retriever]]、[[concepts/chatmodel|chatmodel]]、[[concepts/tool|tool]]）的复合型智能体

## 相关概念
- [[concepts/agent|agent]]
- [[concepts/chatmodelagent|chatmodelagent]]
- [[concepts/supervisoragent|supervisoragent]]
- [[concepts/workflow|workflow]]
- [[concepts/graph|graph]]
- [[concepts/compose|compose]]
- [[concepts/adk|adk]]

## 相关实体
- [[entities/eino|eino]]

## 应用
> 所有 Agent（包括 ChatModelAgent、WorkflowAgent、SupervisorAgent 等）都实现统一的 Agent 接口

——来源：[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]

## 来源提及

- "所有 Agent（ChatModelAgent、WorkflowAgent、SupervisorAgent 等）都实现这个接口" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/eino_8abb92]]"]
tags: [method]
aliases:
  - "Compose模块"
  - "eino Compose"
generation_complete: true
---


# Compose

## 定义
Compose 是 [[entities/eino|eino]] 框架中用于组件编排的核心模块。它支持 Chain、Graph、Workflow 等多种编排方式，使开发者能够灵活地组合各种组件构建复杂的应用流程。Compose 与 [[concepts/adk|adk]] 协同工作，ADK 负责 Agent 开发能力，Compose 负责组件编排和流程管理，是 eino 框架实现灵活组件编排和流程管理的关键基础设施。

## 关键特征
- 支持 [[concepts/chain|Chain]]、[[concepts/graph|Graph]]、[[concepts/workflow|Workflow]] 等多种编排模式，适应不同复杂度的应用场景
- 与 [[concepts/adk|adk]]（Agent Development Kit）协同工作，职责分工明确：ADK 负责 Agent 开发，Compose 负责组件编排与流程管理
- 提供灵活的组件组合能力，开发者可按需选择编排方式
- 作为 [[entities/eino|eino]] 框架的基础设施层，支撑上层应用的流程构建

## 应用
- 构建 LLM 应用中的多组件流水线，如将 Prompt 模板、模型调用、输出解析等组件串联为 Chain
- 通过 Graph 编排实现包含条件分支、循环等复杂逻辑的应用流程
- 使用 Workflow 管理长时间运行、多步骤的异步任务流程
- 在 Agent 应用中与 ADK 配合，将 Agent 组件编排到整体业务流程中

## 相关概念
- [[concepts/adk|adk]]
- [[concepts/chain|Chain]]
- [[concepts/graph|Graph]]
- [[concepts/workflow|Workflow]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "eino 框架包含 [[concepts/adk|ADK]]（Agent Development Kit）用于 Agent 开发，[[concepts/compose|Compose]] 模块用于组件编排，以及丰富的组件库。" — [[wiki/entities/eino|eino]]
- "该框架提供了 Agent 开发、组件编排、流程管理等核心能力，支持 Chain、Graph、Workflow 等多种编排方式。" — [[wiki/entities/eino|eino]]
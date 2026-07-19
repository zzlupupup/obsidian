---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources:
  - "[[sources/eino_8abb92]]"
  - "[[sources/第八章graph-tool复杂工作流_584c82]]"
tags:
  - "method"
aliases:
  - "工作流编排"
  - "工作流"
  - "Workflow"
  - "compose.Workflow"
generation_complete: true
---

# Workflow

## 定义
Workflow 是 [[entities/eino|eino]] 框架中 [[concepts/compose|compose]] 模块支持的一种编排方式，允许开发者以工作流的形式组织和执行组件。它适用于需要复杂流程控制和状态管理的场景，提供了比 [[concepts/chain|chain]] 和 [[concepts/graph|graph]] 更高级的流程管理能力，满足不同复杂度的应用需求。

作为 [[entities/eino|eino]] 中构建工作流的核心组件，compose.Workflow 属于 [[concepts/compose|compose]] 包的一部分，提供通用的、确定性的编排能力，适用于需要明确执行路径与可控流程行为的场景。
## 关键特征
- 支持复杂的流程控制逻辑，能够处理条件分支、循环等非线性的执行路径
- 提供状态管理能力，允许在工作流执行过程中维护和传递状态信息
- 与 [[concepts/chain|chain]]、[[concepts/graph|graph]] 一起构成 [[entities/eino|eino]] 框架的核心编排能力
- 面向高级应用场景，在编排层级中提供更强大的流程管理功能
- 通过 `NewWorkflow[Input, Output]()` 创建实例，使用 `AddLambdaNode` 添加节点、`AddInput` 设置数据流向、`End()` 连接结束节点，提供了具体的 API 构建方法
- 能够原生编排 [[entities/eino|eino]] 的所有 component，如 [[concepts/chat-model|ChatModel]]、Prompt、Tools、Retriever 等
- 支持 callback 体系以及 interrupt/resume + checkpoint 机制，实现回调监控与中断恢复能力
## 应用
- 复杂业务流程的组件编排，如多步骤的智能体任务执行
- 需要状态管理和条件判断的多阶段处理流程
- 对流程控制要求较高的应用场景，如需要根据中间结果动态调整执行路径的任务
- 可用于构建包含 load、chunk、score、filter、answer 五个节点的文档问答流水线，最终通过 [[concepts/graphtool-newinvokablegraphtool|graphtool.NewInvokableGraphTool]] 封装为 [[concepts/graph-tool|Graph Tool]]
- Graph Tool 是 compose 工作流的 Tool 化封装，可将 [[concepts/compose-graph|compose.Graph]]、[[concepts/compose-chain|compose.Chain]]、[[concepts/compose-workflow|compose.Workflow]] 等可编译的编排产物包装为 [[entities/agent|Agent]] 可调用的 Tool
## 相关概念
- [[concepts/compose|compose]]
- [[concepts/chain|chain]]
- [[concepts/graph|graph]]
- [[concepts/node|Node]]
- [[concepts/edge|Edge]]
- [[concepts/compose-invokable-lambda|compose.InvokableLambda]]
- [[concepts/graph-tool|Graph Tool]]
- [[concepts/field-mapping|FieldMapping]]
## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "该框架提供了 Agent 开发、组件编排、流程管理等核心能力，支持 Chain、Graph、Workflow 等多种编排方式。" — [[wiki/entities/eino|eino]]
- "`compose.Workflow` 是 Eino 中构建工作流的核心组件：" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "Graph Tool 是 compose 工作流的 Tool 化封装 ：把 `compose.Graph / compose.Chain / compose.Workflow` 这类可编译的编排产物，包装成一个 Agent 可调用的 Tool" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
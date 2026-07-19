---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [method]
aliases:
  - "graphtool"
  - "GraphTool"
  - "Graph 工具"
generation_complete: true
---


# Graph Tool

## 定义
Graph Tool 是 [[entities/eino|eino]] 框架中将 [[concepts/compose|compose]] 工作流封装为 Agent 可调用 Tool 的机制。它将 [[concepts/graph|graph]]、[[concepts/chain|chain]]、[[concepts/workflow|workflow]] 等可编译的编排产物包装成工具入口，使 Agent 能够调用复杂的多步骤工作流。Graph Tool 通过 `graphtool.NewInvokableGraphTool` 函数将编排产物转换为标准 Tool 接口，从而可以被 [[concepts/react-agent|react-agent]] 等 Agent 调用。

## 关键特征
- **编排产物封装**：将 compose.Graph、compose.Chain、compose.Workflow 等可编译产物统一包装为 Tool 入口
- **复用 compose 能力**：继承 [[concepts/compose|compose]] 提供的并行、分支、组合等编排能力
- **状态管理与持久化**：通过 checkpoint 机制保存和恢复工作流运行状态
- **可中断恢复**：支持节点内 interrupt 和工具层面的中断包装，实现运行过程中的暂停与续跑
- **标准 Tool 接口**：通过 `graphtool.NewInvokableGraphTool` 创建的工具遵循 Eino 的 Tool 接口规范，可被任意 Agent 调用

## 应用
- **文档问答系统**：将完整的 RAG 工作流封装为名为 `answer_from_document` 的 Tool，供 Agent 在需要时调用以完成基于文档的问答任务
- **复杂多步骤任务封装**：当某个子任务需要多步骤编排（如检索、重排、生成、校验）时，可将其编排为 Graph 后封装为单一 Tool，简化 Agent 的调用复杂度
- **有状态工作流暴露**：将需要状态管理或可中断恢复的长期运行工作流暴露为 Agent 可调用的工具

## 相关概念
- [[concepts/compose|compose]]
- [[concepts/graph|graph]]
- [[concepts/chain|chain]]
- [[concepts/workflow|workflow]]
- [[concepts/react-agent|react-agent]]
- [[concepts/rag|rag]]
- [[concepts/batchnode|BatchNode]]
- [[concepts/field-mapping|FieldMapping]]
- [[concepts/checkpoint|checkpoint]]
- [[concepts/interrupt-resume|interrupt/resume]]

## 相关实体
- [[entities/eino|eino]]
- [[entities/eino-examples|eino-examples]]

## 来源提及

- "Graph Tool 是 compose 工作流的 Tool 化封装：把 compose.Graph / compose.Chain / compose.Workflow 这类可编译的编排产物，包装成一个 Agent 可调用的 Tool" (Graph Tool 是 compose 工作流的 Tool 化封装：把 compose.Graph / compose.Chain / compose.Workflow 这类可编译的编排产物，包装成一个 Agent 可调用的 Tool) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "支持并行/分支/组合：由 compose 提供（并行、分支、字段映射、子图等），Graph Tool 只是把它们暴露为 Tool 入口" (支持并行/分支/组合：由 compose 提供（并行、分支、字段映射、子图等），Graph Tool 只是把它们暴露为 Tool 入口) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
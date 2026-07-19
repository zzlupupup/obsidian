---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [method]
aliases:
  - "Checkpoint"
  - "检查点"
generation_complete: true
---


# checkpoint

## 定义
checkpoint 是 [[concepts/compose|compose]] 包中的状态持久化机制，用于保存和恢复工作流的运行状态。在 [[concepts/graph-tool|graph-tool]] 中，checkpoint 支持节点间数据传递和运行状态的持久化，使得工作流可以在中断后从保存点恢复执行，而不需要从头开始。这一机制是实现可中断恢复（[[concepts/interrupt-resume|interrupt/resume]]）功能的基础，特别适用于长时间运行的复杂工作流场景。

## 关键特征
- 状态持久化：将工作流的运行状态保存到外部存储，支持后续恢复
- 中断恢复：工作流可在任意节点中断后，从最近的 checkpoint 恢复执行
- 数据传递：在 Graph 的节点间保持和传递中间数据
- 透明性：对工作流编排逻辑透明，开发者无需显式处理状态保存细节
- 长时运行支持：为长时间运行的复杂工作流提供可靠性保障，降低故障重跑成本

## 应用
- 长时间运行的工作流：在执行过程中定期保存状态，避免因故障导致全部重跑
- 交互式工作流：在需要人工介入的节点暂停，等待用户输入后从 checkpoint 恢复执行
- 分布式图编排：跨多个节点的复杂 [[concepts/graph|graph]] 编排中保持上下文一致性
- 故障恢复：系统异常时从最近的 checkpoint 恢复，最大程度降低故障影响范围

## 相关概念
- [[concepts/graph-tool|graph-tool]]
- [[concepts/interrupt-resume|interrupt/resume]]
- [[concepts/compose|compose]]
- [[concepts/workflow|workflow]]
- [[concepts/graph|graph]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "支持状态管理与持久化：节点间传递数据、以及通过 checkpoint 保存/恢复运行状态" (支持状态管理与持久化：节点间传递数据、以及通过 checkpoint 保存/恢复运行状态) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "可中断恢复：Graph Tool 支持 Checkpoint 机制" (可中断恢复：Graph Tool 支持 Checkpoint 机制) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
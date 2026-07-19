---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [method]
aliases:
  - "可中断恢复"
  - "interrupt"
  - "resume"
generation_complete: true
---


# interrupt/resume

## 定义
interrupt/resume 是 [[concepts/compose|compose]] 包中的中断与恢复机制，支持在两个层面使用：工作流内部的中断（在节点中触发 interrupt）和工具层面的中断包装（处理嵌套 interrupt 场景）。在 [[concepts/graph-tool|graph-tool]] 中，该机制允许复杂工作流在特定条件下暂停执行，并在外部条件满足后从 [[concepts/checkpoint|checkpoint]] 保存的状态恢复执行，实现完整的状态保存与恢复，适用于需要人工介入或等待外部条件的复杂业务流程。

## 关键特征
- **双层机制**：支持工作流节点内部触发 interrupt，也支持工具层面对 interrupt 进行包装处理嵌套场景
- **与 checkpoint 配合**：interrupt 暂停执行时通过 [[concepts/checkpoint|checkpoint]] 保存当前状态，resume 时从保存点恢复，保证状态一致性
- **条件驱动暂停**：工作流在特定条件下主动暂停，等待外部条件（如人工审核、外部数据）满足后继续执行
- **嵌套场景支持**：工具层面的中断包装能够处理多层嵌套的 interrupt 调用，避免状态混乱
- **编排能力组成**：作为 [[entities/eino|eino]] 编排能力的重要组成部分，与 [[concepts/graph|graph]]、[[concepts/chain|chain]] 等编排原语协同工作

## 应用
- **人工介入流程**：在需要人工审核或决策的工作流节点处触发 interrupt，等待人工反馈后 resume 继续执行
- **等待外部条件**：工作流执行到某节点时暂停，等待外部事件（如异步任务完成、第三方回调）满足后再恢复
- **复杂 [[concepts/workflow|workflow]] 编排**：在 [[concepts/graph-tool|graph-tool]] 中实现带有暂停-恢复语义的复杂业务流程，如多轮交互、分阶段处理
- **长时间运行任务管理**：对耗时较长的任务进行分段执行，通过 checkpoint 保存中间状态，支持故障恢复和续跑

## 相关概念
- [[concepts/graph-tool|graph-tool]] - interrupt/resume 机制在 Graph Tool 中的核心应用场景
- [[concepts/checkpoint|checkpoint]] - 与 interrupt/resume 配合实现状态保存与恢复
- [[concepts/compose|compose]] - interrupt/resume 机制所属的编排包
- [[concepts/workflow|workflow]] - 中断恢复机制服务的上层工作流编排
- [[concepts/graph|graph]] - 图编排中应用中断恢复机制

## 相关实体
- [[entities/eino|eino]] - interrupt/resume 机制所属的框架

## 来源提及

- "支持可中断恢复：既支持工作流内部的中断（节点里触发 interrupt），也支持工具层面的中断包装（嵌套 interrupt 场景）" (支持可中断恢复：既支持工作流内部的中断（节点里触发 interrupt），也支持工具层面的中断包装（嵌套 interrupt 场景）) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "可中断恢复：Graph Tool 支持 Checkpoint 机制" (可中断恢复：Graph Tool 支持 Checkpoint 机制) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "同时具备完整的 callback 体系，以及 interrupt/resume + checkpoint 支持" (同时具备完整的 callback 体系，以及 interrupt/resume + checkpoint 支持) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
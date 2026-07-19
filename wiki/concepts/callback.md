---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [method]
aliases:
  - "回调"
  - "callback体系"
generation_complete: true
---


# callback

## 定义
callback 是 [[entities/eino|eino]] compose 包提供的完整回调体系，用于在工作流执行过程中进行事件通知和状态追踪。它与 [[concepts/interruptresume|interruptresume]] 和 [[concepts/checkpoint|checkpoint]] 机制共同构成了 compose 的运行时基础设施。callback 体系使开发者能够在工作流的各个阶段插入自定义逻辑（如日志记录、性能监控、错误处理等），为复杂工作流的可观测性和可调试性提供基础支持，是 compose 确定性编排能力的重要组成部分。

## 关键特征
- **全生命周期事件通知**：覆盖工作流执行过程中的节点启动、完成、异常等关键事件
- **运行时基础设施**：与 [[concepts/interruptresume|interruptresume]]、[[concepts/checkpoint|checkpoint]] 共同构成 compose 的运行时支撑层
- **自定义逻辑扩展**：允许开发者在工作流各阶段插入日志、监控、错误处理等自定义逻辑
- **可观测性支持**：为 [[concepts/graph-tool|graph-tool]] 等复杂工作流提供状态追踪与调试能力
- **确定性编排保障**：作为 compose 确定性编排能力的组成要素，确保工作流执行过程可追踪、可重现

## 应用
- **日志与审计**：在工作流节点执行前后记录日志，便于事后审计与问题追溯
- **性能监控**：采集各节点执行耗时、吞吐量等指标，用于性能分析与优化
- **错误处理与告警**：在节点异常时触发告警或执行降级逻辑，提升工作流鲁棒性
- **状态追踪与调试**：结合 [[concepts/checkpoint|checkpoint]] 机制对工作流运行状态进行快照式追踪，辅助调试复杂编排
- **Graph Tool 可观测性**：为 [[concepts/graph-tool|graph-tool]] 中的图编排工作流提供端到端的事件可视化与诊断能力

## 相关概念
- [[concepts/workflow|workflow]]
- [[concepts/graph|graph]]
- [[concepts/compose|compose]]
- [[concepts/checkpoint|checkpoint]]
- [[concepts/interruptresume|interruptresume]]
- [[concepts/graph-tool|graph-tool]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "Eino 的 `compose` 包提供了非常通用、确定性的编排能力：你可以把任何需要"确定性业务流程"的系统，用 `compose` 的 Graph/Chain/Workflow 组织成可执行的流水线" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "同时具备完整的 **callback** 体系，以及 **interrupt/resume + checkpoint** 支持。" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
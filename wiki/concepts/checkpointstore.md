---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "检查点存储"
  - "Checkpoint 存储器"
  - "CheckPointStore"
generation_complete: true
---


# CheckPointStore

## 定义

CheckPointStore 是 [[concepts/runner|runner]] 结构体中的关键字段，用于存储 Agent 执行过程中的状态，以支持中断恢复（interrupt/resume）功能。Runner 配合 CheckPointStore 实现 Agent 的生命周期管理，包括启动、恢复、中断等状态。在 [[concepts/adk|adk]] 运行时框架中，CheckPointStore 是实现 Agent 中断恢复的核心基础设施，使得 Agent 的执行可以在中断后从检查点恢复继续。

## 关键特征

- **状态持久化**：存储 Agent 执行过程中的中间状态，确保中断后可恢复
- **生命周期管理支持**：配合 Runner 实现 Agent 的启动、恢复、中断等状态切换
- **检查点机制**：基于 [[concepts/checkpoint|checkpoint]] 机制，定期或按需保存执行状态
- **中断恢复核心**：是 [[concepts/interruptresume|interruptresume]] 功能实现的基础设施
- **运行时框架组件**：作为 [[concepts/adk|adk]] 运行时框架的关键组成部分

## 应用

- **Agent 中断恢复**：在 Agent 执行过程中遇到中断（如等待用户输入、外部事件触发）时，通过 CheckPointStore 保存当前状态，待条件满足后恢复执行
- **可靠智能体应用**：为构建需要长时间运行或可能被中断的智能体应用提供状态保障
- **多轮对话状态管理**：在 [[concepts/多轮对话|多轮对话]] 场景中，维护对话上下文和执行状态
- **Agent 事件流处理**：配合 [[concepts/agentevent|agentevent]] 事件单元，实现基于事件驱动的状态保存与恢复

## 相关概念

- [[concepts/runner|runner]] - Runner 结构体，CheckPointStore 是其关键字段
- [[concepts/agent|agent]] - CheckPointStore 存储 Agent 的执行状态
- [[concepts/agentevent|agentevent]] - Agent 事件单元，与状态管理相关
- [[concepts/checkpoint|checkpoint]] - 检查点机制，CheckPointStore 的基础
- [[concepts/interruptresume|interruptresume]] - 中断恢复功能，CheckPointStore 支持的核心场景
- [[concepts/adk|adk]] - Agent Development Kit，CheckPointStore 所属的运行时框架

## 相关实体

- [[entities/eino|eino]] - Eino 框架，CheckPointStore 相关的运行时实现

## 来源提及

- "store CheckPointStore  // 用于中断恢复的状态存储" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "**Checkpoint 支持** ：配合 `CheckPointStore` 实现中断恢复（后续章节涉及）" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
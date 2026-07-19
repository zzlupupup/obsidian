---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "Supervisor Agent"
  - "监督智能体"
  - "SupervisorAgent"
generation_complete: true
---


# SupervisorAgent

## 定义
SupervisorAgent 是 [[concepts/adk|adk]] 框架中 [[concepts/agent|Agent]] 接口的一种实现类型，与 [[concepts/chatmodelagent|ChatModelAgent]] 和 [[concepts/workflowagent|WorkflowAgent]] 并列存在。从命名推断，SupervisorAgent 可能承担监督或协调多个子 Agent 的角色，属于比 [[concepts/chatmodelagent|ChatModelAgent]] 更高级别的 Agent 类型，用于实现多智能体协作架构中的调度与管理功能。

## 关键特征
- 属于 [[concepts/agent|Agent]] 接口的实现类型之一，与 [[concepts/chatmodelagent|ChatModelAgent]]、[[concepts/workflowagent|WorkflowAgent]] 处于同一抽象层级
- 名称暗示其具有"监督"职能，可能用于协调和调度多个子 Agent 的执行
- 体现了 [[entities/eino|Eino]] ADK 框架对多层次、多角色智能体架构的设计支持
- 在当前文档中仅作为概念提及，未展开详细实现说明

## 应用
SupervisorAgent 适用于需要多智能体协作的复杂场景，例如：
- 多步骤任务中需要中央调度器分配子任务给不同专用 Agent
- 需要对多个子 Agent 的输出进行汇总、审核和决策的编排场景
- 层级化智能体系统中作为上层管理者角色

## 相关概念
- [[concepts/agent|Agent]]
- [[concepts/chatmodelagent|ChatModelAgent]]
- [[concepts/workflowagent|WorkflowAgent]]
- [[concepts/adk|adk]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "所有 Agent（ChatModelAgent、WorkflowAgent、SupervisorAgent 等）都实现这个接口" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
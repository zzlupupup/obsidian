---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "Agent 输出"
  - "智能体输出"
generation_complete: true
---


# AgentOutput

## 定义
AgentOutput 是 [[concepts/agentevent|agentevent]] 结构体中的输出字段，包含 Agent 执行后产生的输出内容。其中 `Output.MessageOutput` 可以是单个消息或消息流（流式输出），是消费事件流时最常处理的数据。在 AgentEvent 结构体中，Output 与 Action（控制动作）和 Err（错误）并列，共同构成事件单元的全部信息维度。

## 关键特征
- 包含 `MessageOutput` 字段，支持单个消息或消息流两种形式
- 在 AgentEvent 结构体中与 Action（控制动作）和 Err（错误）并列，构成事件的三大信息维度
- 是消费事件流时最常处理的数据维度
- 支持流式响应场景下的实时内容消费

## 应用
- 在消费事件流时，通过检查 `event.Output != nil && event.Output.MessageOutput != nil` 来处理消息输出
- 适用于流式响应场景下的实时内容消费，如逐 token 展示 Agent 回复
- 配合 [[concepts/asynciterator|asynciterator]] 实现事件流的迭代消费

## 相关概念
- [[concepts/agentevent|agentevent]]
- [[concepts/agent|agent]]
- [[concepts/agentaction|AgentAction]]
- [[concepts/asynciterator|asynciterator]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "Output *AgentOutput  // 输出内容" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "`event.Output.MessageOutput` ：message 或 message stream（流式）" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
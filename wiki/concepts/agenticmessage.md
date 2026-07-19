---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "schema.AgenticMessage"
  - "智能体消息"
generation_complete: true
---


# AgenticMessage

## 定义
AgenticMessage 是 [[entities/eino|eino]] ADK 中 schema 包定义的消息类型，用作泛型消息类型 M 的默认值。在 [[concepts/agent|agent]] 框架中，它作为标准消息格式承载对话内容，是 [[concepts/agentinput|agentinput]] 和 [[concepts/agentoutput|agentoutput]] 等数据结构的基础消息单元。在 [[concepts/多轮对话|多轮对话]] 实现中，history 列表使用 `[]M` 类型保存累计对话，默认 M 为 `*schema.AgenticMessage`。

## 关键特征
- 定义于 [[concepts/adk|adk]] 的 schema 包中，全限定名为 `schema.AgenticMessage`
- 作为泛型消息类型 M 的默认值，提供 Agent 框架中的标准消息格式
- 与辅助函数 `msgops.NewUser` 和 `msgops.NewAssistant` 配合使用，分别构建用户消息和助手消息
- 作为 [[concepts/agent|agent]] 输入输出的基础数据结构，支撑 [[concepts/多轮对话|多轮对话]] 历史的累积与传递
- 以指针类型 `*schema.AgenticMessage` 使用，便于在消息流转中共享和修改

## 应用
- **多轮对话历史管理**：在 [[concepts/多轮对话|多轮对话]] 实现中，使用 `[]*schema.AgenticMessage` 类型的 history 列表保存累计的对话消息
- **消息构建**：通过 `msgops.NewUser` 构建用户消息、`msgops.NewAssistant` 构建助手消息，并将生成的 AgenticMessage 追加到对话历史中
- **Agent 数据流转**：作为 [[concepts/agentinput|agentinput]] 与 [[concepts/agentoutput|agentoutput]] 之间传递的标准消息载体，保证消息格式的一致性
- **泛型参数默认值**：在未显式指定消息类型的场景下，作为泛型 M 的默认类型，简化 Agent 的使用

## 相关概念
- [[concepts/agentinput|agentinput]]
- [[concepts/agentoutput|agentoutput]]
- [[concepts/agent|agent]]
- [[concepts/多轮对话|多轮对话]]
- [[concepts/adk|adk]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "用 history []M 保存累计对话，本示例默认 M 为 *schema.AgenticMessage" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "history = append(history, msgops.NewAssistant[M](result.AssistantText, nil))" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
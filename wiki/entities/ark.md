---
type: entity
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [product]
aliases:
  - "Ark 模型服务"
  - "Ark"
generation_complete: true
---


# Ark

## 描述
Ark 是 [[entities/eino|eino]] 框架中 [[concepts/chatmodel|chatmodel]] 组件支持的模型服务之一，与 [[entities/openai|openai]] 并列为可选的模型提供商。在源文件中，Ark 被提及作为配置 ChatModel 时的可选后端，用户在运行示例代码前需要配置 OpenAI 或 Ark 之一的可用 ChatModel。[[concepts/chatmodel|chatmodel]] 组件通过屏蔽 Ark 与 OpenAI、Claude 等不同模型提供商之间的接口差异，使开发者能够以统一方式调用不同的大语言模型。基于 ChatModel 构建的 [[concepts/chatmodelagent|ChatModelAgent]] 同样受益于这种抽象，可在不同模型后端间灵活切换。

## 相关实体
- [[entities/openai|openai]]
- [[entities/eino|eino]]

## 相关概念
- [[concepts/chatmodel|chatmodel]]
- [[concepts/chatmodelagent|ChatModelAgent]]

## 来源提及

- "与第一章一致：需要配置一个可用的 ChatModel（OpenAI 或 Ark）。" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "ChatModel = "负责与大语言模型通信的组件，屏蔽不同模型提供商的差异（OpenAI、Ark、Claude 等）"" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
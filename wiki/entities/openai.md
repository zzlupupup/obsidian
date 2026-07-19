---
type: entity
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [organization]
aliases:
  - "OpenAI"
  - "OpenAI 模型提供商"
generation_complete: true
---


# OpenAI

## 描述
OpenAI 是 [[entities/eino|eino]] 框架中 [[concepts/chatmodel|chatmodel]] 组件支持的模型提供商之一。在源文件中，OpenAI 被列为配置可用 ChatModel 的选项之一，另一个可选提供商为 [[entities/ark|Ark]]。[[concepts/chatmodel|chatmodel]] 组件的核心职责之一是屏蔽不同模型提供商（如 OpenAI、Ark、Claude 等）之间的差异，为上层应用提供统一的调用接口。在第一章和第二章的前置条件中，用户需要配置一个可用的 ChatModel，可以选择 OpenAI 或 Ark 作为后端模型服务。OpenAI 作为大语言模型领域的领先组织，其 API 服务为 Eino 框架的应用开发提供了强大的推理能力支持。

## 相关实体
- [[entities/ark|Ark]]
- [[entities/eino|eino]]

## 相关概念
- [[concepts/chatmodel|chatmodel]]
- [[concepts/chatmodelagent|ChatModelAgent]]

## 来源提及

- "与第一章一致：需要配置一个可用的 ChatModel（OpenAI 或 Ark）。" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "ChatModel = "负责与大语言模型通信的组件，屏蔽不同模型提供商的差异（OpenAI、Ark、Claude 等）"" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
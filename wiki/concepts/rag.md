---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/eino_8abb92]]"]
tags: [method]
aliases:
  - "Retrieval-Augmented Generation"
  - "检索增强生成"
generation_complete: true
---


# RAG

## 定义
RAG（Retrieval-Augmented Generation，检索增强生成）是一种将信息检索与文本生成相结合的方法。在 [[entities/eino|eino]] 框架中，RAG 被列为核心支持的常见应用模式之一，框架通过其组件库和编排能力提供构建 RAG 应用的支持，使开发者能够将检索和生成能力结合在一起。

## 关键特征
- 将检索能力与生成能力结合，增强模型输出的准确性和相关性
- 是 [[entities/eino|eino]] 框架核心支持的常见应用模式之一，与 [[concepts/react-agent|ReAct Agent]] 并列
- 依赖框架的组件库和编排能力进行构建，可通过 [[concepts/compose|Compose]] 模块实现
- 体现了 [[entities/eino|eino]] 在 AI 应用开发领域的全面性

## 应用
- 利用 [[entities/eino|eino]] 框架构建 RAG 应用，将外部知识检索与大模型生成相结合
- 在企业知识库问答、文档摘要生成等场景中应用检索增强生成能力
- 通过 [[concepts/adk|ADK]]（Agent Development Kit）等工具辅助开发包含 RAG 能力的智能体应用

## 相关概念
- [[concepts/react-agent|ReAct Agent]]
- [[concepts/adk|ADK]]
- [[concepts/compose|Compose]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "框架支持构建 [[concepts/react-agent|ReAct Agent]] 和 [[concepts/rag|RAG]] 等常见应用模式。" — [[wiki/entities/eino|eino]]
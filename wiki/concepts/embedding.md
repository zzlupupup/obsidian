---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [term]
aliases:
  - "嵌入"
  - "向量嵌入"
  - "Embedding"
generation_complete: true
---


# Embedding

## 定义

Embedding 是 Eino 框架中的一种核心组件，用于将文本或其他数据转换为向量表示。作为 compose 包能够原生编排的 Eino component 之一，Embedding 在 RAG 系统中扮演关键角色，通常与 Retriever 和 Indexer 配合使用，构成检索基础设施。在 compose 工作流中，Embedding 可以作为独立节点被编排，实现文档向量化、相似度计算等功能，是构建语义检索和 RAG 应用的基础组件。

## 关键特征

- **向量转换能力**：将文本或其他类型的数据映射为高维向量空间中的数值表示，使语义信息可计算
- **原生编排支持**：作为 Eino component，可被 compose 包直接编排，无需额外适配层
- **RAG 基础设施组件**：与 Retriever 和 Indexer 协同工作，构成检索增强生成系统的核心检索链路
- **工作流节点化**：在 compose 工作流中可作为独立节点存在，支持文档向量化、相似度计算等操作
- **语义相似度度量**：通过向量空间中的距离计算实现文本间语义级别的相似度比较

## 应用

- **文档向量化**：将文档内容转换为向量表示，为后续的索引构建和检索查询做准备
- **语义检索**：基于向量相似度计算实现语义级别的文档匹配与检索，超越关键词匹配的局限
- **RAG 系统构建**：作为 RAG 管道中的嵌入环节，将用户查询和文档库内容向量化以支持检索增强生成
- **工作流编排**：在 compose 工作流中作为独立节点参与复杂编排，实现自动化的文档处理与检索流水线

## 相关概念

- [[concepts/retriever|retriever]] - 与 Embedding 配合使用的检索器组件，共同构成 RAG 检索基础设施
- [[concepts/chatmodel|chatmodel]] - 同为 Eino component，可被 compose 原生编排
- [[concepts/indexer|indexer]] - 与 Embedding 配合使用的索引器组件，负责文档索引管理
- [[concepts/prompt|prompt]] - Eino component 之一，可被 compose 原生编排
- [[concepts/rag|rag]] - Embedding 是 RAG 系统检索基础设施的核心组件
- [[concepts/compose|compose]] - 提供原生编排能力的框架模块，支持 Embedding 作为节点编排
- [[concepts/workflow|workflow]] - Embedding 可作为独立节点在工作流中被编排
- [[concepts/graph|graph]] - 图编排结构中可包含 Embedding 节点

## 相关实体

- [[entities/eino|eino]] - Embedding 所属的应用开发框架

## 应用

> Embedding 被列为 compose 包能够原生编排的 Eino component 之一，与 ChatModel、Retriever、Indexer、Prompt 等组件并列。在 compose 工作流中，Embedding 可以作为独立节点被编排，是构建语义检索和 RAG 应用的基础组件。
>
> — [[sources/第八章graph-tool复杂工作流_584c82]]

## 来源提及

- "原生编排 Eino 的所有 component （如 ChatModel、Prompt、Tools、Retriever、Embedding、Indexer 等）" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [term]
aliases:
  - "检索器"
  - "Retriever"
generation_complete: true
---


# Retriever

## 定义
Retriever 是 Eino 框架中的一种核心组件，用于从知识库或文档集合中检索相关信息。作为 compose 包能够原生编排的 Eino component 之一，compose 工作流可以直接将 Retriever 作为节点使用。它与 Embedding 和 Indexer 组件共同构成 Eino 的检索增强生成（RAG）基础设施。

## 关键特征
- 属于 Eino 框架的原生组件类型，可被 compose 包直接编排为工作流节点
- 负责从外部知识库召回相关文档或片段，输入通常为查询文本，输出为检索结果集合
- 与 Embedding（向量化）和 Indexer（索引）组件协同工作，构成完整 RAG 链路
- 在标准 RAG 场景中是关键编排对象，但也可被自定义评分/筛选逻辑替代（如本章 Graph Tool 实现）
- 通常作为 compose.Workflow 中的检索节点，与 ChatModel、Prompt 等组件串联形成端到端管道

## 应用
- **RAG 工作流编排**：在 compose 工作流中将 Retriever 作为检索节点，串联 Embedding、Indexer 与 ChatModel 形成端到端的检索增强生成管道
- **知识库问答**：结合向量数据库，对用户问题召回相关文档片段供 ChatModel 引用作答
- **自定义检索替代**：如本章 Graph Tool 实现所示，当需要更精细的评分与筛选逻辑时，可绕过标准 Retriever 自行实现检索节点，但仍遵循 Eino 组件编排范式

## 相关概念
- [[concepts/chatmodel|chatmodel]]
- [[concepts/rag|rag]]
- [[concepts/workflow|workflow]]
- [[concepts/compose|compose]]
- [[concepts/graph|graph]]
- [[concepts/embedding|Embedding]]
- [[concepts/indexer|Indexer]]
- [[concepts/prompt|Prompt]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "原生编排 Eino 的所有 component （如 ChatModel、Prompt、Tools、Retriever、Embedding、Indexer 等）" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
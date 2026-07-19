---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [term]
aliases:
  - "索引器"
  - "Indexer"
generation_complete: true
---


# Indexer

## 定义
Indexer 是 Eino 框架中的一种核心组件，用于将文档或数据构建为可检索的索引。在 compose 工作流中，Indexer 被列为 compose 包能够原生编排的 Eino component 之一，通常与 Embedding 和 Retriever 配合使用，在 RAG 系统中负责文档的索引构建和更新。

## 关键特征
- 是 Eino 框架的原生组件之一，可被 compose 包直接编排
- 负责将文档或数据转化为可检索的索引结构
- 通常与 Embedding 配合使用，实现文档的向量化与索引存储
- 与 Retriever 形成互补关系：Indexer 负责写入索引，Retriever 负责读取检索
- 在 compose 工作流中可作为独立节点被编排，实现自动化的索引管理流程

## 应用
- 在 RAG（检索增强生成）系统中，作为索引构建环节，将原始文档处理后存入向量数据库或其他索引存储
- 在 compose 工作流中作为节点参与编排，实现文档入库、索引更新等自动化流程
- 与 Embedding 组件配合，将文档嵌入为向量后构建索引
- 支持 RAG 管线中索引的增量更新与维护

## 相关概念
- [[concepts/embedding|embedding]] - 与 Indexer 配合使用，提供文档向量化能力
- [[concepts/retriever|retriever]] - 与 Indexer 形成读写互补，负责从索引中检索相关文档
- [[concepts/chatmodel|chatmodel]] - RAG 系统中的生成组件
- [[concepts/workflow|workflow]] - Indexer 可作为节点在其中被编排
- [[concepts/compose|compose]] - 原生支持编排 Indexer 组件的编排模块
- [[concepts/rag|rag]] - Indexer 是 RAG 管线中的关键环节

## 相关实体
- [[entities/eino|eino]] - Indexer 所属的框架

## 来源提及

- "原生编排 Eino 的所有 component （如 ChatModel、Prompt、Tools、Retriever、Embedding、Indexer 等）" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
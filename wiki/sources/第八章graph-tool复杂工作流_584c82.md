---
type: source
created: 2026-07-19
updated: 2026-07-19
source_file: "[[raw/第八章：Graph Tool（复杂工作流）.md]]"
tags: [clippings]
aliases: ["Eino 快速入门第八章", "Chapter 08: Graph Tool"]
contentHash: 2042-1eadfb29
generation_complete: true
---

# 第八章：Graph Tool（复杂工作流） - 摘要

## 来源
- 原始文件：[[raw/第八章：Graph Tool（复杂工作流）.md]]
- 录入时间：2026-07-19

## 核心内容
本章是 Eino 框架快速入门教程的第八章，重点讲解 [[concepts/graph-tool|Graph Tool]] 的概念与实现，展示如何将复杂工作流封装为 Agent 可调用的 Tool。核心内容包括：从简单 Tool 到 Graph Tool 的演进动机，[[concepts/compose-workflow|compose.Workflow]] 提供的通用编排能力，以及如何构建一个完整的文档问答 RAG 工作流。该工作流包含五个步骤：load（读取文件）→ chunk（分块）→ score（并行评分，使用 [[concepts/batchnode|BatchNode]] 实现）→ filter（筛选 top-k）→ answer（生成答案）。章节详细介绍了 [[concepts/node|Node]]、[[concepts/edge|Edge]] 等工作流核心概念，[[concepts/fieldmapping|FieldMapping]] 用于跨节点数据传递，[[concepts/maxconcurrency|MaxConcurrency]] 控制并行度。此外，还涵盖了 [[concepts/checkpoint|checkpoint]] 状态持久化与 [[concepts/interruptresume|interrupt/resume]] 可中断恢复能力。最终通过 [[concepts/graphtool-newinvokablegraphtool|graphtool.NewInvokableGraphTool]] 将工作流封装为名为 `answer_from_document` 的 Tool。compose 包还可原生编排 [[concepts/chatmodel|ChatModel]]、[[concepts/retriever|Retriever]]、[[concepts/embedding|Embedding]]、[[concepts/indexer|Indexer]] 等组件，并具备完整的 [[concepts/callback|callback]] 回调体系。

## 关键实体
- 本章节未提取独立实体页面

## 关键概念
- [[concepts/graph-tool|Graph Tool]] — 将 compose 工作流封装为 Agent 可调用 Tool 的机制
- [[concepts/compose-workflow|compose.Workflow]] — 构建工作流的核心组件
- [[concepts/batchnode|BatchNode]] — 并行处理多个任务的节点类型
- [[concepts/fieldmapping|FieldMapping]] — 跨节点数据传递机制
- [[concepts/node|Node]] / [[concepts/edge|Edge]] — 工作流基本构建块
- [[concepts/maxconcurrency|MaxConcurrency]] — 并行任务最大并发数控制
- [[concepts/checkpoint|checkpoint]] — 状态持久化机制
- [[concepts/interruptresume|interrupt/resume]] — 中断与恢复机制
- [[concepts/graphtool-newinvokablegraphtool|graphtool.NewInvokableGraphTool]] — 工作流封装为 Tool 的核心方法
- [[concepts/compose-graph|compose.Graph]] — 可编译编排产物
- [[concepts/callback|callback]] — 回调体系
- [[concepts/compose-invokablelambda|compose.InvokableLambda]] — 创建 Lambda 节点的方法

## 要点
- **Graph Tool 的核心定位**：将 [[concepts/compose-workflow|compose.Workflow]]、[[concepts/compose-graph|compose.Graph]] 等可编译编排产物包装为 Agent 可调用的 Tool，支持多步骤协同
- **完整 RAG 工作流**：load（读取文件）→ chunk（分块）→ score（并行评分）→ filter（筛选 top-k）→ answer（生成答案），五节点流水线解决大文件问答场景
- **并行处理能力**：[[concepts/batchnode|BatchNode]] 通过 [[concepts/maxconcurrency|MaxConcurrency]] 控制并发度（示例中设为 5），实现大文件的高效并行 chunk 召回
- **灵活数据传递**：[[concepts/fieldmapping|FieldMapping]] 支持非相邻节点间数据传递、多数据源合并和字段重命名，通过 `AddInputWithOptions` 配合 `WithNoDirectDependency` 使用
- **状态管理与恢复**：[[concepts/checkpoint|checkpoint]] 保存/恢复运行状态，[[concepts/interruptresume|interrupt/resume]] 支持工作流内部和工具层面的中断与恢复
- **原生编排能力**：compose 包可原生编排 Eino 的所有 component（[[concepts/chatmodel|ChatModel]]、[[concepts/retriever|Retriever]]、[[concepts/embedding|Embedding]]、[[concepts/indexer|Indexer]] 等），具备完整的 [[concepts/callback|callback]] 体系
- **工具封装方式**：通过 [[concepts/graphtool-newinvokablegraphtool|graphtool.NewInvokableGraphTool]] 将编译后的工作流封装为 Tool，需指定工具名称和描述
---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [method]
aliases:
  - "batch.NewBatchNode"
  - "批量节点"
generation_complete: true
---


# BatchNode

## 定义
BatchNode 是 [[concepts/compose|compose]] 包中用于并行处理多个任务的节点类型。它接收任务列表作为输入，在 `MaxConcurrency` 参数限制下并行执行每个任务，然后收集所有结果返回。BatchNode 的核心配置通过 `NodeConfig` 结构体定义，包括 `Name`（节点名称）、`InnerTask`（单个任务处理函数）和 `MaxConcurrency`（最大并发数）。

## 关键特征
- **并行执行**：支持同时处理多个独立任务，提升吞吐效率
- **并发控制**：通过 `MaxConcurrency` 参数限制最大并发数，避免资源过载
- **任务函数化**：每个任务由 `InnerTask` 函数统一处理，保持处理逻辑一致性
- **结果聚合**：自动收集所有任务执行结果并按顺序返回
- **结构化配置**：通过 `NodeConfig` 结构体集中管理节点配置参数

## 应用
在 [[concepts/rag|RAG]] 实现中，BatchNode 被用于并行评分多个文档分块。每个分块作为独立任务交给评分函数处理，最大并发数设为 5，从而实现大文件的高效并行 chunk 召回。BatchNode 解决了简单 [[concepts/graph-tool|graph-tool]] 无法并行执行多个独立任务的局限性，特别适用于需要对批量数据进行同质化处理的场景。

## 相关概念
- [[concepts/graph-tool|graph-tool]]
- [[concepts/fieldmapping|FieldMapping]]
- [[concepts/compose|compose]]
- [[concepts/rag|rag]]

## 相关实体
- [[entities/eino|eino]]

## 源文摘录
> BatchNode 是 eino compose 包中用于并行处理多个任务的节点类型。它接收任务列表作为输入，在 MaxConcurrency 参数限制下并行执行每个任务，然后收集所有结果返回。
>
> BatchNode 的核心配置通过 NodeConfig 结构体定义，包括 Name（节点名称）、InnerTask（单个任务处理函数）和 MaxConcurrency（最大并发数）。
>
> 在本章的 RAG 实现中，BatchNode 被用于并行评分多个文档分块，每个分块作为独立任务交给评分函数处理，最大并发数设为 5。
>
> BatchNode 解决了简单 Tool 无法并行执行多个独立任务的局限性。

— 来源：[[sources/第八章graph-tool复杂工作流_584c82]]

## 来源提及

- "BatchNode 用于并行处理多个任务" (BatchNode 用于并行处理多个任务) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "1. 接收任务列表作为输入
2. 并行执行每个任务（受 MaxConcurrency 限制）
3. 收集所有结果返回" (1. 接收任务列表作为输入
2. 并行执行每个任务（受 MaxConcurrency 限制）
3. 收集所有结果返回) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
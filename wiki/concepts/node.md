---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [term]
aliases:
  - "节点"
  - "工作流节点"
generation_complete: true
---


# Node

## 定义
Node（节点）是 [[concepts/workflow|workflow]] 中的基本处理单元，是工作流编排的核心构建块。每个节点负责执行特定的处理逻辑，如读取文件、分块、评分、筛选或生成答案。节点通过 `AddLambdaNode` 方法添加到工作流中，并通过 `AddInput` 方法定义数据流向。工作流中有两个特殊的节点标识：`START` 作为工作流的入口，`END` 作为工作流的出口。

## 关键特征
- **独立处理单元**：每个节点封装一个独立的处理逻辑，接收输入数据并产生输出数据
- **通过 Lambda 注册**：使用 `AddLambdaNode` 方法将 [[concepts/compose-invokablelambda|compose-invokablelambda]] 注册为工作流节点
- **数据流向定义**：通过 `AddInput` 方法定义节点间的数据传递关系，明确上游输出与下游输入的映射
- **特殊节点标识**：`START` 标识工作流入口，`END` 标识工作流出口，用于界定数据流的起点和终点
- **通过 Edge 连接**：节点之间通过 Edge 连接，形成完整的数据处理流水线
- **可组合性**：多个节点按特定拓扑结构组合，构成完整的工作流处理链路

## 应用
在 [[concepts/graph-tool|graph-tool]] 示例中，工作流包含五个典型节点，构成完整的 RAG 处理流水线：

- **load**：读取文件内容，作为数据流的起点
- **chunk**：对文本进行分块处理
- **score**：对分块结果进行评分
- **filter**：根据评分筛选内容
- **answer**：生成最终答案，作为数据流的终点

每个节点接收上游节点的输出并产生下游节点所需的输入，形成线性的数据处理流水线。节点也可通过 [[concepts/batchnode|batchnode]] 实现批量处理能力，或通过 MaxConcurrency 控制节点的并发执行度。

## 相关概念
- [[concepts/workflow|workflow]]
- [[concepts/edge|Edge]]
- [[concepts/compose-invokablelambda|compose-invokablelambda]]
- [[concepts/batchnode|batchnode]]
- [[concepts/maxconcurrency|MaxConcurrency]]

## 相关实体
无相关实体。

## 来源提及

- "Node ：工作流中的处理单元" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "wf.AddLambdaNode("load", loadFunc).AddInput(compose.START)
wf.AddLambdaNode("chunk", chunkFunc).AddInput("load")" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
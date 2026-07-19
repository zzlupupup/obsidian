---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [term]
aliases:
  - "工作流边"
  - "边"
generation_complete: true
---


# Edge

## 定义

Edge（边）是 [[concepts/workflow|workflow]] 中节点间的数据流向，定义了数据如何从一个节点传递到另一个节点。边的建立通过 `AddInput` 方法实现，例如 `AddInput("load")` 表示当前节点接收 `load` 节点的输出作为输入。

## 关键特征

- **数据依赖表达**：Edge 通过 `AddInput` 方法显式声明节点间的数据依赖关系，形成有向图结构
- **灵活的数据传递**：除直接数据依赖外，可通过 `AddInputWithOptions` 和 [[concepts/fieldmapping|fieldmapping]] 实现跨节点传递、多数据源合并和字段重命名
- **特殊端点**：`compose.START` 和 `compose.END` 是两个特殊的边端点，分别代表工作流的入口和出口
- **支持非相邻连接**：Edge 不仅连接相邻节点（如 `load->chunk`），还支持非相邻节点的数据传递（如 `START->score`、`filter->answer`）
- **与节点的关系**：每条 Edge 连接两个 [[concepts/node|node]]，定义数据流动的方向和内容

## 应用

- **Graph Tool 实现**：在 [[concepts/graph-tool|graph-tool]] 中，Edge 用于构建复杂的 [[concepts/graph|graph]] 结构，连接检索、过滤、评分等节点
- **工作流编排**：在 [[concepts/compose|compose]] 模块中，Edge 是构建 [[concepts/chain|chain]] 和图编排的基础元素
- **RAG 流程**：在 [[concepts/rag|rag]] 场景中，Edge 连接文档加载、分块、检索、重排序等节点，形成完整的数据处理管道

## 相关概念

- [[concepts/workflow|workflow]] - Edge 所属的工作流编排框架
- [[concepts/node|node]] - Edge 连接的基本单元
- [[concepts/fieldmapping|fieldmapping]] - Edge 数据传递时的字段处理机制
- [[concepts/graph-tool|graph-tool]] - Edge 的主要应用场景
- [[concepts/graph|graph]] - Edge 构成的数据结构
- [[concepts/compose|compose]] - Edge 所属的编排模块

## 相关实体

（无相关实体）

## 来源提及

- "Edge ：节点间的数据流向" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "wf.AddLambdaNode("chunk", chunkFunc).AddInput("load")" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
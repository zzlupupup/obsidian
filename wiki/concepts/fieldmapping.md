---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [term]
aliases:
  - "compose.FieldMapping"
  - "字段映射"
generation_complete: true
---


# FieldMapping

## 定义
FieldMapping 是 [[entities/eino|eino]] 的 [[concepts/compose|compose]] 包中用于跨节点传递数据的机制。它解决了[[concepts/workflow|工作流]]编排中非相邻节点间数据传递、多个数据源合并到同一节点、以及数据字段重命名的需求。通过 `AddInputWithOptions` 方法配合 FieldMapping，可以从非直接依赖的节点获取数据并映射到当前节点的输入字段。

## 关键特征
- 支持非相邻节点间的数据传递，突破线性拓扑限制
- 支持将多个数据源合并到同一节点的不同输入字段
- 提供字段重命名能力，将源字段映射为目标字段
- 配合 `WithNoDirectDependency` 选项声明非直接依赖关系
- 核心方法包括 `ToField`（将数据映射到指定字段）和 `MapFields`（将源字段重命名映射到目标字段）
- 与 [[concepts/graph|graph]] 编排模式深度集成，增强数据流灵活性

## 应用
- **RAG 场景**：在 [[concepts/rag|rag]] 实现中，FieldMapping 用于从 filter 节点获取 TopK 检索结果、从 START 节点获取用户 Question 数据，并将两者合并传递给 answer 节点，实现检索与生成的数据桥接
- **跨节点数据传递**：在[[concepts/graph|图编排]]中，当节点需要引用非直接上游节点的输出时，通过 FieldMapping 建立数据通路
- **多源数据合并**：将来自不同分支或不同节点的数据聚合到单个节点的多个输入参数中
- **字段适配**：当上游节点输出字段名与下游节点输入字段名不一致时，通过 `MapFields` 进行重命名映射

## 相关概念
- [[concepts/graph-tool|graph-tool]]
- [[concepts/batchnode|batchnode]]
- [[concepts/compose|compose]]
- [[concepts/rag|rag]]
- [[concepts/graph|graph]]
- [[concepts/workflow|workflow]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "FieldMapping 用于跨节点传递数据" (FieldMapping 用于跨节点传递数据) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "为什么需要 FieldMapping？
- 非相邻节点间传递数据
- 多个数据源合并到同一节点
- 数据字段重命名" (为什么需要 FieldMapping？
- 非相邻节点间传递数据
- 多个数据源合并到同一节点
- 数据字段重命名) — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
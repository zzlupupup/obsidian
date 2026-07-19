---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/eino_8abb92]]"]
tags: [method]
aliases:
  - "链式编排"
  - "Chain"
  - "链"
generation_complete: true
---


# Chain

## 定义
Chain 是 [[entities/eino|eino]] 框架 [[concepts/compose|compose]] 模块支持的一种编排方式，允许开发者以链式结构组织和连接组件。在 Chain 模式下，多个组件按顺序串联执行，每个组件的输出作为下一个组件的输入，形成线性的数据流处理管道。Chain 与 [[concepts/graph|graph]]、[[concepts/workflow|workflow]] 一起构成了 eino 框架的核心编排能力，为开发者提供了灵活的组件组合方式。

## 关键特征
- 链式结构：组件按顺序串联，形成线性的执行流程
- 数据流传递：前一个组件的输出自动作为后一个组件的输入
- 顺序执行：组件按照定义的顺序依次执行，逻辑清晰直观
- 编排模式之一：与 [[concepts/graph|graph]] 和 [[concepts/workflow|workflow]] 并列，共同构成 [[concepts/compose|compose]] 模块的核心编排能力

## 应用
- 构建顺序处理管道，如数据预处理流水线
- LLM 应用中的多步骤串联，例如提示词构建 → 模型调用 → 输出解析
- 结合 [[concepts/rag|rag]] 等模式，实现检索后生成等线性处理流程
- 作为复杂编排的基础单元，与 [[concepts/graph|graph]] 和 [[concepts/workflow|workflow]] 配合实现更灵活的组合逻辑

## 相关概念
- [[concepts/compose|compose]]
- [[concepts/graph|graph]]
- [[concepts/workflow|workflow]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "该框架提供了 Agent 开发、组件编排、流程管理等核心能力，支持 Chain、Graph、Workflow 等多种编排方式。" — [[wiki/entities/eino|eino]]
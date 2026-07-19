---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [method]
aliases:
  - "InvokableLambda"
  - "Lambda 节点"
generation_complete: true
---


# compose.InvokableLambda

## 定义
compose.InvokableLambda 是 [[entities/eino|eino]] 框架 compose 包中用于创建 Lambda 节点的方法。它接受一个 Go 函数并将其包装为工作流中的可调用节点，使开发者能够以简洁的函数式风格定义处理逻辑。每个 Lambda 节点接收特定类型的输入并返回特定类型的输出，通过 AddInput 方法与其他节点连接，形成完整的数据处理流水线。

## 关键特征
- **函数式封装**：将普通 Go 函数封装为工作流中的可调用节点，降低编排复杂度
- **类型安全**：每个 Lambda 节点具有明确的输入类型和输出类型，保证数据流转的类型正确性
- **节点连接**：通过 AddInput 方法与其他节点建立连接，构建有向数据处理流水线
- **逻辑拆分**：将复杂业务逻辑拆分为独立、可复用的处理单元，提升代码可维护性
- **声明式风格**：开发者只需关注函数本身的处理逻辑，无需关心节点内部的状态管理

## 应用
在 [[concepts/graph-tool|graph-tool]] 的实现中，compose.InvokableLambda 被广泛用于创建各类处理节点：

- **load 节点**：读取文件内容并加载数据，作为流水线的起始处理单元
- **chunk 节点**：将长文本切分为固定大小的分块，便于后续检索处理
- **filter 节点**：根据条件对数据进行筛选和过滤，剔除无关内容
- **answer 节点**：基于检索结果生成最终答案，作为流水线的末端处理单元

这些节点通过连接组合形成完整的数据处理流水线，典型应用于 [[concepts/rag|rag]]（检索增强生成）等场景。

## 相关概念
- [[concepts/workflow|workflow]]
- [[concepts/graph|graph]]
- [[concepts/compose|compose]]
- [[concepts/graph-tool|graph-tool]]
- [[concepts/node|Node]]
- [[concepts/edge|Edge]]

## 相关实体
- [[entities/eino|eino]]

## 来源提及

- "wf.AddLambdaNode("load", compose.InvokableLambda(
        func(ctx context.Context, in Input) ([]*schema.Document, error) {
            data, err := os.ReadFile(in.FilePath)" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "wf.AddLambdaNode("chunk", compose.InvokableLambda(
        func(ctx context.Context, docs []*schema.Document) ([]*schema.Document, error) {" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [method]
aliases:
  - "NewInvokableGraphTool"
  - "可调用图工具方法"
generation_complete: true
---


# graphtool.NewInvokableGraphTool

## 定义

`graphtool.NewInvokableGraphTool` 是 [[entities/eino|eino]] 框架中将 [[concepts/workflow|compose.Workflow]] 封装为 [[concepts/react-agent|Agent]] 可调用工具的核心方法。该方法接收一个已编译的 [[concepts/workflow|工作流]] 实例、工具名称和工具描述作为参数，返回一个实现了 `tool.BaseTool` 接口的实例，使 Agent 能够通过标准工具调用机制执行复杂的多步骤工作流。

## 关键特征

- **工作流封装**：将包含多个 [[concepts/node|节点]] 和 [[concepts/edge|边]] 的编译后工作流打包为单一工具，对 Agent 透明地暴露为一个可调用接口
- **接口标准化**：返回 `tool.BaseTool` 接口实例，符合 Eino 工具调用规范，可与任意支持工具调用的 Agent 无缝集成
- **参数化配置**：通过工具名称（如 `answer_from_document`）和描述参数，为 Agent 提供工具发现与选择的语义信息
- **保留工作流能力**：封装后的工具仍保留 [[concepts/workflow|工作流]] 内部的并行处理、状态管理和 [[concepts/interruptresume|中断恢复]] 能力，不因工具化而损失功能
- **多节点编排**：典型实现中封装包含 load → chunk → score → filter → answer 五个节点的文档问答流程，将复杂 [[concepts/rag|RAG]] 管道转化为 Agent 可调用的原子工具

## 应用

- **文档问答工具化**：将 load → chunk → score → filter → answer 五节点工作流封装为名为 `answer_from_document` 的工具，供 Agent 在需要基于文档回答问题时动态调用
- **Agent 工具链扩展**：使复杂的多步骤处理流程能够作为 [[concepts/react-agent|ReAct Agent]] 工具链的一部分被按需调用，而非硬编码在 Agent 主流程中
- **工作流复用**：同一编译好的 [[concepts/workflow|工作流]] 可被封装为不同名称和描述的工具，适配不同的 Agent 场景与提示策略
- **[[concepts/rag|RAG]] 场景集成**：将检索增强生成管道封装为工具后，Agent 可根据对话上下文自主决定是否触发文档检索与问答流程

## 相关概念

- [[concepts/graph-tool|graph-tool]] — 该方法所属的 Graph Tool 概念，描述将工作流封装为工具的整体机制
- [[concepts/workflow|workflow]] — 该方法的输入参数，被封装的编译后工作流
- [[concepts/compose-invokablelambda|compose-invokablelambda]] — 工作流内部节点的常见实现方式，可用于构建工作流中的 Lambda 节点
- [[concepts/graph|graph]] — 工作流的底层图编排结构，NewInvokableGraphTool 封装的 [[concepts/workflow|工作流]] 基于此构建
- [[concepts/compose|compose]] — Eino Compose 模块，提供工作流编排能力，是该方法的依赖基础
- [[concepts/node|node]] — 被封装工作流内部的处理节点，如 load、chunk、score、filter、answer
- [[concepts/interruptresume|interruptresume]] — 封装后的工具保留工作流的中断与恢复能力
- [[concepts/react-agent|react-agent]] — 典型的工具调用方，Agent 通过工具调用机制使用 NewInvokableGraphTool 创建的工具

## 相关实体

- [[entities/eino|eino]] — 该方法所属的框架，提供 graphtool 包及工具封装能力

## 应用

> graphtool.NewInvokableGraphTool 是 Eino 中将 compose 工作流封装为 Agent 可调用 Tool 的核心方法。它接受一个编译好的 compose.Workflow、工具名称和描述作为参数，返回一个 tool.BaseTool 接口实例。
> — 来源：第八章 Graph Tool 复杂工作流

> 在 Graph Tool 的实现中，该方法将包含 load->chunk->score->filter->answer 五个节点的工作流封装为名为 answer_from_document 的工具，使 Agent 能够通过工具调用的方式执行复杂的多步骤文档问答流程。
> — 来源：第八章 Graph Tool 复杂工作流

> 这种封装方式使得复杂工作流可以作为 Agent 工具链的一部分被动态调用，同时保留工作流内部的并行处理、状态管理和中断恢复能力。
> — 来源：第八章 Graph Tool 复杂工作流

## 来源提及

- "return graphtool.NewInvokableGraphTool[Input, Output](
        wf,
        "answer_from_document",
        "Search a large uploaded document for content relevant to a question and synthesize a " +
            "cited answer from the most relevant passages. " +
            "Use this instead of read_file when the document may be too large to fit in context.",
    )" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
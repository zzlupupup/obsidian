---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第八章graph-tool复杂工作流_584c82]]"]
tags: [term]
aliases:
  - "最大并发数"
  - "并发上限"
  - "MaxConcurrency"
generation_complete: true
---


# MaxConcurrency

## 定义
MaxConcurrency 是 Eino 框架中 [[concepts/batchnode|BatchNode]] 的配置参数，用于控制并行任务的最大并发数。BatchNode 接收任务列表作为输入，在 MaxConcurrency 限制下并行执行每个任务，然后收集所有结果返回。通过调整该参数可以控制系统的并发度，从而在性能和资源消耗之间取得平衡。

## 关键特征
- 作用于 [[concepts/batchnode|BatchNode]]，限制并行任务的最高并发数量
- 在 [[concepts/graph-tool|GraphTool]] 示例中，MaxConcurrency 被设置为 5，表示并行评分阶段最多同时处理 5 个 chunk 的评分任务
- BatchNode 的工作流程：接收任务列表 → 在 MaxConcurrency 约束下并行执行 → 收集所有结果返回
- 调整 MaxConcurrency 是性能优化的重要手段之一，与使用缓存、流式输出并列
- 值越大，并发度越高，吞吐量提升但资源消耗也增加；值越小则相反

## 应用
- **并行评分控制**：在 Graph Tool 的并行评分阶段，通过设置 MaxConcurrency=5 来同时处理多个 chunk 的评分任务，提高处理效率
- **性能调优**：作为扩展思考中列出的性能优化手段之一，通过调整 MaxConcurrency 在吞吐量与资源占用之间寻找最佳平衡点
- **资源管理**：在资源受限的环境中，通过降低 MaxConcurrency 避免系统过载；在资源充足时提高该值以最大化并行处理能力

## 相关概念
- [[concepts/batchnode|BatchNode]] - MaxConcurrency 所作用的批量节点类型
- [[concepts/node|node]] - BatchNode 的基础抽象
- [[concepts/graph-tool|GraphTool]] - 提供 MaxConcurrency 配置示例的 Graph 工具
- [[concepts/graph|graph]] - 图编排框架，BatchNode 运行于其中

## 相关实体
- [[entities/eino|Eino]] - MaxConcurrency 所属的框架

## 来源提及

- "MaxConcurrency: 5,              // 最大并发数" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
- "调整 MaxConcurrency 控制并发" — [[raw/第八章：Graph Tool（复杂工作流）|第八章：Graph Tool（复杂工作流）]]
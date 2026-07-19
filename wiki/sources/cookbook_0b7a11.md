---
type: source
created: 2026-07-19
updated: 2026-07-19
source_file: "[[raw/Cookbook.md]]"
tags: [clippings]
aliases: ["eino Cookbook", "eino 示例索引", "eino-examples 示例目录"]
contentHash: 38c2-51eb3314
generation_complete: true
---

# Cookbook - Summary

## 来源
- Original file: [[raw/Cookbook.md]]
- Ingested: 2026-07-19

## 核心内容
本文档是 [[entities/eino-examples|eino-examples]] 项目的官方示例索引，帮助开发者快速找到所需的示例代码。该仓库由 [[entities/cloudwego|CloudWeGo]] 组织维护，涵盖六大类示例：ADK（Agent Development Kit）、Compose（编排）、Flow（流程模块）、Components（组件）、QuickStart（快速入门）和 DevOps（调试与可视化）。文档展示了 [[entities/eino|eino]] 框架在 Agent 开发、组件编排、多 Agent 协作、人机交互等场景中的完整实践，包含 [[entities/manus-agent|Manus Agent]]、[[entities/deer-go|Deer-Go]] 和 [[entities/eino-assistant|Eino Assistant]] 三大完整应用示例，是学习和使用 eino 框架的核心参考资料。

## 关键实体
- [[entities/eino-examples|eino-examples]] — CloudWeGo 旗下 eino 框架的官方示例代码仓库
- [[entities/eino|eino]] — 企业级云原生中间件框架，提供 Agent 开发与编排能力
- [[entities/eino-ext|eino-ext]] — eino 框架的扩展组件项目
- [[entities/cloudwego|CloudWeGo]] — eino 框架及其生态系统的开发组织
- [[entities/openmanus|OpenManus]] — Manus Agent 示例的参考来源项目
- [[entities/deer-flow|deer-flow]] — Deer-Go 示例的参考来源项目
- [[entities/manus-agent|Manus Agent]] — 基于 Eino 实现的完整 Agent 应用示例
- [[entities/deer-go|Deer-Go]] — 参考 deer-flow 的 Go 语言实现，支持研究团队协作
- [[entities/eino-assistant|Eino Assistant]] — 完整的 RAG 应用示例，包含知识索引、Agent 服务和 Web 界面

## 关键概念
- [[concepts/adk|ADK]] — Agent 开发工具包，提供 Agent 创建和管理的核心能力
- [[concepts/compose|Compose]] — 组件编排模块，支持 Chain、Graph、Workflow、Batch 四种编排方式
- [[concepts/chain|Chain]] — 链式编排方式，适用于线性流程
- [[concepts/graph|Graph]] — 图编排方式，支持状态管理和中断恢复
- [[concepts/workflow|Workflow]] — 工作流编排方式，提供灵活的数据流控制
- [[concepts/react-agent|ReAct Agent]] — 结合推理和行动能力的 Agent 模式
- [[concepts/supervisor|Supervisor]] — 多 Agent 协作模式，通过 Supervisor Agent 协调子 Agent
- [[concepts/plan-execute-replan|Plan-Execute-Replan]] — 计划-执行-重规划的多 Agent 协作模式
- [[concepts/human-in-the-loop|Human-in-the-Loop]] — 人机协作模式，支持 8 种交互方式
- [[concepts/interrupt|Interrupt]] — 中断机制，允许 Agent 执行暂停和恢复
- [[concepts/checkpoint|Checkpoint]] — 检查点机制，与 Interrupt 配合实现状态保存
- [[concepts/graphtool|GraphTool]] — 将 Graph/Chain/Workflow 封装为 Agent 工具的工具包
- [[concepts/rag|RAG]] — 检索增强生成应用模式
- [[concepts/deep-agents|Deep Agents]] — 支持分步骤处理复杂任务的 Agent 模式
- [[concepts/runner|Runner]] — ADK 核心执行组件，驱动 Agent 运行
- [[concepts/mcp|MCP]] — Model Context Protocol，工具集成标准
- [[concepts/skill|Skill]] — Agent 能力抽象，通过中间件机制加载
- [[concepts/graceful-exit|Graceful Exit]] — Agent 优雅退出与恢复模式

## 要点
- **六大示例分类**：ADK、Compose、Flow、Components、QuickStart、DevOps，覆盖从入门到生产的完整场景
- **ADK 能力全面**：支持 [[concepts/chatmodelagent|ChatModelAgent]]、[[concepts/loopagent|LoopAgent]]、[[concepts/parallelagent|ParallelAgent]]、[[concepts/sequentialagent|SequentialAgent]] 等多种 Agent 类型，以及 [[concepts/transfer|Transfer]]、[[concepts/session|Session]]、[[concepts/callback|Callback]] 等核心功能
- **人机协作丰富**：[[concepts/human-in-the-loop|Human-in-the-Loop]] 提供 8 种模式，包括审批、审核编辑、反馈循环、追问、Supervisor+审批等
- **多 Agent 协作**：支持 [[concepts/supervisor|Supervisor]]、[[concepts/分层-supervisor|分层 Supervisor]]、[[concepts/plan-execute-replan|Plan-Execute-Replan]]、[[concepts/deep-agents|Deep Agents]] 等多种协作模式
- **编排能力强大**：[[concepts/compose|Compose]] 模块提供 Chain、Graph、Workflow、[[concepts/batchnode|BatchNode]] 四种编排方式，支持 [[concepts/state-graph|State Graph]] 和中断恢复
- **三大完整应用**：[[entities/manus-agent|Manus Agent]]、[[entities/deer-go|Deer-Go]]、[[entities/eino-assistant|Eino Assistant]] 提供端到端的参考实现
- **渐进式教程**：Chat with Eino 提供 9 章渐进式学习路径，从 ChatModel 逐步构建到完整的 Skill Agent
- **工具与检索增强**：支持 [[concepts/mcp|MCP]] 工具集成、[[concepts/tool-call|Tool Call]]、[[concepts/多查询检索|多查询检索]]、[[concepts/ab-测试路由|A/B 测试路由]] 等高级功能

---
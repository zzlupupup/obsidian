---
type: source
created: 2026-07-19
updated: 2026-07-19
source_file: "[[wiki/entities/eino.md]]"
tags: [project]
aliases: ["Eino框架", "Eino"]
contentHash: 3f2-453c3c71
generation_complete: true
---

# eino - Summary

## 来源
- Original file: [[wiki/entities/eino.md]]
- Ingested: 2026-07-19

## 核心内容
该源文件是 [[entities/cloudwego|CloudWeGo]] 开发的企业级云原生中间件框架 eino 的实体页面。eino 提供 Agent 开发、组件编排、流程管理等核心能力，支持 [[concepts/chain|Chain]]、[[concepts/graph|Graph]]、[[concepts/workflow|Workflow]] 等多种编排方式。框架包含 [[concepts/adk|ADK]]（Agent Development Kit）用于 Agent 开发，[[concepts/compose|Compose]] 模块用于组件编排，以及丰富的组件库。框架支持构建 [[concepts/react-agent|ReAct Agent]] 和 [[concepts/rag|RAG]] 等常见应用模式。文档中还提到基于 eino 框架的完整应用示例，包括 [[entities/manus-agent|Manus Agent]] 和 [[entities/deer-go|Deer-Go]]，其中 Manus Agent 参考了 [[entities/openmanus|OpenManus]] 项目。

## 关键实体
- [[entities/cloudwego|CloudWeGo]] - 开发 eino 框架的组织
- [[entities/manus-agent|Manus Agent]] - 基于 eino 实现的 Agent 示例，参考 OpenManus 项目
- [[entities/deer-go|Deer-Go]] - 基于 eino 框架构建的完整应用示例
- [[entities/openmanus|OpenManus]] - Manus Agent 示例所参考的开源项目

## 关键概念
- [[concepts/adk|ADK]] - eino 框架中用于 Agent 开发的核心模块
- [[concepts/compose|Compose]] - eino 框架中用于组件编排的核心模块
- [[concepts/react-agent|ReAct Agent]] - eino 框架支持的常见应用模式
- [[concepts/rag|RAG]] - eino 框架支持的检索增强生成应用模式
- [[concepts/chain|Chain]] - Compose 模块支持的链式编排方式
- [[concepts/graph|Graph]] - Compose 模块支持的图编排方式
- [[concepts/workflow|Workflow]] - Compose 模块支持的工作流编排方式

## 要点
- eino 是由 CloudWeGo 开发的企业级云原生中间件框架，GitHub 仓库位于 https://github.com/cloudwego/eino
- 框架提供 Agent 开发、组件编排、流程管理等核心能力，支持 Chain、Graph、Workflow 等多种编排方式
- ADK 用于 Agent 开发，Compose 模块用于组件编排，两者协同工作
- 框架支持构建 ReAct Agent 和 RAG 等常见应用模式
- Manus Agent 和 Deer-Go 是基于 eino 框架的完整应用示例，其中 Manus Agent 参考了 OpenManus 项目
- eino 框架与 eino-ext 扩展库配合使用，提供更丰富的组件和功能支持
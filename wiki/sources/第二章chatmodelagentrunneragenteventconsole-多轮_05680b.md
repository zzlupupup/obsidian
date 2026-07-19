---
type: source
created: 2026-07-19
updated: 2026-07-19
source_file: "[[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）.md]]"
tags: [clippings]
aliases: ["Eino 快速入门第二章", "Chapter 2: ChatModelAgent, Runner, AgentEvent"]
contentHash: 1aa7-fddb9271
generation_complete: true
---

# 第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮） - 摘要

## 来源
- 原始文件: [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）.md]]
- 采集日期: 2026-07-19

## 核心内容
本章是 Eino 框架快速入门的第二章，系统介绍了 ADK（Agent Development Kit）的执行抽象层。从 [[concepts/component|Component]] 与 [[concepts/agent|Agent]] 的关系切入，阐明 Component 只是能力单元，需要被组织编排，而 Agent 封装完整业务逻辑可直接运行。[[concepts/chatmodelagent|ChatModelAgent]] 作为最简单的 Agent 实现，内部仅使用 [[concepts/chatmodel|ChatModel]]，但已具备完整能力框架，后续可扩展 [[concepts/tool|Tool]]、middleware、interrupt 等能力。[[concepts/runner|Runner]] 负责管理 Agent 生命周期、[[concepts/checkpointstore|CheckPointStore]] 支持和事件流封装，提供 Run() 和 Query() 两种便捷方法。[[concepts/agentevent|AgentEvent]] 作为事件驱动输出单元，包含 [[concepts/agentoutput|Output]]、[[concepts/agentaction|Action]] 和 Err 字段。[[concepts/asynciterator|AsyncIterator]] 作为非阻塞流式迭代器，让消费者实时消费执行事件。最后通过 Console 多轮对话示例，演示调用侧维护 history 实现多轮交互。

## 关键实体
- [[entities/openai|OpenAI]] - ChatModel 组件支持的模型提供商之一
- [[entities/ark|Ark]] - ChatModel 组件支持的模型服务之一

## 关键概念
- [[concepts/agent|Agent]] - ADK 核心接口，定义智能体基本行为
- [[concepts/chatmodelagent|ChatModelAgent]] - Agent 接口的最简单实现，基于 ChatModel 构建
- [[concepts/runner|Runner]] - 执行 Agent 的入口点，管理生命周期
- [[concepts/agentevent|AgentEvent]] - Runner 返回的事件单元，支持事件驱动输出
- [[concepts/asynciterator|AsyncIterator]] - 非阻塞流式迭代器，用于消费事件流
- [[concepts/component|Component]] - 可替换、可组合的能力单元
- [[concepts/chatmodel|ChatModel]] - 负责与大语言模型通信的核心组件
- [[concepts/tool|Tool]] - Agent 使用的执行能力组件
- [[concepts/多轮对话|多轮对话]] - 通过调用侧维护 history 实现的交互模式
- [[concepts/checkpointstore|CheckPointStore]] - 用于中断恢复的状态存储
- [[concepts/agentinput|AgentInput]] - Agent Run() 方法接收的输入参数类型
- [[concepts/agentoutput|AgentOutput]] - AgentEvent 中的输出内容字段
- [[concepts/agentaction|AgentAction]] - AgentEvent 中的控制动作字段
- [[concepts/agenticmessage|AgenticMessage]] - schema 包定义的标准消息类型
- [[concepts/workflowagent|WorkflowAgent]] - Agent 接口的工作流实现类型
- [[concepts/supervisoragent|SupervisorAgent]] - Agent 接口的监督实现类型
- [[concepts/typedagentevent|TypedAgentEvent]] - AgentEvent 的泛型类型化版本
- [[concepts/runstep|RunStep]] - 记录 Agent 执行步骤路径的类型

## 要点
- **Agent 是核心抽象**: [[concepts/agent|Agent]] 定义了 Name()、Description() 和 Run() -> AsyncIterator[*AgentEvent] 方法，所有 Agent 类型（[[concepts/chatmodelagent|ChatModelAgent]]、[[concepts/workflowagent|WorkflowAgent]]、[[concepts/supervisoragent|SupervisorAgent]] 等）都实现此统一接口
- **Component 与 Agent 的层级关系**: [[concepts/component|Component]] 是底层能力单元，[[concepts/agent|Agent]] 是更高层抽象，组合多种 Component 并封装完整业务逻辑；[[concepts/chatmodel|ChatModel]] 像数据库驱动，[[concepts/chatmodelagent|ChatModelAgent]] 像业务逻辑层
- **Runner 提供运行时能力**: [[concepts/runner|Runner]] 管理生命周期、[[concepts/checkpointstore|CheckPointStore]] 中断恢复和事件流封装，直接调用 Agent.Run() 会缺少这些运行时能力
- **AgentEvent 三维信息**: [[concepts/agentevent|AgentEvent]] 包含 [[concepts/agentoutput|Output]]（消息输出）、[[concepts/agentaction|Action]]（控制动作）和 Err（错误），支持流式响应和复杂场景
- **AsyncIterator 实时消费**: [[concepts/asynciterator|AsyncIterator]] 每次 Run() 创建新迭代器，消费一次后不可重复使用，是实现事件驱动架构的基础
- **多轮对话实现机制**: [[concepts/多轮对话|多轮对话]] 通过调用侧维护 history 实现，使用 msgops.NewUser 和 msgops.NewAssistant 管理消息追加，每次 Run() 完成一轮模型调用

---
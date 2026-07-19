---
type: concept
created: 2026-07-19
updated: 2026-07-19
sources: ["[[sources/第二章chatmodelagentrunneragenteventconsole-多轮_05680b]]"]
tags: [term]
aliases:
  - "Agent 控制动作"
  - "AgentAction 控制动作"
generation_complete: true
---


# AgentAction

## 定义
AgentAction 是 [[concepts/agentevent|agentevent]] 结构体中的一个字段，表示 Agent 执行过程中的控制动作。它涵盖中断、转移、退出等控制动作类型，与 AgentEvent 的 Output 字段并列存在：Output 携带消息输出内容，而 Action 携带执行流程的控制信号。这一设计使得 Agent 的事件流不仅能传递模型生成的消息，还能传递对执行流程的控制指令，为中断恢复、状态转移等高级能力奠定基础。

## 关键特征
- **控制信号载体**：AgentAction 专门用于携带执行流程的控制指令，区别于携带消息内容的 Output 字段
- **多种动作类型**：涵盖中断（interrupt）、转移（transfer）、退出（exit）等多种控制动作类型
- **事件流增强**：使 Agent 事件流具备双向传递能力——既传递模型生成的消息，也传递流程控制指令
- **高级能力基础**：为中断恢复、状态转移等高级执行流程控制能力提供底层支持
- **与 Output 并列**：在 [[concepts/agentevent|agentevent]] 结构中，Action 与 Output 作为两个独立字段并列存在，职责分离

## 应用
- **中断与恢复**：在 Agent 执行过程中触发中断动作，配合检查点机制实现执行状态的保存与恢复
- **状态转移**：通过转移动作控制 Agent 在不同执行阶段之间的流转
- **流程退出**：在满足特定条件时通过退出动作终止 Agent 执行流程
- **多轮对话控制**：在 [[concepts/多轮对话|多轮对话]] 场景中，利用 Action 字段传递对话流程的控制信号，协调多步骤交互
- **[[concepts/runner|runner]] 编排**：在 Runner 执行框架中，Action 字段为执行流程的动态调度提供控制指令通道

## 相关概念
- [[concepts/agentevent|agentevent]] - AgentAction 所属的结构体，包含 Output 和 Action 两个字段
- [[concepts/agent|agent]] - AgentAction 所服务的智能体接口
- [[concepts/runner|runner]] - 执行 Agent 并产生 AgentEvent 流的运行器
- [[concepts/interruptresume|interruptresume]] - AgentAction 中断动作所支持的核心能力
- [[concepts/checkpoint|checkpoint]] - 与中断动作配合实现状态保存与恢复

## 相关实体
无相关实体

---

## 来源提及

- "Action *AgentAction  // 控制动作" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
- "event.Action：中断/转移/退出等控制动作（后续章节用到）" — [[raw/第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）|第二章：ChatModelAgent、Runner、AgentEvent（Console 多轮）]]
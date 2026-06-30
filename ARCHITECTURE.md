# ARCHITECTURE.md

> AI Conversation Studio（ACS）
>
> 系统架构设计规范（Architecture Specification）
>
> Version：2.0
>
> Status：Active
>
> Priority：High
>
> Scope：Entire Repository

---

# 一、文档说明

本文件定义整个 AI Conversation Studio（ACS）的系统架构。

任何模块开发之前，都必须遵循本架构规范。

本文件负责规定：

- 系统架构
- 模块划分
- 分层原则
- 模块依赖
- AI 引擎
- Workflow
- Prompt
- Knowledge（RAG）
- Plugin
- Runtime
- Storage
- Version
- 可扩展设计

不涉及：

- AI 行为规范（CLAUDE.md）
- 编码规范（CODING_RULES.md）
- Review（REVIEW_RULES.md）

---

# 二、总体架构目标

ACS 必须构建成为：

一个企业级 AI 对话平台。

平台应满足：

- 配置驱动
- 插件化
- 高内聚
- 低耦合
- 可扩展
- 可测试
- 可维护
- 可观测

所有模块均可独立演进。

任何业务能力不得直接耦合到底层实现。

---

# 三、总体架构原则

整个系统必须遵循：

## Clean Architecture（整洁架构）

业务逻辑独立。

框架可替换。

数据库可替换。

UI 可替换。

模型可替换。

---

## DDD（领域驱动设计）

按领域划分模块。

禁止按技术划分业务。

例如：

正确：

Conversation

Workflow

Knowledge

Prompt

Agent

Tool

Memory

错误：

controller

service

util

dao

---

## SOLID

所有模块必须遵循：

- 单一职责
- 开闭原则
- 里氏替换
- 接口隔离
- 依赖倒置

---

## Configuration First

所有业务行为优先配置化。

不得写死：

Prompt

Workflow

Knowledge

Model

Provider

---

## Plugin First

所有第三方能力必须插件化。

不得依赖具体厂商。

---

# 四、系统架构

```
                        Admin UI
                            │
                            ▼
                    API Gateway
                            │
──────────────────────────────────────────────

Conversation Engine

Workflow Engine

Prompt Engine

Knowledge Engine

Memory Engine

Intent Engine

Skill Engine

Tool Engine

Plugin Engine

──────────────────────────────────────────────

Application Layer

──────────────────────────────────────────────

Domain Layer

──────────────────────────────────────────────

Infrastructure Layer

──────────────────────────────────────────────

Storage / Provider
```

各层职责清晰。

禁止跨层调用。

---

# 五、模块划分

平台划分为以下核心领域：

## Conversation

负责：

会话生命周期。

上下文。

状态管理。

消息流。

---

## Workflow

负责：

流程编排。

节点执行。

条件判断。

异常恢复。

版本管理。

---

## Prompt

负责：

Prompt 管理。

Prompt 版本。

Prompt 发布。

Prompt 调试。

---

## Knowledge

负责：

RAG。

Chunk。

Embedding。

Retrieval。

Metadata。

引用。

---

## Agent

负责：

Agent 生命周期。

Skill。

Memory。

Tool。

Workflow。

---

## Memory

负责：

长期记忆。

短期记忆。

会话记忆。

用户记忆。

---

## Tool

负责：

HTTP。

MCP。

Python。

Function。

API。

SQL。

Plugin。

---

## Plugin

负责：

统一 Provider。

Adapter。

驱动管理。

---

## Runtime

负责：

统一运行时。

任务调度。

事件管理。

生命周期。

---

# 六、模块依赖原则

允许：

UI

↓

API

↓

Application

↓

Domain

↓

Infrastructure

禁止：

Infrastructure

↓

Domain

禁止：

UI

↓

Repository

禁止：

Domain

↓

Controller

所有依赖必须单向。

---

# 七、Workflow 架构

Workflow 必须支持：

开始节点。

LLM 节点。

条件节点。

HTTP 节点。

Knowledge 节点。

Tool 节点。

人工节点。

循环节点。

结束节点。

Workflow 必须：

可视化。

可版本化。

可调试。

可回滚。

---

# 八、Prompt 架构

Prompt 必须独立管理。

每个 Prompt 包含：

ID

名称

版本

变量

模板

模型

温度

上下文

发布时间

Prompt 不得写死在代码。

---

# 九、Knowledge（RAG）架构

Knowledge 支持：

文档上传。

Chunk。

Embedding。

Metadata。

Hybrid Search。

ReRank。

Citation。

Version。

Chunk Strategy。

Embedding Provider。

Retrieval Strategy。

全部配置化。

---

# 十、Plugin 架构

Provider：

LLM

Embedding

ASR

TTS

Storage

SMS

Email

Webhook

CRM

ERP

全部通过统一接口接入。

新增 Provider：

不得修改业务代码。

---

# 十一、Runtime 架构

Runtime 管理：

Workflow。

Conversation。

Tool。

Memory。

Prompt。

Knowledge。

Runtime 应支持：

生命周期。

调度。

异常恢复。

日志。

监控。

---

# 十二、存储架构

支持：

MySQL

PostgreSQL

Redis

MinIO

S3

Vector DB：

FAISS

Milvus

pgvector

Chroma

允许自由切换。

---

# 十三、UI 架构

所有后台页面统一：

Layout。

Theme。

Permission。

Loading。

Error。

Empty。

Responsive。

国际化。

所有页面风格保持一致。

---

# 十四、版本管理

所有核心对象必须版本化。

包括：

Workflow。

Prompt。

Knowledge。

Robot。

Agent。

Skill。

Plugin。

API。

支持：

发布。

回滚。

Diff。

审计。

---

# 十五、可扩展原则

新增：

模型。

Provider。

Workflow。

Prompt。

Knowledge。

Plugin。

Agent。

不得修改核心代码。

必须通过：

配置。

插件。

接口。

扩展实现。

---

# 十六、长期演进原则

未来支持：

Multi-Agent。

Reasoning。

Computer Use。

MCP。

Voice。

Video。

Digital Human。

Cloud。

Private Deployment。

SaaS。

所有设计均应兼容未来能力。

---

# 十七、架构约束

严禁：

硬编码。

循环依赖。

重复模块。

跨层调用。

共享状态。

紧耦合。

复制 Workflow。

复制 Prompt。

复制 Knowledge。

任何架构调整，都必须保证：

向后兼容。

长期可维护。

长期可扩展。

---

# 十八、最终原则

架构永远优先于实现。

平台永远优先于业务。

配置永远优先于代码。

插件永远优先于修改。

复用永远优先于重写。

长期演进永远优先于短期需求。

---

# 文档关系

CLAUDE.md

↓

PROJECT.md

↓

ARCHITECTURE.md

↓

TRAE_RULES.md

↓

CODING_RULES.md

↓

REVIEW_RULES.md

↓

TASK_EXECUTION.md

↓

MEMORY.md
# PROJECT.md

> AI Conversation Studio（ACS）
>
> 项目定义文档（Project Definition）
>
> Version：1.0
>
> Priority：High
>
> Scope：Entire Repository
>
> Status：Active

---

# 一、文档说明

本文件用于定义 AI Conversation Studio（ACS）项目本身。

它回答以下问题：

- 项目是什么？
- 项目为什么存在？
- 项目最终目标是什么？
- 平台需要具备哪些能力？
- 平台未来的发展方向是什么？

本文件仅描述项目本身，不涉及：

- AI 行为规范（CLAUDE.md）
- 系统架构（ARCHITECTURE.md）
- 编码规范（CODING_RULES.md）
- Review 规范（REVIEW_RULES.md）

---

# 二、项目使命（Project Mission）

AI Conversation Studio（ACS）的目标是打造一个完整的企业级 AI 对话开发平台。

当前版本（V1）：

构建一个完整的 AI Conversation Platform。

当前阶段暂不接入真实电话系统。

所有会话均通过 Mock Call Engine（模拟通话引擎）完成。

未来平台应支持无缝接入：

- SIP
- FreeSWITCH
- Asterisk
- 腾讯云
- 阿里云
- Twilio
- Genesys
- ASR（语音识别）
- TTS（语音合成）

在接入上述能力时，不允许修改 AI Core（AI 核心）。

今天开发的所有能力，都必须支持未来扩展。

任何业务实现，都不得阻碍未来平台演进。

---

# 三、项目愿景（Vision）

ACS 的长期目标是成为：

**企业级 AI 对话开发平台（Enterprise AI Conversation Platform）。**

平台帮助企业：

- 构建 AI 对话系统
- 管理 AI 对话系统
- 部署 AI 对话系统
- 优化 AI 对话系统

所有能力均应通过：

**配置（Configuration）**

而不是

**硬编码（Hard Coding）**

完成。

平台应持续支持快速创新，同时保持工程质量。

---

# 四、项目定位（Project Position）

ACS 是：

一个 AI 对话平台（Platform）。

而不是：

- 一个 AI 客服机器人
- 一个 AI 外呼机器人
- 一个 AI 呼入机器人
- 一个 ChatBot
- 一个行业解决方案

所有具体业务，都建立在平台能力之上。

平台保持业务无关（Business Agnostic）。

---

# 五、核心目标（Core Objectives）

整个项目只有一个最终目标：

> 构建一个可配置的平台，而不是构建一个固定机器人。

平台必须满足：

- 可配置（Configurable）
- 可复用（Reusable）
- 可替换（Replaceable）
- 可测试（Testable）
- 可版本化（Versioned）
- 可观测（Observable）
- 可扩展（Extensible）

以下内容严禁硬编码：

- Prompt
- Workflow
- Knowledge
- Model
- Robot Behavior

机器人所有行为必须来源于配置。

---

# 六、平台能力（Platform Objectives）

平台最终应提供以下统一能力。

## Prompt 管理

统一 Prompt 管理。

Prompt 版本管理。

Prompt 调试。

Prompt 发布。

---

## Workflow 管理

可视化 Workflow Designer。

Workflow 调试。

Workflow 发布。

Workflow 版本管理。

---

## Knowledge（RAG）

知识库管理。

知识检索。

知识更新。

知识版本。

---

## Robot

机器人管理。

机器人配置。

机器人生命周期。

---

## Skill

Skill 管理。

Skill 调用。

Skill 扩展。

---

## Plugin

插件体系。

统一 Provider。

统一 Adapter。

统一接口。

---

## Model

模型管理。

模型切换。

模型配置。

---

## Version

版本管理。

版本发布。

版本回滚。

---

## Testing

测试中心。

Prompt 测试。

Workflow 测试。

Knowledge 测试。

Agent 测试。

---

## Debug

调试中心。

Conversation Debug。

Workflow Debug。

Prompt Debug。

---

## Monitoring

日志。

Tracing。

Metrics。

可观测。

---

## Dashboard

运营分析。

数据统计。

系统监控。

---

## Open API

开放接口。

第三方集成。

SDK。

Webhook。

所有子系统必须支持独立演进。

---

# 七、工程使命（Engineering Mission）

平台统一支持：

- AI Customer Service（AI 客服）
- AI Outbound Calling（AI 外呼）
- AI Inbound Calling（AI 呼入）
- Voice Assistant（语音助手）
- ChatBot（聊天机器人）
- Knowledge QA（知识问答）
- Workflow Automation（工作流自动化）
- Prompt Engineering（Prompt 工程）
- Multi-Agent Collaboration（多 Agent 协作）

未来所有 AI 场景均应共享统一平台能力。

---

# 八、平台设计原则

平台始终坚持：

- 配置驱动（Configuration Driven）
- Workflow 驱动（Workflow Driven）
- Knowledge 驱动（Knowledge Driven）
- Plugin Based（插件化）
- Event Driven（事件驱动）
- Version Controlled（版本管理）
- Highly Observable（高可观测）
- Secure by Default（默认安全）
- Cloud Ready（云原生）
- Multi-Tenant Ready（多租户）
- Extensible（可扩展）
- Maintainable（可维护）
- Production Ready（生产可用）

---

# 九、用户体验目标

平台应支持用户：

无需修改代码即可：

- 创建 Prompt
- 创建 Workflow
- 管理知识库
- 管理机器人
- 配置 Agent
- 调试 AI
- 优化 AI

降低业务人员使用 AI 的技术门槛。

---

# 十、持续演进

平台应持续支持：

新增：

- LLM
- Speech Model
- Embedding Model
- Retrieval Strategy
- Multi-Agent
- Reasoning Model
- Enterprise Integration

未来新增能力，应优先通过：

- Plugin
- Adapter
- Configuration

完成，而不是修改核心代码。

---

# 十一、成功标准（Success Criteria）

当平台能够提供：

✓ 稳定架构

✓ 完整开发框架

✓ 可配置 AI 平台

✓ 可复用工程能力

✓ 企业级可靠性

✓ 配置驱动开发

✓ 完整文档体系

✓ 人机协同开发

并支持长期持续演进时。

项目视为成功。

---

# 十二、最终目标（Ultimate Objective）

AI Conversation Studio 的最终目标是：

打造一个：

现代化

企业级

配置驱动

插件化

长期可维护

长期可扩展

AI 对话开发平台。

帮助企业：

设计

部署

管理

优化

治理

各种智能对话系统。

实现：

**最少代码（Minimal Code）**

**最大灵活性（Maximum Flexibility）**

**长期可维护（Long-term Maintainability）**

---

# 十三、最终原则（Final Principle）

整个项目始终坚持：

构建平台，

而不是功能。

构建能力，

而不是方案。

构建配置，

而不是硬编码。

构建长期架构，

而不是技术债。

每一个工程决策，都必须让平台：

更简单。

更稳定。

更容易扩展。

更容易维护。

---

# 文档关系

CLAUDE.md
        │
        ▼
PROJECT.md
        │
        ▼
ARCHITECTURE.md
        │
        ▼
TRAE_RULES.md
        │
        ▼
CODING_RULES.md
        │
        ▼
REVIEW_RULES.md
        │
        ▼
TASK_EXECUTION.md
        │
        ▼
MEMORY.md
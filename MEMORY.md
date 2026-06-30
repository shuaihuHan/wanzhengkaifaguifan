# MEMORY.md

> AI Conversation Studio（ACS）
>
> 工程长期记忆（Project Memory）
>
> Version：2.0
>
> Status：Active
>
> Priority：Medium
>
> Scope：Entire Repository

---

# 一、文档说明

本文件用于保存整个项目的长期工程记忆（Project Memory）。

目标：

避免 AI 在不同开发任务之间丢失关键工程背景。

Memory 保存的是：

- 架构决策
- 技术决策
- 长期约束
- 历史原因
- 开发经验
- 已知问题
- 未来规划

Memory 不保存：

- 临时需求
- 临时调试信息
- 一次性 Bug
- 用户聊天内容
- 敏感信息
- 个人信息

本文件属于长期维护文档。

---

# 二、Memory 使用原则

Memory 仅记录：

长期有效。

未来仍有参考价值。

能够影响后续开发。

所有内容必须：

真实。

准确。

可验证。

禁止记录猜测或未经确认的信息。

---

# 三、项目长期目标

AI Conversation Studio 的长期目标保持不变：

构建：

企业级

配置驱动

插件化

AI Conversation Platform。

任何开发决策都必须围绕这一目标。

不得为了短期需求破坏长期架构。

---

# 四、长期架构决策（Architecture Decisions）

以下架构决策已确定，不得随意修改。

## Decision 001

平台采用：

Configuration First。

所有业务能力优先配置实现。

---

## Decision 002

平台采用：

Workflow First。

业务流程通过 Workflow 编排。

---

## Decision 003

平台采用：

Prompt First。

Prompt 独立管理。

不得写入代码。

---

## Decision 004

平台采用：

Knowledge First。

业务知识进入 Knowledge（RAG）。

不得直接写入 Prompt。

---

## Decision 005

平台采用：

Plugin First。

所有第三方能力统一插件化。

---

## Decision 006

平台采用：

Provider Abstraction。

业务代码不得依赖具体模型厂商。

---

## Decision 007

平台采用：

Version Everywhere。

以下对象必须支持版本管理：

- Prompt
- Workflow
- Knowledge
- Agent
- Plugin
- API

---

# 五、技术选型记录（Technical Decisions）

当前长期技术方向：

架构：

- Clean Architecture
- DDD
- SOLID

开发方式：

- AI Native
- Configuration Driven
- Workflow Driven

未来如需调整，应记录原因与影响。

---

# 六、已确认的工程约束

以下约束长期有效：

- 不允许硬编码 Prompt。
- 不允许硬编码 Workflow。
- 不允许硬编码业务知识。
- 不允许业务代码直接调用 Provider。
- 不允许跨层依赖。
- 不允许重复实现公共能力。
- 不允许破坏模块边界。

所有新开发均需遵守。

---

# 七、历史决策记录（Decision Log）

## ADR-001

采用配置驱动架构。

原因：

降低代码耦合。

支持业务快速调整。

---

## ADR-002

Workflow 独立管理。

原因：

降低流程修改成本。

---

## ADR-003

Prompt 独立版本管理。

原因：

支持持续优化。

支持回滚。

---

## ADR-004

Knowledge 独立管理。

原因：

提高知识维护效率。

减少 Prompt 长度。

---

## ADR-005

Provider 抽象层。

原因：

支持模型快速切换。

降低厂商绑定风险。

新增架构决策时，应持续追加 ADR 编号。

不得覆盖历史记录。

---

# 八、已知限制（Known Limitations）

当前已知限制：

- Mock Call Engine 用于模拟通话。
- 暂未接入真实电话系统。
- Provider 接入范围将逐步扩展。
- Marketplace 功能规划中。

所有开发需考虑这些限制。

---

# 九、开发经验（Lessons Learned）

长期记录具有参考价值的经验。

例如：

- Prompt 应保持职责单一。
- Workflow 不宜过度复杂。
- Chunk 大小需根据业务调整。
- Knowledge 应持续维护。
- Provider 必须统一抽象。

经验应来源于实际开发。

禁止记录主观意见。

---

# 十、技术债（Technical Debt）

发现技术债时，应记录：

编号：

TD-001

内容：

问题描述。

影响范围。

产生原因。

建议方案。

优先级。

状态：

Open / Resolved。

技术债不得长期忽略。

---

# 十一、未来规划（Future Roadmap）

长期规划包括：

- Multi-Agent
- Voice
- Video
- MCP
- Reasoning Model
- Plugin Marketplace
- Prompt Marketplace
- Workflow Marketplace
- Knowledge Marketplace
- SaaS
- 私有化部署

未来规划可持续更新。

---

# 十二、Memory 更新规则

满足以下条件时，应更新 Memory：

- 新增长期架构决策。
- 技术路线调整。
- 新增长期约束。
- 新增重要经验。
- 解决长期技术债。
- 新增重要 ADR。

普通开发无需更新。

---

# 十三、禁止记录内容

禁止记录：

- 用户隐私
- 密钥
- Token
- 密码
- 临时调试信息
- 临时需求
- 未确认方案
- 敏感业务数据

Memory 必须保持长期有效。

---

# 十四、AI 使用 Memory 的原则

AI 在开发前应读取 Memory。

开发过程中应：

尊重历史决策。

避免重复讨论已确定方案。

保持架构一致性。

如果需要推翻已有决策：

必须说明：

- 原因
- 风险
- 替代方案
- 影响范围

未经充分评估，不得修改长期决策。

---

# 十五、最终原则

Memory 是项目的长期知识资产。

所有长期决策：

可追溯。

可解释。

可持续维护。

每一次更新，都应帮助未来开发者更快理解项目，而不是增加混乱。

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
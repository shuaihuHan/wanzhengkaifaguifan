# TRAE_RULES.md

> AI Conversation Studio（ACS）
>
> Trae AI 开发执行规范（Trae Development Rules）
>
> Version：2.0
>
> Status：Active
>
> Priority：High
>
> Scope：AI Daily Development

---

# 一、文档说明

本文件规定 Trae 在本项目中的日常开发流程。

目标：

让 AI 每一次开发任务都遵循统一流程，而不是随意生成代码。

本文件规定：

- 开发流程
- 思考方式
- 执行规范
- 输出规范
- 自检流程
- 任务完成标准

本文件不负责：

- 项目目标（PROJECT.md）
- 系统架构（ARCHITECTURE.md）
- 编码规范（CODING_RULES.md）

---

# 二、开发原则

Trae 每完成一个任务，都必须遵循：

**理解 > 分析 > 设计 > 开发 > 检查 > Review > 完成交付**

严禁直接开始编写代码。

---

# 三、任务执行流程

收到任务后，必须按照以下流程执行：

```
接收任务
    │
    ▼
理解需求
    │
    ▼
阅读 CLAUDE.md
    │
    ▼
阅读 PROJECT.md
    │
    ▼
阅读 ARCHITECTURE.md
    │
    ▼
分析现有代码
    │
    ▼
设计方案
    │
    ▼
风险评估
    │
    ▼
开始开发
    │
    ▼
自检
    │
    ▼
Review
    │
    ▼
更新文档
    │
    ▼
任务完成
```

任何阶段均不得跳过。

---

# 四、需求分析规则

开始开发前必须确认：

## 需求目标

本次要解决什么问题？

最终交付什么？

成功标准是什么？

---

## 影响范围

影响哪些模块？

影响哪些接口？

影响哪些 Workflow？

影响哪些 Prompt？

影响哪些数据库？

---

## 风险分析

是否影响旧版本？

是否影响生产环境？

是否影响其他业务？

是否存在兼容性问题？

分析完成后，方可开始设计。

---

# 五、开发规则

开发过程中必须遵循：

优先：

复用

↓

扩展

↓

新增

不得：

复制已有代码。

重复实现。

修改稳定接口。

绕过架构。

硬编码业务。

---

# 六、代码生成规则

AI 输出代码必须：

完整。

可运行。

符合架构。

符合编码规范。

包含异常处理。

包含日志。

支持配置。

支持扩展。

不得输出：

Demo。

伪代码。

临时实现。

未完成代码。

---

# 七、配置优先规则

能够配置实现的功能：

不得写代码。

例如：

Prompt

Workflow

Knowledge

Skill

Temperature

Provider

变量

全部通过配置完成。

---

# 八、插件优先规则

涉及：

LLM

ASR

TTS

Storage

CRM

ERP

Webhook

全部走 Plugin。

不得直接依赖厂商 SDK。

---

# 九、Workflow 优先规则

涉及业务流程：

优先 Workflow。

不得：

把流程写死在代码。

Workflow 应负责：

流程。

判断。

节点。

Tool 调用。

Knowledge。

LLM。

---

# 十、Prompt 优先规则

涉及：

角色

话术

输出格式

总结

分类

判断

全部优先 Prompt。

不得：

把 Prompt 写进 Java / Python / TypeScript 代码。

---

# 十一、Knowledge 优先规则

涉及：

知识问答

FAQ

产品说明

业务规则

操作手册

优先：

Knowledge。

不得：

把知识直接写进 Prompt。

---

# 十二、开发完成后的自检

开发完成后必须检查：

是否符合架构？

是否符合规范？

是否存在重复代码？

是否遗漏异常？

是否遗漏日志？

是否支持配置？

是否支持插件？

是否支持扩展？

全部通过后才能进入 Review。

---

# 十三、Review 执行

完成开发后必须执行：

Architecture Review

↓

Code Review

↓

Prompt Review

↓

Workflow Review

↓

Knowledge Review

↓

Security Review

↓

Performance Review

Review 不通过：

禁止提交。

---

# 十四、输出规范

每次任务结束必须输出：

## 任务目标

说明完成内容。

---

## 实现方案

说明设计方式。

---

## 修改内容

新增：

文件。

接口。

Workflow。

Prompt。

Knowledge。

配置。

---

## 风险

说明：

兼容性。

性能。

安全。

部署。

---

## 后续建议

说明：

优化方向。

技术债。

未来扩展。

---

# 十五、禁止行为

禁止：

直接生成代码。

猜测需求。

编造 API。

编造数据库。

跳过设计。

跳过 Review。

跳过测试。

删除已有能力。

修改稳定接口。

引入重复代码。

绕过 Workflow。

绕过 Prompt。

绕过 Knowledge。

绕过 Plugin。

---

# 十六、持续开发原则

每一次开发，都必须让项目：

更加：

稳定。

简单。

统一。

规范。

易维护。

易扩展。

不得因为一次需求：

破坏整体架构。

---

# 十七、Definition of Done

一个任务完成时必须满足：

✓ 功能完成

✓ 架构正确

✓ 配置完成

✓ Workflow 正常

✓ Prompt 正常

✓ Knowledge 正常

✓ Review 完成

✓ 测试完成

✓ 文档更新

✓ 可正常运行

否则不得标记完成。

---

# 十八、AI 输出要求

AI 输出必须：

准确。

完整。

可运行。

可维护。

可扩展。

不得输出：

半成品。

TODO。

FIXME。

Placeholder。

Demo。

Mock（非要求情况下）。

---

# 十九、每日执行准则

Trae 每完成一个需求，都必须坚持：

先理解。

再设计。

再开发。

先复用。

后新增。

先配置。

后代码。

先插件。

后耦合。

长期架构优先。

短期需求其次。

---

# 二十、最终执行原则

Trae 是：

AI 软件工程师。

AI 架构师。

AI Review 工程师。

AI 文档工程师。

AI 不只是生成代码。

AI 负责整个软件生命周期。

任何开发，都必须保证：

平台越来越稳定。

架构越来越清晰。

代码越来越规范。

能力越来越可复用。

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
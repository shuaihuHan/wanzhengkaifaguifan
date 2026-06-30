# REVIEW_RULES.md

> AI Conversation Studio（ACS）
>
> AI 自动审查规范（Review Rules）
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

本文件定义整个项目的统一 Review（代码审查）规范。

Review 是开发流程中的强制步骤。

任何功能在通过 Review 前，不得标记为完成。

Review 的目标不是挑错，而是确保：

- 架构正确
- 功能正确
- 代码规范
- Prompt 合理
- Workflow 正确
- Knowledge 可维护
- 系统安全
- 长期可扩展

---

# 二、Review 原则

所有 Review 必须遵循以下原则：

- 客观（Objective）
- 全面（Comprehensive）
- 可验证（Verifiable）
- 可追踪（Traceable）
- 可改进（Actionable）

Review 应关注系统整体质量，而不是个人编码风格。

---

# 三、Review 执行时机

以下场景必须执行 Review：

- 新增功能
- 修改功能
- 修复 Bug
- 调整架构
- 修改 Prompt
- 修改 Workflow
- 修改 Knowledge
- 修改插件
- 修改 Provider
- 修改公共接口

任何影响生产能力的变更，都必须 Review。

---

# 四、Review 流程

统一执行流程：

```
开发完成
    │
    ▼
架构检查
    │
    ▼
代码检查
    │
    ▼
Prompt 检查
    │
    ▼
Workflow 检查
    │
    ▼
Knowledge 检查
    │
    ▼
安全检查
    │
    ▼
性能检查
    │
    ▼
文档检查
    │
    ▼
Review 通过
```

任何一项未通过，都不得结束任务。

---

# 五、架构 Review

检查内容：

- 是否符合 ARCHITECTURE.md
- 是否遵循分层设计
- 是否存在循环依赖
- 是否新增不必要模块
- 是否破坏模块职责
- 是否影响已有架构
- 是否支持未来扩展

发现架构问题时，应优先整改。

---

# 六、代码 Review

检查内容：

- 是否符合 CODING_RULES.md
- 是否存在重复代码
- 是否存在硬编码
- 是否存在魔法值
- 是否存在超长函数
- 是否命名规范
- 是否包含异常处理
- 是否包含日志
- 是否易于维护

禁止因为赶工忽略代码质量。

---

# 七、Prompt Review

检查内容：

- Prompt 是否职责单一
- 是否支持变量配置
- 是否可复用
- 是否存在重复 Prompt
- 是否包含无效指令
- 是否存在歧义
- 是否易于维护
- 是否支持版本管理

禁止将 Prompt 写入业务代码。

---

# 八、Workflow Review

检查内容：

- 是否存在重复流程
- 是否节点职责清晰
- 是否可配置
- 是否可调试
- 是否可回滚
- 是否支持版本管理
- 是否遵循平台 Workflow 规范

业务流程应尽可能通过 Workflow 实现。

---

# 九、Knowledge（RAG）Review

检查内容：

- 知识是否准确
- 是否存在重复内容
- Chunk 是否合理
- Metadata 是否完整
- 检索策略是否合理
- 是否支持引用来源
- 是否支持版本管理

禁止将业务知识直接写入 Prompt。

---

# 十、Agent Review

检查内容：

- Agent 职责是否清晰
- Skill 是否可复用
- Tool 是否统一调用
- Memory 是否合理
- Workflow 是否正确
- 是否支持扩展

禁止 Agent 承担多个无关职责。

---

# 十一、安全 Review

检查内容：

- 是否进行权限校验
- 是否存在 SQL 注入风险
- 是否存在 XSS 风险
- 是否存在命令注入风险
- 是否泄露敏感信息
- 是否存在硬编码密钥
- 是否符合安全规范

任何高危安全问题必须优先修复。

---

# 十二、性能 Review

检查内容：

- 是否存在重复查询
- 是否存在重复计算
- 是否存在阻塞调用
- 是否合理使用缓存
- 是否支持异步执行
- 是否存在资源泄漏
- 是否影响系统性能

性能问题应在上线前解决。

---

# 十三、文档 Review

检查内容：

是否同步更新：

- PROJECT.md
- ARCHITECTURE.md
- Prompt 文档
- Workflow 文档
- Knowledge 文档
- API 文档
- README
- 版本记录

文档必须与代码保持一致。

---

# 十四、Review 检查清单（Checklist）

## 架构

□ 架构正确

□ 无循环依赖

□ 模块职责清晰

---

## 代码

□ 命名规范

□ 无重复代码

□ 无硬编码

□ 包含异常处理

□ 包含日志

---

## Prompt

□ 可配置

□ 可复用

□ 已版本化

---

## Workflow

□ 可配置

□ 可调试

□ 已版本化

---

## Knowledge

□ 内容准确

□ Metadata 完整

□ 支持引用

---

## 安全

□ 权限校验

□ 无敏感信息

□ 无安全漏洞

---

## 文档

□ 已更新

□ 与实现一致

全部通过后方可完成 Review。

---

# 十五、Review 结果等级

Review 结果分为四个等级：

## PASS

完全通过。

允许提交。

---

## PASS WITH SUGGESTIONS

允许提交。

但建议后续优化。

---

## NEEDS CHANGES

存在问题。

必须修改后重新 Review。

---

## REJECT

存在重大问题。

禁止提交。

必须重新设计或开发。

---

# 十六、AI 自动 Review 要求

AI 在每次开发完成后，必须自动执行：

1. 架构 Review
2. 代码 Review
3. Prompt Review
4. Workflow Review
5. Knowledge Review
6. Security Review
7. Performance Review
8. Documentation Review

Review 不得遗漏任何模块。

---

# 十七、禁止行为

禁止：

- 跳过 Review
- 仅 Review 代码
- 忽略 Prompt
- 忽略 Workflow
- 忽略 Knowledge
- 忽略安全问题
- 忽略性能问题
- 忽略文档更新
- 带高危 Bug 提交
- 为通过 Review 而隐藏问题

Review 的目标是提升质量，而不是追求通过率。

---

# 十八、最终原则

Review 是质量保障体系的一部分。

每一次 Review，都必须让项目：

更加稳定。

更加规范。

更加安全。

更加易维护。

更加易扩展。

发现问题应及时修复，而不是留作未来技术债。

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
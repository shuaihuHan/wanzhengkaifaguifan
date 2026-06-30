# TASK_EXECUTION.md

> AI Conversation Studio（ACS）
>
> AI 任务执行规范（Task Execution Specification）
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

本文件定义 AI 在整个项目中的统一任务执行流程。

目标：

确保所有开发任务均采用一致的执行方式，保证交付质量、可追溯性和可维护性。

本规范适用于：

- 新功能开发
- Bug 修复
- 架构优化
- Prompt 优化
- Workflow 调整
- Knowledge（RAG）更新
- Agent 配置
- 插件开发

---

# 二、任务生命周期（Task Lifecycle）

所有任务必须严格按照以下生命周期执行：

```
接收任务
    │
    ▼
理解需求
    │
    ▼
分析上下文
    │
    ▼
阅读相关规范
    │
    ▼
制定方案
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
测试验证
    │
    ▼
更新文档
    │
    ▼
输出结果
    │
    ▼
任务完成
```

任何步骤不得跳过。

---

# 三、第一阶段：接收任务

收到任务后，首先确认：

- 任务目标
- 业务背景
- 输入内容
- 输出结果
- 成功标准

如果需求不完整：

停止开发。

先确认需求。

禁止自行猜测业务逻辑。

---

# 四、第二阶段：分析上下文

开发前必须了解：

- 当前模块
- 当前架构
- 已有实现
- 相关 Prompt
- 相关 Workflow
- 相关 Knowledge
- 配置文件
- 接口依赖

优先复用已有能力。

禁止重复开发。

---

# 五、第三阶段：阅读规范

开始设计前必须阅读：

1. CLAUDE.md
2. PROJECT.md
3. ARCHITECTURE.md
4. TRAE_RULES.md
5. CODING_RULES.md
6. REVIEW_RULES.md

根据任务需要，再阅读：

- Prompt 文档
- Workflow 文档
- API 文档
- Knowledge 文档

确保设计符合项目规范。

---

# 六、第四阶段：制定方案

方案至少应包含：

## 功能目标

本次开发解决什么问题。

---

## 实现思路

采用什么设计方式。

---

## 影响范围

涉及哪些：

- 模块
- 接口
- Prompt
- Workflow
- Knowledge
- 配置

---

## 风险分析

是否影响：

- 历史功能
- 数据兼容
- 性能
- 安全
- 部署

方案确认后再开始开发。

---

# 七、第五阶段：开发实现

开发必须遵循：

- ARCHITECTURE.md
- CODING_RULES.md
- TRAE_RULES.md

开发原则：

优先：

配置

↓

Workflow

↓

Prompt

↓

Plugin

↓

代码

禁止：

修改核心架构。

重复开发。

绕过统一能力。

---

# 八、第六阶段：自检（Self Check）

开发完成后必须完成自检。

## 架构检查

□ 是否符合架构？

□ 是否破坏模块边界？

□ 是否新增循环依赖？

---

## 功能检查

□ 功能是否完整？

□ 是否满足需求？

□ 是否存在遗漏？

---

## 代码检查

□ 是否符合编码规范？

□ 是否存在重复代码？

□ 是否存在硬编码？

□ 是否包含异常处理？

□ 是否包含日志？

---

## Prompt 检查

□ 是否支持变量？

□ 是否支持版本？

□ 是否可复用？

---

## Workflow 检查

□ 是否可配置？

□ 是否可调试？

□ 是否可扩展？

---

## Knowledge 检查

□ 是否更新知识？

□ 是否支持引用？

□ Metadata 是否完整？

---

## 文档检查

□ 是否更新文档？

□ 是否更新接口？

□ 是否更新配置？

全部通过后，方可进入 Review。

---

# 九、第七阶段：Review

按照 REVIEW_RULES.md 执行：

- 架构 Review
- 代码 Review
- Prompt Review
- Workflow Review
- Knowledge Review
- 安全 Review
- 性能 Review
- 文档 Review

Review 未通过：

禁止进入下一阶段。

---

# 十、第八阶段：测试验证

至少完成：

- 单元测试
- 集成测试
- Prompt 测试
- Workflow 测试
- Knowledge 检索测试
- 回归测试

核心功能必须验证：

- 正常流程
- 异常流程
- 边界条件

---

# 十一、第九阶段：更新文档

开发完成后同步更新：

- README
- Prompt 文档
- Workflow 文档
- API 文档
- Knowledge 文档
- Architecture 文档（如涉及）
- Change Log

确保文档与实现保持一致。

---

# 十二、第十阶段：输出结果

每次任务结束时，统一输出：

## 1. 任务目标

本次完成内容。

---

## 2. 实现方案

采用的设计方式。

---

## 3. 修改内容

包括：

- 新增文件
- 修改文件
- 删除文件
- 配置修改
- Workflow 修改
- Prompt 修改
- Knowledge 更新

---

## 4. 测试结果

说明：

已完成测试。

测试范围。

测试结果。

---

## 5. 风险说明

说明：

兼容性。

性能。

安全。

部署。

---

## 6. 后续建议

包括：

优化方向。

技术债。

未来扩展建议。

---

# 十三、完成定义（Definition of Done）

任务完成必须同时满足：

✓ 需求实现

✓ 架构正确

✓ 代码规范

✓ Prompt 正确

✓ Workflow 正确

✓ Knowledge 更新（如涉及）

✓ Review 通过

✓ 测试通过

✓ 文档更新

✓ 可正常运行

任何一项未满足，均不得标记为完成。

---

# 十四、异常处理

出现以下情况时必须暂停任务：

- 需求不明确
- 缺少必要上下文
- 架构冲突
- 安全风险
- 数据一致性风险
- 高危 Bug
- 核心依赖不可用

暂停后应：

记录问题。

说明原因。

等待确认。

禁止继续开发。

---

# 十五、持续优化

每完成一个任务，都应主动思考：

是否可以：

- 提高复用率
- 简化流程
- 优化 Prompt
- 优化 Workflow
- 优化 Knowledge
- 提升性能
- 降低复杂度

持续减少技术债。

---

# 十六、禁止行为

禁止：

- 未分析需求直接开发
- 跳过设计
- 跳过自检
- 跳过 Review
- 跳过测试
- 跳过文档更新
- 输出半成品
- 输出不可运行代码
- 为赶进度牺牲架构质量

任何违规行为均视为任务未完成。

---

# 十七、最终执行原则

AI 应始终坚持：

先理解。

再分析。

再设计。

再开发。

先验证。

再交付。

每一个任务，都应使项目：

更加稳定。

更加规范。

更加易维护。

更加易扩展。

长期价值始终高于短期交付。

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
# CODING_RULES.md

> AI Conversation Studio（ACS）
>
> 编码规范（Coding Rules）
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

本文件定义整个项目的统一编码规范。

所有 AI 和开发人员必须遵循本规范编写代码。

目标：

- 保持统一代码风格
- 提高代码可读性
- 提高可维护性
- 降低技术债
- 保证长期可扩展

---

# 二、编码原则

所有代码必须遵循以下原则：

- 简单（Simple）
- 清晰（Readable）
- 一致（Consistent）
- 可维护（Maintainable）
- 可测试（Testable）
- 可扩展（Extensible）
- 可复用（Reusable）

禁止为了炫技而增加复杂度。

---

# 三、SOLID 原则

所有模块必须遵循：

## 单一职责（SRP）

一个类、函数或模块只负责一件事情。

---

## 开闭原则（OCP）

新增功能通过扩展实现。

不得修改稳定逻辑。

---

## 里氏替换（LSP）

子类必须可以替换父类。

不得破坏接口契约。

---

## 接口隔离（ISP）

接口应保持精简。

不得设计“万能接口”。

---

## 依赖倒置（DIP）

依赖抽象，而不是具体实现。

所有外部能力必须通过接口调用。

---

# 四、命名规范

所有命名必须具有业务语义。

## 类

使用：

PascalCase

例如：

ConversationService

PromptEngine

WorkflowExecutor

---

## 方法

使用：

camelCase

例如：

executeWorkflow()

searchKnowledge()

loadPrompt()

---

## 变量

使用：

camelCase

例如：

userMessage

workflowConfig

knowledgeResult

---

## 常量

使用：

UPPER_SNAKE_CASE

例如：

MAX_RETRY_COUNT

DEFAULT_TIMEOUT

---

## 文件

统一：

kebab-case

例如：

workflow-engine.ts

prompt-service.py

knowledge-manager.java

---

# 五、函数规范

函数必须：

- 职责单一
- 命名清晰
- 参数合理
- 返回值明确

建议：

函数长度 ≤ 50 行。

超过时应拆分。

禁止：

超长函数。

嵌套过深。

复杂条件判断。

---

# 六、类设计规范

一个类负责一个领域。

建议：

类长度 ≤ 500 行。

超过时应拆分。

禁止：

God Object（上帝对象）。

万能工具类。

超大 Service。

---

# 七、模块规范

模块职责必须明确。

推荐结构：

```
conversation/
    controller/
    service/
    domain/
    repository/
    dto/
    config/
```

禁止：

所有逻辑堆积在一个目录。

---

# 八、异常处理

所有异常必须处理。

禁止：

空 Catch。

忽略异常。

吞掉异常。

必须：

记录日志。

返回明确错误。

保留上下文。

---

# 九、日志规范

日志必须：

- 可读
- 可定位
- 可追踪

日志应包含：

时间。

请求 ID。

用户 ID（如适用）。

模块。

异常信息。

禁止输出敏感数据。

---

# 十、配置规范

所有可变内容必须配置化。

包括：

- URL
- API Key
- Prompt
- Workflow
- 超时时间
- 重试次数
- 模型参数

禁止硬编码。

---

# 十一、重复代码

遵循：

DRY（Don't Repeat Yourself）。

发现重复逻辑：

优先抽取公共能力。

不得复制粘贴。

---

# 十二、魔法值（Magic Number）

禁止直接使用：

```
if retry > 3
```

应写为：

```
MAX_RETRY_COUNT = 3
```

所有固定值必须定义常量。

---

# 十三、注释规范

代码应尽量做到自解释。

仅在以下情况添加注释：

- 复杂算法
- 特殊业务规则
- 第三方兼容
- 临时方案（需标明原因）

禁止：

无意义注释。

注释与代码不一致。

---

# 十四、依赖管理

新增依赖前必须确认：

是否已有实现？

是否标准库可完成？

是否维护稳定？

是否安全？

优先级：

标准库

↓

成熟框架

↓

社区库

↓

新增依赖

---

# 十五、性能规范

避免：

- 重复查询
- 重复计算
- 无效循环
- 阻塞调用

优先：

缓存。

异步。

批处理。

连接复用。

---

# 十六、安全规范

禁止：

SQL 注入。

XSS。

命令注入。

敏感信息硬编码。

密码明文存储。

必须：

输入校验。

权限控制。

参数过滤。

数据加密。

---

# 十七、测试要求

新增代码必须支持测试。

至少包括：

- 单元测试
- 异常测试
- 边界测试

核心模块应支持集成测试。

---

# 十八、AI 编码要求

AI 生成代码必须：

完整。

可运行。

符合架构。

符合命名规范。

包含异常处理。

包含日志。

支持配置。

支持扩展。

不得输出：

- Demo
- TODO
- FIXME
- Placeholder
- 无法运行代码

---

# 十九、禁止行为

禁止：

- 重复代码
- 硬编码
- 超长函数
- 超大类
- 空 Catch
- 魔法值
- 无意义注释
- 编造接口
- 编造数据库
- 修改稳定接口
- 绕过架构

任何违反以上规范的代码均不得提交。

---

# 二十、最终原则

所有代码必须满足：

✓ 易读

✓ 易测

✓ 易维护

✓ 易扩展

✓ 易复用

✓ 易定位问题

代码不是为了今天运行。

而是为了未来持续演进。

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
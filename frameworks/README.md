# 🏗️ Agent 开发框架

这里是用于构建 AI Agent 应用的主要开发框架和平台。

<div align="center">

[![Frameworks](https://img.shields.io/badge/Frameworks-10+-blue)](https://github.com/alg-bug-engineer/agent-skills-collections)
[![Language](https://img.shields.io/badge/Language-Python-green)](https://www.python.org/)

</div>

---

## 📑 目录

- [🌟 主流框架](#-主流框架)
- [🔧 专用框架](#-专用框架)
- [📊 框架对比](#-框架对比)
- [🎯 选择指南](#-选择指南)
- [📚 详细文档](#-详细文档)

---

## 🌟 主流框架

最流行和广泛使用的 Agent 开发框架。

### [LangChain](./langchain.md)
- **Stars**: 90k+
- **语言**: Python/TypeScript
- **适合**: 快速开发和原型设计
- **文档**: [官方文档](https://python.langchain.com/)
- **详细介绍**: [查看文档](./langchain.md)

#### 核心特性
- ✅ 链式调用和工作流
- ✅ 丰富的 Agent 类型
- ✅ 强大的工具集成
- ✅ 灵活的记忆系统
- ✅ 活跃的社区支持

#### 适用场景
- 问答系统
- 文档分析
- 自动化工作流
- 多模态应用

### [AutoGen](./autogen.md)
- **Stars**: 30k+
- **语言**: Python
- **适合**: 多智能体协作场景
- **文档**: [官方文档](https://microsoft.github.io/autogen/)
- **详细介绍**: [查看文档](./autogen.md)

#### 核心特性
- ✅ 多智能体对话
- ✅ 代码执行能力
- ✅ 人类参与
- ✅ 可定制智能体
- ✅ 企业级支持

#### 适用场景
- 多智能体协作
- 代码生成和审查
- 研究和开发
- 企业应用

### [CrewAI](./crewai.md)
- **Stars**: 10k+
- **语言**: Python
- **适合**: 角色扮演和任务委派
- **文档**: [官方文档](https://www.crewai.com/)

#### 核心特性
- ✅ 角色扮演智能体
- ✅ 任务委派机制
- ✅ 简洁的 API
- ✅ 快速上手

#### 适用场景
- 团队协作模拟
- 内容创作
- 客户服务
- 咨询服务

---

## 🔧 专用框架

针对特定场景优化的框架。

### [LangGraph](https://github.com/langchain-ai/langgraph)
- **Stars**: 5k+
- **描述**: 状态图框架，用于构建复杂工作流
- **特点**: 可视化、持久化、循环控制

### [Semantic Kernel](https://github.com/microsoft/semantic-kernel)
- **Stars**: 18k+
- **描述**: Microsoft 的 LLM 集成 SDK
- **特点**: 轻量级、多语言支持

### [Haystack](https://github.com/deepset-ai/haystack)
- **Stars**: 15k+
- **描述**: 问答系统框架
- **特点**: 检索增强、企业部署

### [BabyAGI](https://github.com/yoheinakajima/babyagi)
- **Stars**: 15k+
- **描述**: 任务管理自动化
- **特点**: 自动任务生成和优先级排序

### [Camel](https://github.com/camel-ai/camel)
- **Stars**: 10k+
- **描述**: 通信智能体框架
- **特点**: 角色扮演、双向对话

---

## 📊 框架对比

### 功能对比表

| 功能 | LangChain | AutoGen | CrewAI | LangGraph |
|-----|----------|---------|--------|-----------|
| **多智能体** | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| **代码执行** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| **工作流** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| **工具集成** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| **易用性** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| **企业支持** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| **学习曲线** | 中等 | 较高 | 低 | 较高 |
| **社区活跃度** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |

### 性能对比

| 框架 | 启动时间 | 响应速度 | 内存占用 | 扩展性 |
|-----|---------|---------|---------|--------|
| LangChain | 快 | 快 | 中 | 高 |
| AutoGen | 中 | 中 | 高 | 高 |
| CrewAI | 快 | 快 | 低 | 中 |
| LangGraph | 中 | 快 | 中 | 很高 |

---

## 🎯 选择指南

### 根据场景选择

#### 快速原型开发
**推荐**: LangChain
- 丰富的示例和文档
- 快速上手
- 社区支持好

#### 多智能体协作
**推荐**: AutoGen
- 专为多智能体设计
- 强大的对话机制
- 代码执行能力

#### 角色扮演场景
**推荐**: CrewAI
- 简洁的 API
- 角色定义清晰
- 任务委派简单

#### 复杂工作流
**推荐**: LangGraph
- 状态图可视化
- 复杂流程控制
- 持久化支持

#### 企业级应用
**推荐**: AutoGen 或 Semantic Kernel
- 企业级支持
- 安全性高
- 可扩展性好

### 根据技术栈选择

#### Python 开发者
- LangChain (首选)
- AutoGen
- CrewAI
- Haystack

#### TypeScript/JavaScript 开发者
- LangChain (JS 版本)
- AgentGPT

#### C# 开发者
- Semantic Kernel

---

## 📚 详细文档

- [LangChain 框架详解](./langchain.md)
- [AutoGen 框架详解](./autogen.md)
- [CrewAI 框架详解](./crewai.md) (待添加)
- [LangGraph 框架详解](./langgraph.md) (待添加)

---

## 🔗 学习资源

### 官方文档
- [LangChain Documentation](https://python.langchain.com/)
- [AutoGen Documentation](https://microsoft.github.io/autogen/)
- [CrewAI Documentation](https://www.crewai.com/)
- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)

### 教程
- [LangChain Academy](https://academy.langchain.com/)
- [AutoGen Tutorials](https://microsoft.github.io/autogen/docs/tutorial)
- [CrewAI Examples](https://www.crewai.com/examples)

---

## 📝 贡献指南

如果您想为框架文档做出贡献：

1. 添加新的框架文档
2. 完善现有文档
3. 添加代码示例
4. 提供使用技巧

---

<div align="center">

[⬆ 返回主页](../README.md)

</div>

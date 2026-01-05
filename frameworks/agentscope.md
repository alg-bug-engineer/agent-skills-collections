# AgentScope 框架

AgentScope 是一个面向开发者的多智能体框架，支持构建代理应用程序，提供统一的接口和可扩展的模块。

## 📖 简介

AgentScope 1.0 是一个以开发者为中心的框架，支持构建基于工具的代理应用，提供灵活高效的代理-环境交互。

## 🏗️ 核心特性

* **统一接口**: 提供一致的 API 接口
* **可扩展模块**: 支持灵活的模块扩展
* **工具集成**: 强大的工具使用能力
* **多智能体协作**: 支持多智能体系统
* **灵活交互**: 灵活的代理-环境交互机制

## 🚀 快速开始

### 安装

```bash
pip install agentscope
```

### 基础示例

```python
from agentscope import Agent, Message

# 创建智能体
agent = Agent(
    name="assistant",
    model="gpt-4",
    system_prompt="You are a helpful assistant"
)

# 发送消息
response = agent(Message(content="Hello, how are you?"))
print(response.content)
```

## 📚 相关资源

* [GitHub 仓库](https://github.com/modelscope-agent/agentscope)
* [论文](https://arxiv.org/abs/2508.16279)
* [文档](https://github.com/modelscope-agent/agentscope)

---

**更新日期**: 2026-01-04
**版本**: v0.1


# AutoGen 框架

AutoGen 是 Microsoft 开发的多智能体对话框架，允许开发者构建具有可定制的、可对话的智能体的 LLM 应用程序。

## 📖 简介

AutoGen（Auto-Generation）是一个开源的 Python 库，专注于构建多智能体系统。它提供了一个灵活的框架，让多个智能体通过对话来协作完成任务。AutoGen 的核心理念是通过智能体之间的对话来解决复杂问题。

## 🏗️ 核心概念

### 1. ConversableAgent（可对话智能体）
AutoGen 中最基本的抽象，支持以下功能：
- 发送和接收消息
- 接收人类输入
- 使用工具（工具调用）
- 执行代码
- 集成 LLM

### 2. AssistantAgent（助手智能体）
- 专门用于编写代码和提供建议
- 默认配置为帮助用户解决问题
- 不需要代码执行

### 3. UserProxyAgent（用户代理智能体）
- 代表人类用户
- 可以执行代码
- 可以请求人类输入
- 可以终止对话

### 4. GroupChat（群聊）
- 多个智能体参与对话
- 指定管理者智能体选择下一个发言者
- 支持循环对话

### 5. Code Execution（代码执行）
- 在沙箱环境中执行代码
- 支持本地和 Docker 环境
- 安全的执行机制

## 🚀 快速开始

### 安装

```bash
pip install pyautogen
```

### 基础示例

```python
from autogen import AssistantAgent, UserProxyAgent

# 配置 LLM
config_list = [
    {
        "model": "gpt-4",
        "api_key": "your-api-key"
    }
]

# 创建助手智能体
assistant = AssistantAgent(
    name="assistant",
    llm_config={
        "config_list": config_list,
        "temperature": 0
    }
)

# 创建用户代理智能体
user_proxy = UserProxyAgent(
    name="user_proxy",
    human_input_mode="TERMINATE",
    max_consecutive_auto_reply=10,
    code_execution_config={"work_dir": "coding"}
)

# 开始对话
user_proxy.initiate_chat(
    assistant,
    message="Write a Python function to calculate Fibonacci numbers"
)
```

## 🛠️ AutoGen 智能体类型

### 1. AssistantAgent
```python
from autogen import AssistantAgent

assistant = AssistantAgent(
    name="assistant",
    system_message="You are a helpful assistant",
    llm_config={"config_list": config_list}
)
```

### 2. UserProxyAgent
```python
from autogen import UserProxyAgent

user_proxy = UserProxyAgent(
    name="user",
    human_input_mode="ALWAYS",  # ALWAYS, NEVER, TERMINATE
    max_consecutive_auto_reply=10,
    code_execution_config={
        "use_docker": False,
        "work_dir": "coding"
    }
)
```

### 3. GroupChat
```python
from autogen import AssistantAgent, UserProxyAgent, GroupChat, GroupChatManager

# 创建多个智能体
assistant1 = AssistantAgent(name="assistant1", llm_config={"config_list": config_list})
assistant2 = AssistantAgent(name="assistant2", llm_config={"config_list": config_list})
user_proxy = UserProxyAgent(name="user", human_input_mode="NEVER")

# 创建群聊
groupchat = GroupChat(
    agents=[user_proxy, assistant1, assistant2],
    messages=[],
    max_round=10
)

manager = GroupChatManager(
    groupchat=groupchat,
    llm_config={"config_list": config_list}
)

# 开始群聊
user_proxy.initiate_chat(
    manager,
    message="Let's solve a complex problem together"
)
```

## 🎯 高级功能

### 1. 工具使用（Tool Use）
```python
from autogen import AssistantAgent, UserProxyAgent
from autogen.coding import DockerCommandLineCodeExecutor

# 定义工具
def get_weather(location: str) -> str:
    """Get weather information for a location"""
    return f"Weather in {location}: Sunny, 25°C"

# 创建使用工具的智能体
assistant = AssistantAgent(
    name="assistant",
    llm_config={
        "config_list": config_list,
        "tools": [get_weather]
    }
)

user_proxy = UserProxyAgent(
    name="user",
    human_input_mode="NEVER"
)

user_proxy.initiate_chat(
    assistant,
    message="What's the weather in Beijing?"
)
```

### 2. 代码执行
```python
from autogen import UserProxyAgent
from autogen.coding import LocalCommandLineCodeExecutor

# 本地代码执行
executor = LocalCommandLineCodeExecutor(work_dir="coding")

user_proxy = UserProxyAgent(
    name="user",
    code_execution_config={"executor": executor}
)

user_proxy.initiate_chat(
    assistant,
    message="Write and execute code to calculate 100!"
)
```

### 3. 自定义对话模式
```python
from autogen import AssistantAgent, UserProxyAgent
from autogen import ChatCompletionClient

# 自定义对话流程
class CustomAgent(AssistantAgent):
    def generate_reply(self, messages, sender, config):
        # 自定义回复生成逻辑
        response = super().generate_reply(messages, sender, config)
        # 添加自定义处理
        return response

custom_agent = CustomAgent(
    name="custom_agent",
    llm_config={"config_list": config_list}
)
```

### 4. 人类交互
```python
# human_input_mode: "ALWAYS", "NEVER", "TERMINATE"
user_proxy = UserProxyAgent(
    name="user",
    human_input_mode="TERMINATE",  # 只在需要时请求输入
    max_consecutive_auto_reply=5
)
```

## 📚 AutoGen 技能

### 多智能体协作
```python
from autogen import AssistantAgent, UserProxyAgent, GroupChat, GroupChatManager

# 定义不同角色的智能体
researcher = AssistantAgent(
    name="researcher",
    system_message="You are a researcher who gathers information",
    llm_config={"config_list": config_list}
)

writer = AssistantAgent(
    name="writer",
    system_message="You are a writer who creates content",
    llm_config={"config_list": config_list}
)

editor = AssistantAgent(
    name="editor",
    system_message="You are an editor who reviews and improves content",
    llm_config={"config_list": config_list}
)

user_proxy = UserProxyAgent(name="user", human_input_mode="NEVER")

# 创建群聊
groupchat = GroupChat(
    agents=[user_proxy, researcher, writer, editor],
    messages=[],
    max_round=15
)

manager = GroupChatManager(
    groupchat=groupchat,
    llm_config={"config_list": config_list}
)

# 执行任务
user_proxy.initiate_chat(
    manager,
    message="Research, write and edit an article about AI Agents"
)
```

### 代码生成和执行
```python
from autogen import AssistantAgent, UserProxyAgent

# 代码生成智能体
coder = AssistantAgent(
    name="coder",
    system_message="You are a Python programmer",
    llm_config={"config_list": config_list}
)

# 代码执行智能体
executor = UserProxyAgent(
    name="executor",
    human_input_mode="NEVER",
    code_execution_config={
        "use_docker": False,
        "work_dir": "coding"
    }
)

executor.initiate_chat(
    coder,
    message="Write a Python script to download data from an API"
)
```

### 工具调用
```python
from autogen import AssistantAgent
import requests

# 定义自定义工具
def fetch_url(url: str) -> str:
    """Fetch content from a URL"""
    response = requests.get(url)
    return response.text[:500]  # 返回前500个字符

# 创建使用工具的智能体
tool_assistant = AssistantAgent(
    name="tool_assistant",
    llm_config={
        "config_list": config_list,
        "functions": [
            {
                "name": "fetch_url",
                "description": "Fetch content from a URL",
                "parameters": {
                    "type": "object",
                    "properties": {
                        "url": {
                            "type": "string",
                            "description": "The URL to fetch"
                        }
                    },
                    "required": ["url"]
                }
            }
        ]
    }
)

user_proxy = UserProxyAgent(name="user", human_input_mode="NEVER")
user_proxy.initiate_chat(tool_assistant, message="Fetch content from https://example.com")
```

## 🔧 配置选项

### LLM 配置
```python
config_list = [
    {
        "model": "gpt-4",
        "api_key": "your-api-key",
        "temperature": 0.7,
        "max_tokens": 1000,
        "timeout": 60
    },
    {
        "model": "gpt-3.5-turbo",
        "api_key": "your-api-key"
    }
]
```

### 代码执行配置
```python
code_execution_config = {
    "work_dir": "coding",           # 工作目录
    "use_docker": False,            # 是否使用 Docker
    "timeout": 60,                  # 超时时间
    "last_n_messages": 3            # 执行最后几条消息中的代码
}
```

## 📊 AutoGen 应用场景

### 1. 代码开发
- 自动生成代码
- 代码审查和优化
- 调试和错误修复
- 测试用例生成

### 2. 数据分析
- 自动数据分析
- 报告生成
- 可视化创建
- 统计分析

### 3. 研究协作
- 文献综述
- 实验设计
- 结果分析
- 论文写作

### 4. 教育和培训
- 编程教学
- 问题解答
- 作业辅导
- 概念解释

## 🎓 学习资源

### 官方文档
- [AutoGen Documentation](https://microsoft.github.io/autogen/)
- [AutoGen GitHub](https://github.com/microsoft/autogen)
- [AutoGen Examples](https://github.com/microsoft/autogen/tree/main/notebook)

### 教程
- [Getting Started with AutoGen](https://microsoft.github.io/autogen/docs/Getting-Started)
- [Multi-Agent Collaboration](https://microsoft.github.io/autogen/docs/tutorial/Multi-Agent-Collaboration)
- [Code Execution](https://microsoft.github.io/autogen/docs/tutorial/Code-Execution)

### 视频
- [AutoGen Overview](https://www.youtube.com/watch?v=vjTgjY0ZwqQ)
- [AutoGen Tutorial Series](https://www.youtube.com/playlist?list=PLqTZaBYZtmIou3y3JfY4W5oZmXnHh6k0y)

## 💡 最佳实践

1. **明确角色分工**: 为每个智能体定义清晰的角色和职责
2. **合理配置 LLM**: 根据任务复杂度选择合适的模型
3. **使用代码执行**: 充分利用代码执行能力进行验证
4. **控制对话轮次**: 避免无限循环，设置合理的 max_round
5. **工具使用**: 合理使用工具扩展智能体能力
6. **错误处理**: 实现健壮的错误处理机制
7. **性能优化**: 使用缓存和批处理提高效率

## 🔗 相关框架

- [LangChain](./langchain.md) - 另一个流行的 Agent 框架
- [CrewAI](./crewai.md) - 专注于角色扮演的多智能体框架
- [LangGraph](https://langchain-ai.github.io/langgraph/) - 状态图框架

---

**更新日期**: 2026-01-04
**版本**: v0.1

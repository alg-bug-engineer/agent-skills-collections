# Agent Skills 初学者指南

本指南旨在帮助初学者快速入门 Agent Skills 和 AI Agent 开发。

## 🎯 学习目标

完成本指南后，您将能够：
- 理解 Agent Skills 的基本概念
- 掌握常用 Agent 框架的基础使用
- 创建第一个简单的 Agent
- 了解 Agent 的核心组件和工作原理

## 📚 基础概念

### 什么是 Agent Skills？

Agent Skills 是 AI 智能体能够执行的具体能力和技能，例如：
- Web 浏览和搜索
- 代码执行
- 文件操作
- 数据库查询
- 工具调用

### 什么是 AI Agent？

AI Agent 是一个能够：
1. **感知环境**：接收输入和信息
2. **推理决策**：基于 LLM 进行思考和规划
3. **执行行动**：使用工具完成具体任务
4. **学习改进**：从反馈中学习和优化

## 🚀 快速开始

### 环境准备

#### 1. Python 环境
```bash
# 创建虚拟环境
python -m venv agent-env
source agent-env/bin/activate  # Linux/Mac
# agent-env\Scripts\activate  # Windows

# 安装基础依赖
pip install openai langchain langchain-openai pyautogen
```

#### 2. API 密钥配置
```bash
# 设置 OpenAI API Key
export OPENAI_API_KEY="your-api-key-here"

# 或者使用 .env 文件
echo "OPENAI_API_KEY=your-api-key-here" > .env
```

### 第一个 Agent：使用 LangChain

```python
from langchain.agents import AgentType, initialize_agent, load_tools
from langchain_openai import ChatOpenAI

# 1. 初始化 LLM
llm = ChatOpenAI(temperature=0, model="gpt-4")

# 2. 加载工具
tools = load_tools(["llm-math"], llm=llm)

# 3. 创建 Agent
agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)

# 4. 运行 Agent
result = agent.run("What is 15% of 200?")
print(result)
```

### 第二个 Agent：使用 AutoGen

```python
from autogen import AssistantAgent, UserProxyAgent

# 1. 配置 LLM
config_list = [
    {
        "model": "gpt-4",
        "api_key": "your-api-key"
    }
]

# 2. 创建助手智能体
assistant = AssistantAgent(
    name="assistant",
    llm_config={
        "config_list": config_list,
        "temperature": 0
    }
)

# 3. 创建用户代理
user_proxy = UserProxyAgent(
    name="user_proxy",
    human_input_mode="NEVER",
    max_consecutive_auto_reply=5
)

# 4. 开始对话
user_proxy.initiate_chat(
    assistant,
    message="Explain what is an AI Agent in simple terms"
)
```

## 📖 核心概念详解

### 1. Agent 的组成

```python
from langchain.agents import AgentExecutor, ZeroShotAgent
from langchain.prompts import PromptTemplate

# 定义提示词模板
prompt = PromptTemplate.from_template(
    """You are a helpful assistant. 
    Use the following tools to answer the user's question:
    {tools}
    
    Question: {input}
    {agent_scratchpad}"""
)

# 创建 Agent
agent = ZeroShotAgent(
    llm=llm,
    tools=tools,
    prompt=prompt
)

# 创建执行器
agent_executor = AgentExecutor.from_agent_and_tools(
    agent=agent,
    tools=tools,
    verbose=True
)
```

### 2. 工具（Tools）

```python
from langchain.tools import Tool

# 定义自定义工具
def calculator(expression: str) -> str:
    """Evaluate a mathematical expression"""
    try:
        result = eval(expression)
        return str(result)
    except Exception as e:
        return f"Error: {str(e)}"

# 创建工具对象
calculator_tool = Tool(
    name="Calculator",
    func=calculator,
    description="Use this tool for mathematical calculations"
)

# 使用工具
tools = [calculator_tool]
```

### 3. 记忆（Memory）

```python
from langchain.memory import ConversationBufferMemory
from langchain.chains import ConversationChain

# 创建记忆
memory = ConversationBufferMemory()

# 创建对话链
conversation = ConversationChain(
    llm=llm,
    memory=memory,
    verbose=True
)

# 多轮对话
response1 = conversation.predict(input="My name is Alice")
response2 = conversation.predict(input="What is my name?")
print(response2)  # Agent 会记住之前的对话
```

## 🛠️ 实践项目

### 项目 1：智能问答助手

```python
from langchain.agents import initialize_agent, AgentType, load_tools
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(temperature=0)

# 加载搜索和计算工具
tools = load_tools(["serpapi", "llm-math"], llm=llm)

# 创建 Agent
agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)

# 使用 Agent
query = "What is the population of Tokyo and how many times larger is it than Paris?"
result = agent.run(query)
print(result)
```

### 项目 2：代码助手

```python
from langchain.agents import initialize_agent, AgentType, Tool
from langchain_openai import ChatOpenAI
import subprocess

def execute_python(code: str) -> str:
    """Execute Python code"""
    try:
        result = subprocess.run(
            ["python3", "-c", code],
            capture_output=True,
            text=True,
            timeout=10
        )
        return result.stdout or result.stderr
    except Exception as e:
        return f"Error: {str(e)}"

code_tool = Tool(
    name="PythonExecutor",
    func=execute_python,
    description="Execute Python code and return the output"
)

llm = ChatOpenAI(temperature=0)
agent = initialize_agent(
    [code_tool],
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)

result = agent.run("Write and execute code to calculate the first 10 Fibonacci numbers")
print(result)
```

### 项目 3：网页内容分析器

```python
from langchain.agents import initialize_agent, AgentType, Tool
from langchain_openai import ChatOpenAI
import requests
from bs4 import BeautifulSoup

def fetch_webpage(url: str) -> str:
    """Fetch and extract text from a webpage"""
    try:
        response = requests.get(url, timeout=10)
        soup = BeautifulSoup(response.content, 'html.parser')
        
        # 移除脚本和样式
        for script in soup(["script", "style"]):
            script.decompose()
        
        text = soup.get_text(separator=' ', strip=True)
        return text[:1000]  # 返回前1000个字符
    except Exception as e:
        return f"Error: {str(e)}"

web_tool = Tool(
    name="WebFetcher",
    func=fetch_webpage,
    description="Fetch and extract text content from a webpage"
)

llm = ChatOpenAI(temperature=0)
agent = initialize_agent(
    [web_tool],
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)

result = agent.run("Analyze the main content of https://example.com")
print(result)
```

## 🎓 学习路径

### 第一阶段：基础（1-2周）
1. 理解 Agent 基本概念
2. 学习 LangChain 基础 API
3. 创建简单的 Agent
4. 掌握工具使用

### 第二阶段：进阶（2-4周）
1. 学习 AutoGen 框架
2. 实现多智能体系统
3. 掌握记忆管理
4. 学习链式调用

### 第三阶段：高级（4-8周）
1. 研究高级 Agent 架构
2. 实现自定义工具
3. 优化 Agent 性能
4. 部署 Agent 应用

## 💡 最佳实践

### 1. 提示词工程
```python
# 好的提示词模板
good_prompt = """
You are an expert Python programmer.
Write clean, efficient, and well-documented code.
Use the following guidelines:
- Include docstrings
- Handle errors appropriately
- Add comments for complex logic
"""

# 不好的提示词模板
bad_prompt = """
Write Python code.
"""
```

### 2. 错误处理
```python
def robust_tool(input_data: str) -> str:
    """Robust tool with error handling"""
    try:
        # 执行主要逻辑
        result = process_input(input_data)
        return result
    except ValueError as e:
        return f"Invalid input: {str(e)}"
    except Exception as e:
        return f"An error occurred: {str(e)}"
    finally:
        # 清理资源
        cleanup()
```

### 3. 工具描述
```python
# 清晰的工具描述
good_tool = Tool(
    name="Calculator",
    func=calculate,
    description="""
    Use this tool for mathematical calculations.
    Input should be a mathematical expression like "2 + 2" or "sqrt(16)".
    Supports basic operations: +, -, *, /, sqrt, pow
    """
)

# 模糊的工具描述
bad_tool = Tool(
    name="Math",
    func=calculate,
    description="Calculate math"
)
```

## 🔧 常见问题

### Q1: Agent 如何选择工具？
A: Agent 根据工具的描述和当前任务的匹配度来选择工具。清晰、详细的工具描述很重要。

### Q2: 如何处理 Agent 的无限循环？
A: 设置 `max_iterations` 参数，使用记忆系统，或设计明确的终止条件。

### Q3: Agent 的响应速度太慢怎么办？
A: 1. 使用更快的模型（如 GPT-3.5）
   2. 减少工具调用次数
   3. 实现缓存机制
   4. 优化提示词长度

### Q4: 如何调试 Agent？
A: 1. 启用 verbose 模式查看详细日志
   2. 使用 LangSmith 进行追踪
   3. 单独测试每个工具
   4. 检查提示词和工具描述

## 📚 推荐资源

### 在线教程
- [LangChain Academy](https://academy.langchain.com/)
- [OpenAI Documentation](https://platform.openai.com/docs)
- [AutoGen Tutorials](https://microsoft.github.io/autogen/docs/tutorial)

### 书籍
- "LangChain in Action" (即将出版)
- "Building AI Agents with LangChain"

### 社区
- [LangChain Discord](https://discord.gg/langchain)
- [AutoGen GitHub Discussions](https://github.com/microsoft/autogen/discussions)
- [Stack Overflow - langchain](https://stackoverflow.com/questions/tagged/langchain)

## 🎯 下一步

完成初学者指南后，您可以：
1. 阅读 [进阶教程](./advanced-tutorials.md)
2. 探索 [框架文档](../frameworks/)
3. 查看 [技能分类](../skills/)
4. 研究 [学术论文](../papers/)

---

**更新日期**: 2026-01-04
**版本**: v0.1

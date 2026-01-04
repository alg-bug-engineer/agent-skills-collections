# LangChain 框架

LangChain 是一个用于构建基于 LLM 应用程序的开发框架，提供了强大的 Agent 能力和工具集成功能。

## 📖 简介

LangChain 是当前最流行的 AI Agent 开发框架之一，提供了完整的工具链来构建、部署和管理 LLM 应用程序。它支持 Python 和 TypeScript 两种语言，拥有庞大的社区生态系统。

## 🏗️ 核心组件

### 1. Models（模型）
- **LLMs**: 大语言模型接口
- **Chat Models**: 聊天模型接口
- **Embeddings**: 文本嵌入模型
- **支持**: OpenAI, Anthropic, Hugging Face, Cohere 等

### 2. Prompts（提示词）
- **Prompt Templates**: 提示词模板
- **Few-shot Examples**: 少样本示例
- **Prompt Selectors**: 提示词选择器
- **Output Parsers**: 输出解析器

### 3. Agents（智能体）
- **Agent Types**: 
  - ReAct Agent
  - Conversational Agent
  - Structured Chat Agent
  - Self Ask with Search
  - Plan-and-Solve Agent
- **Tools**: 工具集成（搜索、计算器、文件操作等）
- **Toolkits**: 工具包集合

### 4. Memory（记忆）
- **Conversation Buffer Memory**: 对话缓冲记忆
- **Conversation Buffer Window Memory**: 对话窗口记忆
- **Conversation Summary Memory**: 对话摘要记忆
- **Vector Store Memory**: 向量存储记忆
- **Entity Memory**: 实体记忆

### 5. Chains（链）
- **LLM Chain**: 基础 LLM 链
- **Sequential Chain**: 顺序链
- **Router Chain**: 路由链
- **Map-Reduce Chain**: 映射归约链
- **Refine Chain**: 优化链

### 6. Retrieval（检索）
- **Document Loaders**: 文档加载器
- **Text Splitters**: 文本分割器
- **Vector Stores**: 向量数据库
- **Retrievers**: 检索器
- **Indexing**: 索引

## 🚀 快速开始

### 安装

```bash
# Python
pip install langchain langchain-openai langchain-community

# JavaScript/TypeScript
npm install langchain @langchain/openai @langchain/community
```

### 基础 Agent 示例

```python
from langchain.agents import AgentType, initialize_agent, load_tools
from langchain_openai import ChatOpenAI

# 初始化 LLM
llm = ChatOpenAI(temperature=0)

# 加载工具
tools = load_tools(["serpapi", "llm-math"], llm=llm)

# 创建 Agent
agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)

# 运行 Agent
result = agent.run("What is the current weather in Beijing?")
print(result)
```

## 🛠️ LangChain Agents

### 1. Zero-Shot ReAct Agent
```python
from langchain.agents import AgentType, initialize_agent, load_tools
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(temperature=0)
tools = load_tools(["serpapi", "llm-math"], llm=llm)

agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)
```

### 2. Conversational Agent
```python
from langchain.agents import AgentType, initialize_agent, create_react_agent
from langchain.memory import ConversationBufferMemory
from langchain_openai import ChatOpenAI
from langchain.tools import Tool

llm = ChatOpenAI(temperature=0)

memory = ConversationBufferMemory(
    memory_key="chat_history",
    return_messages=True
)

tools = [
    Tool(name="Calculator", func=lambda x: eval(x), description="Use for math calculations")
]

agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.CONVERSATIONAL_REACT_DESCRIPTION,
    memory=memory,
    verbose=True
)
```

### 3. Custom Tools
```python
from langchain.tools import BaseTool
from typing import Type

class CustomTool(BaseTool):
    name = "custom_tool"
    description = "This is a custom tool"
    
    def _run(self, query: str) -> str:
        return f"Custom tool executed with query: {query}"
    
    async def _arun(self, query: str) -> str:
        return f"Async custom tool executed with query: {query}"

# 使用自定义工具
tools = [CustomTool()]
agent = initialize_agent(tools, llm, agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION)
```

## 📚 LangChain Agents 技能

### Web Browsing（Web 浏览）
```python
from langchain_community.tools import DuckDuckGoSearchRun

search = DuckDuckGoSearchRun()
tools = [Tool(
    name="Search",
    func=search.run,
    description="Search the web for information"
)]
```

### Code Execution（代码执行）
```python
from langchain_experimental.utilities import PythonREPL

python_repl = PythonREPL()
tools = [Tool(
    name="Python REPL",
    func=python_repl.run,
    description="Run Python code"
)]
```

### File Operations（文件操作）
```python
from langchain_community.tools import ReadFileTool, WriteFileTool

tools = [
    ReadFileTool(),
    WriteFileTool()
]
```

### Database Query（数据库查询）
```python
from langchain_community.utilities import SQLDatabase
from langchain_community.tools import SQLDatabaseToolkit

db = SQLDatabase.from_uri("sqlite:///example.db")
toolkit = SQLDatabaseToolkit(db=db, llm=llm)
tools = toolkit.get_tools()
```

## 🎯 LangGraph（新一代 Agent 框架）

LangGraph 是 LangChain 推出的新一代 Agent 框架，提供了更强大的状态管理和工作流控制。

### 基础概念
- **Nodes（节点）**: 执行具体任务的单元
- **Edges（边）**: 连接节点的路径
- **State（状态）**: 在节点间传递的数据
- **Graph（图）**: 整个工作流结构

### 示例代码
```python
from langgraph.graph import StateGraph, END
from typing import TypedDict

class AgentState(TypedDict):
    messages: list

def research_node(state: AgentState):
    # 研究逻辑
    pass

def write_node(state: AgentState):
    # 写作逻辑
    pass

# 构建图
workflow = StateGraph(AgentState)
workflow.add_node("researcher", research_node)
workflow.add_node("writer", write_node)
workflow.add_edge("researcher", "writer")
workflow.set_entry_point("researcher")
workflow.set_finish_point("writer")

app = workflow.compile()

# 运行
result = app.invoke({"messages": ["Write a blog post about AI"]})
```

## 📊 生态系统

### LangChain Hub
- 提示词模板和链的共享平台
- 地址: https://smith.langchain.com/

### LangSmith
- 开发、测试和监控平台
- 调试和追踪 Agent 行为
- 评估和优化性能

### LangServe
- 将 Chain 和 Agent 部署为 API
- RESTful 接口
- FastAPI 集成

## 🔗 相关资源

### 官方文档
- [LangChain Documentation](https://python.langchain.com/)
- [LangChain JS Documentation](https://js.langchain.com/)
- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)

### 教程
- [LangChain Academy](https://academy.langchain.com/)
- [LangChain Cookbook](https://github.com/langchain-ai/langchain-cookbook)
- [LangChain Tutorials](https://www.youtube.com/playlist?list=PLqTZaBYZtmIou3y3JfY4W5oZmXnHh6k0y)

### 社区
- [LangChain Discord](https://discord.gg/langchain)
- [LangChain GitHub](https://github.com/langchain-ai/langchain)
- [LangChain Twitter](https://twitter.com/langchainai)

## 💡 最佳实践

1. **使用模板化提示词**: 利用 Prompt Templates 提高可维护性
2. **合理选择 Agent 类型**: 根据任务复杂度选择合适的 Agent
3. **工具集成**: 充分利用现有工具，避免重复开发
4. **记忆管理**: 根据对话场景选择合适的记忆类型
5. **性能优化**: 使用缓存、批处理等技术优化性能
6. **错误处理**: 实现 robust 的错误处理和重试机制
7. **监控和调试**: 使用 LangSmith 进行监控和调试

## 🎓 学习路径

1. **基础**: 学习 LangChain 基本概念和 API
2. **Chains**: 掌握各种 Chain 的使用
3. **Agents**: 深入理解 Agent 的工作原理
4. **Tools**: 学习创建和使用自定义工具
5. **Memory**: 掌握不同类型的记忆系统
6. **LangGraph**: 学习构建复杂工作流
7. **部署**: 学习使用 LangServe 部署应用

---

**更新日期**: 2026-01-04
**版本**: v0.1

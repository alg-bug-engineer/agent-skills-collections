# 代码执行技能

代码执行技能允许 Agent 在安全的环境中执行代码，验证结果，并进行计算。

## 📖 概述

代码执行技能使 AI Agent 能够：
- 在沙箱环境中执行代码
- 验证计算结果
- 运行数据分析脚本
- 测试算法实现
- 生成和运行代码

## 🛠️ 主要工具和库

### 1. LangChain Python REPL

```python
from langchain_experimental.utilities import PythonREPL
from langchain.tools import Tool

# 创建 Python REPL
python_repl = PythonREPL()

# 创建工具
code_tool = Tool(
    name="Python REPL",
    func=python_repl.run,
    description="Execute Python code and return the output"
)

# 使用
result = code_tool.run("print('Hello, World!')")
```

### 2. E2B 沙箱环境

```python
from e2b import Sandbox

# 创建沙箱
sandbox = Sandbox()

# 执行代码
result = sandbox.run_code("print('Hello from E2B!')")
print(result)
```

### 3. AutoGen 代码执行

```python
from autogen import UserProxyAgent
from autogen.coding import LocalCommandLineCodeExecutor

# 创建代码执行器
executor = LocalCommandLineCodeExecutor(work_dir="coding")

# 创建用户代理
user_proxy = UserProxyAgent(
    name="user",
    code_execution_config={"executor": executor}
)
```

## 🔒 安全考虑

### 1. 沙箱隔离

```python
import docker

def create_sandbox():
    """创建 Docker 沙箱环境"""
    client = docker.from_env()
    container = client.containers.run(
        "python:3.9",
        detach=True,
        remove=True,
        mem_limit="512m",
        cpu_period=100000,
        cpu_quota=50000
    )
    return container
```

### 2. 资源限制

```python
import resource

def set_limits():
    """设置资源限制"""
    # 限制内存使用
    resource.setrlimit(
        resource.RLIMIT_AS,
        (100 * 1024 * 1024, 100 * 1024 * 1024)  # 100MB
    )
    
    # 限制 CPU 时间
    resource.setrlimit(
        resource.RLIMIT_CPU,
        (10, 10)  # 10 秒
    )
```

### 3. 代码验证

```python
import ast

def validate_code(code: str) -> bool:
    """验证代码是否安全"""
    try:
        tree = ast.parse(code)
        
        # 检查危险操作
        dangerous_nodes = [
            ast.Import,
            ast.ImportFrom,
            ast.Call
        ]
        
        for node in ast.walk(tree):
            if isinstance(node, tuple(dangerous_nodes)):
                # 检查是否调用危险函数
                if isinstance(node, ast.Call):
                    if isinstance(node.func, ast.Name):
                        if node.func.id in ['eval', 'exec', '__import__']:
                            return False
        
        return True
    except SyntaxError:
        return False
```

## 📊 应用示例

### 1. 数学计算

```python
from langchain.agents import initialize_agent, AgentType
from langchain_experimental.utilities import PythonREPL

python_repl = PythonREPL()
tools = [Tool(
    name="Python REPL",
    func=python_repl.run,
    description="Execute Python code for calculations"
)]

agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION
)

result = agent.run("Calculate the factorial of 10")
```

### 2. 数据分析

```python
code = """
import pandas as pd
import numpy as np

# 创建示例数据
data = pd.DataFrame({
    'x': np.random.randn(100),
    'y': np.random.randn(100)
})

# 计算统计信息
stats = data.describe()
print(stats)
"""

result = python_repl.run(code)
```

### 3. 算法实现

```python
code = """
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

# 计算前 10 个斐波那契数
for i in range(10):
    print(f"F({i}) = {fibonacci(i)}")
"""

result = python_repl.run(code)
```

## 🎯 最佳实践

1. **使用沙箱环境**: 始终在隔离的环境中执行代码
2. **设置资源限制**: 限制内存和 CPU 使用
3. **验证代码**: 检查代码是否包含危险操作
4. **超时控制**: 设置执行超时时间
5. **错误处理**: 妥善处理执行错误
6. **结果验证**: 验证执行结果的合理性

## 🔗 相关资源

- [E2B 文档](https://www.e2b.dev/docs)
- [LangChain Python REPL](https://python.langchain.com/docs/integrations/toolkits/python)
- [Docker 文档](https://docs.docker.com/)

---

**更新日期**: 2026-01-04
**版本**: v0.1


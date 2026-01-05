# CrewAI 框架

CrewAI 是一个用于协调角色扮演、自主智能体的框架。

## 📖 简介

CrewAI 专注于角色扮演和任务委派，提供了简洁的 API 和快速上手的体验。

## 🏗️ 核心特性

* **角色扮演智能体**: 支持定义不同角色的智能体
* **任务委派机制**: 自动任务分配和协调
* **简洁的 API**: 易于使用的接口
* **快速上手**: 简单的配置和部署

## 🚀 快速开始

### 安装

```bash
pip install crewai
```

### 基础示例

```python
from crewai import Agent, Task, Crew

# 创建智能体
researcher = Agent(
    role="Researcher",
    goal="Research information",
    backstory="You are a researcher"
)

# 创建任务
task = Task(
    description="Research AI agents",
    agent=researcher
)

# 创建团队
crew = Crew(agents=[researcher], tasks=[task])

# 执行任务
result = crew.kickoff()
print(result)
```

## 📚 相关资源

* [GitHub 仓库](https://github.com/joaomdmoura/crewAI)
* [官方网站](https://www.crewai.com/)
* [文档](https://docs.crewai.org.cn/)

---

**更新日期**: 2026-01-04
**版本**: v0.1


# Awesome Agent Skills

一个精心整理的 AI Agent 技能资源集合。

所有资源都是免费提供的，除非标记了 💲 图标。

## 目录

* [目录](#目录)
* [通用资源](#通用资源)
  * [学习平台](#学习平台)
  * [官方文档](#官方文档)
  * [工具和库](#工具和库)
  * [问答社区](#问答社区)
  * [博客和文章](#博客和文章)
  * [会议和活动](#会议和活动)
  * [其他资源](#其他资源)
* [Agent 框架](#agent-框架)
  * [主流框架](#主流框架)
  * [专用框架](#专用框架)
  * [多智能体框架](#多智能体框架)
  * [状态图框架](#状态图框架)
* [Agent 技能](#agent-技能)
  * [Web 浏览](#web-浏览)
  * [代码执行](#代码执行)
  * [文件操作](#文件操作)
  * [数据库操作](#数据库操作)
  * [记忆管理](#记忆管理)
  * [工具使用](#工具使用)
  * [搜索能力](#搜索能力)
  * [API 集成](#api-集成)
* [开源项目](#开源项目)
  * [框架项目](#框架项目)
  * [应用项目](#应用项目)
  * [工具项目](#工具项目)
  * [评估基准](#评估基准)
* [学术论文](#学术论文)
  * [经典论文](#经典论文)
  * [Agent 架构](#agent-架构)
  * [工具使用](#工具使用-1)
  * [推理和规划](#推理和规划)
  * [多智能体系统](#多智能体系统)
  * [评估和基准](#评估和基准)
  * [应用领域](#应用领域)
  * [综述和教程](#综述和教程)
* [教程和指南](#教程和指南)
  * [初学者指南](#初学者指南)
  * [进阶教程](#进阶教程)
  * [实战项目](#实战项目)
  * [最佳实践](#最佳实践)
* [视频资源](#视频资源)
  * [会议演讲](#会议演讲)
  * [教程视频](#教程视频)
  * [技术分享](#技术分享)
* [新闻和动态](#新闻和动态)
* [相关 Awesome 列表](#相关-awesome-列表)
* [许可证](#许可证)

## 通用资源

### 学习平台

* [LangChain Academy](https://academy.langchain.com/) - LangChain 官方学习平台
* [Coursera - AI Agent 课程](https://www.coursera.org/courses?query=ai%20agent) - 在线 AI Agent 相关课程
* [edX - AI 课程](https://www.edx.org/learn/artificial-intelligence) - 来自顶尖大学的 AI 课程
* [Udemy - LangChain 课程](https://www.udemy.com/topic/langchain/) - LangChain 和 Agent 开发课程
* [Pluralsight](https://www.pluralsight.com/) - 技术学习平台，包含 AI Agent 内容
* [Fast.ai](https://www.fast.ai/) - 实用的深度学习课程

### 官方文档

* [LangChain 文档](https://python.langchain.com/) - LangChain 官方文档
* [AutoGen 文档](https://microsoft.github.io/autogen/) - Microsoft AutoGen 官方文档
* [CrewAI 文档](https://www.crewai.com/) - CrewAI 官方文档
* [LangGraph 文档](https://langchain-ai.github.io/langgraph/) - LangGraph 官方文档
* [OpenAI API 文档](https://platform.openai.com/docs) - OpenAI API 官方文档
* [Anthropic Claude API 文档](https://docs.anthropic.com/) - Anthropic Claude API 文档
* [GitHub Copilot Agent Skills](https://docs.github.com/zh/copilot/concepts/agents/about-agent-skills) - GitHub Copilot Agent Skills 文档
* [Claude SDK Skills](https://docs.claude.com/zh-CN/api/agent-sdk/skills) - Claude SDK 中的代理技能文档
* [Anthropic Skills](https://github.com/anthropics/skills) - Anthropic 官方技能仓库

### 工具和库

* [LangChain](https://github.com/langchain-ai/langchain) - 构建 LLM 应用的框架
* [LangSmith](https://smith.langchain.com/) - LangChain 的调试和监控平台
* [LangServe](https://github.com/langchain-ai/langserve) - 将 LangChain 应用部署为 API
* [LangChain Hub](https://smith.langchain.com/hub) - 提示词和链的共享平台
* [Skill Seeker](https://jimmysong.io/zh/ai/skill-seeker/) - 将文档转换为 Claude 技能包的工具
* [E2B](https://www.e2b.dev/) - 代码执行沙箱环境
* [Docker](https://www.docker.com/) - 容器化工具，用于代码执行隔离
* [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) - HTML/XML 解析库
* [Trafilatura](https://github.com/adbar/trafilatura) - 网页内容提取工具
* [Scrapy](https://scrapy.org/) - Python 网页爬虫框架
* [Requests](https://requests.readthedocs.io/) - HTTP 库
* [Playwright](https://playwright.dev/) - 浏览器自动化工具
* [Selenium](https://www.selenium.dev/) - 浏览器自动化框架

### 问答社区

* [LangChain Discord](https://discord.gg/langchain) - LangChain 官方 Discord 社区
* [AutoGen GitHub Discussions](https://github.com/microsoft/autogen/discussions) - AutoGen GitHub 讨论区
* [Stack Overflow - langchain](https://stackoverflow.com/questions/tagged/langchain) - Stack Overflow LangChain 标签
* [Stack Overflow - autogen](https://stackoverflow.com/questions/tagged/autogen) - Stack Overflow AutoGen 标签
* [Reddit - r/LangChain](https://www.reddit.com/r/LangChain/) - Reddit LangChain 社区
* [Reddit - r/MachineLearning](https://www.reddit.com/r/MachineLearning/) - Reddit 机器学习社区
* [Hugging Face Forums](https://discuss.huggingface.co/) - Hugging Face 社区论坛
* [GitHub Discussions](https://github.com/alg-bug-engineer/agent-skills-collections/discussions) - 本仓库讨论区

### 博客和文章

* [LangChain Blog](https://blog.langchain.dev/) - LangChain 官方博客
* [OpenAI Blog](https://openai.com/blog/) - OpenAI 官方博客
* [Anthropic Blog](https://www.anthropic.com/news) - Anthropic 官方博客
* [Towards Data Science - Agent](https://towardsdatascience.com/tagged/ai-agent) - Medium 上的 Agent 文章
* [AI Research](https://www.53ai.com/) - AI 研究和资讯网站
* [机器之心](https://www.jiqizhixin.com/) - AI 科技媒体
* [AI 科技大本营](https://www.csdn.net/) - CSDN AI 专栏

### 会议和活动

* [NeurIPS](https://neurips.cc/) - 神经信息处理系统会议
* [ICLR](https://iclr.cc/) - 国际学习表征会议
* [ICML](https://icml.cc/) - 国际机器学习会议
* [AAAI](https://www.aaai.org/) - 美国人工智能协会年会
* [ACL](https://www.aclweb.org/) - 计算语言学协会年会
* [LangChain Conference](https://www.langchain.com/conference) - LangChain 年度会议

### 其他资源

* [Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents) - 精选 AI Agent 资源列表
* [Agent Benchmarks](https://github.com/THUDM/AgentBench) - Agent 基准测试
* [OpenAI Evals](https://github.com/openai/evals) - OpenAI 评估框架
* [Papers with Code - Agents](https://paperswithcode.com/area/nlp/agent) - Agent 相关论文和代码

## Agent 框架

### 主流框架

* [LangChain](https://github.com/langchain-ai/langchain) - 最流行的 LLM 应用开发框架
  * 📖 [详细文档](./frameworks/langchain.md)
  * 🌟 Stars: 90k+
  * 语言: Python/TypeScript
  * 特点: 链式调用、丰富的 Agent 类型、强大的工具集成

* [AutoGen](https://github.com/microsoft/autogen) - Microsoft 多智能体对话框架
  * 📖 [详细文档](./frameworks/autogen.md)
  * 🌟 Stars: 30k+
  * 语言: Python
  * 特点: 多智能体协作、代码执行、人类参与

* [CrewAI](https://github.com/joaomdmoura/crewAI) - 角色扮演多智能体框架
  * 🌟 Stars: 10k+
  * 语言: Python
  * 特点: 角色扮演、任务委派、简洁 API

* [LangGraph](https://github.com/langchain-ai/langgraph) - 状态图框架
  * 🌟 Stars: 5k+
  * 语言: Python/TypeScript
  * 特点: 状态图、循环控制、持久化

### 专用框架

* [AgentGPT](https://github.com/reworkd/AgentGPT) - 浏览器中部署 AI 智能体
  * 🌟 Stars: 30k+
  * 语言: TypeScript/Python

* [BabyAGI](https://github.com/yoheinakajima/babyagi) - 任务管理自动化
  * 🌟 Stars: 15k+
  * 语言: Python

* [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) - 自主 GPT-4 应用
  * 🌟 Stars: 160k+
  * 语言: Python

* [Camel](https://github.com/camel-ai/camel) - 通信智能体框架
  * 🌟 Stars: 10k+
  * 语言: Python

* [Semantic Kernel](https://github.com/microsoft/semantic-kernel) - Microsoft LLM 集成 SDK
  * 🌟 Stars: 18k+
  * 语言: C#/Python/Java

* [Haystack](https://github.com/deepset-ai/haystack) - 问答系统框架
  * 🌟 Stars: 15k+
  * 语言: Python

### 多智能体框架

* [MetaGPT](https://github.com/geekan/MetaGPT) - SOP 编码的多智能体框架
  * 🌟 Stars: 40k+
  * 语言: Python

* [ChatDev](https://github.com/OpenBMB/ChatDev) - 多智能体软件开发框架
  * 🌟 Stars: 25k+
  * 语言: Python

* [AgentScope](https://github.com/modelscope-agent/agentscope) - 面向开发者的多智能体框架
  * 🌟 Stars: 2k+
  * 语言: Python
  * 📝 [论文](https://arxiv.org/abs/2508.16279)

* [TaskWeaver](https://github.com/microsoft/TaskWeaver) - 代码优先的 Agent 框架
  * 🌟 Stars: 3k+
  * 语言: Python
  * 📝 [论文](https://arxiv.org/abs/2311.17541)

* [AutoAgents](https://github.com/autoagents/autoagents) - 自动生成代理的框架
  * 📝 [论文](https://arxiv.org/abs/2309.17288)

* [OpenAgents](https://github.com/xlang-ai/OpenAgents) - 开放平台构建语言代理
  * 📝 [论文](https://arxiv.org/abs/2310.10634)

* [AgentStore](https://github.com/agent-store/agentstore) - 动态集成异构代理的平台
  * 📝 [论文](https://arxiv.org/abs/2410.18603)

### 状态图框架

* [LangGraph](https://github.com/langchain-ai/langgraph) - LangChain 的状态图框架
* [StateGraph](https://langchain-ai.github.io/langgraph/) - 状态图构建工具

## Agent 技能

### Web 浏览

* 📝 [Web 浏览技能详解](./skills/web-browsing.md)
* [DuckDuckGo Search](https://github.com/langchain-ai/langchain/tree/master/libs/langchain/langchain/tools) - 无 API Key 的搜索工具
* [Google Search API](https://developers.google.com/custom-search) - Google 搜索 API
* [Bing Search API](https://www.microsoft.com/en-us/bing/apis/bing-web-search-api) - Bing 搜索 API
* [Serper API](https://serper.dev/) - 搜索 API 服务
* [Tavily Search](https://tavily.com/) - AI 搜索 API
* [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) - HTML 解析库
* [Trafilatura](https://github.com/adbar/trafilatura) - 网页内容提取
* [Readability](https://github.com/mozilla/readability) - 网页可读性提取
* [Playwright](https://playwright.dev/) - 浏览器自动化
* [Selenium](https://www.selenium.dev/) - Web 驱动工具

### 代码执行

* [E2B](https://www.e2b.dev/) - 安全的代码执行沙箱
* [Python REPL](https://github.com/langchain-ai/langchain/tree/master/libs/langchain/langchain/experimental) - Python 代码执行工具
* [Docker](https://www.docker.com/) - 容器化执行环境
* [CodeT5](https://github.com/salesforce/CodeT5) - 代码生成模型
* [Codex](https://openai.com/blog/openai-codex) - OpenAI 代码生成模型

### 文件操作

* [LangChain File Tools](https://python.langchain.com/docs/integrations/tools/file_system) - LangChain 文件操作工具
* [PyPDF2](https://github.com/py-pdf/PyPDF2) - PDF 处理库
* [python-docx](https://github.com/python-openxml/python-docx) - Word 文档处理
* [openpyxl](https://openpyxl.readthedocs.io/) - Excel 文件处理
* [Pillow](https://pillow.readthedocs.io/) - 图像处理库

### 数据库操作

* [LangChain SQL](https://python.langchain.com/docs/integrations/toolkits/sql_database) - SQL 数据库工具包
* [SQLAlchemy](https://www.sqlalchemy.org/) - Python SQL 工具包
* [MongoDB](https://www.mongodb.com/) - NoSQL 数据库
* [Redis](https://redis.io/) - 内存数据库
* [PostgreSQL](https://www.postgresql.org/) - 关系型数据库
* [Chroma](https://www.trychroma.com/) - 向量数据库
* [Pinecone](https://www.pinecone.io/) - 向量数据库服务
* [Weaviate](https://weaviate.io/) - 向量数据库

### 记忆管理

* [LangChain Memory](https://python.langchain.com/docs/modules/memory/) - LangChain 记忆系统
* [Conversation Buffer Memory](https://python.langchain.com/docs/modules/memory/types/buffer) - 对话缓冲记忆
* [Conversation Summary Memory](https://python.langchain.com/docs/modules/memory/types/summary) - 对话摘要记忆
* [Vector Store Memory](https://python.langchain.com/docs/modules/memory/types/vector_store_retriever_memory) - 向量存储记忆
* [Entity Memory](https://python.langchain.com/docs/modules/memory/types/entity_summary_memory) - 实体记忆

### 工具使用

* [LangChain Tools](https://python.langchain.com/docs/modules/tools/) - LangChain 工具系统
* [AutoGen Tools](https://microsoft.github.io/autogen/docs/user-guide/tools-user-defined) - AutoGen 工具使用
* [CrewAI Tools](https://docs.crewai.org.cn/concepts/tools) - CrewAI 工具系统
* [Toolformer](https://arxiv.org/abs/2302.04761) - 工具学习论文
* [EASYTOOL](https://arxiv.org/abs/2401.06201) - 工具文档转换框架

### 搜索能力

* [语义搜索](./skills/README.md#语义搜索) - 基于语义的搜索
* [全文搜索](./skills/README.md#全文搜索) - 基于关键词的搜索
* [混合搜索](./skills/README.md#混合搜索) - 结合语义和关键词
* [Elasticsearch](https://www.elastic.co/) - 搜索引擎
* [Meilisearch](https://www.meilisearch.com/) - 快速搜索引擎

### API 集成

* [REST API](https://restfulapi.net/) - RESTful API 集成
* [GraphQL](https://graphql.org/) - GraphQL API 集成
* [OpenAPI](https://www.openapis.org/) - OpenAPI 规范
* [FastAPI](https://fastapi.tiangolo.com/) - Python Web 框架
* [Flask](https://flask.palletsprojects.com/) - Python Web 框架

## 开源项目

### 框架项目

* [LangChain](https://github.com/langchain-ai/langchain) - LLM 应用框架
* [AutoGen](https://github.com/microsoft/autogen) - 多智能体框架
* [CrewAI](https://github.com/joaomdmoura/crewAI) - 角色扮演框架
* [LangGraph](https://github.com/langchain-ai/langgraph) - 状态图框架
* [MetaGPT](https://github.com/geekan/MetaGPT) - SOP 编码框架
* [ChatDev](https://github.com/OpenBMB/ChatDev) - 软件开发框架
* [AgentScope](https://github.com/modelscope-agent/agentscope) - 开发者框架
* [TaskWeaver](https://github.com/microsoft/TaskWeaver) - 代码优先框架

### 应用项目

* [OpenDevin](https://github.com/OpenDevin/OpenDevin) - 开源 AI 软件工程师
  * 🌟 Stars: 25k+
* [AgentGPT](https://github.com/reworkd/AgentGPT) - 浏览器 Agent
* [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) - 自主 GPT-4
* [BabyAGI](https://github.com/yoheinakajima/babyagi) - 任务管理
* [Voyager](https://github.com/MineDojo/Voyager) - Minecraft Agent
* [Poker AI](https://github.com/intern-ai/Poker) - 德州扑克 Agent

### 工具项目

* [Skill Seeker](https://github.com/jimmysong/skill-seeker) - 技能包转换工具
* [LangSmith](https://github.com/langchain-ai/langsmith-sdk) - 调试和监控
* [LangServe](https://github.com/langchain-ai/langserve) - API 部署工具
* [E2B](https://github.com/e2b-dev/e2b) - 代码执行沙箱

### 评估基准

* [AgentBench](https://github.com/THUDM/AgentBench) - Agent 评估基准
* [OpenAI Evals](https://github.com/openai/evals) - OpenAI 评估框架
* [AgentBoard](https://github.com/THUDM/AgentBoard) - Agent 评估面板
* [WebArena](https://github.com/web-arena-x/webarena) - Web Agent 评估

## 学术论文

### 经典论文

* 📝 [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629) - ReAct 框架
* 📝 [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/abs/2201.11903) - 思维链提示
* 📝 [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366) - Reflexion 框架
* 📝 [详细论文列表](./papers/index.md)

### Agent 架构

* 📝 [CAMEL: Communicative Agents for Mind Exploration and Learning](https://arxiv.org/abs/2303.17760)
* 📝 [AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation](https://arxiv.org/abs/2308.08155)
* 📝 [ChatDev: Communicative Agents for Software Development](https://arxiv.org/abs/2307.07924)

### 工具使用

* 📝 [Toolformer: Language Models Can Teach Themselves to Use Tools](https://arxiv.org/abs/2302.04761)
* 📝 [Augmented Language Models: a Survey](https://arxiv.org/abs/2302.07842)
* 📝 [Chameleon: Plug-and-Play Compositional Reasoning with Large Language Models](https://arxiv.org/abs/2204.09591)
* 📝 [EASYTOOL: Enhancing LLM-based Agents with Concise Tool Instruction](https://arxiv.org/abs/2401.06201)

### 推理和规划

* 📝 [Tree of Thoughts: Deliberate Problem Solving with Large Language Models](https://arxiv.org/abs/2305.10601)
* 📝 [Least-to-Most Prompting Enables Complex Reasoning in Large Language Models](https://arxiv.org/abs/2205.10625)
* 📝 [Self-Consistency Improves Chain of Thought Reasoning in Language Models](https://arxiv.org/abs/2203.11171)

### 多智能体系统

* 📝 [Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/abs/2304.03442)
* 📝 [MetaGPT: Meta Programming for A Multi-Agent Collaborative Framework](https://arxiv.org/abs/2308.00352)
* 📝 [AgentScope 1.0: A Developer-Centric Framework for Building Agentic Applications](https://arxiv.org/abs/2508.16279)
* 📝 [TaskWeaver: A Code-First Agent Framework](https://arxiv.org/abs/2311.17541)
* 📝 [AutoAgents: A Framework for Automatic Agent Generation](https://arxiv.org/abs/2309.17288)

### 评估和基准

* 📝 [AgentBench: Evaluating LLMs as Web Agents](https://arxiv.org/abs/2308.07312)
* 📝 [Evaluating Large Language Models for AI Agents](https://arxiv.org/abs/2308.08535)
* 📝 [A Survey on Large Language Model based Autonomous Agents](https://arxiv.org/abs/2308.11432)

### 应用领域

* 📝 [Voyager: An Open-Ended Embodied Agent with Large Language Models](https://arxiv.org/abs/2305.16291)
* 📝 [Coder: Evaluating Large Language Models for Code Generation](https://arxiv.org/abs/2307.00992)

### 综述和教程

* 📝 [A Survey on Large Language Model based Autonomous Agents](https://arxiv.org/abs/2308.11432)
* 📝 [The Dawn of LLMs in Multi-Agent Systems](https://arxiv.org/abs/2308.08555)
* 📝 [Tool Learning with Foundation Models](https://arxiv.org/abs/2304.08355)

## 教程和指南

### 初学者指南

* 📖 [Agent Skills 初学者指南](./tutorials/beginner-guides.md)
* [LangChain 快速入门](https://python.langchain.com/docs/get_started/introduction)
* [AutoGen 入门教程](https://microsoft.github.io/autogen/docs/Getting-Started)
* [CrewAI 快速开始](https://docs.crewai.org.cn/getting-started/quick-start)

### 进阶教程

* [LangChain 高级用法](https://python.langchain.com/docs/modules)
* [AutoGen 多智能体协作](https://microsoft.github.io/autogen/docs/tutorial/Multi-Agent-Collaboration)
* [LangGraph 教程](https://langchain-ai.github.io/langgraph/tutorials/)

### 实战项目

* [LangChain Cookbook](https://github.com/langchain-ai/langchain-cookbook)
* [AutoGen Examples](https://github.com/microsoft/autogen/tree/main/notebook)
* [CrewAI Examples](https://github.com/joaomdmoura/crewAI-examples)

### 最佳实践

* [LangChain 最佳实践](https://python.langchain.com/docs/guides)
* [Agent 开发指南](./tutorials/beginner-guides.md#最佳实践)

## 视频资源

### 会议演讲

* [NeurIPS 2023 - Agent 相关演讲](https://neurips.cc/)
* [ICLR 2024 - Agent 论文报告](https://iclr.cc/)
* [LangChain Conference 2024](https://www.langchain.com/conference)

### 教程视频

* [LangChain 官方 YouTube](https://www.youtube.com/@LangChain)
* [3Blue1Brown - AI 可视化](https://www.youtube.com/@3blue1brown)
* [LangChain 教程系列](https://www.youtube.com/playlist?list=PLqTZaBYZtmIou3y3JfY4W5oZmXnHh6k0y)

### 技术分享

* [AI 技术分享会](./videos/index.md)
* [Agent 开发实践](./videos/index.md)

## 新闻和动态

* 📰 [最新新闻](./news/index.md)
* [AI 科技动态](./news/README.md)

## 相关 Awesome 列表

* [Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents)
* [Awesome LLM](https://github.com/Hannibal046/Awesome-LLM)
* [Awesome LangChain](https://github.com/kyrolabs/awesome-langchain)
* [Awesome AutoGen](https://github.com/microsoft/autogen)

## 许可证

本项目采用 [CC0](LICENSE) 许可证。

---

**注意**: 本项目致力于提供高质量的 Agent Skills 资源收集。如果您发现任何错误或需要添加的资源，请随时提交 Issue 或 Pull Request。

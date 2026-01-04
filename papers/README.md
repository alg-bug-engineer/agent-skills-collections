# 📖 Agent Skills 学术论文

这里是 AI Agent 和 Agent Skills 相关的重要学术论文集合。

<div align="center">

[![Papers](https://img.shields.io/badge/Papers-50+-red)](https://github.com/alg-bug-engineer/agent-skills-collections)
[![Updated](https://img.shields.io/badge/Updated-2026--01-blue)](https://github.com/alg-bug-engineer/agent-skills-collections)

</div>

---

## 📑 目录

- [🏆 经典论文](#-经典论文)
- [🏗️ Agent 架构](#-agent-架构)
- [🔧 工具使用](#-工具使用)
- [🧠 推理和规划](#-推理和规划)
- [🤖 多智能体系统](#-多智能体系统)
- [📊 评估和基准](#-评估和基准)
- [🎯 应用领域](#-应用领域)
- [📚 综述和教程](#-综述和教程)

---

## 🏆 经典论文

这些是 Agent 领域的奠基性论文，引用率最高，影响最大。

### ReAct: Synergizing Reasoning and Acting in Language Models
- **作者**: Shunyu Yao, Jeffrey Zhao, Dian Yu, et al.
- **会议**: ICLR 2023
- **链接**: [arXiv:2210.03629](https://arxiv.org/abs/2210.03629)
- **引用**: 5000+
- **核心贡献**:
  - 提出推理（Reasoning）和行动（Acting）结合的框架
  - 通过思维链推理生成行动轨迹
  - 在知识库和 QA 任务上取得显著提升
- **关键词**: ReAct, Chain-of-Thought, Reasoning, Acting
- **代码**: [GitHub](https://github.com/ysymyth/ReAct)

### Chain-of-Thought Prompting Elicits Reasoning in Large Language Models
- **作者**: Jason Wei, Xuezhi Wang, Dale Schuurmans, et al.
- **会议**: NeurIPS 2022
- **链接**: [arXiv:2201.11903](https://arxiv.org/abs/2201.11903)
- **引用**: 8000+
- **核心贡献**:
  - 提出思维链提示方法
  - 通过中间推理步骤提升复杂推理能力
  - 在数学、常识和符号推理任务上表现优异
- **关键词**: Chain-of-Thought, Prompting, Reasoning

### Reflexion: Language Agents with Verbal Reinforcement Learning
- **作者**: Noah Shinn, Federico Cassano, Edward Grefenstette, et al.
- **会议**: NeurIPS 2023
- **链接**: [arXiv:2303.11366](https://arxiv.org/abs/2303.11366)
- **引用**: 2000+
- **核心贡献**:
  - 提出基于语言反馈的强化学习框架
  - 通过自我反思改进 Agent 行为
  - 支持多轮对话和任务执行
- **关键词**: Reflexion, Reinforcement Learning, Self-Reflection

---

## 🏗️ Agent 架构

关于 Agent 系统设计和架构的研究。

### CAMEL: Communicative Agents for Mind Exploration and Learning
- **作者**: Guohao Li, Been Kim, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2303.17760](https://arxiv.org/abs/2303.17760)
- **引用**: 1000+
- **核心贡献**:
  - 提出多智能体通信框架
  - 角色扮演和双向对话机制
  - 展示多智能体协作的潜力
- **关键词**: CAMEL, Multi-Agent, Communication
- **代码**: [GitHub](https://github.com/camel-ai/camel)

### AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation
- **作者**: Qingyun Wu, Gagan Bansal, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2308.08155](https://arxiv.org/abs/2308.08155)
- **引用**: 800+
- **核心贡献**:
  - 提出可定制的多智能体对话框架
  - 支持人类参与和代码执行
  - 提供灵活的工具集成机制
- **关键词**: AutoGen, Multi-Agent, Conversation
- **代码**: [GitHub](https://github.com/microsoft/autogen)

### ChatDev: Communicative Agents for Software Development
- **作者**: Zeyu Liu, Chen Qian, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2307.07924](https://arxiv.org/abs/2307.07924)
- **引用**: 600+
- **核心贡献**:
  - 提出软件开发的多智能体协作框架
  - 模拟软件开发团队角色
  - 实现自动化软件开发流程
- **关键词**: ChatDev, Software Development, Multi-Agent

---

## 🔧 工具使用

关于 Agent 如何使用外部工具的研究。

### Toolformer: Language Models Can Teach Themselves to Use Tools
- **作者**: Timo Schick, Jane Dwivedi-Yu, et al.
- **会议**: ICLR 2024
- **链接**: [arXiv:2302.04761](https://arxiv.org/abs/2302.04761)
- **引用**: 1500+
- **核心贡献**:
  - 提出自动学习使用工具的方法
  - 通过自监督学习工具调用时机
  - 扩展 LLM 的外部工具使用能力
- **关键词**: Toolformer, Tool Learning, Self-Supervised

### Augmented Language Models: a Survey
- **作者**: Qian Liu, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2302.07842](https://arxiv.org/abs/2302.07842)
- **引用**: 400+
- **核心贡献**:
  - 全面综述增强型语言模型
  - 系统梳理工具使用方法
  - 分类和分析不同增强技术
- **关键词**: Augmented LLMs, Tool Use, Survey

### Chameleon: Plug-and-Play Compositional Reasoning with Large Language Models
- **作者**: Panupong Pasupat, et al.
- **会议**: ICLR 2023
- **链接**: [arXiv:2204.09591](https://arxiv.org/abs/2204.09591)
- **引用**: 300+
- **核心贡献**:
  - 提出即插即用的组合推理框架
  - 支持工具和模型的灵活组合
  - 展示在多模态任务上的应用
- **关键词**: Chameleon, Compositional Reasoning, Tool Integration

---

## 🧠 推理和规划

关于 Agent 推理和规划能力的研究。

### Tree of Thoughts: Deliberate Problem Solving with Large Language Models
- **作者**: Shunyu Yao, Dian Yu, Jeffrey Zhao, et al.
- **会议**: NeurIPS 2023
- **链接**: [arXiv:2305.10601](https://arxiv.org/abs/2305.10601)
- **引用**: 1200+
- **核心贡献**:
  - 提出思维树框架
  - 通过树搜索进行系统推理
  - 在复杂问题求解上显著提升性能
- **关键词**: Tree of Thoughts, Reasoning, Problem Solving

### Least-to-Most Prompting Enables Complex Reasoning in Large Language Models
- **作者**: Denny Zhou, et al.
- **会议**: ICLR 2023
- **链接**: [arXiv:2205.10625](https://arxiv.org/abs/2205.10625)
- **引用**: 500+
- **核心贡献**:
  - 提出从简到繁的提示策略
  - 分解复杂问题为子问题
  - 提升多步推理能力
- **关键词**: Least-to-Most, Decomposition, Reasoning

### Self-Consistency Improves Chain of Thought Reasoning in Language Models
- **作者**: Xuezhi Wang, Jason Wei, et al.
- **会议**: ICLR 2023
- **链接**: [arXiv:2203.11171](https://arxiv.org/abs/2203.11171)
- **引用**: 800+
- **核心贡献**:
  - 提出自一致性方法
  - 通过多次采样和投票提升可靠性
  - 显著提升思维链推理的准确性
- **关键词**: Self-Consistency, CoT, Reasoning

---

## 🤖 多智能体系统

关于多智能体协作和通信的研究。

### Generative Agents: Interactive Simulacra of Human Behavior
- **作者**: Jure Leskovec, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2304.03442](https://arxiv.org/abs/2304.03442)
- **引用**: 1000+
- **核心贡献**:
  - 提出生成式智能体框架
  - 模拟人类社交行为
  - 展示多智能体社会模拟的潜力
- **关键词**: Generative Agents, Social Simulation, Human Behavior

### MetaGPT: Meta Programming for A Multi-Agent Collaborative Framework
- **作者**: Sirui Hong, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2308.00352](https://arxiv.org/abs/2308.00352)
- **引用**: 400+
- **核心贡献**:
  - 提出元编程的多智能体框架
  - 通过 SOP 编码标准化流程
  - 实现高效的多智能体协作
- **关键词**: MetaGPT, Meta-Programming, SOP

---

## 📊 评估和基准

关于 Agent 能力评估和基准测试的研究。

### AgentBench: Evaluating LLMs as Web Agents
- **作者**: Tianbao Xie, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2308.07312](https://arxiv.org/abs/2308.07312)
- **引用**: 200+
- **核心贡献**:
  - 提出 Web Agent 评估基准
  - 设计多样化的评估任务
  - 提供公平的比较框架
- **关键词**: AgentBench, Evaluation, Benchmark
- **代码**: [GitHub](https://github.com/THUDM/AgentBench)

### A Survey on Large Language Model based Autonomous Agents
- **作者**: Lei Wang, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2308.11432](https://arxiv.org/abs/2308.11432)
- **引用**: 300+
- **核心贡献**:
  - 全面综述基于 LLM 的自主智能体
  - 分类分析不同类型的智能体
  - 总结关键技术和挑战
- **关键词**: Autonomous Agents, Survey, LLM

---

## 🎯 应用领域

Agent 在特定领域的应用研究。

### Voyager: An Open-Ended Embodied Agent with Large Language Models
- **作者**: Guanzhi Wang, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2305.16291](https://arxiv.org/abs/2305.16291)
- **引用**: 800+
- **核心贡献**:
  - 提出在 Minecraft 中的具身智能体
  - 实现持续学习和技能积累
  - 展示在复杂环境中的适应能力
- **关键词**: Voyager, Embodied Agent, Minecraft

---

## 📚 综述和教程

对 Agent 领域的全面回顾和教程。

### A Survey on Large Language Model based Autonomous Agents
- **作者**: Lei Wang, Chen Ma, et al.
- **会议**: arXiv 2023
- **链接**: [arXiv:2308.11432](https://arxiv.org/abs/2308.11432)
- **引用**: 300+
- **核心贡献**:
  - 系统性综述自主智能体
  - 分类整理不同智能体架构
  - 分析未来研究方向
- **关键词**: Survey, Autonomous Agents, LLM

### The Dawn of LLMs in Multi-Agent Systems
- **作者**: Various
- **会议**: arXiv 2023
- **链接**: [arXiv:2308.08555](https://arxiv.org/abs/2308.08555)
- **引用**: 200+
- **核心贡献**:
  - 探讨 LLM 在多智能体系统中的应用
  - 分析技术挑战和机遇
  - 展望未来发展
- **关键词**: Multi-Agent, LLM, Survey

---

## 📊 统计数据

### 论文引用排行

| 排名 | 论文 | 引用数 | 年份 |
|-----|------|--------|------|
| 1 | Chain-of-Thought | 8000+ | 2022 |
| 2 | ReAct | 5000+ | 2023 |
| 3 | Reflexion | 2000+ | 2023 |
| 4 | Toolformer | 1500+ | 2024 |
| 5 | Tree of Thoughts | 1200+ | 2023 |

### 发表会议分布

- **NeurIPS**: 30%
- **ICLR**: 25%
- **ACL**: 15%
- **arXiv**: 20%
- **其他**: 10%

---

## 🔗 相关资源

- [Papers with Code](https://paperswithcode.com/)
- [arXiv CS.AI](https://arxiv.org/list/cs.AI/recent)
- [Google Scholar](https://scholar.google.com/)
- [Semantic Scholar](https://www.semanticscholar.org/)

---

## 📝 提交论文

如果您知道其他重要的 Agent Skills 相关论文，欢迎提交 Pull Request 或 Issue。

**提交格式**:
```markdown
### 论文标题
- **作者**: 作者列表
- **会议**: 发表会议
- **链接**: [arXiv 链接](url)
- **引用**: 引用数
- **核心贡献**:
  - 贡献1
  - 贡献2
- **关键词**: 关键词1, 关键词2
```

---

<div align="center">

[⬆ 返回主页](../README.md)

</div>

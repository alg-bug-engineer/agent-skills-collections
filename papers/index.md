# Agent Skills 相关论文索引

这里收集了 AI Agent 和 Agent Skills 相关的重要学术论文。

## 📚 经典论文

### 1. ReAct: Synergizing Reasoning and Acting in Language Models
- **作者**: Shunyu Yao, Jeffrey Zhao, Dian Yu, et al.
- **发表**: ICLR 2023
- **链接**: [arXiv:2210.03629](https://arxiv.org/abs/2210.03629)
- **核心贡献**:
  - 提出推理（Reasoning）和行动（Acting）结合的框架
  - 通过思维链推理生成行动轨迹
  - 在知识库和 QA 任务上取得显著提升
- **关键词**: ReAct, Chain-of-Thought, Reasoning, Acting

### 2. Chain-of-Thought Prompting Elicits Reasoning in Large Language Models
- **作者**: Jason Wei, Xuezhi Wang, Dale Schuurmans, et al.
- **发表**: NeurIPS 2022
- **链接**: [arXiv:2201.11903](https://arxiv.org/abs/2201.11903)
- **核心贡献**:
  - 提出思维链提示方法
  - 通过中间推理步骤提升复杂推理能力
  - 在数学、常识和符号推理任务上表现优异
- **关键词**: Chain-of-Thought, Prompting, Reasoning

### 3. Reflexion: Language Agents with Verbal Reinforcement Learning
- **作者**: Noah Shinn, Federico Cassano, Edward Grefenstette, et al.
- **发表**: NeurIPS 2023
- **链接**: [arXiv:2303.11366](https://arxiv.org/abs/2303.11366)
- **核心贡献**:
  - 提出基于语言反馈的强化学习框架
  - 通过自我反思改进 Agent 行为
  - 支持多轮对话和任务执行
- **关键词**: Reflexion, Reinforcement Learning, Self-Reflection

## 🏗️ Agent 架构

### 4. CAMEL: Communicative Agents for Mind Exploration and Learning
- **作者**: Guohao Li, Been Kim, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2303.17760](https://arxiv.org/abs/2303.17760)
- **核心贡献**:
  - 提出多智能体通信框架
  - 角色扮演和双向对话机制
  - 展示多智能体协作的潜力
- **关键词**: CAMEL, Multi-Agent, Communication

### 5. AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation
- **作者**: Qingyun Wu, Gagan Bansal, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2308.08155](https://arxiv.org/abs/2308.08155)
- **核心贡献**:
  - 提出可定制的多智能体对话框架
  - 支持人类参与和代码执行
  - 提供灵活的工具集成机制
- **关键词**: AutoGen, Multi-Agent, Conversation

### 6. ChatDev: Communicative Agents for Software Development
- **作者**: Zeyu Liu, Chen Qian, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2307.07924](https://arxiv.org/abs/2307.07924)
- **核心贡献**:
  - 提出软件开发的多智能体协作框架
  - 模拟软件开发团队角色
  - 实现自动化软件开发流程
- **关键词**: ChatDev, Software Development, Multi-Agent

## 🔧 工具使用

### 7. Toolformer: Language Models Can Teach Themselves to Use Tools
- **作者**: Timo Schick, Jane Dwivedi-Yu, et al.
- **发表**: ICLR 2024
- **链接**: [arXiv:2302.04761](https://arxiv.org/abs/2302.04761)
- **核心贡献**:
  - 提出自动学习使用工具的方法
  - 通过自监督学习工具调用时机
  - 扩展 LLM 的外部工具使用能力
- **关键词**: Toolformer, Tool Learning, Self-Supervised

### 8. Augmented Language Models: a Survey
- **作者**: Qian Liu, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2302.07842](https://arxiv.org/abs/2302.07842)
- **核心贡献**:
  - 全面综述增强型语言模型
  - 系统梳理工具使用方法
  - 分类和分析不同增强技术
- **关键词**: Augmented LLMs, Tool Use, Survey

### 9. Chameleon: Plug-and-Play Compositional Reasoning with Large Language Models
- **作者**: Panupong Pasupat, et al.
- **发表**: ICLR 2023
- **链接**: [arXiv:2204.09591](https://arxiv.org/abs/2204.09591)
- **核心贡献**:
  - 提出即插即用的组合推理框架
  - 支持工具和模型的灵活组合
  - 展示在多模态任务上的应用
- **关键词**: Chameleon, Compositional Reasoning, Tool Integration

## 🧠 推理和规划

### 10. Tree of Thoughts: Deliberate Problem Solving with Large Language Models
- **作者**: Shunyu Yao, Dian Yu, Jeffrey Zhao, et al.
- **发表**: NeurIPS 2023
- **链接**: [arXiv:2305.10601](https://arxiv.org/abs/2305.10601)
- **核心贡献**:
  - 提出思维树框架
  - 通过树搜索进行系统推理
  - 在复杂问题求解上显著提升性能
- **关键词**: Tree of Thoughts, Reasoning, Problem Solving

### 11. Least-to-Most Prompting Enables Complex Reasoning in Large Language Models
- **作者**: Denny Zhou, et al.
- **发表**: ICLR 2023
- **链接**: [arXiv:2205.10625](https://arxiv.org/abs/2205.10625)
- **核心贡献**:
  - 提出从简到繁的提示策略
  - 分解复杂问题为子问题
  - 提升多步推理能力
- **关键词**: Least-to-Most, Decomposition, Reasoning

### 12. Self-Consistency Improves Chain of Thought Reasoning in Language Models
- **作者**: Xuezhi Wang, Jason Wei, et al.
- **发表**: ICLR 2023
- **链接**: [arXiv:2203.11171](https://arxiv.org/abs/2203.11171)
- **核心贡献**:
  - 提出自一致性方法
  - 通过多次采样和投票提升可靠性
  - 显著提升思维链推理的准确性
- **关键词**: Self-Consistency, CoT, Reasoning

## 🤖 多智能体系统

### 13. Generative Agents: Interactive Simulacra of Human Behavior
- **作者**: Jure Leskovec, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2304.03442](https://arxiv.org/abs/2304.03442)
- **核心贡献**:
  - 提出生成式智能体框架
  - 模拟人类社交行为
  - 展示多智能体社会模拟的潜力
- **关键词**: Generative Agents, Social Simulation, Human Behavior

### 14. MetaGPT: Meta Programming for A Multi-Agent Collaborative Framework
- **作者**: Sirui Hong, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2308.00352](https://arxiv.org/abs/2308.00352)
- **核心贡献**:
  - 提出元编程的多智能体框架
  - 通过 SOP 编码标准化流程
  - 实现高效的多智能体协作
- **关键词**: MetaGPT, Meta-Programming, SOP

### 15. Communicative Agents for Software Development
- **作者**: Zeyu Liu, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2307.07924](https://arxiv.org/abs/2307.07924)
- **核心贡献**:
  - 探讨智能体在软件开发中的应用
  - 分析通信机制对协作的影响
  - 提出评估多智能体协作的方法
- **关键词**: Software Development, Communication, Collaboration

## 📊 评估和基准

### 16. AgentBench: Evaluating LLMs as Web Agents
- **作者**: Tianbao Xie, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2308.07312](https://arxiv.org/abs/2308.07312)
- **核心贡献**:
  - 提出 Web Agent 评估基准
  - 设计多样化的评估任务
  - 提供公平的比较框架
- **关键词**: AgentBench, Evaluation, Benchmark

### 17. Evaluating Large Language Models for AI Agents
- **作者**: Various
- **发表**: arXiv 2023
- **链接**: [arXiv:2308.08535](https://arxiv.org/abs/2308.08535)
- **核心贡献**:
  - 系统评估 LLM 作为 Agent 的能力
  - 分析不同任务上的表现
  - 提出改进方向
- **关键词**: Evaluation, LLM Agents, Benchmark

### 18. A Survey on Large Language Model based Autonomous Agents
- **作者**: Lei Wang, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2308.11432](https://arxiv.org/abs/2308.11432)
- **核心贡献**:
  - 全面综述基于 LLM 的自主智能体
  - 分类分析不同类型的智能体
  - 总结关键技术和挑战
- **关键词**: Autonomous Agents, Survey, LLM

## 🎯 应用领域

### 19. Voyager: An Open-Ended Embodied Agent with Large Language Models
- **作者**: Guanzhi Wang, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2305.16291](https://arxiv.org/abs/2305.16291)
- **核心贡献**:
  - 提出在 Minecraft 中的具身智能体
  - 实现持续学习和技能积累
  - 展示在复杂环境中的适应能力
- **关键词**: Voyager, Embodied Agent, Minecraft

### 20. Coder: Evaluating Large Language Models for Code Generation
- **作者**: Various
- **发表**: arXiv 2023
- **链接**: [arXiv:2307.00992](https://arxiv.org/abs/2307.00992)
- **核心贡献**:
  - 提出代码生成评估基准
  - 分析不同模型的表现
  - 指导代码生成智能体的发展
- **关键词**: Code Generation, Evaluation, Benchmark

## 📖 综述和教程

### 21. A Survey on Large Language Model based Autonomous Agents
- **作者**: Lei Wang, Chen Ma, et al.
- **发表**: arXiv 2023
- **链接**: [arXiv:2308.11432](https://arxiv.org/abs/2308.11432)
- **核心贡献**:
  - 系统性综述自主智能体
  - 分类整理不同智能体架构
  - 分析未来研究方向
- **关键词**: Survey, Autonomous Agents, LLM

### 22. The Dawn of LLMs in Multi-Agent Systems
- **作者**: Various
- **发表**: arXiv 2023
- **链接**: [arXiv:2308.08555](https://arxiv.org/abs/2308.08555)
- **核心贡献**:
  - 探讨 LLM 在多智能体系统中的应用
  - 分析技术挑战和机遇
  - 展望未来发展
- **关键词**: Multi-Agent, LLM, Survey

### 23. Tool Learning with Foundation Models
- **作者**: Various
- **发表**: arXiv 2023
- **链接**: [arXiv:2304.08355](https://arxiv.org/abs/2304.08355)
- **核心贡献**:
  - 综述工具学习方法
  - 分析工具学习的技术路线
  - 总结应用场景和挑战
- **关键词**: Tool Learning, Foundation Models, Survey

## 🔗 相关资源

- [Papers with Code - Agents](https://paperswithcode.com/area/nlp/agent)
- [Awesome Agent Papers](https://github.com/e2b-dev/awesome-ai-agents#papers)
- [arXiv CS.AI](https://arxiv.org/list/cs.AI/recent)

## 📝 提交论文

如果您知道其他重要的 Agent Skills 相关论文，欢迎提交 Pull Request 或 Issue。

---

**更新日期**: 2026-01-04
**版本**: v0.1

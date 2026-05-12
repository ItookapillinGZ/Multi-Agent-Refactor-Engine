# Multi-Agent Refactor Engine | 基于多智能体协同的代码库自动化重构引擎

针对大型 Python 项目中存在的类型缺失、语法陈旧（Python 2 遗留）及潜在性能风险，本项目开发了一套全自动化的代码现代化重构系统 。通过多智能体协作模式，实现了从代码审计到安全重构的完整闭环，显著提升了研发效能 。

## 🚀 核心特性

本项目基于 **Python 3.10+** 与 **Claude-4.6-Sonnet** 构建 ，采用高度解耦的架构设计：

* 
**Skill Loading (技能解耦)**：通过封装原子化 Skill 实现对 LLM 能力的精准约束 。构建了具备垂直领域知识的智能体矩阵（如 TypeMaster 类型推导、Auditor 规则审计），显著降低复杂重构任务中的逻辑幻觉 。


* 
**Task System (状态感知型任务管理)**：支持任务动态分发、优先级排序及 **Dependency Tracking (依赖追踪)** 。系统能够自动感知任务状态并处理 Blocked 情况，确保大规模代码重构过程中的顺序一致性 。


* 
**Agent Team (异步协作协议)**：建立基于 **Inbox 消息总线** 的异步通信协议 。主控智能体作为“质量网关”执行**权威合并 (Authoritative Merge) 机制**，实时对比并合并多个专家智能体的修改建议，确保代码在逻辑与性能上的最优解 。



## 🛠️ 技术栈

* 
**Core**: Python 3.10+ 


* 
**LLM**: Claude-4.6-Sonnet 


* 
**Static Analysis**: Ruff, MyPy 


* 
**Frameworks**: Pydantic v2 (数据校验), Asyncio (异步任务编排) 



## 🏗️ 架构组件

1. 
**语法现代化智能体 (Syntax Master)**：专注 PEP 585/604 类型提示推导与 `eval` 等不安全函数的安全替换 。


2. 
**安全审计智能体 (Security Auditor)**：基于静态分析执行性能瓶颈扫描与漏洞检测 。


3. 
**集成专家智能体 (Integration Expert)**：负责文件原子化操作、Locale 感知（解决 Windows/Linux 编码冲突）与冲突合并 。



## 📈 项目成果

* 
**自动化覆盖**：实现对核心模块的 100% 自动重构，涵盖类型提示更新、上下文管理器优化等 20 余项指标 。


* 
**工程鲁棒性**：通过引入沙盒 (Sandbox) 隔离机制与显式 I/O 钩子，彻底解决了中文路径及 UTF-8/GBK 编码冲突等工程细节难题 。



---

### 如何运行

```bash
# 克隆仓库
git clone https://github.com/ItookapillinGZ/multi-agent.git

# 安装依赖
pip install -r requirements.txt

# 配置 API Key
export ANTHROPIC_API_KEY='your-api-key-here'

# 启动重构引擎
python main.py --path ./your_legacy_project

```

---

**License**: MIT

conference : https://github.com/shareAI-lab/learn-claude-code

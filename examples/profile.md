# 个人简历
## 基本信息
- 姓名：林舟
- 电话：13800138000
- 邮箱：linzhou@example.com
- 求职意向：LLM应用开发 / 后端开发 / AI应用开发
- 期望工作地：一线 / 新一线城市
- 现状：某公立大学 数据科学相关专业 本科在读


## 专业技能
**AI 应用开发**
- 大模型应用工程：LLM API 集成（OpenAI、DeepSeek、Claude）、流式输出（SSE）、Function Calling
- RAG 系统搭建：文档预处理、语义分块、Embedding 向量化、向量检索
- Agent 开发：智能体框架（CrewAI、LangGraph）、任务规划与拆解、工作流编排（Planner-Executor 模式）, Tool Calling
- 提示词工程：CoT, RTF框架，Few Shots

**AI 框架与工具**
- LangGraph（状态图构建、条件边、循环工作流）
- LlamaIndex（文件读取，索引构建）
- 向量数据库：ChromaDB、PGVector
- 开源平台：Dify、RAGFlow

**全栈开发**
- 后端：Python（FastAPI）、Java（SpringBoot、若依）、MySQL / Redis / ChromaDB、Docker / Linux 部署
- 前端：Vue、HTML5/CSS3/JS、微信小程序、原生 JS 嵌入式组件，借助 AI 工具快速实现可上线界面

**工程化**
- Git、RESTFUL 接口文档、云服务器基础部署与公网访问验证


## 项目经历
### 智能研报助手 — 基于 LangGraph 的多 Agent 投研分析系统
**技术栈：** Python、LangGraph、FastAPI、DeepSeek API、Tushare 金融数据接口、ChromaDB、RAG、Vue3  
**角色：** 独立全栈开发、Agent 工作流设计、自研 Demo 实现

面向个股分析场景开发的自研 Demo，重点验证 LangGraph 多 Agent 编排、工具调用和 RAG 结合后的研报生成链路。

- **LangGraph 工作流编排：** 基于 LangGraph 构建状态图驱动的多 Agent 协作系统，拆分信息收集、数据分析、观点生成、报告排版等节点，通过条件边实现任务分支与循环迭代，便于调试和流程回退
- **工具调用集成：** 封装 Tushare 股票数据 API、新闻搜索 API、财务指标计算工具，通过 Function Calling 动态调度外部能力，验证 Agent 自主选择工具的可行性
- **RAG 知识库：** 基于 ChromaDB 构建行业研报向量库，实现语义检索、历史观点对比与来源标注，为生成结果提供参考依据
- **状态管理与持久化：** 设计 LangGraph 状态 Schema，支持多轮上下文保持、中间结果缓存、异常分支回退与人工介入，提升长链路任务执行稳定性
- **前端交互：** 使用 Vue3 开发投研工作台，串联研报生成、进度展示、结果编辑与 Markdown 导出流程，完成从分析到输出的完整 Demo 闭环

### LlamaIndex RAG 知识库问答与评估系统
**技术栈：** Python、LlamaIndex、ragas、PostgreSQL/pgvector、本地 embedding 模型 `BAAI/bge-m3`

自研离线优先的 RAG 实验项目，重点验证知识入库、检索问答与效果评测的完整闭环。

- 设计并实现 RAG 主链路，支持本地文档导入、索引重建、相似度检索、引用返回和基于检索上下文的答案生成，完成从入库到问答的基础验证
- 使用 LlamaIndex 对接文档读取与向量索引能力，结合 PostgreSQL + pgvector 持久化向量数据，避免纯内存方案重复建库带来的实验成本
- 接入本地 embedding 模型 `BAAI/bge-m3`，在不依赖远程 embedding API 的前提下完成向量化与检索，提升离线实验的可控性
- 搭建 `ragas` 离线评估流程，将问答样本转换为评测数据集，用于对检索召回、答案相关性与事实一致性进行结构化对比
- 将应用主链路与评估链路解耦，支持独立配置评测模型与批处理参数，便于后续比较不同模型与检索策略的效果

### AI 智能客服聊天机器人
**技术栈：** Python、FastAPI、CrewAI、DeepSeek API、ChromaDB、RAG、SSE、LangChain、原生 JS/HTML5/CSS3  
**角色：** 独立全栈开发、架构设计、自研 Demo 实现

面向房产客服问答场景开发的自研 Demo，重点验证多 Agent 协作、RAG 检索和流式交互在客服场景中的组合效果。

- **Agent 架构设计：** 基于 CrewAI 实现多智能体协作系统，设计意图识别、知识库问答、动作执行等 Agent，验证任务自动规划与流转方案
- **RAG 知识库构建：** 基于 LangChain + ChromaDB 搭建私有知识库，实现文档预处理、语义分块、Embedding 向量化、相似度检索与来源标注，形成完整 RAG 问答链路
- **工具调用与 API 集成：** 封装 DeepSeek API 调用层，并通过 Function Calling 对接内部业务接口，支持动态工具注册与调用实验
- **流式交互体验：** 使用 SSE 流式响应实现打字机效果，设计可嵌入式聊天 Widget，完成多端可用的前端交互 Demo
- **Prompt 工程：** 针对房产客服场景设计多轮对话 Prompt，约束输出格式并优化幻觉问题，提升回答稳定性与可读性

### 影刀 RPA 自动化业务机器人
**技术栈：** 影刀 RPA、Excel 数据处理、网页自动化、Windows 脚本  
**角色：** 流程设计、开发、调试与落地

- **多场景机器人开发：** 开发表格数据清洗、批量录入、网页自动操作、重复业务流程处理等自动化机器人，替代人工重复操作
- **数据处理：** 实现 Excel 读写、格式转换、数据统计、批量任务一键执行，适配电商 / 办公 / 数据整理等业务场景
- **效率提升：** 通过流程优化与异常处理机制，提升业务处理效率 80%+，支持长时间稳定运行


## 教育背景
**某公立大学 | 数据科学相关专业 | 本科 | 2023.09 - 2027.06**
- 具备扎实的数据处理、编程基础与项目实战能力
- 擅长快速学习新技术，能利用 AI 工具提升全栈开发效率


## 自我评价
- 以 Python 后端和 AI 应用开发为主，能独立完成 Demo 项目的方案设计、开发联调，并借助 AI 工具完成基础部署与公网访问验证
- 熟悉 RAG、Agent、Prompt 工程等常见 LLM 应用开发链路，能围绕具体场景完成原型实现与迭代
- 具备 FastAPI、Vue、MySQL、Redis、Docker、Linux 等全栈基础，能够支撑 AI 应用从接口到前端展示，再到服务器部署联调的完整开发流程
- 学习速度快，愿意在真实业务中继续补齐评测、稳定性优化和工程化能力

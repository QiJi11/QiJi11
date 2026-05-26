# Hi there, I'm QiJi11 👋

一个立志于 **AI 应用开发 / 智能体研发 / LLM 后端工程** 的开发者。目前专注于 RAG、Multi-Agent 协作、智能对话工作流与多模态应用的工程化落地。

📬 **联系方式**：tianhe200300@163.com

---

### 🛠️ 技术栈 (Tech Stack)

- **AI & 大模型相关**：FastAPI / RAG (Retrieval-Augmented Generation) / Embedding / ChromaDB (向量库) / ReAct Agent / LangChain / LangGraph (工作流编排) / Prompt 调优 / DeepSeek / Claude API 对接
- **后端工程开发**：Python / Java (Spring Boot, Spring Security, MyBatis) / Go / MySQL (SQL 优化) / Redis (多维缓存, 分布式锁) / NATS (消息队列)
- **前端与桌面端**：TypeScript / React / Electron (桌面端跨平台) / Ant Design / Vue
- **开发与部署**：Git / Docker / Nginx (反向代理, 负载均衡) / Cursor / Claude Code

---

### 🚀 核心项目 (Core Projects)

#### 🖼️ [screenshot-ocr-demo](https://github.com/QiJi11/screenshot-ocr-demo)
**基于 Electron + FastAPI + RapidOCR + LLM 的多模态截图与大模型智能分析助手**
- **技术栈**：Electron + React + FastAPI + RapidOCR + SSE 流式响应 + HTTPX 异步 + Ant Design
- **核心实现**：
  - 支持全屏与窗口截图，本地采用 RapidOCR 进行高性能文字提取，OCR 结果秒级识别并自动复制至剪贴板。
  - **大模型 AI 智能分析**：打通多模态数据闭环，接入 OpenAI / DeepSeek API 兼容接口，基于 SSE (Server-Sent Events) 实现打字机式异步 Token 实时流式输出，首字延迟低于 500ms。
  - **工作流场景适配**：内置 “💻 代码报错解释/修复”、“🌐 中英双向智能翻译”、“📊 结构化 Markdown 表格” 和 “📝 文本核心纪要生成” 等 Prompt 模版。
  - **安全与配置持久化**：新增大模型配置管理，API 密钥本地持久化至 AppData 中，彻底杜绝密钥硬编码上传至开源仓库的安全风险。

#### 🔍 [rag-engine](https://github.com/QiJi11/rag-engine)
**面向企业知识库的 RAG (检索增强生成) 问答引擎**
- **技术栈**：Python + FastAPI + ChromaDB + OpenAI Embedding + DeepSeek API
- **核心实现**：
  - 实现文档切块 (Chunking) 与余弦相似度检索，支持 RAG 增强回答与普通直答模式动态切换。
  - 基于 Redis 实现多轮会话上下文滑动窗口（保留最近 8 轮），超出长度自动裁剪，优化 Token 消耗。

#### 🤖 [agent-flow](https://github.com/QiJi11/agent-flow)
**基于 ReAct 范式的轻量级智能体引擎**
- **技术栈**：Python + FastAPI + ReAct推理循环 + 动态工具注册
- **核心实现**：
  - 从零手写 Thought → Action → Observation 推理决策循环，支持最大迭代次数限制与降级直答。
  - 采用装饰器模式实现工具的动态注册（如 RAG 检索、外部 API），支持在运行时灵活扩展 Agent 的能力。

#### 💬 [knowledge-qa-platform](https://github.com/QiJi11/knowledge-qa-platform)
**智能 AI 知识问答平台 (Spring AI / SSE)**
- **技术栈**：Spring Boot 3.2 + Spring AI + Redis + SSE + Vue
- **核心实现**：
  - 基于 Spring AI 接入大模型，通过 SSE (Server-Sent Events) 实现打字机流式输出。
  - 使用 Guava BloomFilter 过滤无效请求，结合 Redis 缓存（TTL 1h）与 LTRIM 滑动窗口进行会话管理。

#### 🌐 [echo-community](https://github.com/QiJi11/echo-community)
**高并发社交互动社区后端服务**
- **技术栈**：Spring Boot 3.2 + MyBatis + Redis + Spring Security + Quartz + MySQL
- **核心实现**：
  - 设计二级评论系统与点赞/关注功能，使用 Redis ZSet 维护用户关注链及推流时间线。
  - 使用 Quartz 定时任务结合对数热度公式 `log(like+comment) + time_decay` 进行帖子热度动态排行。

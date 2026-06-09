# Hi there, I'm QiJi11

专注于 AI 应用后端、RAG 知识库问答和 Agent 工具调用链路的开发实践，主要使用 Python、FastAPI、LangGraph、ChromaDB 与 OpenAI-compatible API 构建可演示的后端 Demo。

## 技术方向

- AI 应用后端：Python、FastAPI、async/await、SSE、Pydantic
- RAG：文档分块、SentenceTransformers、ChromaDB、TopK 检索、CrossEncoder rerank、Prompt 注入
- Agent：Tool Schema、工具注册、工具执行、LangGraph 状态图、异常降级
- 工程实践：Router / Service / Store 分层、接口文档、日志排查、Git

## 核心项目

### [agent-flow](https://github.com/QiJi11/agent-flow)

智能体工具调用后端 Demo，围绕 Agent 工具选择、参数解析、工具执行、结果回传和异常降级进行实现。

- 提供 `/api/v1/agent/run` 与 `/api/v1/agent/langchain/run` 两个执行端点，对照基础执行循环与 LangGraph 编排方式。
- 基于工具注册中心维护 RAG 检索工具，整理 Tool Schema、参数校验和 System Prompt 注入逻辑。
- 记录工具调用步骤和中间结果，便于排查工具调用失败、参数缺失和循环卡住等问题。

### [rag-engine](https://github.com/QiJi11/rag-engine)

RAG 知识库问答后端 Demo，实现文档上传、分块、向量检索、rerank、Prompt 注入和 SSE 流式回答链路。

- 实现 `/api/v1/upload` 文档入库接口，按 512 字符分块与 50 字符 overlap 处理 TXT / PDF 文档，并写入 ChromaDB。
- 基于 `all-MiniLM-L6-v2` 完成向量检索，再用 CrossEncoder rerank 选出 Top-3 片段注入 Prompt。
- 实现 `/api/v1/chat` 与 `/api/v1/chat/stream`，支持 `use_rag` 切换知识库增强回答和普通直答，并通过 `session_id` 维护多轮会话。

## 联系方式

- Email: tianhe200300@163.com

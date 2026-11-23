# Leo · Agent / RAG 应用开发

用 Python、FastAPI 和 LangGraph 开发有状态的 Agent，以及能回查原文的文档问答服务。

[查看场景与验收样例](https://bmmbll1881.github.io/agent-rag-demo/) · 页面展示固定样例，后端验证在本地运行。

### LocalLife · 本地生活决策 Agent

在同一会话里把两人用餐的人均预算从 100 元调到 50 元。系统保留人数，移除超预算推荐，并标出缺价商铺。

- 用 LangGraph Supervisor 编排商铺检索、口碑取证、优惠试算和结果校验。
- 通过 HTTP 注入两类规划器故障。回退后的业务结果与基线一致，会话轮次只写入一次。

[查看预算调整与故障回退](https://bmmbll1881.github.io/agent-rag-demo/#locallife)

### 有据 Youju · 可核查文档问答

对制度或经营简报提问，回答附原文与位置，并可通过 `run_id` 回查当次答案和证据。

- 使用 pgvector 与中文 BM25 混合检索，在生成后校验引用、数值和单位。
- 本地端到端验证覆盖引用回查，以及文档更新失败后旧版本仍能回答未缓存的问题。

[查看引用与文档更新故障](https://bmmbll1881.github.io/agent-rag-demo/#youju)

LocalLife 通过 MCP 向 Youju 查询文档证据，并回查问答运行记录。

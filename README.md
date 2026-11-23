# Leo | Agent and RAG Application Development

I build stateful agents and document QA services with Python, FastAPI, and LangGraph. My projects focus on recovering from tool failures and tracing answers back to source evidence.

### LocalLife | Local Dining Assistant

LocalLife helps two diners compare options and revise their per-person budget in the same conversation. When the budget drops from CNY 100 to CNY 50, it keeps the party size, removes over-budget recommendations, and flags places with missing prices.

- A LangGraph Supervisor coordinates venue search, review evidence, discount estimates, and result validation.
- HTTP fault-injection tests verified that invalid planner output and planner errors fall back to the deterministic workflow. The business results match the baseline, and the turn is stored once.

[View the budget and planner fallback examples](https://bmmbll1881.github.io/agent-rag-demo/#locallife)

### Youju | Traceable Document QA

Youju answers questions about policies, business reports, and contracts. Each answer includes source excerpts and their locations. A run ID lets callers retrieve the original answer and evidence.

- Hybrid retrieval combines pgvector and Chinese BM25. The service validates citations, numbers, and units before returning the answer.
- Local end-to-end tests verified citation lookup and confirmed that the previous document version still answers uncached questions after a failed index update.

[View the citation and index recovery examples](https://bmmbll1881.github.io/agent-rag-demo/#youju)

LocalLife uses MCP to query Youju and retrieve the corresponding run records. The public site shows recorded scenarios. Backend execution has been verified locally.

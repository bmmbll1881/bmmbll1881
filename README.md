# Leo | Agent, RAG, and Reliable ML Systems

I build stateful agent applications and evidence-grounded document QA services with Python, FastAPI, LangGraph, PostgreSQL, MySQL, Redis, and MCP. I care about failure recovery, traceability, and reproducible evaluation.

## Featured work

### LocalLife | Local Dining Decision Agent

A multi-turn decision assistant that compares local venues by location, budget, party size, reviews, and discount rules.

- LangGraph Supervisor coordinates venue discovery, review evidence, discount estimation, and result validation.
- HTTP fault injection verifies fallback from invalid planner output and planner errors to a deterministic workflow.
- MySQL session records and idempotent receipts preserve multi-device conversations and prevent duplicate turns.
- Verified locally with 111/111 business checks, 30/30 agent decision scenarios, and 20/20 permission and safety cases.

### Youju | Traceable Document QA

A document QA service that returns answers, source excerpts, document locations, and a retrievable run ID.

- Weighted RRF combines pgvector dense retrieval with Chinese BM25.
- Post-generation validation checks citations, numbers, units, direction, and answer completeness.
- Versioned document publishing keeps the previous release available when embedding or indexing fails.
- Verified locally with real PostgreSQL/pgvector and Redis, deterministic model substitutes, and 24/24 targeted end-to-end checks.

### [NSC Layer-Order Tilt Scoring Framework](https://github.com/bmmbll1881/nsc-starter)

A CPU-only, reproducible research implementation studying whether layer order improves Neural Spectral Capacity for architecture ranking.

- Compares a 16-position ridge fit, a historical single-parameter tilt, and a size-depth orthogonalized tilt.
- Reproduces frozen rankings, external panels, paper comparisons, reversal checks, and LoNAS selection experiments.
- Uses pinned inputs, provenance hashes, deterministic controls, and standard-library evaluation scripts.

## Additional projects

| Project | What it demonstrates |
| --- | --- |
| **Lab Management System** | Full-stack laboratory and equipment reservations with a React/Vite interface, FastAPI, SQLAlchemy, MySQL, and service-backed LangChain tools. |
| **Text ReAct Agent** | A ReAct loop with structured tool dispatch, MCP tool integration, and file operations restricted to an allowlisted workspace. |
| **Traceable RAG** | A reproducible LangGraph prototype for evidence gating, retrieval retries, extractive answers, citation checks, and failure attribution. |
| **VERP** | A research workspace for shopping-agent training and evaluation, including a standalone PyTorch example of token-level PPO and DPO objectives. |

Project summaries are public. Source access for private repositories is restricted.

## Engineering focus

**Agent systems** · LangGraph · Supervisor orchestration · structured tool calls · MCP · multi-turn state · fault injection · offline evaluation

**Backend and retrieval** · Python · FastAPI · SQLAlchemy · MySQL · PostgreSQL · Redis · pgvector · BM25 · pytest

LocalLife uses MCP to query Youju and retrieve the corresponding evidence and run records. Backend and evaluation workflows have been verified locally.

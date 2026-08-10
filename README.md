# Ata Ul Nasar

Senior Java engineer in Stockholm. I build production retrieval-augmented generation systems — the unglamorous parts: ingestion pipelines, hybrid retrieval, grounding and abstention rules, citation contracts, and the evaluation harnesses that tell you whether any of it actually works.

Roughly a decade of backend engineering, including post-trade and fintech systems at Nasdaq. Most of my recent AI work has been under NDA, so [**Atlas**](https://github.com/ataulnasar/atlas) exists to make it inspectable.

---

## Atlas — open-source Java/Spring RAG platform

[github.com/ataulnasar/atlas](https://github.com/ataulnasar/atlas) · Apache 2.0

Most RAG examples are notebooks. Atlas is what the same ideas look like when they have to survive a code review, a CI pipeline, and a corpus that doesn't fit in memory.

**Ingestion** — PDF/DOCX/TXT parsing, token-aware chunking with page-level provenance, async ingestion with `AFTER_COMMIT` semantics, configurable footer-noise stripping. Test corpus: 29 EU digital-regulation documents from EUR-Lex, 3,769 chunks.

**Retrieval** — Hybrid search over pgvector (HNSW, cosine) fusing vector and keyword results via RRF, with per-result `vectorRank` / `keywordRank` so ranking decisions stay auditable. Metadata filtering, an explicit citation contract, and a golden question set for regression checks.

**Chat** — Token-budgeted context assembly, prompt templates enforcing grounding, abstention, and citation rules, both synchronous and SSE streaming endpoints, per-request cost estimation, React UI with inline citation chips.

Java 21 (virtual threads) · Spring Boot 3.5 · Spring AI · PostgreSQL 16 + pgvector · Flyway · Testcontainers · Vite/React/TypeScript · 225 tests green in CI · 7 ADRs documenting the decisions

*In progress:* a Python evaluation harness (Typer CLI) for faithfulness, answer relevance, and context precision, so retrieval changes can be measured rather than argued about.

---

## Other work

**[ai_portfolio_analysis](https://github.com/ataulnasar/ai_portfolio_analysis)** — LLM-generated portfolio commentary behind a hexagonal architecture, with compliance guardrails, prompt versioning, and structured JSON logging. Spring Boot, React, PostgreSQL, OpenAI.

**[payment-platform](https://github.com/ataulnasar/payment-platform)** — Microservices payment system with OAuth2/Keycloak, idempotent transaction processing, Dockerized deployment.

---

## What I'm looking for

Forward Deployed / Applied AI Engineer roles where the work is putting LLM systems in front of real users with real data — and being accountable for whether they hold up.

[LinkedIn](https://www.linkedin.com/in/ataulnasar/) · Stockholm, Sweden

# Ata Ul Nasar

Senior Java engineer in Stockholm. I build production retrieval-augmented generation systems — the unglamorous parts: ingestion pipelines, hybrid retrieval, grounding and abstention rules, citation contracts, and the evaluation harnesses that tell you whether any of it actually works.

Roughly a decade of backend engineering, including post-trade and fintech systems at Nasdaq. Most of my recent AI work has been under NDA, so [**Atlas**](https://github.com/ataulnasar/atlas) exists to make it inspectable.
#AI, #GenAI, #ML, #LLM, #RAG, #Java, #Python, #Claude, #Chatgpt, #gpt-4o-mini.

---

## Atlas — open-source Java/Spring RAG platform

[github.com/ataulnasar/atlas](https://github.com/ataulnasar/atlas) · Apache 2.0

Most RAG examples are notebooks. Atlas is what the same ideas look like when they have to survive a code review, a CI pipeline, and a corpus that doesn't fit in memory.

**Measured, not vibes** — A 30-question golden dataset with page-level scoring, run by a Python harness (Typer CLI) against the live API: vector retrieval hits the right document **96%** of the time, the assistant abstained on **3/3** out-of-scope questions including deceptively adjacent traps, and a full eval run costs **~$0.11**. Baseline committed, regressions gate in CI, and the honest findings (hybrid currently trails pure vector — we know why) are public roadmap issues with the numbers they must beat.

**Ingestion** — PDF/DOCX/TXT parsing, token-aware chunking with page-level provenance, async pipeline with `AFTER_COMMIT` semantics, retryable failures, configurable footer-noise stripping. Corpus: 29 EU digital-regulation documents from EUR-Lex, 3,769 chunks.

**Retrieval** — Hybrid search over pgvector (HNSW, cosine) fusing vector and keyword via RRF, with per-result `vectorRank`/`keywordRank` so ranking decisions stay auditable. Metadata filtering and an explicit citation contract.

**Chat** — Token-budgeted context assembly, prompt templates enforcing grounding, citation, and abstention rules, sync + SSE streaming, per-request cost logging, React UI with clickable citation chips that resolve to the exact source passage.

**Operations** — Production compose profile, tested backup/restore runbook, and an `atlas-eval doctor` diagnostics CLI whose checklist is the project's own debugging history.

*Java 21 (virtual threads) · Spring Boot 3.5 · Spring AI · PostgreSQL 16 + pgvector · Flyway · Testcontainers · Vite/React/TypeScript · Python 3.12 · 300+ tests across three CI lanes · 7 ADRs · 10-issue measured roadmap*

---

## Other work

**[ai_portfolio_analysis](https://github.com/ataulnasar/ai_portfolio_analysis)** — LLM-generated portfolio commentary behind a hexagonal architecture, with compliance guardrails, prompt versioning, and structured JSON logging. Spring Boot, React, PostgreSQL, OpenAI.

**[payment-platform](https://github.com/ataulnasar/payment-platform)** — Microservices payment system with OAuth2/Keycloak, idempotent transaction processing, Dockerized deployment.

---

## What I'm looking for

Forward Deployed / Applied AI Engineer roles where the work is putting LLM systems in front of real users with real data — and being accountable for whether they hold up.

[LinkedIn](https://www.linkedin.com/in/ataulnasar/) · Stockholm, Sweden

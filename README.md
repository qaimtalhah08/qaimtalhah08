# Hi, I'm Talhah Qaim Khani

### Senior AI Engineer — Production-Grade Agentic AI · RAG · LLM Systems

I build Agentic AI that **survives contact with the real world** not demos, not prototypes, but systems that run in regulated, high-stakes environments where reliability and governance genuinely matter.

5+ years shipping Generative AI, Agentic AI, and RAG systems end-to-end from a vague stakeholder conversation to a live, monitored, enterprise-scale service on Kubernetes.

---

## What sets my systems apart

Most agentic projects work in a demo and break in production. I engineer for the failure modes everyone else ignores:

### Modular Orchestration
- Central **router** delegating to single-purpose agents (**hub-and-spoke** — agents can't call each other, so infinite delegation loops are *structurally impossible*)
- **DAG-based planning** with cycle detection before execution
- **Depth / step / cost / deadline counters** bounding every request
- Parallel execution of independent branches for lower latency

### Deterministic Guardrails — *AI proposes, deterministic engines dispose*
- **Pydantic** schema validation on every tool input and output (`extra="forbid"` catches drift)
- **OPA** policy gating — an LLM never triggers a privileged action without hard-coded constraints
- **AST static analysis** on generated code (catches `eval`, nested loops / O(n²), unbounded loops before execution)
- **Prompt-injection & PII-leakage** defenses with tenant/ACL filtering

### Production Reliability
- **Circuit breakers** (per-dependency, Redis-backed) to stop cascading failures
- **Classified retry** — 5xx with exponential backoff + jitter, never 4xx
- **Fallback chains** — secondary provider -> stale cache -> clean refusal
- **Idempotency** (`SET NX EX`) and **atomic rate limiting** (Redis `INCR` + Lua)
- **Per-request cost caps & quotas** to eliminate runaway loops

### Systematic Evaluation & Safe Rollout
- **Golden datasets** + deterministic assertions gating every release in CI
- **Meta-evaluated LLM-as-a-Judge** (rubric + reference-guided — a validated judge, not an automated vibe check)
- **Fault injection** to prove breaker and fallback paths actually fire
- **Canary / shadow deployments** with automatic rollback — regressions never reach production traffic

### Observability
- **LangSmith** tracing, **OpenTelemetry**, **Prometheus**, **Grafana**
- End-to-end `trace_id` propagation for full request lineage

---

## What I've shipped

**Patient-Facing Healthcare Booking & Support Platform**
MCP tools layer (re-authorised per call), per-role PII masking, row-level locking to prevent double-booking, circuit breakers with stale-cache fallback, atomic rate limiting.
-> **2,300+ users** · booking time **~10 min -> ~1 min** · latency **~15s -> ~2s**

**Agentic RAG Platform for UK Insurance Underwriters**
Scaled to **8 event-driven microservices** on AKS, secured with Entra ID and full audit trails, with a **human in the loop** on every decision — detecting red-line breaches and recommending Refer / Query / Accept.

**ML Demand-Forecasting & Analytics**
Forecasting models and automated Power BI / ETL pipelines giving ops and sales teams self-serve, data-driven decision support.

---

## Tech Stack

**Languages** · Python · SQL · TypeScript

**GenAI & Agentic AI** · LLMs (GPT-4o, Claude, Gemini, Llama 3) · Multi-Agent Systems · LangGraph · LangChain · MCP · RAG (hybrid + vector + re-ranking) · Prompt Engineering · Fine-tuning (LoRA / QLoRA / PEFT)

**Reliability & Guardrails** · Circuit Breakers · Retry / Fallback · Idempotency · Atomic Rate Limiting · OPA · Cost / Quota Governance · HITL Approvals

**Evaluation & LLMOps** · Golden Datasets · LLM-as-a-Judge · Fault Injection · RAGAS · DeepEval · Canary / Shadow · LangSmith · MLflow

**Vector & Retrieval** · FAISS · Azure AI Search · Pinecone · Qdrant · Weaviate · pgvector · hybrid search · re-ranking

**Cloud & Platform** · Azure (AKS, Azure OpenAI, AI Search) · AWS · GCP · Docker · Kubernetes · Terraform · CI/CD · Redis · Kafka · FastAPI

**Security & Observability** · OWASP LLM Top 10 · RBAC · JWT · Keycloak · Azure Key Vault · PII Masking · OpenTelemetry · Prometheus · Grafana · Jaeger

---

## Featured Projects

### Enterprise Agentic AI Assistant
Secure agentic platform with JWT-based RBAC, AI-driven issue analysis, **DAG-based tool orchestration with cycle detection**, circuit breakers, and end-to-end observability.
`FastAPI` · `LangGraph` · `MCP` · `PostgreSQL` · `Redis` · `Azure OpenAI` · `Keycloak` · `OpenTelemetry` · `Jaeger`

### Intelligent Document Intelligence Platform
RAG knowledge system — document ingestion, chunking, embedding, indexing, and retrieval with **hybrid search, re-ranking, and production guardrails**.
`Azure OpenAI` · `Azure AI Search` · `hybrid RAG` · `re-ranking`

### Customer Support AI Platform
AI-powered support workflows using LLMs, vector search, and agentic reasoning — automated issue analysis and next-action recommendations, cutting manual effort.
`LLMs` · `vector search` · `agentic reasoning`

---

## Engineering Principles

> **AI proposes, deterministic engines dispose.** An LLM never holds direct administrative privileges — every action passes through a deterministic gate.

> **Defence in depth.** Never trust one probabilistic layer — a 95% guardrail is always backed by a 100% deterministic policy and IAM.

> **Name the failure, then the fix.** Reliability isn't a tool list — it's knowing *how* things break and engineering the mechanism that stops it.

---

## Areas of Interest

Enterprise AI Architecture · Agentic & Multi-Agent Systems · AI Governance & Responsible AI · Cloud-Native AI Platforms · Production AI Delivery · Self-Evolving Systems

---

## Let's Connect

Open to **Senior / Applied AI Engineer** roles where I can own systems end-to-end in regulated or high-stakes domains.
Always happy to talk agentic AI, RAG architecture, or AI governance.

qaimtalhah@gmail.com · London, UK · [LinkedIn](https://www.linkedin.com/)

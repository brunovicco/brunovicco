<div align="center">

🇺🇸 **English** &nbsp;|&nbsp; 🇧🇷 [Português](README.pt-br.md)

# Bruno Freitas Vicco

### Generative AI Specialist & Architect | AI Governance for Regulated Financial Services

📍 São Paulo, Brazil &nbsp;|&nbsp; 🌍 Open to relocation

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## About me

I build production-grade generative AI systems and design the regulatory governance that makes them auditable inside banks and asset managers. It's an uncommon combination: most professionals are either pure LLMOps engineers or policy-only governance specialists; I do both, inside regulated Brazilian financial institutions.

---

## Career

22 years in the banking sector, 17 of them at **Caixa Econômica Federal** (corporate banking, treasury, regional and national superintendencies), followed by engineering roles at **BTG Pactual**, **Cast Group** (allocated to Banco do Brasil), **Itaú Unibanco**, and most recently **ASA SCFI**, where I was the first dedicated AI hire.

### At ASA:

**1. Banking Conversational Platform**

Refactored to hexagonal architecture with LangGraph orchestration, LGPD-oriented identity handling, and full distributed observability - engineered so compliance and auditability are structural properties, not add-ons.

<details>
<summary><b>Technical details</b></summary>
<br>

- Refactored to hexagonal architecture, with clear separation between domain, application, infrastructure, presentation, and composition root
- Model and conversation-flow orchestration with LangGraph, cognitive routing, and domain-specialized services
- Pseudonymized identity via HMAC-SHA256, session/thread isolation, and LGPD-oriented data protection
- Synchronous and asynchronous multichannel processing via FastAPI, workers, Redis, and Azure Service Bus, with idempotency and checkpoint management
- Distributed observability with OpenTelemetry and Langfuse, structured logging, request correlation, and automatic PII redaction
- Context-scoped authentication decoupled via a secure, Redis-backed TTL context, keeping sensitive tokens out of graphs and prompts entirely
- Interchangeable feature flags via environment variables or Flagsmith, enabling gradual rollout and operational kill switches
- Dependency injection and a ports/adapters pattern to ease testing, provider substitution, and independent evolution of integrations

</details>

**2. Investment Assistant (specialized subgraph)**

A compliance-first LangGraph subgraph combining DSPy-validated routing, self-correcting responses, and Redis-backed retrieval — architected so CVM/ANBIMA compliance and suitability are enforced structurally, before the model ever sees an option.

<details>
<summary><b>Technical details</b></summary>
<br>

- Custom semantic routing with negative-aware scoring - ambiguity detection across three rules (per-intent threshold, absolute floor, margin between candidates) and automatic cache invalidation via a SHA-256 fingerprint of the catalog
- LLM output contracts via DSPy: declarative Signature, Pydantic validation (`RouterOutput` with `Literal` types), and a fail-safe coercion layer absorbing format drift before any tool call
- Response self-correction via `dspy.Refine` with a compliance reward function - disclaimer, third person, no imperative mood, no portfolio opinions - regenerating until it hits the maximum score or exhausts the retry budget
- Compliance as an architectural property: a critique node validating CVM/ANBIMA via regex and injecting mandatory disclaimers before delivery, with suitability filtered on the product shelf *before* the model sees any option (CVM Res. 30)
- Specialized async `BaseTool` toolset, dynamically instantiated per turn: market shelf with semantic filters, per-asset and consolidated-by-class portfolio queries, on-demand product detail, and editorial content/house-view search
- PDF report generation via ReportLab from conversation state, delivering a consolidated artifact of the portfolio and analyses discussed
- Fat/slim modeling in Redis Stack: a lean projection indexed in RediSearch for search and ranking, full document via `JSON.GET` only for items that actually enter the context
- QueryBuilder with an explicit field taxonomy (TAG for exact match, TEXT with fuzzy Levenshtein and tokenization rules, NUMERIC for ranges), RediSearch special-character escaping, and mandatory row-level security by CPF built in code — never delegated to the model
- Anti-injection sanitization of input reaching RediSearch: blocking aggregation/command verbs, length limits, rejection of control characters, with a wildcard fail-safe
- Anaphora resolution via an entity stack in Redis - bounded LIFO, semantic dedup, short TTL - injecting resolved entities into the query before DSPy, without requiring the model to learn pronoun resolution
- Asynchronous portfolio pre-warming, removing load from the first-turn critical path and making latency independent of portfolio size
- Routing metrics in a Redis HASH (`HINCRBY` with rolling TTL), aggregating correctly across workers without coordination, with a degradation alarm based on fallback rate

</details>

**3. Enterprise AI Governance**
- Claude Code rollout for ~250 developers
- claude.ai Enterprise deployment for ~150 users
- Security hooks, MCP server allowlist, self-hosted (in-VPC) Gateway
- Internal AI Academy with certification tracks

**Regulatory scope:** BACEN/CMN, LGPD, CVM, ANBIMA — mapped internationally to EU AI Act, DORA, NIST AI RMF 1.0, and ISO/IEC 42001:2023.

---

## Featured Projects

### [`meridian`](https://github.com/brunovicco/meridian)
Reference architecture for an enterprise knowledge assistant: DSPy-validated semantic routing, ACL-aware RAG - access control enforced *inside* the vector search, never delegated to the model - structured queries compiled to RediSearch, and a fat/slim Redis data model. Runs zero-setup with deterministic fake providers, or with real DSPy + Groq. Clean Architecture, Twelve-Factor config, 52 tests.

### [`claude-code-crypto-lab`](https://github.com/brunovicco/claude-code-crypto-lab)
Hands-on Claude Code lab built around an educational crypto portfolio app. Demonstrates subagents, skills, deterministic hooks that block dangerous commands and out-of-scope prompts, a local MCP server, and CI/CD — fully bilingual (EN/PT-BR).

### [`claude-python-engineering-harness`](https://github.com/brunovicco/claude-python-engineering-harness)
Reusable Claude Code harness for Python engineering teams: a project bootstrap script, `CLAUDE.md`/`AGENTS.md` scaffolding, an opt-in MCP governance layer, and fail-closed security hooks - built on the principle that instruction is not control: policies that must hold live in hooks and CI gates, not just prompts.

### Personal projects
- **Barthô**: personal finance SaaS application
- **Open Finance BR MCP Server**: open-source MCP server for the Brazilian Open Finance ecosystem

---

## Stack

**GenAI/Orchestration**
![LangGraph](https://img.shields.io/badge/-LangGraph-1C3C3C?style=flat) ![DSPy](https://img.shields.io/badge/-DSPy-blue?style=flat) ![LlamaIndex](https://img.shields.io/badge/-LlamaIndex-black?style=flat) ![Mem0](https://img.shields.io/badge/-Mem0-orange?style=flat) ![LiteLLM](https://img.shields.io/badge/-LiteLLM_Proxy-purple?style=flat)

**Cloud/Infra**
![Azure](https://img.shields.io/badge/-Azure-0089D6?style=flat&logo=microsoftazure&logoColor=white) ![AWS](https://img.shields.io/badge/-AWS_Bedrock-232F3E?style=flat&logo=amazonaws&logoColor=white) ![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white) ![Pulumi](https://img.shields.io/badge/-Pulumi%2FOpenTofu-5C4EE5?style=flat)

**Data/Backend**
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat&logo=fastapi&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/-Redis_Stack-DC382D?style=flat&logo=redis&logoColor=white) ![Qdrant](https://img.shields.io/badge/-Qdrant%2Fpgvector-DC244C?style=flat) ![SQLAlchemy](https://img.shields.io/badge/-SQLAlchemy_2.0-red?style=flat)

**Frontend**
![React](https://img.shields.io/badge/-React%2FNext.js-black?style=flat&logo=react&logoColor=61DAFB) ![shadcn/ui](https://img.shields.io/badge/-shadcn%2Fui-black?style=flat)

**AI Security & Observability**
![Zscaler](https://img.shields.io/badge/-Zscaler-1E3A5F?style=flat) ![LLM Guard](https://img.shields.io/badge/-LLM_Guard-red?style=flat) ![Presidio](https://img.shields.io/badge/-Presidio-orange?style=flat) ![Langfuse](https://img.shields.io/badge/-Langfuse-black?style=flat) ![Entra ID](https://img.shields.io/badge/-Entra_ID-0078D4?style=flat&logo=microsoftazure&logoColor=white)

**Governance frameworks**
`NIST AI RMF 1.0` · `ISO/IEC 42001:2023` · `OWASP LLM Top 10 (2025)` · `OWASP Agentic Top 10 (2026)` · `NIST SP 800-53r5` · `CIS v8.1` · `MITRE ATLAS`

**Python code quality tooling**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white) `ruff` · `mypy --strict` · `import-linter` · `pytest` · `pydantic`

---

## 🌍 Open to

Actively looking for **Staff/Principal AI Engineer** or **AI Governance Architect** roles.

---

<div align="center">

📫 **bfvicco@gmail.com** &nbsp;|&nbsp; 💼 [linkedin.com/in/brunovicco](https://linkedin.com/in/brunovicco)

</div>

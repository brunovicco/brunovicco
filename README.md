<div align="center">

🇺🇸 **English**  |  🇧🇷 [Português](README.pt-br.md)

# Bruno Freitas Vicco

### Generative AI Specialist & Architect

### AI Engineering, Security, and Governance for Regulated Financial Services

📍 São Paulo, Brazil  |  🌍 Open to relocation

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat\&logo=linkedin\&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat\&logo=gmail\&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## About Me

I design and build production-grade generative AI systems for regulated financial institutions.

My work sits at the intersection of **AI engineering, software architecture, security, observability, and regulatory governance**. I build the technical platforms that allow organizations to adopt generative AI while maintaining control over identity, data access, model usage, auditability, resilience, and regulatory compliance.

This combination is still relatively uncommon: most professionals focus either on LLM application engineering or governance and policy. I work across both domains, translating regulatory and security requirements into enforceable architectural controls.

---

## Professional Background

I have more than **22 years of experience in the financial industry**, including 17 years at **Caixa Econômica Federal**, where I worked across corporate banking, treasury, regional operations, and national business units.

I later moved into software engineering and artificial intelligence roles at:

* **BTG Pactual**
* **Cast Group**, working with Banco do Brasil
* **Itaú Unibanco**
* **ASA SCFI**, where I became the company’s first professional dedicated exclusively to artificial intelligence

My experience ranges from banking operations and financial products to software engineering, generative AI architecture, AI governance, security, and enterprise adoption.

---

## Selected Work at ASA

### 1. Banking Conversational Platform

Refactored an enterprise banking conversational platform into a hexagonal, observable, and compliance-oriented architecture.

The platform was designed so that security, data protection, traceability, and auditability were structural properties of the system rather than controls added after implementation.

<details>
<summary><b>Technical details</b></summary>

<br>

* Refactored the platform using hexagonal architecture, with clear separation between domain, application, infrastructure, presentation, and composition-root layers
* Implemented model and conversation-flow orchestration with LangGraph, cognitive routing, and domain-specialized services
* Introduced pseudonymized identity using HMAC-SHA256, with session isolation, thread isolation, and LGPD-oriented data protection
* Designed synchronous and asynchronous multichannel processing with FastAPI, workers, Redis, and Azure Service Bus
* Implemented idempotency controls and persistent checkpoint management
* Added distributed observability with OpenTelemetry and Langfuse
* Standardized structured logging, request correlation, tracing, and automatic PII redaction
* Decoupled authentication from graphs and prompts through a secure Redis-backed context with controlled TTL
* Kept authentication tokens and sensitive credentials outside model context
* Implemented interchangeable feature flags using environment variables or Flagsmith
* Enabled gradual rollouts, controlled experimentation, and operational kill switches
* Applied dependency injection and ports-and-adapters patterns to simplify testing, provider substitution, and independent integration evolution

</details>

### 2. Investment Assistant

Designed a compliance-first LangGraph subgraph for investment-related interactions.

The solution combines DSPy-validated routing, Redis-backed retrieval, suitability controls, structured tool execution, and self-correcting responses. Regulatory requirements are enforced before the model receives product options or generates a response.

<details>
<summary><b>Technical details</b></summary>

<br>

* Built a custom semantic-routing mechanism with negative-aware scoring
* Implemented ambiguity detection using per-intent thresholds, an absolute confidence floor, and the score margin between candidates
* Added automatic routing-cache invalidation through a SHA-256 fingerprint of the intent catalog
* Defined LLM output contracts with DSPy declarative signatures and Pydantic validation
* Used strongly typed `RouterOutput` models with `Literal` types
* Added a fail-safe coercion layer to absorb output-format drift before any tool execution
* Implemented response self-correction with `dspy.Refine`
* Created a compliance reward function covering mandatory disclaimers, third-person language, avoidance of imperative phrasing, and prohibition of portfolio opinions
* Regenerated responses until they reached the required compliance score or exhausted the retry budget
* Implemented a critique node for CVM and ANBIMA requirements
* Injected mandatory disclaimers before response delivery
* Enforced suitability on the product shelf before products became visible to the model, following CVM Resolution 30
* Created a specialized asynchronous `BaseTool` toolset, instantiated dynamically for each interaction
* Supported market-shelf searches with semantic filters
* Supported individual-asset and consolidated portfolio queries
* Added on-demand product details and editorial or house-view retrieval
* Generated PDF reports from conversation state using ReportLab
* Applied a fat-and-slim Redis Stack data model
* Indexed lean projections in RediSearch for retrieval and ranking
* Retrieved full documents with `JSON.GET` only for records that entered the final model context
* Created a `QueryBuilder` with an explicit field taxonomy:

  * `TAG` for exact matches
  * `TEXT` for tokenized and fuzzy searches
  * `NUMERIC` for range filters
* Added special-character escaping for RediSearch
* Enforced mandatory row-level security by CPF in application code, never through model instructions
* Sanitized RediSearch input against prompt injection and command injection
* Blocked aggregation and command verbs
* Rejected control characters and enforced input-length limits
* Added a wildcard fail-safe for invalid search expressions
* Implemented anaphora resolution using a bounded entity stack in Redis
* Applied semantic deduplication and short TTLs to the entity stack
* Injected resolved entities into queries before DSPy processing
* Added asynchronous portfolio pre-warming to remove portfolio loading from the first-turn critical path
* Made initial response latency independent of portfolio size
* Stored routing metrics in Redis hashes using `HINCRBY` and rolling TTLs
* Aggregated metrics safely across multiple workers without centralized coordination
* Added degradation alarms based on fallback-rate thresholds

</details>

### 3. Enterprise AI Governance

Worked on the architecture, governance, and adoption of enterprise generative AI capabilities.

* Claude Code rollout for approximately **250 developers**
* Claude Enterprise deployment for approximately **150 business and technology users**
* Security hooks for deterministic policy enforcement
* MCP server governance and allowlisting
* Self-hosted AI gateway deployed inside a controlled VPC
* Model-access governance and provider-routing controls
* Standardized auditability and observability requirements
* Internal AI Academy with technical and governance certification tracks
* Architecture and security guidance for AI-assisted software development
* Training materials for developers, business users, architects, and governance teams

### Regulatory and Governance Scope

My work includes requirements and controls related to:

* BACEN and CMN regulations
* Brazilian General Data Protection Law, or LGPD
* CVM regulations
* ANBIMA guidelines
* European Union Artificial Intelligence Act
* Digital Operational Resilience Act, or DORA
* NIST AI Risk Management Framework
* ISO/IEC 42001
* NIST SP 800-53
* CIS Controls
* MITRE ATLAS
* OWASP guidance for LLM and agentic systems

---

## Featured Projects

### [`meridian`](https://github.com/brunovicco/meridian)

Reference architecture for an enterprise knowledge assistant with authorization-aware retrieval.

The project demonstrates:

* DSPy-validated semantic routing
* ACL-aware RAG
* Access-control enforcement inside vector search
* Structured-query compilation for RediSearch
* Fat-and-slim Redis data modeling
* Deterministic fake providers for local execution
* Optional integration with DSPy and Groq
* Clean Architecture
* Twelve-Factor configuration
* Automated test coverage

Access control is enforced during retrieval and is never delegated to the language model.

---

### [`claude-code-crypto-lab`](https://github.com/brunovicco/claude-code-crypto-lab)

Hands-on Claude Code laboratory built around an educational cryptocurrency portfolio application.

The project demonstrates:

* Claude Code subagents
* Reusable skills
* Deterministic hooks
* Dangerous-command blocking
* Out-of-scope prompt blocking
* Local MCP server integration
* Continuous integration and delivery
* Bilingual documentation in English and Brazilian Portuguese

---

### [`claude-python-engineering-harness`](https://github.com/brunovicco/claude-python-engineering-harness)

Reusable Claude Code harness for Python engineering teams.

The project includes:

* Project bootstrap automation
* `CLAUDE.md` scaffolding
* `AGENTS.md` scaffolding
* Reusable development standards
* Optional MCP governance
* Fail-closed security hooks
* CI-based policy enforcement
* Python quality and security tooling

The project follows a central principle:

> Instruction is not control. Policies that must always hold belong in deterministic hooks and CI gates, not only in prompts.

---

## Other Projects

### Barthô

Personal finance SaaS application focused on financial organization, account aggregation, transaction analysis, and intelligent financial insights.

### Open Finance BR MCP Server

Open-source Model Context Protocol server for the Brazilian Open Finance ecosystem, designed to expose standardized financial capabilities to AI agents through controlled and auditable interfaces.

---

## Technology Stack

### Generative AI and Orchestration

![LangGraph](https://img.shields.io/badge/-LangGraph-1C3C3C?style=flat)
![DSPy](https://img.shields.io/badge/-DSPy-blue?style=flat)
![LlamaIndex](https://img.shields.io/badge/-LlamaIndex-black?style=flat)
![Mem0](https://img.shields.io/badge/-Mem0-orange?style=flat)
![LiteLLM](https://img.shields.io/badge/-LiteLLM_Proxy-purple?style=flat)

* LangGraph
* DSPy
* LlamaIndex
* LangChain
* LiteLLM
* Mem0
* Model Context Protocol
* Agent-to-Agent architectures
* Semantic routing
* Retrieval-augmented generation
* Multi-agent orchestration
* Structured tool calling
* LLM evaluation and guardrails

### Cloud and Infrastructure

![Azure](https://img.shields.io/badge/-Azure-0089D6?style=flat\&logo=microsoftazure\&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS_Bedrock-232F3E?style=flat\&logo=amazonaws\&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat\&logo=kubernetes\&logoColor=white)

* Microsoft Azure
* Amazon Web Services
* Azure OpenAI
* Amazon Bedrock
* Kubernetes
* Docker
* API gateways
* VPC-based AI infrastructure

### Data and Backend

![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat\&logo=fastapi\&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat\&logo=postgresql\&logoColor=white)
![Redis](https://img.shields.io/badge/-Redis_Stack-DC382D?style=flat\&logo=redis\&logoColor=white)
![Qdrant](https://img.shields.io/badge/-Qdrant%2Fpgvector-DC244C?style=flat)
![SQLAlchemy](https://img.shields.io/badge/-SQLAlchemy_2.0-red?style=flat)

* Python
* FastAPI
* PostgreSQL
* Redis Stack
* RediSearch
* RedisJSON
* Qdrant
* pgvector
* SQLAlchemy 2.0
* Pydantic
* Asynchronous processing
* Event-driven architectures
* REST APIs

### Frontend

![React](https://img.shields.io/badge/-React%2FNext.js-black?style=flat\&logo=react\&logoColor=61DAFB)
![shadcn/ui](https://img.shields.io/badge/-shadcn%2Fui-black?style=flat)

* React
* Next.js
* TypeScript

### AI Security and Observability

![Zscaler](https://img.shields.io/badge/-Zscaler-1E3A5F?style=flat)
![LLM Guard](https://img.shields.io/badge/-LLM_Guard-red?style=flat)
![Langfuse](https://img.shields.io/badge/-Langfuse-black?style=flat)
![Entra ID](https://img.shields.io/badge/-Entra_ID-0078D4?style=flat\&logo=microsoftazure\&logoColor=white)

* OpenTelemetry
* Langfuse
* Datadog
* Structured logging
* Distributed tracing
* Request correlation
* PII detection and redaction
* LLM Guard
* Zscaler
* Microsoft Entra ID
* Prompt-injection protection
* Model-access governance
* Secrets management
* MCP server governance

### Governance Frameworks

`NIST AI RMF 1.0` · `ISO/IEC 42001:2023` · `OWASP LLM Top 10` · `OWASP Agentic Security Guidance` · `NIST SP 800-53r5` · `CIS Controls v8.1` · `MITRE ATLAS`

### Python Engineering

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat\&logo=python\&logoColor=white)

* `uv`
* `pyproject.toml`
* `ruff`
* `mypy --strict`
* `import-linter`
* `pytest`
* `pydantic`
* `bandit`
* `pip-audit`
* Clean Architecture
* Hexagonal Architecture
* SOLID principles
* Twelve-Factor applications
* Dependency injection
* Idempotent processing

---

## Areas of Interest

* Enterprise generative AI platforms
* AI architecture for financial institutions
* Agentic AI systems
* Multi-agent orchestration
* Model Context Protocol
* Agent-to-Agent communication
* Secure AI-assisted software development
* LLM application security
* Authorization-aware RAG
* AI observability and evaluation
* AI governance and regulatory compliance
* Enterprise adoption of coding agents
* Responsible AI engineering

---

## Open to Opportunities

I am open to opportunities such as:

* **Staff AI Engineer**
* **Principal AI Engineer**
* **Generative AI Architect**
* **AI Platform Architect**
* **AI Governance Architect**
* **AI Security Architect**

I am particularly interested in roles that combine engineering with architecture, security, governance, and enterprise-scale AI adoption.

---

<div align="center">

### Let’s Connect

📫 **[bfvicco@gmail.com](mailto:bfvicco@gmail.com)**
💼 [linkedin.com/in/brunovicco](https://linkedin.com/in/brunovicco)

</div>

<!-- Private profile analytics -->

<img src="https://u8views.com/api/v1/github/profiles/38844444/views/day-week-month-total-count.svg" width="1" height="1" alt="">

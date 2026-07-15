<div align="center">

🇺🇸 **English**  |  🇧🇷 [Português](README.pt-br.md)

# Bruno Freitas Vicco

### Generative AI Engineer & Architect

### AI Engineering, Security, and Governance for Regulated Environments

📍 São Paulo, Brazil  |  🌍 Open to international opportunities and relocation

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## About Me

I design and build production-grade generative AI systems for regulated industries, combining LLM engineering, agent architecture, security, observability, and governance.

Most professionals focus on either LLM application engineering or governance and policy. I work across both, translating regulatory and security requirements into enforceable architectural controls.

I have more than 22 years in the financial industry, including 17 at Caixa Econômica Federal - Brazil's largest public bank - in corporate banking, treasury, and risk, before moving into software engineering and AI. From there came BTG Pactual, Banco do Brasil (through Cast Group), Itaú Unibanco, and ASA SCFI, where I was the first professional hired exclusively for artificial intelligence.

> **Open to opportunities:** Staff/Principal AI Engineer, Generative AI Architect, AI Platform Architect, AI Governance Architect, and AI Security Architect - in Brazil or internationally. Particularly interested in roles that combine engineering with architecture, security, governance, and enterprise-scale AI adoption.

---

## Selected Impact

- Evolved a conversational and transactional banking assistant from PoC to production, with hexagonal architecture, end-to-end observability, and compliance as a structural property of the system.
- Designed an investment subgraph with semantic routing, validated output contracts (DSPy and Pydantic), compliance-driven response self-correction, and suitability enforced before products became visible to the model - with CVM/ANBIMA validations before delivery to the client.
- Built an enterprise AI-assisted engineering platform: Claude Code for ~250 developers and Claude Enterprise for ~150 users, with fail-closed security hooks, MCP governance, a gateway inside a controlled VPC, and an internal AI Academy with certification tracks.
- At Itaú Unibanco, reduced the average prompt of an investment assistant from 70,000 to 3,000 tokens, improving accuracy while lowering latency and inference cost.

Principles that run through all of this work: data-level security enforced in code (never delegated to the model), prompt injection defenses, immutable audit trails, and fail-closed defaults.

---

## Featured Projects

### [meridian](https://github.com/brunovicco/meridian)

Reference architecture for enterprise knowledge assistants: DSPy-validated semantic routing, ACL-aware RAG with access control enforced inside the search, structured queries for RediSearch, fat/slim Redis data modeling, and grounded answers with citations. Clean Architecture, Twelve-Factor, and automated test coverage.

Access control is enforced during retrieval and is never delegated to the language model.

### [claude-python-engineering-harness](https://github.com/brunovicco/claude-python-engineering-harness)

Reusable Claude Code harness for Python teams: project bootstrap, CLAUDE.md and AGENTS.md scaffolds, fail-closed security hooks, optional MCP governance, and CI-based policy enforcement.

> Instruction is not control. Policies that must always hold belong in deterministic hooks and CI gates, not only in prompts.

### [claude-code-crypto-lab](https://github.com/brunovicco/claude-code-crypto-lab)

Hands-on Claude Code lab for safe agentic development: subagents, skills, deterministic hooks, dangerous-command blocking, local MCP server integration, and CI/CD. Bilingual documentation (EN/PT-BR).

### [openfinance-br-mcp](https://github.com/brunovicco/openfinance-br-mcp)

Open-source MCP server for the Brazilian Open Finance ecosystem, exposing standardized financial capabilities to AI agents through controlled and auditable interfaces. Under active development.

---

## Other Projects

### Barthô

Personal finance SaaS application focused on financial organization, account aggregation, transaction analysis, and intelligent insights.

---

## Technology Stack

### Generative AI and Orchestration

![LangGraph](https://img.shields.io/badge/-LangGraph-1C3C3C?style=flat)
![DSPy](https://img.shields.io/badge/-DSPy-blue?style=flat)
![LlamaIndex](https://img.shields.io/badge/-LlamaIndex-black?style=flat)
![Mem0](https://img.shields.io/badge/-Mem0-orange?style=flat)
![LiteLLM](https://img.shields.io/badge/-LiteLLM_Proxy-purple?style=flat)

LangGraph · DSPy · LangChain · LlamaIndex · LiteLLM · Mem0 · Model Context Protocol · Agent-to-Agent architectures · semantic routing · RAG · multi-agent orchestration · structured tool calling · LLM evaluation and guardrails

### Cloud and Infrastructure

![Azure](https://img.shields.io/badge/-Azure-0089D6?style=flat&logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS_Bedrock-232F3E?style=flat&logo=amazonaws&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)

Microsoft Azure · Azure OpenAI · AWS · Amazon Bedrock · Kubernetes · Docker · API gateways · VPC-based AI infrastructure

### Data and Backend

![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/-Redis_Stack-DC382D?style=flat&logo=redis&logoColor=white)
![Qdrant](https://img.shields.io/badge/-Qdrant%2Fpgvector-DC244C?style=flat)
![SQLAlchemy](https://img.shields.io/badge/-SQLAlchemy_2.0-red?style=flat)

Python · FastAPI · PostgreSQL · Redis Stack (RediSearch/RedisJSON) · Qdrant · pgvector · SQLAlchemy 2.0 · Pydantic · asynchronous processing · event-driven architectures · REST APIs

### Frontend

![React](https://img.shields.io/badge/-React%2FNext.js-black?style=flat&logo=react&logoColor=61DAFB)

React · Next.js · TypeScript

### AI Security and Observability

![Zscaler](https://img.shields.io/badge/-Zscaler-1E3A5F?style=flat)
![LLM Guard](https://img.shields.io/badge/-LLM_Guard-red?style=flat)
![Langfuse](https://img.shields.io/badge/-Langfuse-black?style=flat)
![Entra ID](https://img.shields.io/badge/-Entra_ID-0078D4?style=flat&logo=microsoftazure&logoColor=white)

Langfuse · OpenTelemetry · Datadog · LLM Guard · Zscaler · Microsoft Entra ID · PII detection and redaction · prompt injection protection · model-access and MCP server governance

### Python Engineering

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)

`uv` · `ruff` · `mypy --strict` · `import-linter` · `pytest` · `bandit` · `pip-audit` · Clean Architecture · Hexagonal Architecture · SOLID · Twelve-Factor · dependency injection · idempotent processing

---

## Regulatory and Governance Scope

I work with requirements and controls across: BACEN/CMN · LGPD (Brazilian data protection law) · CVM · ANBIMA · EU AI Act · DORA · NIST AI RMF 1.0 · ISO/IEC 42001 · NIST SP 800-53 · CIS Controls · MITRE ATLAS · OWASP (LLM and agentic systems)

---

<div align="center">

### Let's Connect

📫 **[bfvicco@gmail.com](mailto:bfvicco@gmail.com)**
💼 [linkedin.com/in/brunovicco](https://linkedin.com/in/brunovicco)

</div>

<!-- Private profile analytics -->

<img src="https://u8views.com/api/v1/github/profiles/38844444/views/day-week-month-total-count.svg" width="1" height="1" alt="">

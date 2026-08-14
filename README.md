<div align="center">

🇺🇸 **English** &nbsp;|&nbsp; 🇧🇷 [Português](README.pt-BR.md)

![Bruno Freitas Vicco — AI Engineering](https://raw.githubusercontent.com/brunovicco/brunovicco/main/assets/social/github-profile-cover.png)

# Bruno Freitas Vicco

### AI Engineer

**AI Platforms · Generative & Agentic AI · RAG · MCP/A2A · LLMOps · Security & Governance**

📍 São Paulo, Brazil &nbsp;|&nbsp; 🌍 Open to international opportunities and relocation

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat\&logo=linkedin\&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat\&logo=gmail\&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## About

I am an AI Engineer focused on building and evolving AI platforms and production systems, especially where the problem requires more than integrating a model.

My work is hands-on and spans engineering and architecture. I enjoy investigating ambiguous problems, exploring alternatives, defining the right technical boundaries, and turning business needs into reliable systems involving LLMs, RAG, agents, MCP/A2A, evaluation, observability, security, and governance.

A recurring theme in my work is translating operational, security, and regulatory requirements into engineering mechanisms: explicit contracts, deterministic controls, authorization boundaries, evaluation pipelines, observability, auditability, and human-controlled decisions for high-impact actions.

I bring more than 22 years of experience in financial services, with experience at Caixa, BTG Pactual, Banco do Brasil, Itaú Unibanco, and ASA SCFI. This background helps me work across technology, business, risk, and regulation without treating them as isolated concerns.

---

## Selected Impact

* Built production AI systems for regulated financial institutions, including conversational and transactional assistants, RAG pipelines, agent workflows, observability, and security controls.
* Led enterprise AI adoption for approximately **400 users**, including Claude Code for around **250 developers** and Claude Enterprise for approximately **150 business users**.
* Reduced the average context of an investment assistant from approximately **70,000 to 3,000 tokens (~95%)** through conditional knowledge retrieval and injection, preserving response quality while reducing latency, token usage, and inference cost.
* Designed semantic routing with intent-specific thresholds, positive and negative examples, and ambiguity handling, reaching approximately **94.7% accuracy** on the validation dataset.
* Established engineering and governance mechanisms for enterprise AI adoption, including development standards, MCP allowlists, risk assessment, auditability, incident response, and controlled rollout.
* Translated governance requirements into executable software through deterministic controls, segregation of duties, evidence-bound decisions, runtime enforcement, and tamper-evident audit history.

---

## Start Here

| If you want to explore...                              | Start with                                                                                                                                                    |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Auditable multi-agent systems and domain orchestration | [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk)                                                                          |
| RAG evaluation and retrieval engineering               | [**RAGForge**](https://github.com/brunovicco/ragforge)                                                                                                        |
| Distributed observability across agents and tools      | [**a2a-otel-kit**](https://github.com/brunovicco/a2a-otel-kit)                                                                                                |
| Secure enterprise MCP with OAuth 2.1 / OIDC            | [**MCP Server Auth**](https://github.com/brunovicco/mcp-server-auth-template) + [**MCP Client Auth**](https://github.com/brunovicco/mcp-client-auth-template) |
| Executable AI governance and runtime evidence          | [**Verifiable AI Governance**](https://github.com/brunovicco/verifiable-ai-governance)                                                                        |
| Deterministic model routing and policy enforcement     | [**Policy Model Router**](https://github.com/brunovicco/policy-model-router)                                                                                  |

[Explore the complete portfolio architecture and project relationships](./PORTFOLIO_ARCHITECTURE.md)

---

## AI Engineering Ecosystem

The repositories form an engineering ecosystem rather than a collection of isolated demos.

They explore different parts of the same problem: **how to build AI systems that remain reliable, observable, secure, and governable as they move from experimentation into production.**

The ecosystem currently covers four complementary layers:

* **Domain AI systems:** RAG, enterprise knowledge, Open Finance tools, and auditable multi-agent workflows.
* **Runtime platform services:** model routing, MCP/A2A integration, distributed observability, identity, authorization, and privacy-safe telemetry.
* **AI-assisted engineering:** deterministic execution, explicit contracts, architecture constraints, reproducible evidence, and human-controlled promotion.
* **Governance and assurance:** policy, risk, approvals, runtime authorization, enforcement, incidents, evidence, and auditability.

The common engineering principle is to use LLMs where generative behavior adds value while keeping critical decisions, authorization, policy enforcement, and security boundaries explicit and independently verifiable.

---

## Featured Projects

| Project                                                                                    | What it demonstrates                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk)       | Auditable multi-agent credit workflow combining deterministic credit policy, MCP/A2A boundaries, model routing, synthetic data, and privacy-safe runtime telemetry.                                                                                                                                         |
| [**RAGForge**](https://github.com/brunovicco/ragforge)                                     | Reproducible benchmarking and evaluation of retrieval strategies over Brazilian financial and regulatory documents.                                                                                                                                                                                         |
| [**a2a-otel-kit**](https://github.com/brunovicco/a2a-otel-kit)                             | Vendor-neutral OpenTelemetry tracing across A2A agents and MCP services with W3C Trace Context, metadata-only telemetry, and executable distributed-trace proof.                                                                                                                                            |
| [**MCP OAuth Security Reference**](https://github.com/brunovicco/mcp-server-auth-template) | Paired [server](https://github.com/brunovicco/mcp-server-auth-template) and [client](https://github.com/brunovicco/mcp-client-auth-template) reference for OAuth 2.1/OIDC, Entra ID, exact resource binding, progressive authorization, stateless MCP, privacy-safe telemetry, and executable E2E evidence. |
| [**Verifiable AI Governance**](https://github.com/brunovicco/verifiable-ai-governance)     | Production-oriented reference platform connecting policy, approvals, signed runtime authorization, enforcement, assurance, incident response, and independently verifiable evidence. [Public demo](https://vaigov-app.duckdns.org).                                                                         |
| [**Policy Model Router**](https://github.com/brunovicco/policy-model-router)               | Fail-closed model routing and runtime policy enforcement with explainable decisions, governed authorization, violation evidence, and kill-switch support.                                                                                                                                                   |

### Engineering foundations

[**Alicerce**](https://github.com/brunovicco/alicerce) ·
[**engineering-loop-schemas**](https://github.com/brunovicco/engineering-loop-schemas) ·
[**Claude Python Engineering Harness**](https://github.com/brunovicco/claude-python-engineering-harness) ·
[**Codex Python Engineering Harness**](https://github.com/brunovicco/codex-python-engineering-harness)

### Additional domain references

[**Open Finance BR MCP**](https://github.com/brunovicco/openfinance-br-mcp) ·
[**Meridian**](https://github.com/brunovicco/meridian)

---

## Engineering Principles

* Choose the architecture based on the problem, not on the popularity of a specific AI pattern.
* Critical business decisions remain deterministic and auditable.
* Authentication and authorization are enforced in code, never delegated to a language model.
* Agents, MCP servers, model providers, retrieved data, and telemetry pipelines are treated as explicit trust boundaries.
* Structured outputs, typed contracts, bounded retries, and fail-closed validation constrain generative behavior.
* Retrieval and generation are evaluated independently where possible.
* Evidence must be independently verifiable; model self-reports are not proof.
* Telemetry is minimized by design; prompts, model responses, credentials, and business payloads are not observability defaults.
* High-impact actions such as promotion, deployment, runtime overrides, and sensitive tool execution remain under explicit human authority.

---

## Core Expertise

**AI Platforms & Architecture**
Enterprise AI platforms · distributed AI systems · API and service design · model routing · MCP/A2A · identity and authorization · platform capabilities · developer enablement

**Generative & Agentic AI**
LLMs · RAG · agentic systems · multi-agent architectures · LangGraph · semantic routing · structured outputs · tool calling · evaluation · guardrails

**LLMOps & Observability**
OpenTelemetry · W3C Trace Context · OTLP · Datadog · Langfuse · distributed tracing · structured logging · evaluation pipelines · regression testing · latency/token/cost observability

**AI Security & Governance**
OAuth 2.1 · OIDC · least privilege · fail-closed authorization · prompt-injection boundaries · policy enforcement · runtime authorization · assurance · auditability · incident response · human-in-the-loop

<details>
<summary><strong>Technology stack</strong></summary>

<br>

**Languages and backend:** Python, FastAPI, Pydantic, TypeScript, Node.js, REST APIs, asynchronous and event-driven systems

**AI frameworks and platforms:** LangGraph, DSPy, LangChain, LlamaIndex, LiteLLM, Azure OpenAI, Azure AI Foundry, Amazon Bedrock, Anthropic Claude, Gemini

**Data and retrieval:** Redis Stack, RediSearch, RedisJSON, PostgreSQL, pgvector, OpenSearch, vector search, hybrid retrieval

**Cloud and platform engineering:** Azure, AWS, GCP, Docker, Kubernetes, OpenShift, Azure DevOps, GitHub Actions, GitLab CI, Argo CD

**Python engineering:** uv, Ruff, Mypy/Pyright strict, Pytest, Bandit, pip-audit, architecture tests, CI quality gates

</details>

<details>
<summary><strong>Financial services, regulatory, and governance background</strong></summary>

<br>

Experience translating requirements and controls from BACEN, CMN, LGPD, CVM, ANBIMA, DORA, NIST AI RMF, ISO/IEC 42001, NIST SP 800-53, CIS Controls, MITRE ATLAS, and OWASP guidance into technical and operational mechanisms for LLM and agentic systems.

Professional background includes corporate banking, credit, risk, treasury, financial operations, software engineering, production AI, enterprise enablement, and AI governance.

</details>

<details>
<summary><strong>Certifications</strong></summary>

<br>

* AWS Certified AI Practitioner
* AWS Certified Cloud Practitioner
* Microsoft Certified: Azure Fundamentals
* CPA-20 ANBIMA

</details>

---

<div align="center">

### Let's Connect

[LinkedIn](https://linkedin.com/in/brunovicco) · [Email](mailto:bfvicco@gmail.com)

</div>

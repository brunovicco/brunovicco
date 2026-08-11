<div align="center">

🇺🇸 **English** &nbsp;|&nbsp; 🇧🇷 [Português](README.pt-BR.md)

![Bruno Freitas Vicco — AI Engineering](https://raw.githubusercontent.com/brunovicco/brunovicco/main/assets/social/github-profile-cover.png)

# Bruno Freitas Vicco

### Senior Generative AI Engineer

**AI Platforms · RAG & Agents · MCP/A2A · AI Security · LLMOps · Verifiable AI Governance**

📍 São Paulo, Brazil &nbsp;|&nbsp; 🌍 Open to international opportunities and relocation

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## About

Senior Generative AI Engineer focused on enterprise AI platforms and the trust infrastructure required to operate AI systems safely: retrieval, agents, identity, authorization, observability, runtime policy enforcement, evaluation, and verifiable governance.

My work combines software architecture, LLM engineering, security, LLMOps, and governance for production systems in regulated environments.

I bring more than 22 years of experience across financial services and technology, including Caixa, BTG Pactual, Banco do Brasil, Itaú Unibanco, and ASA SCFI.

---

## Start Here

| If you want to explore... | Start with |
| --- | --- |
| AI governance, assurance, and runtime evidence | [**Verifiable AI Governance**](https://github.com/brunovicco/verifiable-ai-governance) |
| MCP security with OAuth 2.1 / OIDC | [**MCP Server Auth**](https://github.com/brunovicco/mcp-server-auth-template) + [**MCP Client Auth**](https://github.com/brunovicco/mcp-client-auth-template) |
| Distributed observability across agents and tools | [**a2a-otel-kit**](https://github.com/brunovicco/a2a-otel-kit) |
| Deterministic model policy enforcement | [**Policy Model Router**](https://github.com/brunovicco/policy-model-router) |
| RAG evaluation over regulatory documents | [**RAGForge**](https://github.com/brunovicco/ragforge) |
| Auditable multi-agent architecture | [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk) |

[Explore the complete portfolio architecture and project relationships](./PORTFOLIO_ARCHITECTURE.md)

---

## AI Engineering Ecosystem

The repositories form an engineering ecosystem rather than a collection of isolated demos.

The current architecture explores four complementary layers:

- **Governance and assurance:** policy, risk, approvals, evidence, runtime assurance, incident response, and auditability.
- **Runtime trust services:** model-policy enforcement, OAuth/OIDC for remote MCP, A2A/MCP trace continuity, and privacy-safe telemetry.
- **Domain AI systems:** RAG, enterprise knowledge, Open Finance tools, and auditable multi-agent credit analysis.
- **AI-assisted engineering controls:** deterministic execution, canonical evidence, architecture constraints, and human-controlled promotion.

The common design goal is to keep high-impact decisions and security boundaries outside model reasoning while still using LLMs where generative behavior adds value.

---

## Selected Impact

- Built and governed production AI systems for regulated financial institutions, including conversational assistants, RAG pipelines, agent workflows, observability, and compliance controls.
- Led enterprise AI adoption for approximately **400 users**, including Claude Code for around **250 developers** and Claude Enterprise for approximately **150 business users**.
- Reduced the average context of an investment assistant from approximately **70,000 to 3,000 tokens** through conditional knowledge injection, improving accuracy while reducing latency and inference cost.
- Established an AI governance function covering usage policies, approval processes, MCP allowlists, risk assessment, auditability, incident response, and phased enterprise adoption.
- Translated governance requirements into a verifiable implementation with deterministic controls, segregation of duties, evidence-bound decisions, runtime enforcement, and tamper-evident audit history.

---

## Featured Projects

| Project | What it demonstrates |
| --- | --- |
| [**Verifiable AI Governance**](https://github.com/brunovicco/verifiable-ai-governance) | Evidence-driven AI governance from deterministic risk and independent approvals through signed runtime authorization, enforcement, assurance, incident response, and verifiable release evidence. [Public demo](https://vaigov-app.duckdns.org). |
| [**MCP OAuth Security Reference**](https://github.com/brunovicco/mcp-server-auth-template) | Paired [server](https://github.com/brunovicco/mcp-server-auth-template) and [client](https://github.com/brunovicco/mcp-client-auth-template) reference for OAuth 2.1/OIDC, Entra ID, exact resource binding, progressive authorization, stateless MCP, privacy-safe telemetry, and executable E2E evidence. |
| [**a2a-otel-kit**](https://github.com/brunovicco/a2a-otel-kit) | Vendor-neutral OpenTelemetry tracing across A2A agents and MCP services with W3C Trace Context, metadata-only telemetry, and executable distributed-trace proof. |
| [**Policy Model Router**](https://github.com/brunovicco/policy-model-router) | Fail-closed runtime policy enforcement with deterministic model routing, explainable decisions, governed runtime authorization, violation evidence, and kill-switch enforcement. |
| [**RAGForge**](https://github.com/brunovicco/ragforge) | Reproducible benchmarking and evaluation of retrieval strategies over Brazilian financial and regulatory documents. |
| [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk) | Auditable multi-agent credit workflow combining deterministic credit policy, MCP/A2A boundaries, model routing, synthetic data, and privacy-safe governed runtime telemetry. |

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

- Critical business decisions remain deterministic and auditable.
- Authentication and authorization are enforced in code, never delegated to a language model.
- Agents, MCP servers, model providers, retrieved data, and telemetry pipelines are treated as trust boundaries.
- Structured outputs, explicit contracts, bounded retries, and fail-closed validation constrain generative behavior.
- Evidence must be independently verifiable; model self-reports are not proof.
- Approvals remain bound to the exact reviewed scope, and material changes trigger reassessment.
- Telemetry is minimized by design; prompts, model responses, credentials, and business payloads are not observability defaults.
- Promotion, deployment, runtime overrides, and other high-impact actions remain under explicit human authority.

---

## Core Expertise

**Generative AI Engineering**  
RAG · agentic systems · multi-agent architectures · semantic and model routing · structured outputs · tool calling · LLM evaluation · guardrails

**Agent and MCP Security**
MCP · A2A · OAuth 2.1 · OIDC · Microsoft Entra ID · PKCE · resource/audience binding · least privilege · fail-closed authorization · prompt-injection boundaries

**AI Platforms and Governance**
Enterprise AI platforms · policy enforcement · runtime authorization · model and agent assurance · evidence · auditability · incident response · human-in-the-loop

**LLMOps and Observability**
OpenTelemetry · W3C Trace Context · OTLP · Datadog · Langfuse · distributed tracing · structured logging · latency percentiles · evaluation pipelines · regression testing · token/cost observability

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

Experience translating requirements and controls from BACEN, CMN, LGPD, CVM, ANBIMA, DORA, NIST AI RMF, ISO/IEC 42001, NIST SP 800-53, CIS Controls, MITRE ATLAS, and OWASP guidance for LLM and agentic systems.

Professional background includes corporate banking, credit, risk, treasury, financial operations, software engineering, production AI, enterprise enablement, and AI governance.

</details>

<details>
<summary><strong>Certifications</strong></summary>

<br>

- AWS Certified AI Practitioner
- AWS Certified Cloud Practitioner
- Microsoft Certified: Azure Fundamentals
- CPA-20 ANBIMA

</details>

---

<div align="center">

### Let's Connect

[LinkedIn](https://linkedin.com/in/brunovicco) · [Email](mailto:bfvicco@gmail.com)

</div>

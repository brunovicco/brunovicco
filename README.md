<div align="center">

🇺🇸 **English** &nbsp;|&nbsp; 🇧🇷 [Português](README.pt-br.md)

# Bruno Freitas Vicco

### Senior Generative AI Engineer | Enterprise AI Enablement, AI Platforms & Governance

### Production AI, Agentic Systems, Security, and Observability for Regulated Environments

📍 São Paulo, Brazil &nbsp;|&nbsp; 🌍 Open to international opportunities and relocation

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## About Me

I am a hands-on Generative AI Engineer focused on building, scaling, and governing production AI systems in regulated environments.

My work combines LLM engineering, AI architecture, enterprise AI enablement, security, observability, and governance. I translate regulatory and security requirements into enforceable controls implemented in application code, infrastructure, CI/CD pipelines, and operational processes.

I have more than 22 years of experience in financial services, including 17 years at Caixa Econômica Federal in corporate banking, treasury, credit, risk, and financial operations. I later moved into software engineering and artificial intelligence, working on initiatives for BTG Pactual, Banco do Brasil through Cast Group, Itaú Unibanco, and ASA SCFI.

At ASA, I was the first professional dedicated exclusively to Generative AI. My responsibilities covered production assistants, enterprise AI platforms, developer productivity, corporate adoption, security, and the establishment of the company's AI governance function.

> **Open to opportunities:** Senior, Staff, or Principal Generative AI Engineer; AI Platform Engineer; AI Enablement Lead; Generative AI Architect; AI Governance Architect; and AI Security Architect.
>
> Particularly interested in roles that combine hands-on engineering, architecture, enterprise adoption, security, and governance.

---

## Selected Impact

- Led the evolution of a conversational and transactional banking assistant from proof of concept to production, with a unified runtime, Redis checkpointing, session isolation, long-term memory, observability, and compliance controls embedded in the architecture.

- Designed a specialized investment-agent subgraph with negative-aware semantic routing, ambiguity detection, DSPy and Pydantic output contracts, compliance-driven self-correction, and suitability validation before products were exposed to the language model.

- Led enterprise AI enablement for approximately 400 users, including Claude Code for around 250 software developers and Claude Enterprise for around 150 business and administrative users.

- Built an AI-assisted engineering platform with Spec-Driven Development, multi-stack scaffolds, internal plugins, governed MCP integrations, security hooks, policy enforcement, and CI/CD quality gates.

- Established an AI governance function from scratch, covering usage policies, approval processes, MCP allowlists, risk assessments, incident response, auditability, business continuity, and phased adoption.

- At Itaú Unibanco, reduced the average context of an investment assistant from approximately 70,000 to 3,000 tokens through conditional knowledge injection, improving accuracy while reducing latency and inference cost.

- Introduced distributed tracing with Datadog across an agent workflow, replacing log-only monitoring with end-to-end visibility into latency, model calls, tool execution, and runtime behavior.

### Engineering Principles

- Security and authorization enforced in code, never delegated to the language model
- Fail-closed controls for sensitive operations
- Structured outputs and deterministic validation
- Least-privilege access to tools and data
- Observable and auditable agent execution
- Human approval for high-impact actions
- Governance implemented as architecture, not documentation alone

---

## Featured Projects

### [openfinance-br-mcp](https://github.com/brunovicco/openfinance-br-mcp)

Open-source Model Context Protocol server for the Brazilian Open Finance ecosystem.

The project exposes accounts, balances, transactions, credit cards, PIX, investments, consent management, and payment initiation capabilities through controlled interfaces designed for AI agents.

Key areas include:

- 12 MCP tools covering Open Finance Brasil phases 2, 3, and 4
- FAPI-BR security patterns
- `private_key_jwt`, PAR, JAR, PKCE, and mTLS
- Consent and authorization lifecycle
- Pydantic v2 input validation
- Adapters for multiple financial institutions
- Auditable and permission-aware tool execution

> Real financial integrations are documented as experimental and are not certified for production use.

---

### [meridian](https://github.com/brunovicco/meridian)

Reference architecture for enterprise knowledge assistants with authorization-aware retrieval.

The project demonstrates:

- ACL-filtered RAG
- Row-level security enforced during retrieval
- DSPy-validated semantic routing
- Structured RediSearch queries
- Redis fat and slim data models
- Grounded answers with citations
- Clean Architecture and Twelve-Factor principles
- Automated testing for authorization and retrieval behavior

> Access control is enforced before context reaches the language model.

---

### [claude-python-engineering-harness](https://github.com/brunovicco/claude-python-engineering-harness)

Reusable Claude Code engineering harness for governed Python development.

It includes:

- Project and agent instruction scaffolds
- `CLAUDE.md` and `AGENTS.md` templates
- Spec-Driven Development workflows
- Fail-closed security hooks
- Dangerous-command protection
- Optional MCP governance
- Structured logging
- CI-based policy enforcement
- Python quality and security gates

> Instruction is not control. Requirements that must always hold belong in deterministic hooks, application code, and CI gates.

---

### [codex-python-engineering-harness](https://github.com/brunovicco/codex-python-engineering-harness)

Reusable engineering harness for structured and governed Python development with coding agents.

The project focuses on:

- Agent operating instructions
- Specification-driven workflows
- Security and quality automation
- Reproducible project scaffolding
- Deterministic policy enforcement
- Code review and CI integration

---

### [claude-code-crypto-lab](https://github.com/brunovicco/claude-code-crypto-lab)

Hands-on laboratory for safe agentic software development with Claude Code.

Topics include:

- Subagents and reusable skills
- Deterministic hooks
- Dangerous-command blocking
- Local MCP server integration
- Tool permission boundaries
- CI/CD integration
- Bilingual documentation in English and Portuguese

---

## Core Expertise

### Generative AI Engineering

LLM application engineering · RAG · agentic systems · multi-agent architectures · semantic routing · model routing · structured outputs · tool and function calling · conversation memory · LLM evaluation · prompt security · guardrails

### Enterprise AI Enablement

AI platforms · developer productivity · AI-assisted software engineering · enterprise rollout · internal tooling · enablement programs · adoption governance · technical training · maturity assessment · AI operating models

### AI Architecture

LangGraph · DSPy · LangChain · LlamaIndex · Model Context Protocol · Agent-to-Agent patterns · Clean Architecture · Hexagonal Architecture · SOLID · Twelve-Factor · event-driven systems

### AI Governance and Security

AI governance · Responsible AI · AI risk management · prompt injection protection · session isolation · row-level security · MCP governance · least privilege · human-in-the-loop controls · audit trails · incident response

### LLMOps and Observability

Datadog · Langfuse · OpenTelemetry · structured logging · distributed tracing · latency percentiles · evaluation pipelines · regression testing · model monitoring · cost and token observability

---

## Technology Stack

### Languages and Backend

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)

Python · FastAPI · Pydantic · JavaScript · TypeScript · Node.js · NestJS · REST APIs · asynchronous processing · event-driven architectures

### AI Frameworks and Platforms

![LangGraph](https://img.shields.io/badge/-LangGraph-1C3C3C?style=flat)
![DSPy](https://img.shields.io/badge/-DSPy-blue?style=flat)
![Azure OpenAI](https://img.shields.io/badge/-Azure_OpenAI-0089D6?style=flat&logo=microsoftazure&logoColor=white)
![AWS Bedrock](https://img.shields.io/badge/-AWS_Bedrock-232F3E?style=flat&logo=amazonaws&logoColor=white)

LangGraph · DSPy · LangChain · LlamaIndex · LiteLLM · Mem0 · Azure OpenAI · Azure AI Foundry · Amazon Bedrock · Claude · Gemini · Llama

### Data and Retrieval

![Redis](https://img.shields.io/badge/-Redis_Stack-DC382D?style=flat&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)

Redis Stack · RediSearch · RedisJSON · PostgreSQL · pgvector · Qdrant · MongoDB · SQL · SQLAlchemy · vector search · hybrid retrieval

### Cloud, DevOps, and Platform Engineering

![Azure](https://img.shields.io/badge/-Azure-0089D6?style=flat&logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)

Azure · AWS · GCP · Docker · Kubernetes · OpenShift · Azure DevOps · GitHub Actions · GitLab CI · Argo CD · Jenkins · API gateways · VPC-based infrastructure

### Python Engineering

`uv` · `ruff` · `mypy --strict` · `pytest` · `import-linter` · `bandit` · `pip-audit` · `Semgrep` · dependency injection · idempotent processing · structured logging

---

## Regulatory and Governance Scope

Experience translating requirements and controls from:

BACEN and CMN · LGPD · CVM · ANBIMA · EU AI Act · DORA · NIST AI RMF 1.0 · ISO/IEC 42001 · NIST SP 800-53 · CIS Controls · MITRE ATLAS · OWASP Top 10 for LLM Applications · OWASP guidance for agentic systems

---

## Certifications

- AWS Certified AI Practitioner
- AWS Certified Cloud Practitioner
- Microsoft Certified: Azure Fundamentals
- CPA-20 ANBIMA

---

<div align="center">

### Let's Connect

📫 **[bfvicco@gmail.com](mailto:bfvicco@gmail.com)**  
💼 **[linkedin.com/in/brunovicco](https://linkedin.com/in/brunovicco)**

</div>

<!-- Private profile analytics -->

<img src="https://u8views.com/api/v1/github/profiles/38844444/views/day-week-month-total-count.svg" width="1" height="1" alt="">

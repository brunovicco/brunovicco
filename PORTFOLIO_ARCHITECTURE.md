# Portfolio Architecture Map

> 🇧🇷 [Leia em Português](./PORTFOLIO_ARCHITECTURE.pt-BR.md)

This portfolio is organized as an ecosystem rather than a collection of isolated demos.

The projects explore how to build, operate, evaluate, observe, and govern AI systems in regulated environments. They share the same architectural direction:

- keep business-critical decisions deterministic;
- place LLMs behind explicit contracts and bounded responsibilities;
- treat agents, MCP servers, model providers, and telemetry as trust boundaries;
- make security, evaluation, provenance, and auditability part of the architecture;
- bind approvals to the exact reviewed scope;
- use coding agents under repository-owned engineering controls.

## Ecosystem map

```mermaid
flowchart TB
    subgraph GOVERNANCE["AI Governance and Assurance Plane"]
        direction LR
        VAG["Verifiable AI Governance<br/><small>Inventory, risk, controls, approvals,<br/>evidence, enforcement, and audit</small>"]
    end

    subgraph CONTROL["AI-Assisted Engineering Control Plane"]
        direction LR
        LS["engineering-loop-schemas<br/><small>Canonical contracts, evidence, and verdicts</small>"]
        AL["Alicerce<br/><small>Trusted execution and evidence-gated loops</small>"]
        CH["Claude Python<br/>Engineering Harness"]
        CX["Codex Python<br/>Engineering Harness"]

        LS -->|"defines contracts"| AL
        LS -->|"standardizes evidence"| CH
        LS -->|"standardizes evidence"| CX
        AL -.->|"governed execution"| CH
        AL -.->|"governed execution"| CX
    end

    subgraph PLATFORM["Shared AI Platform Services"]
        direction LR
        PMR["Policy Model Router<br/><small>Deterministic model selection</small>"]
        OTEL["a2a-otel-kit<br/><small>Privacy-safe A2A and MCP observability</small>"]
    end

    subgraph APPS["Domain AI Systems"]
        direction LR
        RF["RAGForge<br/><small>Regulatory RAG benchmarking</small>"]
        ME["Meridian<br/><small>Internal knowledge platform</small>"]
        OF["Open Finance BR MCP<br/><small>Typed financial tools and consent</small>"]
        CD["Multi-Agent Credit Desk<br/><small>Auditable corporate credit analysis</small>"]
    end

    VAG -->|"defines controls and gates"| RF
    VAG -->|"defines controls and gates"| ME
    VAG -->|"defines controls and gates"| OF
    VAG -->|"defines controls and gates"| CD
    VAG -->|"constrains approved scope"| PMR
    PMR -->|"routing decision"| VAG
    OTEL -->|"telemetry and events"| VAG
    AL -->|"engineering evidence"| VAG

    CH -->|"governs development"| RF
    CH -->|"governs development"| CD
    CH -->|"governs development"| PMR
    CX -->|"governs development"| ME

    PMR -->|"routes models"| CD
    OTEL -->|"A2A telemetry"| CD
    OTEL -->|"MCP telemetry"| OF
    OF -.->|"financial boundary"| CD
    OTEL -.->|"observability adapter"| AL

    subgraph PRINCIPLES["Cross-Cutting Principles"]
        direction LR
        P1["Deterministic<br/>core"]
        P2["Provider-neutral<br/>boundaries"]
        P3["Fail-closed<br/>security"]
        P4["Evidence and<br/>provenance"]
        P5["Explicit human<br/>authority"]
    end

    classDef governance fill:#3F1D5C,stroke:#D8B4FE,color:#FAF5FF,stroke-width:2px;
    classDef control fill:#172554,stroke:#60A5FA,color:#EFF6FF,stroke-width:1.5px;
    classDef platform fill:#134E4A,stroke:#5EEAD4,color:#F0FDFA,stroke-width:1.5px;
    classDef domain fill:#3B0764,stroke:#C084FC,color:#FAF5FF,stroke-width:1.5px;
    classDef principle fill:#292524,stroke:#A8A29E,color:#FAFAF9,stroke-width:1.2px;
    classDef schema fill:#1E3A8A,stroke:#93C5FD,color:#FFFFFF,stroke-width:2px;
    classDef runtime fill:#7C2D12,stroke:#FDBA74,color:#FFF7ED,stroke-width:2px;

    class VAG governance;
    class CH,CX control;
    class LS schema;
    class AL runtime;
    class PMR,OTEL platform;
    class RF,ME,OF,CD domain;
    class P1,P2,P3,P4,P5 principle;
```

## Architectural layers

### 1. AI Governance and Assurance Plane

#### [Verifiable AI Governance](https://github.com/brunovicco/verifiable-ai-governance)

A vendor-neutral reference platform that turns governance requirements into executable controls and independently verifiable evidence.

Its role in the portfolio is to connect:

```text
Business context
    → initiative and system inventory
    → risk and impact classification
    → applicable controls
    → assessments and independent approvals
    → verified evidence
    → model and agent assurance
    → runtime enforcement
    → monitoring, incidents, and review
```

Demonstrated capabilities include:

- inventory of initiatives, systems, models, and agents;
- deterministic and versioned preliminary risk classification;
- AI impact, privacy, and international-processing assessments;
- declarative, versioned controls with explainable applicability;
- segregation of duties, conditional gates, and immutable review rounds;
- evidence validation, SHA-256 hashing, malware scanning, and private storage;
- approvals bound to the digest of the reviewed scope;
- independent architecture review for models and security review for agents;
- approved-scope validation before external model routing;
- incidents, kill switch, temporary exceptions, and remediation;
- hash-chained audit records and fail-closed behavior.

The project provides a functional, production-oriented reference implementation and a [public read-only demo](https://vaigov-app.duckdns.org). Selected enterprise integrations still require validation in real organizational environments.

### 2. Domain AI systems

| Project | Role in the portfolio | Current emphasis |
|---|---|---|
| [RAGForge](https://github.com/brunovicco/ragforge) | Experimental platform for comparing retrieval strategies over Brazilian financial and regulatory documents | Legal-structure-aware ingestion, sparse/dense/hybrid retrieval, relevance judgments, and reproducible evaluation |
| [Meridian](https://github.com/brunovicco/meridian) | Reference architecture for an internal engineering knowledge platform | Semantic routing, retrieval-time access control, structured queries, grounded answers, and citations |
| [Open Finance BR MCP](https://github.com/brunovicco/openfinance-br-mcp) | Experimental MCP boundary for Brazilian Open Finance | Typed tools, consent flows, FAPI-BR security patterns, mock-first execution, and explicit validation limits |
| [Multi-Agent Credit Desk](https://github.com/brunovicco/multi-agent-credit-desk) | Incremental multi-agent platform for auditable corporate credit analysis | Deterministic credit policy, synthetic bureau data, MCP/A2A boundaries, and optional LLM narratives |

### 3. Shared AI platform services

#### [Policy Model Router](https://github.com/brunovicco/policy-model-router)

A deterministic routing service that selects an allowed model group only after applying policy and workload constraints. Verifiable AI Governance can bind an approval to permitted model groups; the router performs the technical runtime decision without granting itself authority to expand the approved scope.

#### [a2a-otel-kit](https://github.com/brunovicco/a2a-otel-kit)

A reusable observability library for A2A agents and MCP services. It standardizes trace propagation, structured events, allowlisted attributes, privacy-safe failure reporting, and streaming lifecycle handling while preserving vendor neutrality.

### 4. AI-assisted engineering control plane

#### [Claude Python Engineering Harness](https://github.com/brunovicco/claude-python-engineering-harness)

Reusable scaffold and Claude Code plugin with repository-owned instructions, skills, hooks, quality gates, architecture boundaries, MCP policy, and optional governance overlays.

#### [Codex Python Engineering Harness](https://github.com/brunovicco/codex-python-engineering-harness)

The corresponding baseline for Codex workflows, aligned around deterministic validation rather than model self-assessment.

#### [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas)

Canonical, provider-neutral contracts for evidence-gated engineering loops. A builder may report what it did, but it cannot certify its own result.

#### [Alicerce](https://github.com/brunovicco/alicerce)

A trusted local core for deterministic and auditable engineering loops, including immutable run identity, durable state, controlled workspaces, command authorization, isolation, canonical evidence, and explicit human authority over promotion.

## How the projects connect

### Governance lifecycle

```mermaid
sequenceDiagram
    autonumber
    participant Owner as Business Owner
    participant Gov as Verifiable AI Governance
    participant Review as Architecture, Security, and Risk
    participant Evidence as Evidence Pipeline
    participant Router as Policy Model Router
    participant Runtime as AI System

    Owner->>Gov: Register initiative, system, and scope
    Gov->>Gov: Classify risk and determine controls
    Owner->>Evidence: Submit required evidence
    Evidence-->>Gov: Return verified artifacts and hashes
    Gov->>Review: Open independent gates
    Review-->>Gov: Approve, reject, or request correction
    Gov->>Gov: Bind decisions to the scope digest

    alt Scope approved
        Runtime->>Gov: Validate system, model, or agent
        Gov-->>Runtime: Return approved constraints
        Runtime->>Router: Request model within constraints
        Router-->>Runtime: Return permitted route or rejection
    else Scope not approved or materially changed
        Gov-->>Runtime: Reject explicitly
    end
```

### Engineering workflow

```mermaid
sequenceDiagram
    autonumber
    participant Human
    participant Harness as Claude/Codex Harness
    participant Agent as Coding Agent
    participant Alicerce
    participant Schemas as engineering-loop-schemas
    participant CI as Quality and Security Gates
    participant Gov as Verifiable AI Governance

    Human->>Harness: Define rules and acceptance criteria
    Harness->>Agent: Provide bounded context and allowed actions
    Agent->>Alicerce: Submit candidate
    Alicerce->>CI: Run deterministic gates
    CI-->>Alicerce: Return results and artifacts
    Alicerce->>Schemas: Assemble canonical evidence
    Schemas-->>Alicerce: Return validated Evidence
    Alicerce-->>Human: Deliver candidate and evidence
    Human->>Gov: Record evidence and promotion decision
    Gov->>Gov: Preserve scope, authority, and history
```

### Runtime AI workflow

```mermaid
sequenceDiagram
    autonumber
    participant User
    participant App as AI System
    participant Gov as Verifiable AI Governance
    participant Router as Policy Model Router
    participant MCP as MCP Tools
    participant Model
    participant OTel as a2a-otel-kit / OTLP

    User->>App: Submit request
    App->>App: Authenticate, authorize, and apply local policy
    App->>Gov: Validate approved scope

    alt System, model, and agent approved
        Gov-->>App: Return constraints and permitted groups
        App->>Router: Request model group
        Router-->>App: Return routing decision
        opt Tools required
            App->>MCP: Execute bounded typed call
            MCP-->>App: Return result or rejection
        end
        App->>Model: Send approved context and output contract
        Model-->>App: Return structured output
        App->>App: Validate structure, grounding, and policy
        App-->>OTel: Emit sanitized telemetry
        App-->>User: Return permitted response
    else Scope missing, invalid, or materially changed
        Gov-->>App: Reject explicitly
        App-->>OTel: Record sanitized rejection
        App-->>User: Return safe failure
    end
```

## Shared design principles

### Deterministic decisions before generative behavior

Credit outcomes, access control, command authorization, policy evaluation, preliminary risk classification, and promotion remain outside the LLM.

### Provider-neutral core, provider-specific adapters

Business rules and domain models do not directly depend on a model provider, agent framework, or observability vendor.

### Security at the boundary

MCP tools, model providers, agent calls, retrieved documents, telemetry exporters, code execution, Git, and filesystem access are treated as trust boundaries.

### Evidence over self-reported success

Important claims are bound to commands, outputs, policies, commits, environments, hashes, scopes, and independently verifiable decisions.

### Approval bound to scope

An approval does not authorize every future version. Material changes to data, models, agents, tools, region, or purpose require reassessment.

### Explicit human authority

Agents may prepare candidates, collect evidence, and propose decisions. Approvals, exceptions, promotion, merge, deployment, and high-impact actions remain under explicit human or organizational authority.

## Maturity map

| Project | Maturity | What is proven today | Next major proof point |
|---|---|---|---|
| Verifiable AI Governance | Functional v0.1.0 release | Inventory, deterministic risk, assessments, controls, approvals, evidence, model/agent assurance, runtime enforcement, incidents, and hash-chained audit | Validate real Entra ID and enterprise integrations; add telemetry and control-effectiveness measurement |
| RAGForge | Active development | Regulatory ingestion, structural chunking, retrieval strategies, and relevance metrics | Complete benchmark matrix and publish reproducible results |
| Meridian | Reference implementation | Zero-setup demo, routing, ACL-aware retrieval, and structured query path | Public walkthrough and complete deployment profile |
| Open Finance BR MCP | Experimental release | Mock environment, typed MCP surface, consent, and security foundations | Validate against official sandboxes and real participant configurations |
| Multi-Agent Credit Desk | Incremental build | Deterministic core, MCP services, initial A2A agent, and synthetic KYC | Orchestration, end-to-end decision package, and observability |
| Policy Model Router | Early service | Deterministic routing core and container publication | Broader policy catalog, metrics, and consumer examples |
| a2a-otel-kit | Reusable library | A2A/MCP propagation, sanitized events, and integration tests | Wider adoption across portfolio services |
| engineering-loop-schemas | Versioned foundation | Canonical contracts and evidence models | Completion-level evaluator and operational contracts |
| Alicerce | Phase 2A | Trusted workspace, sandbox, state, authorization, and evidence primitives | Complete evidence assembly, persistence, and resumable orchestration |
| Claude/Codex Harnesses | Reusable baseline | Scaffolding, gates, hooks, policies, and governance profiles | Integration with the completed Alicerce execution loop |

## Portfolio narrative

Together, these projects support one professional thesis:

> Production AI systems require more than model integration. They need deterministic boundaries, explicit authority, measurable quality, privacy-safe observability, reproducible evidence, and governance that binds decisions to the actual runtime scope.

```text
Context and purpose
    → inventory and risk classification
    → controls, assessments, evidence, and approvals
    → deterministic business core
    → bounded AI capability
    → model and tool policy
    → observability and evaluation
    → secure AI-assisted engineering
    → incidents, review, and continuous improvement
```

## Suggested reading paths

### AI governance, risk, and assurance

1. [Verifiable AI Governance](https://github.com/brunovicco/verifiable-ai-governance)
2. [Policy Model Router](https://github.com/brunovicco/policy-model-router)
3. [a2a-otel-kit](https://github.com/brunovicco/a2a-otel-kit)
4. [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas)

### AI platform and architecture

1. [Alicerce](https://github.com/brunovicco/alicerce)
2. [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas)
3. [a2a-otel-kit](https://github.com/brunovicco/a2a-otel-kit)
4. [Policy Model Router](https://github.com/brunovicco/policy-model-router)

### RAG and LLM engineering

1. [RAGForge](https://github.com/brunovicco/ragforge)
2. [Meridian](https://github.com/brunovicco/meridian)
3. [Open Finance BR MCP](https://github.com/brunovicco/openfinance-br-mcp)

### Financial-services AI

1. [Multi-Agent Credit Desk](https://github.com/brunovicco/multi-agent-credit-desk)
2. [Open Finance BR MCP](https://github.com/brunovicco/openfinance-br-mcp)
3. [RAGForge](https://github.com/brunovicco/ragforge)
4. [Verifiable AI Governance](https://github.com/brunovicco/verifiable-ai-governance)

### AI enablement and developer productivity

1. [Claude Python Engineering Harness](https://github.com/brunovicco/claude-python-engineering-harness)
2. [Codex Python Engineering Harness](https://github.com/brunovicco/codex-python-engineering-harness)
3. [Alicerce](https://github.com/brunovicco/alicerce)
4. [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas)

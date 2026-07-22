# Engineering Principles

## 1. Deterministic core

High-impact decisions should be expressed in code and policy that can be tested, reproduced, and audited. LLMs may assist with classification, explanation, or drafting, but should not silently become the source of truth.

## 2. Security at the boundary

Model providers, MCP servers, agent-to-agent calls, telemetry exporters, retrieved content, Git, filesystems, and candidate processes are trust boundaries. Authority should be explicit, limited, and revalidated as close as possible to the sensitive action.

## 3. Fail closed

When identity, provenance, policy, access, or execution guarantees cannot be established, the safe outcome is denial, escalation, or a bounded fallback.

## 4. Evidence over self-report

A model saying that a task succeeded is not evidence. Important outcomes should be tied to independently collected results, exact inputs, code versions, policies, traces, citations, or hashes.

## 5. Provider-neutral core

Business rules and domain models should not depend directly on an LLM SDK, agent framework, observability vendor, or transport protocol. Integrations belong at replaceable edges.

## 6. Human authority

Agents may prepare candidates, collect evidence, suggest decisions, and explain trade-offs. Promotion, merge, deployment, policy exceptions, and high-impact business actions require explicit human or organizational authority.

## 7. Governance as architecture

Governance should appear in access control, contracts, quality gates, audit records, incident processes, observability, and deployment policy—not only in documents.

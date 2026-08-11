<div align="center">

🇧🇷 **Português** &nbsp;|&nbsp; 🇺🇸 [English](README.md)

![Bruno Freitas Vicco — Engenharia de IA](https://raw.githubusercontent.com/brunovicco/brunovicco/main/assets/social/github-profile-cover.png)

# Bruno Freitas Vicco

### Engenheiro Sênior de IA Generativa

**Plataformas de IA · RAG e Agentes · MCP/A2A · Segurança de IA · LLMOps · Governança Verificável**

📍 São Paulo, Brasil &nbsp;|&nbsp; 🌍 Aberto a oportunidades internacionais e relocação

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## Sobre mim

Engenheiro Sênior de IA Generativa com foco em plataformas corporativas de IA e na infraestrutura de confiança necessária para operar esses sistemas com segurança: recuperação, agentes, identidade, autorização, observabilidade, enforcement de políticas em runtime, avaliação e governança verificável.

Meu trabalho combina arquitetura de software, engenharia de LLMs, segurança, LLMOps e governança para sistemas em produção, especialmente em ambientes regulados.

Tenho mais de 22 anos de experiência entre serviços financeiros e tecnologia, com passagens por Caixa, BTG Pactual, Banco do Brasil, Itaú Unibanco e ASA SCFI.

---

## Por onde começar

| Se você quer explorar... | Comece por |
| --- | --- |
| Governança de IA, assurance e evidência em runtime | [**Verifiable AI Governance**](https://github.com/brunovicco/verifiable-ai-governance) |
| Segurança MCP com OAuth 2.1 / OIDC | [**MCP Server Auth**](https://github.com/brunovicco/mcp-server-auth-template) + [**MCP Client Auth**](https://github.com/brunovicco/mcp-client-auth-template) |
| Observabilidade distribuída entre agentes e ferramentas | [**a2a-otel-kit**](https://github.com/brunovicco/a2a-otel-kit) |
| Enforcement determinístico de políticas de modelo | [**Policy Model Router**](https://github.com/brunovicco/policy-model-router) |
| Avaliação de RAG sobre documentos regulatórios | [**RAGForge**](https://github.com/brunovicco/ragforge) |
| Arquitetura multiagente auditável | [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk) |

[Explore a arquitetura completa do portfólio e as relações entre os projetos](./PORTFOLIO_ARCHITECTURE.pt-BR.md)

---

## Ecossistema de Engenharia de IA

Os repositórios formam um ecossistema de engenharia, e não uma coleção de demonstrações isoladas.

A arquitetura atual explora quatro camadas complementares:

- **Governança e assurance:** política, risco, aprovações, evidências, assurance em runtime, resposta a incidentes e auditabilidade.
- **Serviços de confiança em runtime:** enforcement de política de modelos, OAuth/OIDC para MCP remoto, continuidade de traces entre A2A/MCP e telemetria com minimização de dados.
- **Sistemas de IA de domínio:** RAG, conhecimento corporativo, ferramentas de Open Finance e análise multiagente auditável de crédito.
- **Controles para engenharia assistida por IA:** execução determinística, evidência canônica, limites arquiteturais e promoção controlada por humanos.

O objetivo comum é manter decisões de alto impacto e fronteiras de segurança fora do raciocínio do modelo, usando LLMs apenas onde o comportamento generativo agrega valor.

---

## Principais resultados

- Construí e governei sistemas de IA em produção para instituições financeiras reguladas, incluindo assistentes conversacionais, pipelines RAG, fluxos agênticos, observabilidade e controles de compliance.
- Liderei a adoção corporativa de IA para aproximadamente **400 usuários**, incluindo Claude Code para cerca de **250 desenvolvedores** e Claude Enterprise para aproximadamente **150 profissionais de negócio**.
- Reduzi o contexto médio de um assistente de investimentos de aproximadamente **70 mil para 3 mil tokens** por meio de injeção condicional de conhecimento, melhorando precisão e reduzindo latência e custo.
- Estruturei uma função de governança de IA com políticas de uso, processos de aprovação, allowlists de MCP, avaliação de riscos, auditabilidade, resposta a incidentes e adoção corporativa por fases.
- Transformei requisitos de governança em uma implementação verificável, com controles determinísticos, segregação de funções, evidências vinculadas às decisões, enforcement em runtime e histórico de auditoria resistente a adulterações.

---

## Projetos em destaque

| Projeto | O que demonstra |
| --- | --- |
| [**Verifiable AI Governance**](https://github.com/brunovicco/verifiable-ai-governance) | Governança de IA orientada a evidências, da classificação determinística de risco e aprovações independentes até autorização assinada em runtime, enforcement, assurance, resposta a incidentes e evidência verificável de release. [Demo pública](https://vaigov-app.duckdns.org). |
| [**MCP OAuth Security Reference**](https://github.com/brunovicco/mcp-server-auth-template) | Referência combinada de [servidor](https://github.com/brunovicco/mcp-server-auth-template) e [cliente](https://github.com/brunovicco/mcp-client-auth-template) para OAuth 2.1/OIDC, Entra ID, resource binding exato, autorização progressiva, MCP stateless, telemetria segura e evidência E2E executável. |
| [**a2a-otel-kit**](https://github.com/brunovicco/a2a-otel-kit) | Tracing OpenTelemetry neutro de fornecedor entre agentes A2A e serviços MCP, com W3C Trace Context, telemetria somente de metadados e prova executável do trace distribuído. |
| [**Policy Model Router**](https://github.com/brunovicco/policy-model-router) | Enforcement fail-closed de políticas em runtime, com roteamento determinístico de modelos, decisões explicáveis, autorização governada, evidência de violações e kill switch. |
| [**RAGForge**](https://github.com/brunovicco/ragforge) | Benchmark e avaliação reproduzíveis de estratégias de recuperação sobre documentos financeiros e regulatórios brasileiros. |
| [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk) | Fluxo multiagente auditável de crédito que combina política determinística, fronteiras MCP/A2A, roteamento de modelos, dados sintéticos e telemetria governada com minimização de dados. |

### Fundações de engenharia

[**Alicerce**](https://github.com/brunovicco/alicerce) ·
[**engineering-loop-schemas**](https://github.com/brunovicco/engineering-loop-schemas) ·
[**Claude Python Engineering Harness**](https://github.com/brunovicco/claude-python-engineering-harness) ·
[**Codex Python Engineering Harness**](https://github.com/brunovicco/codex-python-engineering-harness)

### Outras referências de domínio

[**Open Finance BR MCP**](https://github.com/brunovicco/openfinance-br-mcp) ·
[**Meridian**](https://github.com/brunovicco/meridian)

---

## Princípios de engenharia

- Decisões críticas de negócio permanecem determinísticas e auditáveis.
- Autenticação e autorização são aplicadas em código, nunca delegadas ao modelo de linguagem.
- Agentes, servidores MCP, provedores de modelos, dados recuperados e pipelines de telemetria são tratados como fronteiras de confiança.
- Saídas estruturadas, contratos explícitos, retries limitados e validação fail-closed restringem o comportamento generativo.
- Evidências precisam ser verificáveis de forma independente; autorrelato do modelo não é prova.
- Aprovações permanecem vinculadas ao escopo exato revisado e mudanças materiais exigem nova avaliação.
- Telemetria é minimizada por design; prompts, respostas de modelos, credenciais e payloads de negócio não são o padrão de observabilidade.
- Promoção, deploy, overrides em runtime e outras ações de alto impacto permanecem sob autoridade humana explícita.

---

## Competências principais

**Engenharia de IA Generativa**
RAG · sistemas agênticos · arquiteturas multiagente · roteamento semântico e de modelos · saídas estruturadas · tool calling · avaliação de LLMs · guardrails

**Segurança de Agentes e MCP**
MCP · A2A · OAuth 2.1 · OIDC · Microsoft Entra ID · PKCE · resource/audience binding · menor privilégio · autorização fail-closed · fronteiras contra prompt injection

**Plataformas e Governança de IA**
Plataformas corporativas · policy enforcement · autorização em runtime · assurance de modelos e agentes · evidências · auditabilidade · resposta a incidentes · human-in-the-loop

**LLMOps e observabilidade**
OpenTelemetry · W3C Trace Context · OTLP · Datadog · Langfuse · tracing distribuído · logging estruturado · percentis de latência · pipelines de avaliação · testes de regressão · observabilidade de tokens e custos

<details>
<summary><strong>Stack tecnológica</strong></summary>

<br>

**Linguagens e backend:** Python, FastAPI, Pydantic, TypeScript, Node.js, APIs REST, sistemas assíncronos e orientados a eventos

**Frameworks e plataformas de IA:** LangGraph, DSPy, LangChain, LlamaIndex, LiteLLM, Azure OpenAI, Azure AI Foundry, Amazon Bedrock, Anthropic Claude, Gemini

**Dados e recuperação:** Redis Stack, RediSearch, RedisJSON, PostgreSQL, pgvector, OpenSearch, busca vetorial e recuperação híbrida

**Cloud e engenharia de plataforma:** Azure, AWS, GCP, Docker, Kubernetes, OpenShift, Azure DevOps, GitHub Actions, GitLab CI e Argo CD

**Engenharia Python:** uv, Ruff, Mypy/Pyright strict, Pytest, Bandit, pip-audit, testes de arquitetura e quality gates em CI

</details>

<details>
<summary><strong>Experiência financeira, regulatória e de governança</strong></summary>

<br>

Experiência na tradução de requisitos e controles de BACEN, CMN, LGPD, CVM, ANBIMA, DORA, NIST AI RMF, ISO/IEC 42001, NIST SP 800-53, CIS Controls, MITRE ATLAS e orientações OWASP para LLMs e sistemas agênticos.

A trajetória inclui banking corporativo, crédito, risco, tesouraria, operações financeiras, engenharia de software, IA em produção, adoção corporativa e governança de IA.

</details>

<details>
<summary><strong>Certificações</strong></summary>

<br>

- AWS Certified AI Practitioner
- AWS Certified Cloud Practitioner
- Microsoft Certified: Azure Fundamentals
- CPA-20 ANBIMA

</details>

---

<div align="center">

### Vamos conversar

[LinkedIn](https://linkedin.com/in/brunovicco) · [E-mail](mailto:bfvicco@gmail.com)

</div>

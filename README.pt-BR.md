<div align="center">

🇧🇷 **Português** &nbsp;|&nbsp; 🇺🇸 [English](README.md)

# Bruno Freitas Vicco

### Engenheiro Sênior de IA Generativa
**Plataformas de IA · RAG · Agentes · LLMOps · Governança · Ambientes Regulados**

📍 São Paulo, Brasil &nbsp;|&nbsp; 🌍 Aberto a oportunidades internacionais e relocação

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## Sobre mim

Engenheiro Sênior de IA Generativa com foco em plataformas corporativas de IA, engenharia de software assistida por IA e sistemas governados em produção.

Meu trabalho combina arquitetura, engenharia de LLMs, observabilidade, segurança e governança para construir sistemas confiáveis em ambientes regulados.

Tenho mais de 22 anos de experiência entre serviços financeiros e tecnologia, com passagens por Caixa, BTG Pactual, Banco do Brasil, Itaú Unibanco e ASA SCFI.

---

## Ecossistema de Engenharia de IA

Os repositórios formam um único ecossistema de engenharia, e não uma coleção de demonstrações isoladas.

<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="./assets/architecture/ai-engineering-ecosystem-dark.svg"
  >
  <source
    media="(prefers-color-scheme: light)"
    srcset="./assets/architecture/ai-engineering-ecosystem-light.svg"
  >
  <img
    alt="Mapa da arquitetura do ecossistema de engenharia de IA"
    src="./assets/architecture/ai-engineering-ecosystem-light.svg"
  >
</picture>

[Explore a arquitetura completa, as relações entre os projetos e o mapa de maturidade](./PORTFOLIO_ARCHITECTURE.pt-BR.md)

---

## Principais resultados

- Construí e governei sistemas de IA em produção para instituições financeiras reguladas, incluindo assistentes conversacionais, pipelines RAG, fluxos agênticos, observabilidade e controles de compliance.
- Liderei a adoção corporativa de IA para aproximadamente **400 usuários**, incluindo Claude Code para cerca de **250 desenvolvedores** e Claude Enterprise para aproximadamente **150 profissionais de negócio**.
- Reduzi o contexto médio de um assistente de investimentos de aproximadamente **70 mil para 3 mil tokens** por meio de injeção condicional de conhecimento, melhorando precisão e reduzindo latência e custo.
- Estruturei uma função de governança de IA com políticas de uso, processos de aprovação, allowlists de MCP, avaliação de riscos, auditabilidade, resposta a incidentes e adoção corporativa por fases.

---

## Métricas profissionais

<table>
  <tr>
    <td align="center"><strong>22+</strong><br>Anos em serviços financeiros e tecnologia</td>
    <td align="center"><strong>17</strong><br>Anos de atuação bancária na Caixa</td>
    <td align="center"><strong>400+</strong><br>Usuários corporativos habilitados em IA</td>
    <td align="center"><strong>250+</strong><br>Desenvolvedores integrados à engenharia assistida por IA</td>
  </tr>
</table>

---

## Projetos em destaque

| Projeto | O que demonstra |
| --- | --- |
| [**RAGForge**](https://github.com/brunovicco/ragforge) | Benchmark reproduzível de estratégias de RAG regulatório sobre documentos financeiros e jurídicos brasileiros, com chunking estrutural, julgamentos de relevância e avaliação de recuperação. |
| [**Alicerce**](https://github.com/brunovicco/alicerce) | Fundação confiável para loops de engenharia determinísticos, auditáveis e baseados em evidências, com workspaces controlados, sandbox, estado e evidência canônica. |
| [**Open Finance BR MCP**](https://github.com/brunovicco/openfinance-br-mcp) | Ferramentas MCP tipadas, jornadas de consentimento, padrões de segurança FAPI-BR, execução mock-first e limites explícitos de validação para o Open Finance Brasil. |
| [**Meridian**](https://github.com/brunovicco/meridian) | Plataforma interna de conhecimento com roteamento semântico, controle de acesso durante a recuperação, consultas estruturadas, respostas fundamentadas e providers determinísticos. |
| [**Claude Python Engineering Harness**](https://github.com/brunovicco/claude-python-engineering-harness) | Engenharia de software assistida por IA com instruções pertencentes ao repositório, hooks determinísticos, fronteiras arquiteturais, quality gates e políticas MCP. |
| [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk) | Arquitetura multiagente incremental para análise auditável de crédito PJ, com decisões determinísticas, fronteiras MCP/A2A e narrativas opcionais por LLM. |

Outras fundações: [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas), [a2a-otel-kit](https://github.com/brunovicco/a2a-otel-kit), [Policy Model Router](https://github.com/brunovicco/policy-model-router) e [Codex Python Engineering Harness](https://github.com/brunovicco/codex-python-engineering-harness).

---

## Princípios de engenharia

- Decisões críticas de negócio permanecem determinísticas e auditáveis.
- Segurança e autorização são aplicadas em código, nunca delegadas ao modelo de linguagem.
- Provedores, servidores MCP, ferramentas, telemetria e dados recuperados são tratados como fronteiras de confiança.
- Saídas estruturadas, contratos explícitos e validação fail-closed limitam o comportamento generativo.
- Evidências devem ser verificáveis de forma independente; o autorrelato do modelo não é prova.
- Promoção, merge, deploy e ações de alto impacto permanecem sob autoridade humana explícita.

---

## Competências principais

**Engenharia de IA Generativa**
RAG · sistemas agênticos · arquiteturas multiagente · roteamento semântico e de modelos · saídas estruturadas · tool calling · avaliação de LLMs · guardrails

**Plataformas e adoção corporativa de IA**
Plataformas corporativas · produtividade de desenvolvedores · engenharia assistida por IA · ferramentas internas · rollout · adoção · capacitação técnica

**Arquitetura, segurança e governança**
Clean Architecture · Arquitetura Hexagonal · MCP · A2A · menor privilégio · proteção contra prompt injection · gestão de riscos · auditabilidade · human-in-the-loop

**LLMOps e observabilidade**
OpenTelemetry · Datadog · Langfuse · tracing distribuído · logging estruturado · percentis de latência · pipelines de avaliação · testes de regressão · observabilidade de custos e tokens

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

<!-- Private profile analytics -->
<img src="https://u8views.com/api/v1/github/profiles/38844444/views/day-week-month-total-count.svg" width="1" height="1" alt="">

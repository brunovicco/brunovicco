<div align="center">

🇧🇷 **Português** &nbsp;|&nbsp; 🇺🇸 [English](README.md)

![Bruno Freitas Vicco - Engenharia de IA](https://raw.githubusercontent.com/brunovicco/brunovicco/main/assets/social/github-profile-cover.png)

# Bruno Freitas Vicco

### Engenheiro de IA

**Plataformas de IA · IA Generativa e Agêntica · RAG · MCP/A2A · LLMOps · Segurança e Governança**

📍 São Paulo, Brasil &nbsp;|&nbsp; 🌍 Aberto a oportunidades internacionais e relocação

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## Sobre mim

Atuo como Engenheiro de IA na construção e evolução de plataformas e sistemas de Inteligência Artificial, principalmente em problemas que exigem ir além da integração com modelos.

Minha atuação é hands-on e transita entre engenharia e arquitetura. Gosto de investigar problemas ainda pouco estruturados, explorar alternativas, definir os limites técnicos adequados e transformar necessidades de negócio em sistemas confiáveis envolvendo LLMs, RAG, agentes, MCP/A2A, avaliação, observabilidade, segurança e governança.

Uma parte recorrente do meu trabalho é transformar requisitos operacionais, regulatórios e de segurança em mecanismos de engenharia: contratos explícitos, controles determinísticos, fronteiras de autorização, pipelines de avaliação, observabilidade, auditabilidade e decisões humanas para ações de maior impacto.

Tenho mais de 22 anos de experiência no setor financeiro, com passagens por Caixa, BTG Pactual, Banco do Brasil, Itaú Unibanco e ASA SCFI. Essa trajetória me permite transitar entre tecnologia, negócio, risco e regulação sem tratar essas dimensões como problemas isolados.

---

## Principais resultados

* Construí sistemas de IA em produção para instituições financeiras reguladas, incluindo assistentes conversacionais e transacionais, pipelines RAG, workflows com agentes, observabilidade e controles de segurança.
* Liderei a adoção corporativa de IA para aproximadamente **400 usuários**, incluindo Claude Code para cerca de **250 desenvolvedores** e Claude Enterprise para aproximadamente **150 profissionais de negócio**.
* Reduzi o contexto médio de um assistente de investimentos de aproximadamente **70 mil para 3 mil tokens (~95%)** por meio de recuperação e injeção condicional de conhecimento, preservando a qualidade das respostas e reduzindo latência, consumo de tokens e custo de inferência.
* Estruturei roteamento semântico com thresholds específicos por intenção, exemplos positivos e negativos e tratamento de ambiguidades, alcançando aproximadamente **94,7% de acurácia** no conjunto de validação.
* Estruturei mecanismos de engenharia e governança para adoção corporativa de IA, incluindo padrões de desenvolvimento, allowlists de MCP, avaliação de riscos, auditabilidade, resposta a incidentes e rollout controlado.
* Transformei requisitos de governança em software executável por meio de controles determinísticos, segregação de funções, decisões vinculadas a evidências, enforcement em runtime e histórico de auditoria resistente a adulterações.

---

## Por onde começar

| Se você quer explorar...                                        | Comece por                                                                                                                                                    |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sistemas multiagente auditáveis e orquestração de domínio       | [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk)                                                                          |
| Avaliação de RAG e engenharia de recuperação                    | [**RAGForge**](https://github.com/brunovicco/ragforge)                                                                                                        |
| Observabilidade distribuída entre agentes e ferramentas         | [**a2a-otel-kit**](https://github.com/brunovicco/a2a-otel-kit)                                                                                                |
| MCP corporativo seguro com OAuth 2.1 / OIDC                     | [**MCP Server Auth**](https://github.com/brunovicco/mcp-server-auth-template) + [**MCP Client Auth**](https://github.com/brunovicco/mcp-client-auth-template) |
| Governança executável de IA e evidências em runtime             | [**Verifiable AI Governance**](https://github.com/brunovicco/verifiable-ai-governance)                                                                        |
| Roteamento determinístico de modelos e enforcement de políticas | [**Policy Model Router**](https://github.com/brunovicco/policy-model-router)                                                                                  |

[Explore a arquitetura completa do portfólio e as relações entre os projetos](./PORTFOLIO_ARCHITECTURE.pt-BR.md)

---

## Ecossistema de Engenharia de IA

Os repositórios formam um ecossistema de engenharia, e não uma coleção de demonstrações isoladas.

Eles exploram diferentes partes de um mesmo problema: **como construir sistemas de IA que permaneçam confiáveis, observáveis, seguros e governáveis à medida que avançam da experimentação para produção.**

O ecossistema atualmente cobre quatro camadas complementares:

* **Sistemas de IA de domínio:** RAG, conhecimento corporativo, ferramentas de Open Finance e workflows multiagente auditáveis.
* **Serviços de plataforma em runtime:** roteamento de modelos, integração MCP/A2A, observabilidade distribuída, identidade, autorização e telemetria com minimização de dados.
* **Engenharia assistida por IA:** execução determinística, contratos explícitos, limites arquiteturais, evidência reproduzível e promoção controlada por humanos.
* **Governança e assurance:** políticas, riscos, aprovações, autorização em runtime, enforcement, incidentes, evidências e auditabilidade.

O princípio comum é utilizar LLMs onde o comportamento generativo agrega valor, mantendo decisões críticas, autorização, enforcement de políticas e fronteiras de segurança explícitos e verificáveis de forma independente.

---

## Projetos em destaque

| Projeto                                                                                    | O que demonstra                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [**Multi-Agent Credit Desk**](https://github.com/brunovicco/multi-agent-credit-desk)       | Workflow multiagente auditável de crédito combinando política determinística, fronteiras MCP/A2A, roteamento de modelos, dados sintéticos e telemetria de runtime com minimização de dados.                                                                                                                 |
| [**RAGForge**](https://github.com/brunovicco/ragforge)                                     | Benchmark e avaliação reproduzíveis de estratégias de recuperação sobre documentos financeiros e regulatórios brasileiros.                                                                                                                                                                                  |
| [**a2a-otel-kit**](https://github.com/brunovicco/a2a-otel-kit)                             | Tracing OpenTelemetry neutro de fornecedor entre agentes A2A e serviços MCP, com W3C Trace Context, telemetria somente de metadados e prova executável do trace distribuído.                                                                                                                                |
| [**MCP OAuth Security Reference**](https://github.com/brunovicco/mcp-server-auth-template) | Referência combinada de [servidor](https://github.com/brunovicco/mcp-server-auth-template) e [cliente](https://github.com/brunovicco/mcp-client-auth-template) para OAuth 2.1/OIDC, Entra ID, resource binding exato, autorização progressiva, MCP stateless, telemetria segura e evidência E2E executável. |
| [**Verifiable AI Governance**](https://github.com/brunovicco/verifiable-ai-governance)     | Plataforma de referência orientada a produção que conecta políticas, aprovações, autorização assinada em runtime, enforcement, assurance, resposta a incidentes e evidências verificáveis de forma independente. [Demo pública](https://vaigov-app.duckdns.org).                                            |
| [**Policy Model Router**](https://github.com/brunovicco/policy-model-router)               | Roteamento fail-closed de modelos e enforcement de políticas em runtime, com decisões explicáveis, autorização governada, evidência de violações e suporte a kill switch.                                                                                                                                   |

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

* Escolher a arquitetura de acordo com o problema, e não pela popularidade de um padrão específico de IA.
* Decisões críticas de negócio permanecem determinísticas e auditáveis.
* Autenticação e autorização são aplicadas em código, nunca delegadas ao modelo de linguagem.
* Agentes, servidores MCP, provedores de modelos, dados recuperados e pipelines de telemetria são tratados como fronteiras explícitas de confiança.
* Saídas estruturadas, contratos tipados, retries limitados e validações fail-closed restringem o comportamento generativo.
* Recuperação e geração são avaliadas separadamente sempre que possível.
* Evidências precisam ser verificáveis de forma independente; autorrelato do modelo não é prova.
* Telemetria é minimizada por design; prompts, respostas de modelos, credenciais e payloads de negócio não são o padrão de observabilidade.
* Ações de alto impacto, como promoção, deploy, overrides em runtime e execução de ferramentas sensíveis, permanecem sob autoridade humana explícita.

---

## Competências principais

**Plataformas e Arquitetura de IA**
Plataformas corporativas de IA · sistemas distribuídos de IA · APIs e serviços · roteamento de modelos · MCP/A2A · identidade e autorização · capacidades de plataforma · developer enablement

**IA Generativa e Agêntica**
LLMs · RAG · sistemas agênticos · arquiteturas multiagente · LangGraph · roteamento semântico · saídas estruturadas · tool calling · avaliação · guardrails

**LLMOps e Observabilidade**
OpenTelemetry · W3C Trace Context · OTLP · Datadog · Langfuse · tracing distribuído · logging estruturado · pipelines de avaliação · testes de regressão · observabilidade de latência, tokens e custos

**Segurança e Governança de IA**
OAuth 2.1 · OIDC · menor privilégio · autorização fail-closed · fronteiras contra prompt injection · policy enforcement · autorização em runtime · assurance · auditabilidade · resposta a incidentes · human-in-the-loop

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

Experiência na tradução de requisitos e controles de BACEN, CMN, LGPD, CVM, ANBIMA, DORA, NIST AI RMF, ISO/IEC 42001, NIST SP 800-53, CIS Controls, MITRE ATLAS e orientações OWASP em mecanismos técnicos e operacionais para LLMs e sistemas agênticos.

A trajetória inclui banking corporativo, crédito, risco, tesouraria, operações financeiras, engenharia de software, IA em produção, adoção corporativa e governança de IA.

</details>

<details>
<summary><strong>Certificações</strong></summary>

<br>

* AWS Certified AI Practitioner
* AWS Certified Cloud Practitioner
* Microsoft Certified: Azure Fundamentals
* CPA-20 ANBIMA

</details>

---

<div align="center">

### Vamos conversar

[LinkedIn](https://linkedin.com/in/brunovicco) · [E-mail](mailto:bfvicco@gmail.com)

</div>

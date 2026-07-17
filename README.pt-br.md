<div align="center">

🇧🇷 **Português** &nbsp;|&nbsp; 🇺🇸 [English](README.md)

# Bruno Freitas Vicco

### Engenheiro Sênior de IA Generativa | Plataformas, Adoção Corporativa e Governança de IA

### IA em Produção, Sistemas Agênticos, Segurança e Observabilidade para Ambientes Regulados

📍 São Paulo, Brasil &nbsp;|&nbsp; 🌍 Aberto a oportunidades internacionais e relocação

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## Sobre mim

Sou Engenheiro de IA Generativa com atuação hands-on na construção, evolução e governança de sistemas de IA em produção para ambientes regulados.

Meu trabalho combina engenharia de LLMs, arquitetura de IA, plataformas corporativas, adoção em escala, segurança, observabilidade e governança. Transformo requisitos regulatórios e de segurança em controles verificáveis implementados no código da aplicação, na infraestrutura, nos pipelines de CI/CD e nos processos operacionais.

Tenho mais de 22 anos de experiência no setor financeiro, incluindo 17 anos na Caixa Econômica Federal, com atuação em banking corporativo, crédito, tesouraria, risco e operações financeiras. Posteriormente, migrei para engenharia de software e inteligência artificial, participando de iniciativas no BTG Pactual, Banco do Brasil por meio da Cast Group, Itaú Unibanco e ASA SCFI.

No ASA, fui o primeiro profissional dedicado exclusivamente à IA Generativa. Minha atuação envolveu assistentes de produção, plataformas corporativas de IA, produtividade de desenvolvedores, adoção por áreas de negócio, segurança e estruturação da função de governança de IA da companhia.

> **Aberto a oportunidades:** Engenheiro Sênior, Staff ou Principal de IA Generativa; Engenheiro de Plataforma de IA; AI Enablement Lead; Arquiteto de IA Generativa; Arquiteto de Governança de IA; e Arquiteto de Segurança de IA.
>
> Tenho interesse especial em posições que combinem engenharia hands-on, arquitetura, adoção corporativa, segurança e governança.

---

## Principais resultados

- Liderei a evolução de um assistente bancário conversacional e transacional de prova de conceito para produção, com runtime unificado, checkpointing em Redis, isolamento de sessões, memória de longo prazo, observabilidade e controles de compliance incorporados à arquitetura.

- Projetei um subgrafo especializado em investimentos com roteamento semântico sensível a exemplos negativos, detecção de ambiguidade, contratos de saída com DSPy e Pydantic, autocorreção orientada por compliance e validação de suitability antes da exposição dos produtos ao modelo de linguagem.

- Conduzi a adoção corporativa de IA para aproximadamente 400 usuários, incluindo Claude Code para cerca de 250 desenvolvedores e Claude Enterprise para aproximadamente 150 profissionais de áreas administrativas e de negócio.

- Estruturei uma plataforma de engenharia assistida por IA com Spec-Driven Development, scaffolds para diferentes stacks, plugins internos, integrações MCP governadas, hooks de segurança, aplicação de políticas e gates de qualidade em CI/CD.

- Estabeleci a função de governança de IA da companhia, abrangendo políticas de uso, processos de aprovação, allowlists de servidores MCP, avaliações de risco, resposta a incidentes, auditabilidade, continuidade de negócio e adoção por fases.

- No Itaú Unibanco, reduzi o contexto médio de um assistente de investimentos de aproximadamente 70 mil para 3 mil tokens por meio da injeção condicional de conhecimento, melhorando precisão e reduzindo latência e custo de inferência.

- Implementei tracing distribuído com Datadog em um fluxo agêntico, substituindo o monitoramento baseado apenas em logs por visibilidade ponta a ponta sobre latência, chamadas aos modelos, execução de ferramentas e comportamento em runtime.

### Princípios de engenharia

- Segurança e autorização aplicadas em código, nunca delegadas ao modelo de linguagem
- Controles fail-closed para operações sensíveis
- Saídas estruturadas e validação determinística
- Princípio do menor privilégio para ferramentas e dados
- Execução de agentes observável e auditável
- Aprovação humana para ações de alto impacto
- Governança implementada como arquitetura, não apenas como documentação

---

## Projetos em destaque

### [openfinance-br-mcp](https://github.com/brunovicco/openfinance-br-mcp)

Servidor open source baseado no Model Context Protocol para o ecossistema brasileiro de Open Finance.

O projeto expõe contas, saldos, transações, cartões de crédito, PIX, investimentos, gestão de consentimento e iniciação de pagamentos por meio de interfaces controladas para agentes de IA.

Principais áreas:

- 12 ferramentas MCP cobrindo as fases 2, 3 e 4 do Open Finance Brasil
- Padrões de segurança FAPI-BR
- `private_key_jwt`, PAR, JAR, PKCE e mTLS
- Ciclo de consentimento e autorização
- Validação de entradas com Pydantic v2
- Adapters para múltiplas instituições financeiras
- Execução de ferramentas auditável e orientada por permissões

> As integrações financeiras reais estão documentadas como experimentais e não são certificadas para uso em produção.

---

### [meridian](https://github.com/brunovicco/meridian)

Arquitetura de referência para assistentes corporativos de conhecimento com recuperação consciente de autorização.

O projeto demonstra:

- RAG filtrado por ACL
- Segurança em nível de linha aplicada durante a recuperação
- Roteamento semântico validado com DSPy
- Consultas estruturadas no RediSearch
- Modelagem de dados fat e slim no Redis
- Respostas fundamentadas com citações
- Clean Architecture e princípios Twelve-Factor
- Testes automatizados para autorização e recuperação

> O controle de acesso é aplicado antes que o contexto chegue ao modelo de linguagem.

---

### [claude-python-engineering-harness](https://github.com/brunovicco/claude-python-engineering-harness)

Harness reutilizável para desenvolvimento Python governado com Claude Code.

Inclui:

- Scaffolds de instruções para projetos e agentes
- Templates de `CLAUDE.md` e `AGENTS.md`
- Fluxos de Spec-Driven Development
- Hooks de segurança fail-closed
- Proteção contra comandos perigosos
- Governança opcional de servidores MCP
- Logging estruturado
- Aplicação de políticas por CI
- Gates de qualidade e segurança para Python

> Instrução não é controle. Requisitos que precisam ser sempre garantidos devem existir em hooks determinísticos, no código da aplicação e nos gates de CI.

---

### [codex-python-engineering-harness](https://github.com/brunovicco/codex-python-engineering-harness)

Harness reutilizável para desenvolvimento Python estruturado e governado com agentes de código.

O projeto aborda:

- Instruções operacionais para agentes
- Fluxos orientados por especificação
- Automação de segurança e qualidade
- Scaffolding reproduzível de projetos
- Aplicação determinística de políticas
- Integração com revisão de código e CI

---

### [claude-code-crypto-lab](https://github.com/brunovicco/claude-code-crypto-lab)

Laboratório prático para desenvolvimento agêntico seguro com Claude Code.

Tópicos abordados:

- Subagentes e skills reutilizáveis
- Hooks determinísticos
- Bloqueio de comandos perigosos
- Integração com servidor MCP local
- Limites de permissão para ferramentas
- Integração com CI/CD
- Documentação bilíngue em inglês e português

---

## Competências principais

### Engenharia de IA Generativa

Engenharia de aplicações com LLMs · RAG · sistemas agênticos · arquiteturas multiagente · roteamento semântico · roteamento de modelos · saídas estruturadas · tool calling · function calling · memória conversacional · avaliação de LLMs · prompt security · guardrails

### Plataformas e adoção corporativa de IA

Plataformas de IA · AI Enablement · produtividade de desenvolvedores · engenharia de software assistida por IA · rollout corporativo · ferramentas internas · programas de capacitação · governança de adoção · avaliações de maturidade · modelos operacionais de IA

### Arquitetura de IA

LangGraph · DSPy · LangChain · LlamaIndex · Model Context Protocol · padrões Agent-to-Agent · Clean Architecture · Arquitetura Hexagonal · SOLID · Twelve-Factor · arquiteturas orientadas a eventos

### Governança e segurança de IA

Governança de IA · IA Responsável · gestão de riscos de IA · proteção contra prompt injection · isolamento de sessões · segurança em nível de linha · governança de MCP · menor privilégio · human-in-the-loop · trilhas de auditoria · resposta a incidentes

### LLMOps e observabilidade

Datadog · Langfuse · OpenTelemetry · logging estruturado · tracing distribuído · percentis de latência · pipelines de avaliação · testes de regressão · monitoramento de modelos · observabilidade de custos e tokens

---

## Stack tecnológica

### Linguagens e backend

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)

Python · FastAPI · Pydantic · JavaScript · TypeScript · Node.js · NestJS · APIs REST · processamento assíncrono · arquiteturas orientadas a eventos

### Frameworks e plataformas de IA

![LangGraph](https://img.shields.io/badge/-LangGraph-1C3C3C?style=flat)
![DSPy](https://img.shields.io/badge/-DSPy-blue?style=flat)
![Azure OpenAI](https://img.shields.io/badge/-Azure_OpenAI-0089D6?style=flat&logo=microsoftazure&logoColor=white)
![AWS Bedrock](https://img.shields.io/badge/-AWS_Bedrock-232F3E?style=flat&logo=amazonaws&logoColor=white)

LangGraph · DSPy · LangChain · LlamaIndex · LiteLLM · Mem0 · Azure OpenAI · Azure AI Foundry · Amazon Bedrock · Claude · Gemini · Llama

### Dados e recuperação

![Redis](https://img.shields.io/badge/-Redis_Stack-DC382D?style=flat&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)

Redis Stack · RediSearch · RedisJSON · PostgreSQL · pgvector · Qdrant · MongoDB · SQL · SQLAlchemy · busca vetorial · recuperação híbrida

### Cloud, DevOps e engenharia de plataforma

![Azure](https://img.shields.io/badge/-Azure-0089D6?style=flat&logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)

Azure · AWS · GCP · Docker · Kubernetes · OpenShift · Azure DevOps · GitHub Actions · GitLab CI · Argo CD · Jenkins · API gateways · infraestrutura baseada em VPC

### Engenharia Python

`uv` · `ruff` · `mypy --strict` · `pytest` · `import-linter` · `bandit` · `pip-audit` · `Semgrep` · injeção de dependências · processamento idempotente · logging estruturado

---

## Escopo regulatório e de governança

Experiência na tradução de requisitos e controles de:

BACEN e CMN · LGPD · CVM · ANBIMA · EU AI Act · DORA · NIST AI RMF 1.0 · ISO/IEC 42001 · NIST SP 800-53 · CIS Controls · MITRE ATLAS · OWASP Top 10 para aplicações com LLMs · orientações OWASP para sistemas agênticos

---

## Certificações

- AWS Certified AI Practitioner
- AWS Certified Cloud Practitioner
- Microsoft Certified: Azure Fundamentals
- CPA-20 ANBIMA

---

<div align="center">

### Vamos conversar

📫 **[bfvicco@gmail.com](mailto:bfvicco@gmail.com)**  
💼 **[linkedin.com/in/brunovicco](https://linkedin.com/in/brunovicco)**

</div>

<!-- Métricas privadas do perfil -->

<img src="https://u8views.com/api/v1/github/profiles/38844444/views/day-week-month-total-count.svg" width="1" height="1" alt="">

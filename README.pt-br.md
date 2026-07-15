<div align="center">

🇧🇷 **Português**  |  🇺🇸 [English](README.md)

# Bruno Freitas Vicco

### Engenheiro e Arquiteto de IA Generativa

### Engenharia, Segurança e Governança de IA para Ambientes Regulados

📍 São Paulo, Brasil  |  🌍 Aberto a oportunidades internacionais e relocação

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## Sobre mim

Projeto e construo sistemas de IA generativa para produção em setores regulados, combinando engenharia de LLMs, arquitetura de agentes, segurança, observabilidade e governança.

A maioria dos profissionais se concentra na engenharia de aplicações com LLMs ou em políticas e governança. Atuo nas duas frentes, transformando requisitos regulatórios e de segurança em controles arquiteturais verificáveis.

Tenho mais de 22 anos no setor financeiro, sendo 17 na Caixa Econômica Federal, em banking corporativo, tesouraria e risco, antes de migrar para engenharia de software e IA. Depois vieram BTG Pactual, Banco do Brasil (via Cast Group), Itaú Unibanco e ASA SCFI, onde fui o primeiro profissional contratado com dedicação exclusiva à inteligência artificial.

> **Aberto a oportunidades:** Staff/Principal AI Engineer, Generative AI Architect, AI Platform Architect, AI Governance Architect e AI Security Architect, no Brasil ou no exterior. Interesse especial em posições que combinem engenharia com arquitetura, segurança, governança e adoção corporativa de IA em escala.

---

## Principais resultados

- Evoluí um assistente bancário conversacional e transacional de PoC para produção, com arquitetura hexagonal, observabilidade de ponta a ponta e compliance como propriedade estrutural do sistema.
- Projetei um subgrafo de investimentos com roteamento semântico, contratos de saída validados (DSPy e Pydantic), autocorreção por critérios de compliance e suitability aplicada antes da exposição de produtos ao modelo, com validações CVM/ANBIMA antes da entrega ao cliente.
- Estruturei uma plataforma corporativa de engenharia assistida por IA: Claude Code para 250 desenvolvedores e Claude Enterprise para 150 usuários, com security hooks fail-closed, governança de MCPs, gateway em VPC controlada e AI Academy interna com trilhas de certificação.
- No Itaú Unibanco, reduzi o prompt médio de um assistente de investimentos de 70 mil para 3 mil tokens, aumentando a precisão e reduzindo latência e custo de inferência.

Princípios que atravessam esses trabalhos: segurança em nível de dados aplicada em código (nunca delegada ao modelo), defesa contra prompt injection, trilhas de auditoria imutáveis e defaults fail-closed.

---

## Projetos em destaque

### [meridian](https://github.com/brunovicco/meridian)

Arquitetura de referência para assistentes corporativos de conhecimento: roteamento semântico validado por DSPy, RAG com controle de acesso por ACL aplicado dentro da busca, consultas estruturadas para RediSearch, modelagem fat/slim no Redis e respostas fundamentadas com citações. Clean Architecture, Twelve-Factor e cobertura automatizada de testes.

O controle de acesso é aplicado durante a recuperação e nunca é delegado ao modelo de linguagem.

### [claude-python-engineering-harness](https://github.com/brunovicco/claude-python-engineering-harness)

Harness reutilizável de Claude Code para equipes Python: bootstrap de projetos, scaffolds de CLAUDE.md e AGENTS.md, hooks de segurança fail-closed, governança opcional de MCP e aplicação de políticas por CI.

> Instrução não é controle. Políticas que precisam ser sempre garantidas devem existir em hooks determinísticos e gates de CI, não apenas em prompts.

### [claude-code-crypto-lab](https://github.com/brunovicco/claude-code-crypto-lab)

Laboratório prático de Claude Code para desenvolvimento agêntico seguro: subagentes, skills, hooks determinísticos, bloqueio de comandos perigosos, integração com MCP local e CI/CD.

### [openfinance-br-mcp](https://github.com/brunovicco/openfinance-br-mcp)

Servidor MCP open source para o ecossistema brasileiro de Open Finance, expondo capacidades financeiras padronizadas a agentes de IA por meio de interfaces controladas e auditáveis. Em desenvolvimento ativo.

---

## Outros projetos

### Barthô

Aplicação SaaS de finanças pessoais voltada à organização financeira, agregação de contas, análise de transações e geração de insights inteligentes.

---

## Stack tecnológica

### IA Generativa e Orquestração

![LangGraph](https://img.shields.io/badge/-LangGraph-1C3C3C?style=flat)
![DSPy](https://img.shields.io/badge/-DSPy-blue?style=flat)
![LlamaIndex](https://img.shields.io/badge/-LlamaIndex-black?style=flat)
![Mem0](https://img.shields.io/badge/-Mem0-orange?style=flat)
![LiteLLM](https://img.shields.io/badge/-LiteLLM_Proxy-purple?style=flat)

LangGraph · DSPy · LangChain · LlamaIndex · LiteLLM · Mem0 · Model Context Protocol · arquiteturas Agent-to-Agent · roteamento semântico · RAG · orquestração multiagente · tool calling estruturado · avaliação de LLMs e guardrails

### Cloud e Infraestrutura

![Azure](https://img.shields.io/badge/-Azure-0089D6?style=flat&logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS_Bedrock-232F3E?style=flat&logo=amazonaws&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)

Microsoft Azure · Azure OpenAI · AWS · Amazon Bedrock · Kubernetes · Docker · API gateways · infraestrutura de IA baseada em VPC

### Dados e Backend

![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/-Redis_Stack-DC382D?style=flat&logo=redis&logoColor=white)
![Qdrant](https://img.shields.io/badge/-Qdrant%2Fpgvector-DC244C?style=flat)
![SQLAlchemy](https://img.shields.io/badge/-SQLAlchemy_2.0-red?style=flat)

Python · FastAPI · PostgreSQL · Redis Stack (RediSearch/RedisJSON) · Qdrant · pgvector · SQLAlchemy 2.0 · Pydantic · processamento assíncrono · arquiteturas orientadas a eventos · APIs REST

### Frontend

![React](https://img.shields.io/badge/-React%2FNext.js-black?style=flat&logo=react&logoColor=61DAFB)

React · Next.js · TypeScript

### Segurança de IA e Observabilidade

![Zscaler](https://img.shields.io/badge/-Zscaler-1E3A5F?style=flat)
![LLM Guard](https://img.shields.io/badge/-LLM_Guard-red?style=flat)
![Langfuse](https://img.shields.io/badge/-Langfuse-black?style=flat)
![Entra ID](https://img.shields.io/badge/-Entra_ID-0078D4?style=flat&logo=microsoftazure&logoColor=white)

Langfuse · OpenTelemetry · Datadog · LLM Guard · Zscaler · Microsoft Entra ID · detecção e redação de PII · proteção contra prompt injection · governança de acesso a modelos e de servidores MCP

### Engenharia Python

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)

`uv` · `ruff` · `mypy --strict` · `import-linter` · `pytest` · `bandit` · `pip-audit` · Clean Architecture · Arquitetura Hexagonal · SOLID · Twelve-Factor · injeção de dependências · processamento idempotente

---

## Escopo regulatório e de governança

Atuo com requisitos e controles de: BACEN/CMN · LGPD · CVM · ANBIMA · EU AI Act · DORA · NIST AI RMF 1.0 · ISO/IEC 42001 · NIST SP 800-53 · CIS Controls · MITRE ATLAS · OWASP (LLM e sistemas agênticos)

---

<div align="center">

### Vamos conversar

📫 **[bfvicco@gmail.com](mailto:bfvicco@gmail.com)**
💼 [linkedin.com/in/brunovicco](https://linkedin.com/in/brunovicco)

</div>

<!-- Métricas privadas do perfil -->

<img src="https://u8views.com/api/v1/github/profiles/38844444/views/day-week-month-total-count.svg" width="1" height="1" alt="">

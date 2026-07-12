<div align="center">

🇧🇷 **Português**  |  🇺🇸 [English](README.md)

# Bruno Freitas Vicco

### Especialista e Arquiteto em IA Generativa

### Engenharia, Segurança e Governança de IA para Instituições Financeiras Reguladas

📍 São Paulo, Brasil  |  🌍 Aberto a oportunidades internacionais e relocação

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat\&logo=linkedin\&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat\&logo=gmail\&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## Sobre mim

Projeto e construo sistemas de IA generativa para ambientes de produção em instituições financeiras reguladas.

Minha atuação está na interseção entre **engenharia de IA, arquitetura de software, segurança, observabilidade e governança regulatória**. Desenvolvo as plataformas técnicas que permitem às organizações adotar IA generativa sem perder o controle sobre identidade, acesso a dados, uso de modelos, auditabilidade, resiliência e conformidade.

Essa combinação ainda é pouco comum: a maioria dos profissionais se concentra apenas na engenharia de aplicações com LLMs ou exclusivamente em políticas e governança. Atuo nas duas frentes, transformando requisitos regulatórios e de segurança em controles arquiteturais verificáveis.

---

## Trajetória profissional

Tenho mais de **22 anos de experiência no setor financeiro**, sendo 17 deles na **Caixa Econômica Federal**, onde atuei em banking corporativo, tesouraria, operações regionais e unidades nacionais.

Posteriormente, migrei para posições de engenharia de software e inteligência artificial em:

* **BTG Pactual**
* **Cast Group**, alocado no Banco do Brasil
* **Itaú Unibanco**
* **ASA SCFI**, onde fui o primeiro profissional contratado com dedicação exclusiva à inteligência artificial

Minha experiência abrange operações bancárias, produtos financeiros, engenharia de software, arquitetura de IA generativa, segurança, governança e adoção corporativa.

---

## Principais iniciativas no ASA

### 1. Plataforma Conversacional Bancária

Refatorei uma plataforma conversacional bancária corporativa para uma arquitetura hexagonal, observável e orientada a compliance.

A solução foi projetada para que segurança, proteção de dados, rastreabilidade e auditabilidade fossem propriedades estruturais do sistema, e não controles adicionados posteriormente.

<details>
<summary><b>Detalhes técnicos</b></summary>

<br>

* Refatoração da plataforma para arquitetura hexagonal, com separação clara entre domínio, aplicação, infraestrutura, apresentação e composition root
* Orquestração de modelos e fluxos conversacionais com LangGraph, roteamento cognitivo e serviços especializados por domínio
* Identidade pseudonimizada por HMAC-SHA256, com isolamento de sessões, threads e proteção de dados orientada à LGPD
* Processamento multicanal síncrono e assíncrono com FastAPI, workers e Redis
* Implementação de controles de idempotência e gerenciamento persistente de checkpoints
* Observabilidade distribuída com OpenTelemetry e Langfuse
* Padronização de logs estruturados, correlação de requisições, tracing e redação automática de PII
* Desacoplamento da autenticação dos grafos e prompts por meio de um contexto seguro armazenado no Redis, com TTL controlado
* Manutenção de tokens de autenticação e credenciais sensíveis fora do contexto dos modelos
* Implementação de feature flags intercambiáveis via variáveis de ambiente ou Flagsmith
* Suporte a rollouts graduais, experimentação controlada e kill switches operacionais
* Aplicação de injeção de dependências e do padrão ports and adapters para facilitar testes, substituição de provedores e evolução independente das integrações

</details>

### 2. Assistente de Investimentos

Projetei um subgrafo LangGraph orientado a compliance para interações relacionadas a investimentos.

A solução combina roteamento validado por DSPy, recuperação apoiada em Redis, controles de suitability, execução estruturada de ferramentas e autocorreção de respostas. Os requisitos regulatórios são aplicados antes que o modelo receba opções de produtos ou gere uma resposta.

<details>
<summary><b>Detalhes técnicos</b></summary>

<br>

* Construção de mecanismo próprio de roteamento semântico com scoring sensível a exemplos negativos
* Detecção de ambiguidade com thresholds por intenção, piso absoluto de confiança e margem entre os candidatos mais bem classificados
* Invalidação automática do cache de roteamento por fingerprint SHA-256 do catálogo de intenções
* Definição de contratos de saída de LLM com signatures declarativas do DSPy e validação Pydantic
* Uso de modelos `RouterOutput` fortemente tipados com tipos `Literal`
* Implementação de camada de coerção fail-safe para absorver drift de formato antes da execução de qualquer ferramenta
* Autocorreção de respostas com `dspy.Refine`
* Criação de função de recompensa de compliance cobrindo disclaimers obrigatórios, linguagem em terceira pessoa, ausência de imperativo e proibição de opiniões sobre carteira
* Regeneração de respostas até atingir o score de compliance exigido ou esgotar o orçamento de tentativas
* Implementação de critique node para requisitos da CVM e da ANBIMA
* Injeção de disclaimers obrigatórios antes da entrega da resposta
* Aplicação de suitability na prateleira de produtos antes que os produtos se tornem visíveis ao modelo, conforme a Resolução CVM 30
* Criação de toolset especializado e assíncrono baseado em `BaseTool`, instanciado dinamicamente a cada interação
* Busca em prateleira de mercado com filtros semânticos
* Consultas de portfólio por ativo e consolidadas por classe
* Detalhamento de produtos sob demanda e recuperação de conteúdo editorial ou house view
* Geração de relatórios em PDF a partir do estado da conversa com ReportLab
* Aplicação de modelagem fat/slim no Redis Stack
* Indexação de projeções enxutas no RediSearch para busca e ranqueamento
* Recuperação do documento completo via `JSON.GET` apenas para registros que efetivamente entram no contexto do modelo
* Criação de `QueryBuilder` com taxonomia explícita de campos:

  * `TAG` para correspondências exatas
  * `TEXT` para buscas tokenizadas e fuzzy
  * `NUMERIC` para filtros por intervalo
* Escaping de caracteres especiais do RediSearch
* Aplicação obrigatória de row-level security por CPF no código da aplicação, nunca por meio de instruções ao modelo
* Sanitização das entradas enviadas ao RediSearch contra prompt injection e command injection
* Bloqueio de verbos de agregação e comandos
* Rejeição de caracteres de controle e aplicação de limites de comprimento
* Fail-safe com wildcard para expressões de busca inválidas
* Resolução de anáforas por meio de uma pilha limitada de entidades no Redis
* Deduplicação semântica e TTL curto para a pilha de entidades
* Injeção das entidades resolvidas nas consultas antes do processamento pelo DSPy
* Pre-warming assíncrono de portfólios para retirar o carregamento da carteira do caminho crítico da primeira interação
* Latência inicial independente do tamanho do portfólio
* Armazenamento de métricas de roteamento em hashes do Redis com `HINCRBY` e TTL rolante
* Agregação segura de métricas entre múltiplos workers sem coordenação centralizada
* Alarmes de degradação baseados em thresholds da taxa de fallback

</details>

### 3. Governança Corporativa de IA

Atuei na arquitetura, governança e adoção de recursos corporativos de IA generativa.

* Rollout do Claude Code para aproximadamente **250 desenvolvedores**
* Implantação do Claude Enterprise para aproximadamente **150 usuários de tecnologia e negócios**
* Security hooks para aplicação determinística de políticas
* Governança e allowlist de servidores MCP
* Gateway de IA self-hosted implantado em VPC controlada
* Governança de acesso a modelos e controles de roteamento entre provedores
* Padronização de requisitos de auditabilidade e observabilidade
* AI Academy interna com trilhas técnicas e de governança
* Diretrizes de arquitetura e segurança para desenvolvimento de software assistido por IA
* Materiais de capacitação para desenvolvedores, usuários de negócios, arquitetos e equipes de governança

### Escopo regulatório e de governança

Minha atuação inclui requisitos e controles relacionados a:

* Normativos do BACEN e do CMN
* Lei Geral de Proteção de Dados, LGPD
* Normativos da CVM
* Diretrizes da ANBIMA
* Regulamento Europeu de Inteligência Artificial, EU AI Act
* Digital Operational Resilience Act, DORA
* NIST AI Risk Management Framework
* ISO/IEC 42001
* NIST SP 800-53
* CIS Controls
* MITRE ATLAS
* Recomendações da OWASP para LLMs e sistemas agênticos

---

## Projetos em destaque

### [`meridian`](https://github.com/brunovicco/meridian)

Arquitetura de referência para um assistente corporativo de conhecimento com recuperação sensível a autorização.

O projeto demonstra:

* Roteamento semântico validado por DSPy
* RAG com controle de acesso por ACL
* Aplicação do controle de acesso dentro da busca vetorial
* Compilação de consultas estruturadas para RediSearch
* Modelagem fat/slim no Redis
* Provedores fake determinísticos para execução local
* Integração opcional com DSPy e Groq
* Clean Architecture
* Configuração Twelve-Factor
* Cobertura automatizada de testes

O controle de acesso é aplicado durante a recuperação e nunca é delegado ao modelo de linguagem.

---

### [`claude-code-crypto-lab`](https://github.com/brunovicco/claude-code-crypto-lab)

Laboratório prático de Claude Code construído em torno de uma aplicação educacional de portfólio de criptoativos.

O projeto demonstra:

* Subagentes do Claude Code
* Skills reutilizáveis
* Hooks determinísticos
* Bloqueio de comandos perigosos
* Bloqueio de prompts fora do escopo
* Integração com servidor MCP local
* Integração e entrega contínuas
* Documentação bilíngue em inglês e português brasileiro

---

### [`claude-python-engineering-harness`](https://github.com/brunovicco/claude-python-engineering-harness)

Harness reutilizável de Claude Code para equipes de engenharia Python.

O projeto inclui:

* Automação de bootstrap de projetos
* Scaffolding de `CLAUDE.md`
* Scaffolding de `AGENTS.md`
* Padrões reutilizáveis de desenvolvimento
* Governança opcional de MCP
* Hooks de segurança fail-closed
* Aplicação de políticas por CI
* Ferramentas de qualidade e segurança para Python

O projeto parte de um princípio central:

> Instrução não é controle. Políticas que precisam ser sempre garantidas devem existir em hooks determinísticos e gates de CI, não apenas em prompts.

---

## Outros projetos

### Barthô

Aplicação SaaS de finanças pessoais voltada à organização financeira, agregação de contas, análise de transações e geração de insights inteligentes.

### Open Finance BR MCP Server

Servidor open-source baseado em Model Context Protocol para o ecossistema brasileiro de Open Finance, projetado para expor capacidades financeiras padronizadas a agentes de IA por meio de interfaces controladas e auditáveis.

---

## Stack tecnológica

### IA Generativa e Orquestração

![LangGraph](https://img.shields.io/badge/-LangGraph-1C3C3C?style=flat)
![DSPy](https://img.shields.io/badge/-DSPy-blue?style=flat)
![LlamaIndex](https://img.shields.io/badge/-LlamaIndex-black?style=flat)
![Mem0](https://img.shields.io/badge/-Mem0-orange?style=flat)
![LiteLLM](https://img.shields.io/badge/-LiteLLM_Proxy-purple?style=flat)

* LangGraph
* DSPy
* LlamaIndex
* LangChain
* LiteLLM
* Mem0
* Model Context Protocol
* Arquiteturas Agent-to-Agent
* Roteamento semântico
* Retrieval-Augmented Generation
* Orquestração multiagente
* Tool calling estruturado
* Avaliação de LLMs e guardrails

### Cloud e Infraestrutura

![Azure](https://img.shields.io/badge/-Azure-0089D6?style=flat\&logo=microsoftazure\&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS_Bedrock-232F3E?style=flat\&logo=amazonaws\&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat\&logo=kubernetes\&logoColor=white)

* Microsoft Azure
* Amazon Web Services
* Azure OpenAI
* Amazon Bedrock
* Kubernetes
* Docker
* API gateways
* Infraestrutura de IA baseada em VPC

### Dados e Backend

![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat\&logo=fastapi\&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat\&logo=postgresql\&logoColor=white)
![Redis](https://img.shields.io/badge/-Redis_Stack-DC382D?style=flat\&logo=redis\&logoColor=white)
![Qdrant](https://img.shields.io/badge/-Qdrant%2Fpgvector-DC244C?style=flat)
![SQLAlchemy](https://img.shields.io/badge/-SQLAlchemy_2.0-red?style=flat)

* Python
* FastAPI
* PostgreSQL
* Redis Stack
* RediSearch
* RedisJSON
* Qdrant
* pgvector
* SQLAlchemy 2.0
* Pydantic
* Processamento assíncrono
* Arquiteturas orientadas a eventos
* APIs REST

### Frontend

![React](https://img.shields.io/badge/-React%2FNext.js-black?style=flat\&logo=react\&logoColor=61DAFB)

* React
* Next.js
* TypeScript

### Segurança de IA e Observabilidade

![Zscaler](https://img.shields.io/badge/-Zscaler-1E3A5F?style=flat)
![LLM Guard](https://img.shields.io/badge/-LLM_Guard-red?style=flat)
![Langfuse](https://img.shields.io/badge/-Langfuse-black?style=flat)
![Entra ID](https://img.shields.io/badge/-Entra_ID-0078D4?style=flat\&logo=microsoftazure\&logoColor=white)

* OpenTelemetry
* Langfuse
* Datadog
* Logging estruturado
* Tracing
* Correlação de requisições
* Detecção e redação de PII
* LLM Guard
* Zscaler
* Microsoft Entra ID
* Proteção contra prompt injection
* Governança de acesso a modelos
* Gerenciamento de secrets
* Governança de servidores MCP

### Frameworks de governança

`NIST AI RMF 1.0` · `ISO/IEC 42001:2023` · `OWASP LLM Top 10` · `OWASP Agentic Security Guidance` · `NIST SP 800-53r5` · `CIS Controls v8.1` · `MITRE ATLAS`

### Engenharia Python

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat\&logo=python\&logoColor=white)

* `uv`
* `pyproject.toml`
* `ruff`
* `mypy --strict`
* `import-linter`
* `pytest`
* `pydantic`
* `bandit`
* `pip-audit`
* Clean Architecture
* Arquitetura Hexagonal
* Princípios SOLID
* Aplicações Twelve-Factor
* Injeção de dependências
* Processamento idempotente

---

## Áreas de interesse

* Plataformas corporativas de IA generativa
* Arquitetura de IA para instituições financeiras
* Sistemas de IA agêntica
* Orquestração multiagente
* Model Context Protocol
* Comunicação Agent-to-Agent
* Desenvolvimento de software seguro assistido por IA
* Segurança de aplicações com LLMs
* RAG sensível a autorização
* Observabilidade e avaliação de IA
* Governança de IA e conformidade regulatória
* Adoção corporativa de agentes de desenvolvimento
* Engenharia responsável de IA

---

## Aberto a oportunidades

Tenho interesse em oportunidades como:

* **Staff AI Engineer**
* **Principal AI Engineer**
* **Generative AI Architect**
* **AI Platform Architect**
* **AI Governance Architect**
* **AI Security Architect**

Tenho interesse especial em posições que combinem engenharia com arquitetura, segurança, governança e adoção corporativa de IA em escala.

---

<div align="center">

### Vamos conversar

📫 **[bfvicco@gmail.com](mailto:bfvicco@gmail.com)**
💼 [linkedin.com/in/brunovicco](https://linkedin.com/in/brunovicco)

</div>

<!-- Métricas privadas do perfil -->

<img src="https://u8views.com/api/v1/github/profiles/38844444/views/day-week-month-total-count.svg" width="1" height="1" alt="">

<div align="center">

🇧🇷 **Português** &nbsp;|&nbsp; 🇺🇸 [English](README.md)

# Bruno Freitas Vicco

### Especialista e Arquiteto em IA Generativa | Governança de IA para Instituições Financeiras Reguladas

📍 São Paulo, Brasil &nbsp;|&nbsp; 🌍 Aberto a relocação

[![LinkedIn](https://img.shields.io/badge/LinkedIn-brunovicco-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/brunovicco)
[![Email](https://img.shields.io/badge/Email-bfvicco%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bfvicco@gmail.com)

</div>

---

## Sobre mim

Construo sistemas de IA generativa de produção e, ao mesmo tempo, desenho a governança regulatória que os torna auditáveis em bancos e asset managers. É uma combinação pouco comum: a maioria dos profissionais domina apenas engenharia (LLMOps) ou apenas política (governança); eu atuo nas duas frentes, dentro de instituições financeiras brasileiras reguladas.

---

## Trajetória

22 anos no setor bancário, dos quais 17 na **Caixa Econômica Federal** (banking corporativo, tesouraria, superintendências regional e nacional), seguidos por posições de engenharia no **BTG Pactual**, **Cast Group** (alocado no Banco do Brasil), **Itaú Unibanco** e, mais recentemente, **ASA SCFI**, onde fui a primeira contratação dedicada a IA.

### No ASA:

**1. Plataforma Conversacional Bancária**

Refatoração para arquitetura hexagonal com orquestração via LangGraph, tratamento de identidade orientado à LGPD e observabilidade distribuída completa, projetada para que compliance e auditabilidade sejam propriedades estruturais, não adições posteriores.

<details>
<summary><b>Detalhes técnicos</b></summary>
<br>

- Refatoração para arquitetura hexagonal, com separação clara entre domínio, aplicação, infraestrutura, apresentação e composition root
- Orquestração de modelos e fluxos conversacionais com LangGraph, roteamento cognitivo e serviços especializados por domínio
- Identidade pseudonimizada com HMAC-SHA256, isolamento por sessão/thread e proteção de dados orientada à LGPD
- Processamento multicanal síncrono e assíncrono via FastAPI, workers, e Redis, com idempotência e gerenciamento de checkpoints
- Observabilidade distribuída com OpenTelemetry e Langfuse, logging estruturado, correlação de requisições e redação automática de PII
- Autenticação desacoplada por contexto seguro com TTL no Redis, evitando que tokens sensíveis trafeguem pelos grafos e prompts
- Feature flags intercambiáveis via ambiente ou Flagsmith, permitindo rollout gradual e kill switches operacionais
- Injeção de dependências e ports/adapters para facilitar testes, substituição de provedores e evolução independente das integrações

</details>

**2. Assistente de Investimentos (subgrafo especializado)**

Um subgrafo LangGraph compliance-first combinando roteamento validado por DSPy, autocorreção de respostas e recuperação apoiada em Redis, arquitetado para que compliance CVM/ANBIMA e suitability sejam garantidos estruturalmente, antes mesmo de o modelo ver qualquer opção.

<details>
<summary><b>Detalhes técnicos</b></summary>
<br>

- Roteamento semântico próprio com scoring negativo-aware - detecção de ambiguidade em três regras (threshold por intenção, piso absoluto e margem entre candidatos) e invalidação automática de cache por fingerprint SHA-256 do catálogo
- Contratos de saída do LLM com DSPy: Signature declarativa, validação Pydantic (`RouterOutput` com tipos `Literal`) e camada de coerção fail-safe que absorve drift de formato antes de qualquer tool call
- Autocorreção de resposta via `dspy.Refine` com reward function de compliance — disclaimer, terceira pessoa, ausência de imperativo e de opinião sobre carteira - regenerando até atingir nota máxima ou esgotar o orçamento de tentativas
- Compliance como propriedade da arquitetura: critique node validando CVM/ANBIMA por regex e injetando disclaimers obrigatórios antes da entrega, com suitability filtrada na prateleira de produtos *antes* que o modelo veja qualquer opção (CVM Res. 30)
- Toolset especializado sobre `BaseTool` assíncrono, instanciado dinamicamente por turno: prateleira de mercado com filtros semânticos, consulta de portfólio por ativo e consolidada por classe, detalhamento de produto sob demanda e busca em conteúdo editorial/house view
- Geração de relatórios em PDF via ReportLab a partir do estado da conversa, entregando ao cliente um artefato consolidado do portfólio e das análises discutidas
- Modelagem fat/slim no Redis Stack: projeção enxuta indexada em RediSearch para busca e ranqueamento, documento completo via `JSON.GET` apenas para os itens que efetivamente entram no contexto
- QueryBuilder com taxonomia explícita de campos (TAG por match exato, TEXT com fuzzy Levenshtein e regras de tokenização, NUMERIC por range), escaping de caracteres especiais do RediSearch e row-level security obrigatória por CPF construída em código - não delegada ao modelo
- Sanitização anti-injection do input que alcança o RediSearch: bloqueio de verbos de agregação e comando, limite de comprimento e rejeição de caracteres de controle, com fail-safe para wildcard
- Resolução de anáfora com pilha de entidades no Redis - LIFO limitada, dedup semântica e TTL curto - injetando as entidades resolvidas na query antes do DSPy, sem exigir que o modelo aprenda a resolver pronomes
- Pre-warm assíncrono do portfólio, retirando a carga do caminho crítico do primeiro turno e tornando a latência independente do tamanho da carteira
- Métricas de roteamento em HASH Redis (`HINCRBY` com TTL rolante), agregando corretamente entre workers sem coordenação, com alarme de degradação por taxa de fallback

</details>

**3. Governança de IA Corporativa**
- Rollout do Claude Code para ~250 desenvolvedores
- Implantação do claude.ai Enterprise para ~150 usuários
- Security hooks, allowlist de servidores MCP, Gateway Prompt Security self-hosted (in-VPC)
- AI Academy interna com trilhas de certificação

**Escopo regulatório:** BACEN/CMN, LGPD, CVM, ANBIMA mapeados internacionalmente contra EU AI Act, DORA, NIST AI RMF 1.0 e ISO/IEC 42001:2023.

---

## Projetos em destaque

### [`meridian`](https://github.com/brunovicco/meridian)
Arquitetura de referência para um assistente de conhecimento corporativo: roteamento semântico validado por DSPy, RAG com controle de acesso (ACL) - aplicado *dentro* da busca vetorial, nunca delegado ao modelo -, queries estruturadas compiladas para RediSearch, e modelagem fat/slim no Redis. Roda com zero configuração usando provedores fake determinísticos, ou com DSPy + Groq reais. Clean Architecture, configuração Twelve-Factor, 52 testes.

### [`claude-code-crypto-lab`](https://github.com/brunovicco/claude-code-crypto-lab)
Laboratório prático de Claude Code construído em torno de um app educacional de portfólio cripto. Demonstra subagents, skills, hooks determinísticos que bloqueiam comandos perigosos e prompts fora de escopo, servidor MCP local e CI/CD - totalmente bilíngue (EN/PT-BR).

### [`claude-python-engineering-harness`](https://github.com/brunovicco/claude-python-engineering-harness)
Harness reutilizável de Claude Code para times de engenharia Python: script de bootstrap de projeto, scaffolding de `CLAUDE.md`/`AGENTS.md`, camada de governança de MCP opt-in e hooks de segurança fail-closed - construído sobre o princípio de que instrução não é controle: políticas que precisam ser garantidas vivem em hooks e gates de CI, não apenas em prompts.

### Projetos pessoais
- **Barthô**: aplicativo SaaS de finanças pessoais
- **Open Finance BR MCP Server**: servidor MCP open-source para o ecossistema de Open Finance brasileiro

---

## Stack

**GenAI/Orquestração**
![LangGraph](https://img.shields.io/badge/-LangGraph-1C3C3C?style=flat) ![DSPy](https://img.shields.io/badge/-DSPy-blue?style=flat) ![LlamaIndex](https://img.shields.io/badge/-LlamaIndex-black?style=flat) ![Mem0](https://img.shields.io/badge/-Mem0-orange?style=flat) ![LiteLLM](https://img.shields.io/badge/-LiteLLM_Proxy-purple?style=flat)

**Cloud/Infra**
![Azure](https://img.shields.io/badge/-Azure-0089D6?style=flat&logo=microsoftazure&logoColor=white) ![AWS](https://img.shields.io/badge/-AWS_Bedrock-232F3E?style=flat&logo=amazonaws&logoColor=white) ![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white) ![Pulumi](https://img.shields.io/badge/-Pulumi%2FOpenTofu-5C4EE5?style=flat)

**Dados/Backend**
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat&logo=fastapi&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/-Redis_Stack-DC382D?style=flat&logo=redis&logoColor=white) ![Qdrant](https://img.shields.io/badge/-Qdrant%2Fpgvector-DC244C?style=flat) ![SQLAlchemy](https://img.shields.io/badge/-SQLAlchemy_2.0-red?style=flat)

**Frontend**
![React](https://img.shields.io/badge/-React%2FNext.js-black?style=flat&logo=react&logoColor=61DAFB) ![shadcn/ui](https://img.shields.io/badge/-shadcn%2Fui-black?style=flat)

**AI Security & Observability**
![Zscaler](https://img.shields.io/badge/-Zscaler-1E3A5F?style=flat) ![LLM Guard](https://img.shields.io/badge/-LLM_Guard-red?style=flat) ![Presidio](https://img.shields.io/badge/-Presidio-orange?style=flat) ![Langfuse](https://img.shields.io/badge/-Langfuse-black?style=flat) ![Entra ID](https://img.shields.io/badge/-Entra_ID-0078D4?style=flat&logo=microsoftazure&logoColor=white)

**Frameworks de governança**
`NIST AI RMF 1.0` · `ISO/IEC 42001:2023` · `OWASP LLM Top 10 (2025)` · `OWASP Agentic Top 10 (2026)` · `NIST SP 800-53r5` · `CIS v8.1` · `MITRE ATLAS`

**Qualidade de código Python**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white) `ruff` · `mypy --strict` · `import-linter` · `pytest` · `pydantic`

---

## Aberto a

Buscando ativamente posições de **Staff/Principal AI Engineer** ou **AI Governance Architect**.

---

<div align="center">

📫 **bfvicco@gmail.com** &nbsp;|&nbsp; 💼 [linkedin.com/in/brunovicco](https://linkedin.com/in/brunovicco)

</div>

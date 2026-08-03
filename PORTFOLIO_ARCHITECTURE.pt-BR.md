# Mapa de Arquitetura do Portfólio

> 🇺🇸 [Read in English](./PORTFOLIO_ARCHITECTURE.md)

Este portfólio foi organizado como um ecossistema, e não como uma coleção de demonstrações isoladas.

Os projetos exploram como construir, operar, avaliar, observar e governar sistemas de IA em ambientes regulados. Todos seguem a mesma direção arquitetural:

- manter decisões críticas de negócio em componentes determinísticos;
- colocar LLMs atrás de contratos explícitos e responsabilidades limitadas;
- tratar agentes, servidores MCP, provedores de modelos e telemetria como fronteiras de confiança;
- incorporar segurança, avaliação, proveniência e auditabilidade à arquitetura;
- vincular aprovações ao escopo exato revisado;
- usar agentes de código sob controles pertencentes ao repositório.

## Mapa do ecossistema

```mermaid
flowchart TB
    subgraph GOVERNANCE["Plano de Governança e Assurance de IA"]
        direction LR
        VAG["Verifiable AI Governance<br/><small>Inventário, risco, controles, aprovações,<br/>evidências, enforcement e auditoria</small>"]
    end

    subgraph CONTROL["Plano de Controle da Engenharia Assistida por IA"]
        direction LR
        LS["engineering-loop-schemas<br/><small>Contratos, evidências e veredictos canônicos</small>"]
        AL["Alicerce<br/><small>Execução confiável e loops baseados em evidências</small>"]
        CH["Claude Python<br/>Engineering Harness"]
        CX["Codex Python<br/>Engineering Harness"]

        LS -->|"define contratos"| AL
        LS -->|"padroniza evidências"| CH
        LS -->|"padroniza evidências"| CX
        AL -.->|"execução governada"| CH
        AL -.->|"execução governada"| CX
    end

    subgraph PLATFORM["Serviços Compartilhados da Plataforma de IA"]
        direction LR
        PMR["Policy Model Router<br/><small>Seleção determinística de modelos</small>"]
        OTEL["a2a-otel-kit<br/><small>Observabilidade segura para A2A e MCP</small>"]
    end

    subgraph APPS["Sistemas de IA de Domínio"]
        direction LR
        RF["RAGForge<br/><small>Benchmark regulatório de RAG</small>"]
        ME["Meridian<br/><small>Plataforma interna de conhecimento</small>"]
        OF["Open Finance BR MCP<br/><small>Ferramentas financeiras tipadas e consentimento</small>"]
        CD["Multi-Agent Credit Desk<br/><small>Análise auditável de crédito PJ</small>"]
    end

    VAG -->|"define controles e gates"| RF
    VAG -->|"define controles e gates"| ME
    VAG -->|"define controles e gates"| OF
    VAG -->|"define controles e gates"| CD
    VAG -->|"restringe escopo permitido"| PMR
    PMR -->|"decisão de roteamento"| VAG
    OTEL -->|"telemetria e eventos"| VAG
    AL -->|"evidências de engenharia"| VAG

    CH -->|"governa desenvolvimento"| RF
    CH -->|"governa desenvolvimento"| CD
    CH -->|"governa desenvolvimento"| PMR
    CX -->|"governa desenvolvimento"| ME

    PMR -->|"roteia modelos"| CD
    OTEL -->|"telemetria A2A"| CD
    OTEL -->|"telemetria MCP"| OF
    OF -.->|"fronteira financeira"| CD
    OTEL -.->|"adaptador de observabilidade"| AL

    subgraph PRINCIPLES["Princípios Transversais"]
        direction LR
        P1["Núcleo<br/>determinístico"]
        P2["Neutralidade<br/>de provedor"]
        P3["Segurança<br/>fail-closed"]
        P4["Evidência e<br/>proveniência"]
        P5["Autoridade<br/>humana explícita"]
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

## Camadas arquiteturais

### 1. Plano de Governança e Assurance de IA

#### [Verifiable AI Governance](https://github.com/brunovicco/verifiable-ai-governance)

Plataforma de referência neutra de fornecedor que transforma requisitos de governança em controles executáveis e evidências verificáveis.

Seu papel no portfólio é conectar:

```text
Contexto de negócio
    → inventário de iniciativas e sistemas
    → classificação de risco e impacto
    → controles aplicáveis
    → avaliações e aprovações independentes
    → evidências verificadas
    → assurance de modelos e agentes
    → enforcement em runtime
    → monitoramento, incidentes e revisão
```

As capacidades demonstradas incluem:

- inventário de iniciativas, sistemas, modelos e agentes;
- classificação preliminar de risco por motor determinístico e versionado;
- avaliações de impacto de IA, privacidade e processamento internacional;
- controles declarativos, versionados e com aplicabilidade explicável;
- segregação de funções, gates condicionais e rodadas de revisão imutáveis;
- evidências com validação de tipo, hash SHA-256, análise antimalware e armazenamento privado;
- aprovações vinculadas ao digest do escopo revisado;
- assurance independente de arquitetura para modelos e de segurança para agentes;
- validação do escopo aprovado antes do roteamento externo de modelos;
- incidentes, kill switch, exceções temporárias e remediação;
- trilha de auditoria encadeada por hash e comportamento fail-closed.

O projeto possui uma implementação funcional orientada à produção e uma [demo pública somente para leitura](https://vaigov-app.duckdns.org). Integrações corporativas selecionadas ainda dependem de validação em ambientes reais.

### 2. Sistemas de IA de domínio

Estes projetos demonstram como capacidades de IA são aplicadas a problemas concretos de negócio e engenharia.

| Projeto | Papel no portfólio | Ênfase atual |
|---|---|---|
| [RAGForge](https://github.com/brunovicco/ragforge) | Plataforma experimental para comparar estratégias de recuperação sobre normas financeiras e regulatórias brasileiras | Ingestão consciente da estrutura legal, recuperação esparsa/densa/híbrida, julgamentos de relevância e avaliação reproduzível |
| [Meridian](https://github.com/brunovicco/meridian) | Arquitetura de referência para uma plataforma interna de conhecimento de engenharia | Roteamento semântico, controle de acesso durante a recuperação, consultas estruturadas e respostas fundamentadas com citações |
| [Open Finance BR MCP](https://github.com/brunovicco/openfinance-br-mcp) | Fronteira MCP experimental para o Open Finance Brasil | Ferramentas tipadas, jornadas de consentimento, padrões de segurança FAPI-BR, execução mock-first e limites explícitos de validação |
| [Multi-Agent Credit Desk](https://github.com/brunovicco/multi-agent-credit-desk) | Plataforma multiagente incremental para análise auditável de crédito corporativo | Política de crédito determinística, dados sintéticos de bureau, fronteiras MCP/A2A e narrativas opcionais geradas por LLM |

### 3. Serviços compartilhados de plataforma de IA

Estes repositórios extraem capacidades reutilizáveis que não deveriam ser implementadas novamente dentro de cada aplicação.

#### [Policy Model Router](https://github.com/brunovicco/policy-model-router)

Serviço determinístico de roteamento que seleciona um grupo de modelos permitido somente após aplicar restrições de política e workload.

O Verifiable AI Governance pode vincular uma aprovação a grupos de modelos permitidos; o router continua responsável pela decisão técnica em runtime, sem conceder a si próprio autoridade para ampliar o escopo aprovado.

#### [a2a-otel-kit](https://github.com/brunovicco/a2a-otel-kit)

Biblioteca reutilizável de observabilidade para agentes A2A e serviços MCP.

Ela padroniza propagação de contexto, eventos estruturados, atributos baseados em allowlist, reporte seguro de falhas e operações em streaming, preservando a neutralidade em relação ao fornecedor de observabilidade.

### 4. Plano de controle da engenharia assistida por IA

Estes projetos tratam de como usar agentes de código sem delegar a eles autoridade sobre a engenharia.

#### [Claude Python Engineering Harness](https://github.com/brunovicco/claude-python-engineering-harness)

Scaffold reutilizável e plugin para Claude Code com instruções pertencentes ao repositório, skills, hooks, quality gates, fronteiras arquiteturais, políticas MCP e overlays opcionais de governança.

#### [Codex Python Engineering Harness](https://github.com/brunovicco/codex-python-engineering-harness)

Linha-base correspondente para fluxos com Codex, orientada a validação determinística em vez de autoavaliação pelo modelo.

#### [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas)

Contratos canônicos e neutros de provedor para loops de engenharia baseados em evidências. O builder pode relatar o que fez, mas não pode certificar o próprio resultado.

#### [Alicerce](https://github.com/brunovicco/alicerce)

Núcleo local confiável para loops determinísticos e auditáveis de engenharia, com identidade imutável da execução, estado durável, workspaces controlados, autorização de comandos, isolamento, evidência canônica e autoridade humana sobre promoção.

## Como os projetos se conectam

### Ciclo de governança

```mermaid
sequenceDiagram
    autonumber
    participant Owner as Responsável de negócio
    participant Gov as Verifiable AI Governance
    participant Review as Arquitetura, Segurança e Risco
    participant Evidence as Pipeline de evidências
    participant Router as Policy Model Router
    participant Runtime as Sistema de IA

    Owner->>Gov: Registra iniciativa, sistema e escopo
    Gov->>Gov: Classifica risco e determina controles
    Owner->>Evidence: Anexa evidências requeridas
    Evidence-->>Gov: Retorna artefatos verificados e hashes
    Gov->>Review: Abre gates independentes
    Review-->>Gov: Aprova, rejeita ou solicita correção
    Gov->>Gov: Vincula decisões ao digest do escopo

    alt Escopo aprovado
        Runtime->>Gov: Valida sistema, modelo ou agente
        Gov-->>Runtime: Retorna limites aprovados
        Runtime->>Router: Solicita modelo dentro dos limites
        Router-->>Runtime: Retorna rota permitida ou rejeição
    else Escopo não aprovado ou alterado
        Gov-->>Runtime: Rejeita de forma explícita
    end
```

### Fluxo de engenharia

```mermaid
sequenceDiagram
    autonumber
    participant Human as Humano
    participant Harness as Harness Claude/Codex
    participant Agent as Agente de código
    participant Alicerce
    participant Schemas as engineering-loop-schemas
    participant CI as Quality e Security Gates
    participant Gov as Verifiable AI Governance

    Human->>Harness: Define regras e critérios de aceitação
    Harness->>Agent: Fornece contexto e ações permitidas
    Agent->>Alicerce: Submete candidato
    Alicerce->>CI: Executa gates determinísticos
    CI-->>Alicerce: Retorna resultados e artefatos
    Alicerce->>Schemas: Monta evidências canônicas
    Schemas-->>Alicerce: Retorna Evidence validada
    Alicerce-->>Human: Entrega candidato e evidências
    Human->>Gov: Registra evidências e decisão de promoção
    Gov->>Gov: Preserva escopo, autoridade e histórico
```

### Fluxo de execução de IA

```mermaid
sequenceDiagram
    autonumber
    participant User as Usuário
    participant App as Sistema de IA
    participant Gov as Verifiable AI Governance
    participant Router as Policy Model Router
    participant MCP as Ferramentas MCP
    participant Model as Modelo
    participant OTel as a2a-otel-kit / OTLP

    User->>App: Envia solicitação
    App->>App: Autentica, autoriza e aplica políticas locais
    App->>Gov: Valida escopo aprovado

    alt Sistema, modelo e agente aprovados
        Gov-->>App: Retorna limites e grupos permitidos
        App->>Router: Solicita grupo de modelos
        Router-->>App: Retorna decisão
        opt Ferramentas necessárias
            App->>MCP: Executa chamada limitada e tipada
            MCP-->>App: Retorna resultado ou rejeição
        end
        App->>Model: Envia contexto aprovado e contrato de saída
        Model-->>App: Retorna saída estruturada
        App->>App: Valida estrutura, fundamentação e políticas
        App-->>OTel: Emite telemetria sanitizada
        App-->>User: Retorna resposta permitida
    else Escopo ausente, inválido ou alterado
        Gov-->>App: Rejeita explicitamente
        App-->>OTel: Registra rejeição sanitizada
        App-->>User: Retorna falha segura
    end
```

## Princípios compartilhados

### Decisões determinísticas antes do comportamento generativo

Resultado de crédito, controle de acesso, autorização de comandos, avaliação de políticas, classificação preliminar de risco e promoção permanecem fora do LLM.

### Núcleo neutro de provedor, integrações nas bordas

Regras de negócio e modelos de domínio não dependem diretamente de um provedor de modelo, framework de agentes ou fornecedor de observabilidade.

### Segurança aplicada na fronteira

Ferramentas MCP, provedores, chamadas entre agentes, documentos recuperados, exportadores de telemetria, execução de código, Git e filesystem são tratados como fronteiras de confiança.

### Evidência em vez de sucesso autorrelatado

Afirmações importantes são vinculadas a comandos, outputs, políticas, commits, ambientes, hashes, escopos e decisões verificáveis.

### Aprovação vinculada ao escopo

Uma aprovação não autoriza qualquer versão futura do sistema. Mudanças materiais em dados, modelos, agentes, ferramentas, região ou finalidade exigem nova análise.

### Autoridade humana explícita

Agentes podem preparar candidatos, coletar evidências e propor decisões. Aprovações, exceções, promoção, merge, deploy e ações de alto impacto permanecem sob autoridade humana ou organizacional explícita.

## Mapa de maturidade

| Projeto | Maturidade | O que está comprovado hoje | Próxima prova principal |
|---|---|---|---|
| Verifiable AI Governance | Release funcional v0.1.0 | Inventário, risco determinístico, avaliações, controles, aprovações, evidências, assurance de modelos/agentes, enforcement em runtime, incidentes e auditoria encadeada por hash | Validar Entra ID e integrações corporativas reais; incorporar telemetria e efetividade de controles |
| RAGForge | Desenvolvimento ativo | Ingestão regulatória, chunking estrutural, estratégias de recuperação e métricas de relevância | Completar a matriz de benchmarks e publicar resultados reproduzíveis |
| Meridian | Implementação de referência | Demo sem setup, roteamento, recuperação com ACL e consultas estruturadas | Walkthrough público e perfil completo de deploy |
| Open Finance BR MCP | Release experimental | Ambiente mock, superfície MCP tipada, consentimento e fundamentos de segurança | Validação em sandboxes oficiais e configurações reais |
| Multi-Agent Credit Desk | Construção incremental | Núcleo determinístico, serviços MCP, primeiro agente A2A e fluxo sintético de KYC | Orquestração, pacote decisório ponta a ponta e observabilidade |
| Policy Model Router | Serviço inicial | Núcleo determinístico de roteamento e publicação de imagem | Catálogo de políticas, métricas e exemplos de consumo |
| a2a-otel-kit | Biblioteca reutilizável | Propagação A2A/MCP, eventos sanitizados e testes de integração | Adoção mais ampla pelos serviços do portfólio |
| engineering-loop-schemas | Fundação versionada | Contratos e modelos canônicos de evidência | Avaliador no nível de completion e contratos operacionais |
| Alicerce | Phase 2A | Workspace confiável, sandbox, estado, autorização e primitivas de evidência | Evidência completa, persistência e orquestração retomável |
| Harnesses Claude/Codex | Linha-base reutilizável | Scaffolding, quality gates, hooks, políticas e perfis de governança | Integração com o loop completo do Alicerce |

## Narrativa do portfólio

Juntos, os projetos sustentam uma única tese profissional:

> Sistemas de IA em produção exigem mais do que integração com modelos. Precisam de fronteiras determinísticas, autoridade explícita, qualidade mensurável, observabilidade segura, evidências reproduzíveis e governança capaz de vincular decisões ao escopo real do runtime.

```text
Contexto e finalidade
    → inventário e classificação de risco
    → controles, avaliações, evidências e aprovações
    → núcleo determinístico de negócio
    → capacidade de IA limitada
    → política de modelos e ferramentas
    → observabilidade e avaliação
    → engenharia assistida por IA com segurança
    → incidentes, revisão e melhoria contínua
```

## Trilhas sugeridas de leitura

### Governança, risco e assurance de IA

1. [Verifiable AI Governance](https://github.com/brunovicco/verifiable-ai-governance)
2. [Policy Model Router](https://github.com/brunovicco/policy-model-router)
3. [a2a-otel-kit](https://github.com/brunovicco/a2a-otel-kit)
4. [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas)

### Arquitetura e plataforma de IA

1. [Alicerce](https://github.com/brunovicco/alicerce)
2. [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas)
3. [a2a-otel-kit](https://github.com/brunovicco/a2a-otel-kit)
4. [Policy Model Router](https://github.com/brunovicco/policy-model-router)

### RAG e LLM Engineering

1. [RAGForge](https://github.com/brunovicco/ragforge)
2. [Meridian](https://github.com/brunovicco/meridian)
3. [Open Finance BR MCP](https://github.com/brunovicco/openfinance-br-mcp)

### IA em serviços financeiros

1. [Multi-Agent Credit Desk](https://github.com/brunovicco/multi-agent-credit-desk)
2. [Open Finance BR MCP](https://github.com/brunovicco/openfinance-br-mcp)
3. [RAGForge](https://github.com/brunovicco/ragforge)
4. [Verifiable AI Governance](https://github.com/brunovicco/verifiable-ai-governance)

### AI Enablement e produtividade de desenvolvimento

1. [Claude Python Engineering Harness](https://github.com/brunovicco/claude-python-engineering-harness)
2. [Codex Python Engineering Harness](https://github.com/brunovicco/codex-python-engineering-harness)
3. [Alicerce](https://github.com/brunovicco/alicerce)
4. [engineering-loop-schemas](https://github.com/brunovicco/engineering-loop-schemas)

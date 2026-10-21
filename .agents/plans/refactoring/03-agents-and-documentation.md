# 03 - Refatoração de Agentes, Skills e Documentação

## Objetivos Globais
Atualizar a identidade do projeto nas ferramentas de IA (skills e routers) para refletir o escopo generalista do **Academic Lab**. O repositório deixará de ser focado exclusivamente em assuntos específicos (ex: Revit) e se tornará uma base universal focada em estudos acadêmicos impulsionados por Inteligência Artificial.

---

## Fases da Refatoração

### Fase 1: Atualização das Skills (com `skill-expert`)
Todas as skills customizadas precisam ser adaptadas ao novo propósito do monorepo.
- [ ] Inspecionar todas as skills ativas em `.agents/skills/`.
- [ ] Utilizar a skill `skill-expert` para refatorar os arquivos `SKILL.md` (e potenciais scripts) adequando o contexto para pertencer ao projeto `@tupynambalucas/academic-lab`.
- [ ] Assegurar que as instruções das skills estão coerentes com a nova estrutura de documentação (ex: nova estrutura do Docusaurus e pasta `handbook`).

### Fase 2: Criação do Contexto de Estudo do Usuário (`LEARNING_CONTEXT.md`)
Como o repositório agora é genérico para estudos acadêmicos, precisamos de um mecanismo para que o agente entenda o foco atual do usuário (o pesquisador/estudante).
- [ ] Criar o arquivo `LEARNING_CONTEXT.md` na raiz do projeto.
- [ ] Estruturar o arquivo como um **template** (instruindo o usuário a preencher seus objetivos, área de estudo, projeto acadêmico atual, etc.).
- [ ] Modificar o arquivo `.agents/AGENTS.md` para referenciar/incorporar este novo arquivo (`LEARNING_CONTEXT.md`), permitindo que a IA sempre conheça os objetivos momentâneos do estudante.

### Fase 3: Generalização dos Routers de Agentes (com `agent-router-expert`)
Os arquivos que guiam o comportamento padrão das IAs no repositório devem ser atualizados.
- [ ] Atualizar o `AGENTS.md` da raiz: remover menções hardcoded a ferramentas específicas (como Autodesk Revit) e focar na persona de um "Assistente de Pesquisa e Documentação Acadêmica".
- [ ] Atualizar os demais `AGENTS.md` das subpastas (ex: `docs/AGENTS.md`, `.agents/AGENTS.md`) para refletirem a nova hierarquia de pastas e a visão generalista apoiada por IA.

### Fase 4: Atualização dos READMEs (com `markdown-expert`)
A documentação legível por humanos deve ser sincronizada com a nova missão do projeto.
- [ ] Atualizar o `README.md` raiz para descrever o Academic Lab como um ecossistema de estudos acadêmicos guiados por IA.
- [ ] Refatorar os `README.md` das workspaces internas (`docs`, `config`, etc) para refletirem seus papéis simplificados e puramente técnicos dentro do monorepo.

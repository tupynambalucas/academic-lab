# Plano Geral de Refatoração do Monorepo

Este documento centraliza e rege as etapas de refatoração necessárias para estruturar o monorepo do projeto Knowledge Lab de forma limpa, previsível e escalável.

## Índice de Etapas

### 1. [Refatoração Inicial do Monorepo](./01-initial-monorepo.md) (Concluída)
Foco inicial na raiz do projeto: limpeza de `pnpm-workspace.yaml`, padronização rigorosa do `eslint.config.ts`, remoção de dependências mortas (relacionadas a um workspace antigo `app`), e padronização dos namespaces dos pacotes para `@tupynambalucas/*`.

### 2. [Refatoração e Estruturação das Workspaces (Config e Docs)](./02-workspaces-refactoring.md)
Foco na padronização estrutural de `docs` (remoção da pasta docusaurus e centralização) e unificação das namespaces para `@knowledge-lab/*`.

### 3. [Refatoração de Agentes, Skills e Documentação](./03-agents-and-documentation.md)
Foco na generalização do projeto para "estudos acadêmicos impulsionados por IA". Inclui a atualização de todas as skills, a revisão profunda de `AGENTS.md` e `README.md` (removendo viés de assuntos específicos) e a criação do template `LEARNING_CONTEXT.md` na raiz.

### 4. [Personalização e Variáveis Dinâmicas](./04-personalization-and-config.md)
Refatoração de `config/src/project.config.ts` para atuar como o perfil do pesquisador. O arquivo deixará de focar no nome do projeto e passará a definir o estudante, a lista do que ele está estudando, além de alimentar dados do Docusaurus (siteTitle, idioma) e oferecer contexto técnico dinâmico para os arquivos `AGENTS.md`.

---
*Nota: Siga os arquivos linkados acima para ver o detalhamento rigoroso de cada tarefa.*

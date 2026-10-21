# 01 - Refatoração Inicial do Monorepo

## Objetivos
- Revisar e adequar os arquivos de configuração raiz para o formato final do monorepo.
- Limpar configurações não utilizadas (herdados de repositórios antigos).

## Tarefas Realizadas
- [x] **`pnpm-workspace.yaml`**: Atualizado para incluir apenas as workspaces ativas (`config` e `docs`) e removidas dependências de catálogos não utilizados.
- [x] **`eslint.config.ts`**: Adotadas as regras globais empresariais que estavam comentadas e removidos os blocos de regras antigos de uma workspace `app` inexistente.
- [x] **Estrutura de Diretórios**: A pasta `knowledge-base` foi renomeada para `docs`.
- [x] **Nomes dos Pacotes (`package.json`)**: Os campos `name` foram atualizados para seguir o padrão `@tupynambalucas/*` (ex: `@tupynambalucas/config`, `@tupynambalucas/docs-portal`).
- [x] **Dependências Internas**: Substituídas as referências `@monorepo/*` antigas para o novo padrão `@tupynambalucas/*` globalmente.

## Próximos Passos
- [ ] Revisar configurações gerais de Typescript (`tsconfig.json` raiz).
- [ ] Avaliar configurações do Prettier e outras ferramentas base para o ecossistema.

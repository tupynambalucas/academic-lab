# 02 - Refatoração das Workspaces (Config e Docs)

## Objetivos Globais
A reestruturação visa centralizar a arquitetura do Docusaurus diretamente na pasta `website`, eliminando a separação complexa entre pacotes de presets, themes e portal.

---

## Fases da Refatoração

### Fase 1: Centralização na Estrutura Padrão do Docusaurus
Iremos eliminar a pasta `docusaurus`, bem como os workspaces separados para `preset` e `theme`. O projeto seguirá a arquitetura recomendada pela documentação oficial do Docusaurus, onde plugins locais residem em `src/plugins` e temas customizados residem em `src/theme`.
- [ ] Mover o portal `docs/docusaurus/services/portal` para a raiz `docs/website`.
- [ ] Mover todo o conteúdo de plugins locais de `docs/docusaurus/packages/preset/src/plugins` para `docs/website/src/plugins`.
- [ ] Mover o código de customização visual de `docs/docusaurus/packages/theme/src` (ou arquivos correspondentes do tema) para `docs/website/src/theme`.
- [ ] Remover as pastas `docs/docusaurus`, `preset` e `theme` que ficaram vazias/obsoletas.

### Fase 2: Reestruturação do Conteúdo (`content`)
Os arquivos markdown da documentação precisam ser isolados e melhor categorizados para atuar como o centro de conhecimento.
- [ ] Renomear a atual pasta `docs/collections` para `docs/content`.
- [ ] Criar a subpasta interna `docs/content/collections`.
- [ ] Mover o conteúdo de `docs/content/namespaces/portal/content/*` para dentro da nova pasta `collections`.
- [ ] Renomear a subpasta `docs` (movida de portal/content/docs) para `handbook` (O caminho final será `docs/content/collections/handbook`).
- [ ] Remover o aninhamento e pastas vazias (ex: `namespaces/portal/content/`).

### Fase 3: Padronização de Namespaces (`@knowledge-lab`)
Todos os `package.json` de todas as workspaces e subpastas devem ser analisados recursivamente para usar o novo namespace do projeto:
- [ ] Alterar os campos `name` nos `package.json` para o padrão `@knowledge-lab/*` (Exemplo: `@knowledge-lab/docs-content`, `@knowledge-lab/docs-website`, `@knowledge-lab/config`).
- [ ] Atualizar todas as dependências internas nestes `package.json` para refletirem os novos nomes.
- [ ] Atualizar referências no `package.json` raiz (`scripts` e `dependencies`).

### Fase 4: Refatoração de Plugins e docusaurus.config.ts
O novo website será puramente técnico, minimalista, de idioma único e focado.
- [ ] Remover completamente o plugin `locales-sync` (sincronização de traduções) e configurações do Crowdin / i18n do `docusaurus.config.ts`.
- [ ] Remover os plugins de webpack (`webpack-loaders`), bem como apagar suas invocações.
- [ ] Identificar e remover completamente o script e lógica de `changelog` (ex: `tooling/generate-changelog.ts` e scripts no package.json).
- [ ] Atualizar as instâncias de documentação no `docusaurus.config.ts` (ou chamadas do plugin `content-docs` local) para declarar a nova pasta `handbook` como sua **única instância padrão**. Remover a instância `community` e `blog`.
- [ ] Alterar o `docusaurus.config.ts` para carregar os plugins locais a partir das pastas relativas `./src/plugins/*`.

### Fase 5: Limpeza do Website (`docs/website`)
O foco deve estar no texto. Todo o "peso" visual herdado deve ser eliminado.
- [ ] Remover a dependência de pacotes obsoletos como `studio-assets` do package.json do website e da lógica de sincronização no `docusaurus.config.ts`.
- [ ] Configurar o docusaurus para usar somente a sua pasta `static` padrão, limpa.
- [ ] Refatorar a página inicial (`src/pages/home` ou `src/pages/index`) para ser uma Home simples e descritiva voltada exclusivamente para o projeto **Knowledge Lab**.

### Fase 6: Alinhamento de Configurações (Root e TSConfig)
Garantir que o monorepo compreenda a nova forma da arquitetura achatada.
- [ ] **`pnpm-workspace.yaml`**: Atualizar a diretiva de workspaces para refletir explicitamente a nova estrutura mais simples:
  - `config`
  - `docs/content`
  - `docs/website`
- [ ] **TypeScript (`tsconfig.json`)**: Revisar a estrutura de `tsconfig.json` na raiz do projeto e em `docs/website` para garantir que referências (`references`) e mapeamento de caminhos (`paths`) apontam corretamente para os novos locais e namespaces `@knowledge-lab/*`.

# 04 - Personalização e Variáveis Dinâmicas

## Objetivos Globais
Tornar o monorepo `academic-lab` perfeitamente adaptável para diferentes estudantes ou pesquisadores que fizerem fork/deploy. Para isso, vamos refatorar o arquivo central de configurações (`project.config.ts`) de modo que ele sirva como a "bússola" de variáveis da pessoa, alimentando tanto a documentação gerada (Docusaurus) quanto fornecendo contexto estruturado para os Agentes de IA.

---

## Fases da Refatoração

### Fase 1: Refatoração do `project.config.ts`
O arquivo `config/src/project.config.ts` não deve mais manter informações fixas sobre o repositório (`REPOSITORY_NAME`, etc), pois isso estará implícito nos agentes. Ele deve exportar variáveis de personalização e estudo.
- [ ] Alterar o arquivo para exportar tipagens ricas focadas no usuário.
- [ ] Criar campos de identificação pessoal: `studentName`, `authorEmail`.
- [ ] Criar campos de contexto de estudo: `studyTopics` (array de strings, ex: `["Inteligência Artificial", "Arquitetura de Software"]`), `studyFocusDescription` (resumo em texto).
- [ ] Criar campos de configuração da documentação (`docs`): `siteTitle`, `siteTagline`, `docsLanguage` (padrão `"pt-BR"`), `primaryColor`.

### Fase 2: Integração com Docusaurus (`docs/website`)
O Docusaurus deve consumir puramente o `project.config.ts` para sua renderização, garantindo que o deploy do site mude de nome e foco assim que as variáveis da pessoa mudarem.
- [ ] Atualizar `docusaurus.config.ts` para buscar o `title`, `tagline` e linguagens (i18n) a partir das novas variáveis do `project.config.ts`.
- [ ] Configurar os metadados e rodapés gerados para exibir os `studyTopics` e o `studentName`.

### Fase 3: Integração com os Agentes (`AGENTS.md`)
Além de alimentar a interface visual (Docusaurus), as variáveis de `project.config.ts` devem ser uma ponte vitalícia de contexto técnico para a Inteligência Artificial.
- [ ] Alterar o `AGENTS.md` (na raiz e em `.agents/`) para instruir explicitamente os agentes a lerem `config/src/project.config.ts` sempre que precisarem compreender **o que a pessoa está estudando e quais as suas matérias foco**.
- [ ] Clarificar no `AGENTS.md` a diferença entre os arquivos: 
  - `config/src/project.config.ts` dita as *variáveis rígidas, tópicos atuais e configurações do site*.
  - `LEARNING_CONTEXT.md` (criado na etapa 3) descreve de forma subjetiva os *objetivos e a jornada acadêmica* da pessoa.

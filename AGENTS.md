# Academic Lab Agent Context

This document serves as the root context router (Layer 1) for AI agents operating in the Academic Lab project.

## Agent Persona

- **Role**: Senior Academic Research & Study Assistant.
- **Tone**: Highly didactic, educational, clear, and accessible.
- **Target Audience**: The primary reader is a student/researcher engaged in academic studies.
- **Responsibility**: Organize, extract, and structure academic knowledge to support learning and planning. Always be didactic, breaking down complex topics step-by-step when creating plans and documentation. Assist in parsing external data via tools like Firecrawl and Context7, and maintain a highly structured knowledge hierarchy.

## Repository Entry Points

- [README.md](./README.md): The official developer and user entry point for the repository.

## Bounded Contexts

- [knowledge-base](./knowledge-base/AGENTS.md): The primary knowledge base and documentation hub.
  - [collections](./knowledge-base/collections/AGENTS.md): Documentation and blog collections workspace.
  - [packages/preset](./knowledge-base/packages/preset/AGENTS.md): Custom Docusaurus preset workspace.
  - [packages/theme](./knowledge-base/packages/theme/AGENTS.md): Custom Docusaurus theme and stylesheet workspace.
  - [apps/main](./knowledge-base/apps/main/AGENTS.md): Main Docusaurus portal application.
- [config](./config/AGENTS.md): Project configuration workspace. The file [project.config.ts](./config/src/project.config.ts) acts as the programmatic source of truth for the user's hardcoded study topics, name, and website variables. Always read it to know what topics the user is formally studying.
- [LEARNING_CONTEXT.md](./LEARNING_CONTEXT.md): Subjective study goals and focus. Read this to understand the human's current academic journey and broader objectives.
- [.agents](./.agents/AGENTS.md): Automation, skills, plugins, and planning workspace.
  - [plans](./.agents/plans/): Directory dedicated to user-created execution and study plans.
  - [plugins](./.agents/plugins/): Directory dedicated to workspace plugins and MCP tool definitions.

## Global Constraints

- **Language Policy**:
  - All AGENTS.md and README.md files MUST be written in English (en-US).
  - All academic documentation in knowledge-base/ and plans in .agents/plans/ MUST be written in Portuguese (pt-BR).
- MUST NOT use emojis in any technical document, README, or skill file.
- MUST NOT use placeholders (e.g., TODO, TBD).
- MUST use relative paths for all Markdown links. Absolute filesystem paths are strictly forbidden.
- MUST format all files according to Prettier standards (2-space indent, max 100-character line width).

## Required Skills

When performing documentation tasks in this project, agents MUST activate the appropriate skill by name before beginning:

- **agent-router-expert**: MUST be active when creating, updating, or reviewing any AGENTS.md file anywhere in the repository. Defines the 3-layer context hierarchy standard, context-hierarchy directive syntax, line budgets, and validation workflow.
- **markdown-expert**: MUST be active when creating, updating, or reviewing any README.md, .md skill file, or general Markdown document across the repository.
- **docusaurus-expert**: MUST be active when extracting, creating, updating, or reviewing academic documentation in MDX format inside knowledge-base/ or configuring Docusaurus packages. Governs the Diátaxis framework, Portuguese (pt-BR) language standards, and MDX component syntax.
- **plugin-expert**: MUST be active when creating, structuring, or updating Antigravity plugins under .agents/plugins/.
- **skill-expert**: MUST be active when managing custom Agent Skills under .agents/skills/.

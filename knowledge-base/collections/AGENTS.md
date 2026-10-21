<context-hierarchy>
  <parent src="../../AGENTS.md" type="global-rules" />
  <parent src="../AGENTS.md" type="bounded-context-rules" />
  <system-instruction>
    AGENT: If you have not read "../../AGENTS.md" and "../AGENTS.md" in this session, stop now
    and read both files using your file-reading tools before proceeding.
  </system-instruction>
</context-hierarchy>

# Collections Workspace Context

This document serves as the sub-domain context router (Layer 3) for the collections/ workspace.

## Purpose

This workspace (`@academic-lab/collections`) stores modular documentation and blog collections that can be dynamically imported into Docusaurus portal applications.

## Directory Layout

- [docs/](./docs/): Documentation collections structured under the Diátaxis framework.
  - [docs/docs-template/](./docs/docs-template/): Base template covering explanation, guides, reference, and tutorials.
  - [docs/community-template/](./docs/community-template/): Community roadmap and ecosystem guides.
- [blogs/](./blogs/): Chronological and topic-based blog collections.
  - [blogs/blog-template/](./blogs/blog-template/): Default blog template with author and tag configurations.
- [package.json](./package.json): Workspace package manifest defining subpath exports.

## Scoped Guardrails

- MUST write all educational content inside docs/ and blogs/ in Brazilian Portuguese (pt-BR).
- MUST use the .mdx file extension for all content files.
- MUST structure documentation collections according to the four Diátaxis quadrants.
- MUST keep templates clean with overview.mdx, intro.mdx, and _category_.json files.
- MUST NOT use emojis or placeholder tokens.

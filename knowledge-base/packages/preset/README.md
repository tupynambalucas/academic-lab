# Preset Package

The `@knowledge-lab/preset` package is a custom Docusaurus preset providing dynamic collection resolution, integrated themes, and AST remark plugins for Knowledge Lab.

## Features

- **Dynamic Collection Resolution**: Automatically routes `collection: 'docs-template'` to `collections/docs/docs-template` and `collection: 'blog-template'` to `collections/blogs/blog-template`.
- **Theme Integration**: Registers `@docusaurus/theme-classic`, `@knowledge-lab/theme`, codeblock playgrounds, and Mermaid diagrams.
- **Remark Variable Transformer**: Injects project metadata into MDX frontmatter during compilation.
- **Standardized Navigation & Sidebars**: Exports pre-configured `getBaseThemeConfig` and `sidebars` ready for portal applications.

## Usage

In any Docusaurus application's `docusaurus.config.ts`:

```typescript
import type { MonorepoPresetOptions } from '@knowledge-lab/preset/options';

// Inside docusaurus.config.ts
presets: [
  [
    require.resolve('@knowledge-lab/preset'),
    {
      docs: [
        {
          id: 'default',
          collection: 'docs-template',
          routeBasePath: 'docs',
          sidebarPath: require.resolve('@knowledge-lab/preset/sidebars'),
        },
      ],
      blog: {
        collection: 'blog-template',
        routeBasePath: 'blog',
      },
    } satisfies MonorepoPresetOptions,
  ],
];
```

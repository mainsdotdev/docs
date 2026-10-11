# Mains documentation

The documentation for [Mains](https://mains.dev), a local workspace for AI agents across Code, Work, and Chat. Atlas holds Pages, documents, and images alongside your conversations.

The site uses [Mintlify](https://mintlify.com). Pages are `.mdx` files with YAML frontmatter. `docs.json` defines navigation and site configuration.

## Structure

- **Guides**: getting started, core concepts, Atlas, everyday workflows, scheduling, Mains Connect, and preferences.
- **Agents**: provider setup and provider-specific capabilities.
- **Integrations**: service connections, plugins, skills, MCP, and dependency guards.

Existing page paths remain stable even when their navigation group changes. In particular, the `/relay/*` paths now describe Mains Connect.

## Local development

Install the Mintlify CLI:

```bash
npm install -g mint
```

Run the preview from this repository:

```bash
mint dev
```

The default preview is `http://localhost:3000`.

Before publishing, run:

```bash
mint validate
mint broken-links
git diff --check
```

Preview changed tables, callouts, steps, and navigation. Every user-facing page should have a title, description, and navigation entry.

## Source of truth

The October 10, 2026 refresh was checked against the sibling `mains` repository at `81588428` (v0.17.0), its current implementation, and the live website. Verify behavior again when the implementation changes.

| Area | Main implementation references in `mains` |
| --- | --- |
| Modes and capabilities | `packages/contracts/src/modes.ts`, desktop mode configuration, provider capability adapters |
| Projects, workspaces, and runs | Backend project/workspace/run modules and desktop workspace UI |
| Atlas and Pages | Backend Atlas/Page modules and desktop Atlas UI |
| Provider settings and tools | Backend provider adapters, Mains tool registry, desktop provider settings |
| Connections and task context | Backend connections/sync modules and desktop Tasks UI |
| Pulse and Auto Sync | Backend Pulse/automation modules and desktop scheduling UI |
| Mains Connect, server, and mobile | Backend transport, `apps/server`, `apps/mobile`, desktop backend settings |
| Browser, Lens, voice, and shortcuts | Desktop main-process services and renderer feature/settings modules |

Read implementation and tests together when a README, release post, or old document disagrees with current behavior. Use official provider documentation for external prerequisites. Keep release announcements separate from shipping capabilities.

## Website link compatibility

The audit covered the website sitemap plus its Work, Atlas, and Bridge pages. These documentation destinations appeared in the live site and remain available in this repository:

- `/` → `introduction`
- `/file-explorer`
- `/relay/overview`
- `/runs`
- `/plugins`

Preserve these paths, or configure redirects and check all referring pages before moving them. Check both rendered links and the website sitemap during later audits.

## Publishing and support

Deploy through the repository's Mintlify integration after review. A local preview does not publish the changes.

For help, contact [team@mains.dev](mailto:team@mains.dev).

# Mains Documentation

The official documentation for **Mains** — a unified desktop workspace for AI coding agents.

Mains runs GitHub Copilot, Claude Code, OpenAI Codex, and Cursor side by side in managed, Git-backed workspaces, tracks every run with full observability, and syncs issues from the tools you already use — all from one app.

This repo holds the docs site, built with [Mintlify](https://mintlify.com). Content lives in the `.mdx` pages, and navigation is configured in `docs.json`.

## Local development

Install the [Mintlify CLI](https://www.npmjs.com/package/mint):

```bash
npm i -g mint
```

Then run the dev server from the repo root (where `docs.json` lives):

```bash
mint dev
```

Preview at `http://localhost:3000`.

## Publishing

Changes are deployed automatically once merged to the default branch via the Mintlify GitHub app.

## Help

- Docs not building? Run `mint update` to get the latest CLI.
- A page 404s? Make sure it's listed in `docs.json`.
- Questions: [team@mains.dev](mailto:team@mains.dev)

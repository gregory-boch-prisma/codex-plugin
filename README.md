# Prisma Codex Plugin Marketplace

This repo exposes a Prisma Codex plugin through `.agents/plugins/marketplace.json`.

## Install

Requires Codex CLI `0.125.0` or newer.

```bash
codex --version
```

If your Codex CLI does not show the `plugin` command, update it first:

```bash
bun add -g @openai/codex@latest
```

After this repo is published to GitHub, users can add the marketplace:

```bash
codex plugin marketplace add prisma/codex-plugin
```

Then open Codex and install the plugin:

```bash
codex
/plugins
```

Select the `Prisma` marketplace, open the `prisma` plugin, and choose install.

Users can also add the marketplace by URL:

```bash
codex plugin marketplace add https://github.com/prisma/codex-plugin.git
```

## Plugin

The plugin lives at `plugins/prisma` and bundles:

- Prisma CLI guidance
- Prisma Client API guidance
- Database setup guidance
- Prisma Postgres guidance
- Prisma ORM v7 upgrade guidance
- Prisma remote MCP server config

## Local testing

For development, from this repo root:

```bash
codex plugin marketplace add ./
```

The marketplace entry points to `./plugins/prisma`.

Restart Codex after editing the plugin so the installed local copy refreshes.

Destructive Prisma actions such as migration resets still require explicit user consent and review.

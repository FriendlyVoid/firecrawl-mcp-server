# CLAUDE.md — firecrawl-mcp-server (fork)

## What this is

A fork of [firecrawl/firecrawl-mcp-server](https://github.com/firecrawl/firecrawl-mcp-server)
— the official Firecrawl MCP server (search, scrape, crawl, extract for
MCP-compatible agents). The fork exists to build and publish the container
image under the fork owner's registry namespace
(`ghcr.io/friendlyvoid/firecrawl-mcp-server`) for self-hosted deployment.

## Fork delta

Kept deliberately minimal so upstream syncs stay trivial — see `PATCHES.md`
for the authoritative list. In short: only `.github/workflows/image.yml` is
changed (publishes to this fork's GHCR namespace on push to `main`); no
source-code changes.

## Key rules (repo-specific)

- **Do not edit upstream source** (`src/`, `Dockerfile`, package config).
  Local changes stay confined to the publishing workflow; anything else
  belongs in an upstream PR.
- **Sync via merge from upstream** (`upstream` remote is configured), then
  update `PATCHES.md` with the new upstream base.
- **Secrets:** `FIRECRAWL_API_KEY` etc. are runtime-injected by the consuming
  deployment. Never commit real env files (`.gitignore` blocks `*.env`;
  gitleaks CI enforces).

## Conventions

Repo-specific rules live here; the fork otherwise follows the maintainer's
shared cross-repo conventions (gitignore baseline, gitleaks CI, PATCHES.md
delta tracking for forks).

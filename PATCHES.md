# PATCHES.md — delta vs upstream

This file records what this fork changes relative to upstream, and which
upstream base the changes sit on.

## Upstream

- Upstream project: `firecrawl/firecrawl-mcp-server`
  (https://github.com/firecrawl/firecrawl-mcp-server); `upstream` remote is
  configured in this clone.
- Upstream base: `e30722e` ("bump") — last sync, merged via this fork's PR #1
  (merge commit `ac43f4f`).

## Fork-local changes

Verified via `git diff e30722e HEAD` — the entire delta is one file:

1. **`.github/workflows/image.yml`** (`08bfdea`): reworked the image-deploy
   workflow to build and push to `ghcr.io/${{ github.repository }}`
   (i.e. `ghcr.io/friendlyvoid/firecrawl-mcp-server`) on push to `main` and
   manual dispatch, with metadata-action tags.

No source-code, Dockerfile, or package changes vs upstream.

2. *(post-sync scaffolding, this repo only)*: `CLAUDE.md`, `PATCHES.md`,
   `.gitleaks.toml`, `.github/workflows/gitleaks.yml`, and `.gitignore`
   env-file hardening — fork housekeeping, not upstream-relevant.

## Updating

`git fetch upstream && git merge upstream/main`, resolve (only `image.yml`
can conflict), then update the upstream base SHA above.

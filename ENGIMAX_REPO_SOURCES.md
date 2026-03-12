# EngiMax Repo Sources (Online)
Last updated: 2026-03-12

Use this file as the canonical source map for online-only analysis.
If a URL changes, update this file first.

## 1. daydream-cms
- GitHub: https://github.com/DeDaydreamer/daydream-cms
- Primary branch: main
- Repo role: CMS API backend (Cloudflare Worker + D1 + KV)
- Key files:
  - AGENTS.md
  - docs/AI_CONTEXT.md
  - apps/api/wrangler.toml
  - docs/CLOUDFLARE_SETUP.md
  - docs/INTEGRATION_CONTRACT.md

## 2. DeDynamics-pro-site-vCodex
- GitHub: https://github.com/DeDaydreamer/DeDynamics-pro-site-vCodex
- Production branch: release/prod-site-v2
- Repo role: DeDynamics public site (Cloudflare Pages + Pages Functions support flow)
- Key files:
  - AGENTS.md
  - docs/AI_CONTEXT.md
  - SESSION-HANDOFF.md
  - version-control.md
  - CLOUDFLARE-RUNBOOK.md
  - functions/README.md

## 3. amethyst-mapper
- GitHub: https://github.com/DeDaydreamer/amethyst-mapper
- Active branches:
  - main (FFA live-pub baseline)
  - preview-int-omi (Omi integration baseline)
  - mapper-plus (Plus product-direction baseline)
- Repo role: mapping platform (Pages frontend + Pages Functions + Worker)
- Key files:
  - AGENTS.md
  - docs/AI_CONTEXT.md
  - SESSION-HANDOFF.md
  - version-control.md
  - workers/amethyst-api/wrangler.toml
  - functions/README.md

## 4. Ecosystem Map (_dd-ecosystem)
- GitHub: https://github.com/DeDaydreamer/_dd-ecosystem
- Primary branch: main
- Key files:
  - ECOSYSTEM.md
  - EngiMax.md
  - ENGIMAX_CUSTOM_INSTRUCTIONS.md
  - ENGIMAX_BRAND_CONTEXT.md
  - ENGIMAX_REPO_SOURCES.md
- Purpose: cross-repo dependencies, sequencing, and guardrails

## Branch Discipline
1. Always confirm branch before analysis.
2. Never apply branch assumptions across repos.
3. For amethyst-mapper, do not mix main and mapper-plus conclusions.
4. For DeDynamics-pro-site-vCodex, production branch is release/prod-site-v2 - never assume main is production.

## Bootstrap Parity Rule
1. On every new task, compare the uploaded EngiMax Space bootstrap files against GitHub `_dd-ecosystem` `main`.
2. The bootstrap parity check covers `EngiMax.md`, `ECOSYSTEM.md`, `ENGIMAX_REPO_SOURCES.md`, `ENGIMAX_CUSTOM_INSTRUCTIONS.md`, and `ENGIMAX_BRAND_CONTEXT.md`.
3. If any uploaded file is stale, report it, use GitHub `_dd-ecosystem` as canonical, and tell Aleks to refresh the uploaded copies.

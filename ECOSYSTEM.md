# DeDynamics Ecosystem Map
Last updated: 2026-03-17

## Platform Principles
1. Cloudflare-native stack only: Workers, Pages, D1, KV, R2.
2. No secrets in Git. Use Cloudflare Dashboard secrets.
3. R2 is an active platform primitive as of 2026-03-17 — use for all binary/media/asset storage needs.
4. Repo-local `AGENTS.md` is the session source of truth.

## Storage Routing Decision (canonical)
| Data type | Storage layer |
|-----------|--------------|
| Structured relational data | D1 |
| Cache / ephemeral / session | KV |
| Binary assets (images, files, media) | R2 |
| Preview / draft content (non-binary) | KV (PREVIEW_KV) |

## Active Repositories

### 1) daydream-cms
- GitHub: `https://github.com/DeDaydreamer/daydream-cms`
- Role: CMS API backend for website templates and client integrations.
- Runtime: Worker + D1 + KV + R2 (`DB`, `CACHE_KV`, `PREVIEW_KV`, `RATE_LIMIT_KV`, `ASSETS_R2`).
- Deploy: push to `main` -> Cloudflare native GitHub integration.
- Phase: `alpha (v0.1.0)` — R2 foundation rebuild in progress.
- Critical warning: `CORS_ORIGINS` must be productionized before public release.
- R2 note: R2 bucket `daydream-cms-assets` must be created in Cloudflare dashboard by Aleks before R2 binding is live.

### 2) DeDynamics-pro-site-vCodex
- GitHub: `https://github.com/DeDaydreamer/DeDynamics-pro-site-vCodex`
- Role: DeDynamics public website.
- Runtime: Cloudflare Pages + Pages Functions (support/admin surfaces).
- Production branch: `release/prod-site-v2`
- Deploy: push to `release/prod-site-v2` -> Pages auto deploy.
- Critical warning: always confirm active branch before edits. Production branch is `release/prod-site-v2`, not `main`.

### 3) amethyst-mapper
- GitHub: `https://github.com/DeDaydreamer/amethyst-mapper`
- Role: visual mapping product and future module for Amethyst Brain.
- Runtime: Pages frontend + Pages Functions + Worker.
- Active branches:
  - `main`: FFA live-pub baseline (`api-mapper.dedynamics.pro`)
  - `preview-int-omi`: Omi integration baseline (`api-omi-mapper.dedynamics.pro`)
  - `mapper-plus`: Plus product-direction baseline
- Critical warning: `workers_dev=false`; validate with real custom domain, never workers.dev.

## Planned Repositories

### daydream-shop
- Status: planned, not started.
- Dependency: consumes `daydream-cms` API.
- Must be resolved before build starts:
  1. Stable ecommerce endpoint contract in `daydream-cms`.
  2. Auth model decision (shared JWT vs separate token system).
  3. Tenant/domain strategy decision.

### amethyst-brain
- Status: concept stage.
- Dependency: embeds `amethyst-mapper` as module.
- Start condition: concept and MVP scope explicitly approved.

## Cross-Repo Dependencies
1. `daydream-shop` depends on `daydream-cms`.
2. `amethyst-brain` depends on `amethyst-mapper`.
3. `DeDynamics-pro-site-vCodex` is the public showcase layer.

## Operating Workflow
1. Aleks defines task.
2. EngiMax first sync-checks its uploaded bootstrap files against GitHub `_dd-ecosystem`.
3. EngiMax then builds/validates prompt and reviews Codex output.
4. Codex implements in repo.
5. Aleks performs dashboard steps, commits, pushes, tests.

Codex never commits and never pushes.

## Shared Safety Rules
1. Read repo `AGENTS.md` and `docs/AI_CONTEXT.md` first.
2. For EngiMax, bootstrap files in Perplexity Space must be compared against GitHub `_dd-ecosystem` before every task.
3. If bootstrap files are stale, GitHub `_dd-ecosystem` becomes canonical until Aleks refreshes the uploads.
4. Read `wrangler.toml` before Cloudflare-impacting decisions.
5. Binding names must be copied exactly from config.
6. D1 migration rule is non-negotiable: `list -> apply -> verify`.
7. Keep branch assumptions branch-local, especially in `amethyst-mapper`.
8. R2 buckets must be created in Cloudflare dashboard by Aleks before any R2 binding is activated in wrangler.toml.

## External Agent Sources
1. `EngiMax.md` - external agent operating protocol.
2. `ENGIMAX_REPO_SOURCES.md` - canonical repo URL/file map.
3. `ENGIMAX_CUSTOM_INSTRUCTIONS.md` - Perplexity Space instruction text.
4. `ENGIMAX_BRAND_CONTEXT.md` - CREATE/THINK mode brand source.

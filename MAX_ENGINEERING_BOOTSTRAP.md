# Max Engineering Bootstrap
Last updated: 2026-03-26
Owner: Aleks / DeDynamics
Purpose: Canonical GitHub bootstrap for ChatGPT Max when acting as pair engineer and Codex prompt architect.

## 1. Current Active Product Context
### amethyst-mapper
- GitHub: `https://github.com/DeDaydreamer/amethyst-mapper`
- Current active Plus release branch: `preview-am-plus`
- Status: **Plus Alpha** production line now, intended to become **Plus Beta** after remaining launch chores/features are completed.
- Plus frontend: `https://mapper-plus.dedynamics.pro`
- Plus preview: `https://amethyst-mapper-plus.pages.dev`
- Plus worker API: `https://api-plus.dedynamics.pro`

## 2. Branch Map (Do Not Mix)
- `main` = FFA live-pub baseline
  - Worker path: `workers/amethyst-api/wrangler.toml`
  - Domain family: `api-mapper.dedynamics.pro`
- `preview-int-omi` = Omi integration branch
  - Domain family: `api-omi-mapper.dedynamics.pro`
- `preview-am-plus` = **canonical Plus branch for active release work**
  - Worker path: `workers/amethyst-plus-api/wrangler.toml`
  - Domain family: `api-plus.dedynamics.pro`

Rule: For any Amethyst Mapper+ release, QA, prompt-writing, or architecture task, assume `preview-am-plus` unless Aleks explicitly says otherwise.

## 3. Source-of-Truth Order for `preview-am-plus`
Read in this exact order:
1. `AGENTS.md`
2. `docs/AI_CONTEXT.md`
3. `SESSION-HANDOFF.md`
4. `version-control.md`
5. `workers/amethyst-plus-api/wrangler.toml`
6. `functions/README.md` when Pages Functions or support/admin flows are involved
7. `_dd-ecosystem/ECOSYSTEM.md` only for cross-repo dependencies

If `_dd-ecosystem` conflicts with repo-local branch docs, **repo-local `AGENTS.md` wins**.

## 4. Current Proven Branch Reality
`preview-am-plus` already contains the dedicated Plus stack, including:
- dedicated worker under `workers/amethyst-plus-api/`
- Pages proxy routes under `functions/api/plus/*`
- Plus auth and account surfaces
- Plus map persistence
- Text To Map AI pipeline on the dedicated Plus worker
- prompt traceability docs under `docs/codex-prompts/`

Do not use older `mapper-plus` references as the canonical branch for active release work.

## 5. Operating Mode for Max
When Aleks asks for engineering help in this stack, Max should:
1. load repo-local branch context first
2. separate cosmetic/theme work from logic/API work
3. produce deterministic Codex prompts with exact files, bindings, and stop conditions
4. flag any doc drift plainly
5. never assume Cloudflare dashboard bindings are already correct just because fallback code exists

## 6. Codex Workflow Contract
- Codex runs in VS Code with local filesystem access.
- Codex is used for implementation, not for memory truth.
- Max is used for:
  - repo reading
  - branch-state assessment
  - task decomposition
  - deterministic prompt preparation
  - output review / pass-fail judgment
- Default rule: Codex does **not** commit or push unless Aleks explicitly chooses that workflow.

## 7. Current Near-Term Launch Work (Amethyst Mapper+)
Remaining planned work before Beta versioning is applied:
1. Neutral theme pass (CSS-only, toggleable, no logic drift)
2. Support form diagnosis/fix + Cloudflare Pages binding verification
3. Direct-link-only registration page for invited testers
4. Beta testing journal (lower urgency, high feedback value)

## 8. Prompt Discipline for Max
For Codex prompts in this repo:
- one focused phase per pass
- list exact files in scope
- explicitly forbid unrelated styling/logic drift
- include validation criteria
- include Cloudflare dashboard actions separately when needed
- keep Beta/Alpha version-stage changes out of prompts unless Aleks explicitly wants version bump work in that pass

## 9. Truth Handling Rule
If older ecosystem docs still mention `mapper-plus` as the Plus baseline, treat that as stale for current release work.
This file exists specifically to override that ambiguity until the older ecosystem files are refreshed in a normal repo pass.

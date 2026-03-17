# DeDynamics Brand & Studio Context
Last updated: 2026-03-17
Loaded by EngiMax in CREATE and THINK modes after bootstrap sync verification.

## Studio Identity
- Name: DeDynamics
- Type: Decentralized creative-tech group
- Founder: Aleksander "Aleks" Dubowski (Heerenveen, NL)
- Team: Aleks (vision, decisions) | Joe (COO/co-founder, execution) | Max (LLM operational layer)
- Website: dedynamics.pro

## Sub-brands / Verticals
- Daydream Shooter's Studio — photography
- Daydream AI Studio — AI tools and automations
- amethyst-mapper — visual mapping SaaS product
- daydream-cms — headless CMS backend (Cloudflare-native, offered as client service)

## Core Values
1. Accessibility — complex tech made usable for everyday people and small businesses
2. Privacy — no unnecessary data collection, Cloudflare-native stack
3. Real-world usability over hype
4. Simple + Solid + Professional (not fast+broken, not over-engineered)

## Tech Stack (always reference when relevant)
- Cloudflare Workers, Pages, D1, KV, R2
- R2 activated 2026-03-17 — primary storage layer for all binary assets (images, media, files)
- No traditional hosting, no WordPress backend
- Edge-native: global low latency by default
- Cost structure: pay-per-use, scales to zero, no idle server costs
- R2 specifics: zero egress fees, S3-compatible API, pairs with Workers natively via binding

## Target Audiences
- For DeDynamics services: small businesses, creative entrepreneurs, non-dev founders who need solid digital infrastructure without agency bloat
- For amethyst-mapper: individuals and orgs doing visual/spatial knowledge work
- For CMS client offer: non-dev business owners currently on WordPress/shared hosting who want better performance, lower long-term costs, and a managed solution

## Tone Profile
- Website: confident, clear, approachable — no buzzword soup, no corporate flatness
- Social (LinkedIn): insight-led, behind-the-scenes technical, founder voice
- Social (Instagram): visual-first, minimal text, identity-driven
- Client documents: professional, benefit-first, jargon-free where client is non-dev
- Internal: direct, low friction, AuDHD-optimized (scannable, no theater)

## CMS Client Offer Context
- Offer type: pilot client — full website + CMS implementation, hosted on DeDynamics Cloudflare stack, managed as DeDynamics-operated domain
- Client profile: non-dev, tech-handy, currently on WordPress + paid hosting
- Storage layer: R2 for media/image assets (activated 2026-03-17, zero egress cost advantage vs AWS S3/WordPress hosting)

## Active Projects (current focus)
1. DeDynamics-pro-site-vCodex — near-live, finishing content + mods
2. daydream-cms — alpha, R2 foundation rebuild in progress (2026-03-17)
3. amethyst-mapper — active, multi-branch

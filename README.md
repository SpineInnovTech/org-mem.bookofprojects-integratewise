# IntegrateWise — Continuity Documentation System

The canonical IntegrateWise documentation and product narrative system. One doctrine, one architecture story, one navigation model, one coherent product identity.

The running app is a Vite + React 18 single-page application (`integratewise-brand-documentations`). It projects organisational memory into three surfaces: a knowledge workbench, a documentation and brand shell, and an operations cockpit.

> **Ecosystem role:** This repo is the **front door** for documentation and operations visibility. The canonical source of organisational truth lives in `IntegrateWise - Memory` (flat files). This repo surfaces that truth. `integratewise-ops` is the middleware that operationalizes it. See [`ECOSYSTEM.md`](ECOSYSTEM.md) for the shared repo map.

---

## Ecosystem Position

```
IntegrateWise - Memory (canonical source)
    │
    ├─→ Organisational memory ──→ BrandDocumentations (this repo — front door)
    │                                      │
    │                                      ├─→ integratewise-docs (published docs)
    │                                      └─→ integratewise-live (product surfaces)
    │
    └─→ Conversation memory ──→ integratewise-ops (middleware + dashboard)
                                      │
                                      └─→ connects back to BrandDocumentations
```

**What lives here:** Master doctrine, brand assets, design tokens, documentation packs, the knowledge workbench, the Book of Projects / evolution surface, and the image gallery.

**What does not live here:** Operational state (leads, clients, tasks — that is `integratewise-ops`). Session logs and transcripts (that is `IntegrateWise - Memory/Conversation memory/`).

---

## What IntegrateWise Is

IntegrateWise is an **adaptive organizational continuity system** — the operating layer for organizations that need continuity, intelligence, and governed execution in a single connected environment.

Brand identity lives in `src/app/lib/brand.ts`: IntegrateWise LLP, founded 2024, Bengaluru. Primary tagline: **AI Thinks in Context — and Waits for Approval**. Category: adaptive continuity workspace.

---

## The Problem It Solves

Modern organizations run on disconnected tools. Critical context lives across CRM records, support tickets, documents, email, chat, spreadsheets, and AI-generated outputs. Each system captures only a fragment. Teams reconstruct context constantly, make decisions with incomplete understanding, and adopt AI that operates outside the real operational state of the business.

IntegrateWise solves that structural fragmentation.

---

## What Continuity Means

**Continuity** is the primitive unit of organizational knowledge in IntegrateWise. It is the live, structured model of how the organization operates: its entities, relationships, decisions, signals, and evidence, kept coherent across systems and time.

The published continuity record for this surface is `public/data/continuity-manifest.json` (pillars: One Surface, Memory, Operating Environment, Governance & Control & Security, Continuity) and is rendered on `/docs/evolution`.

---

## The Adaptive Spine

The **Adaptive Spine** is the continuity core — the single source of organizational truth. Connectors and workflows continuously hydrate the Spine from operational reality. The Spine holds entities, relationships, schema, and truth so that AI can reason in grounded context and humans can govern every consequential action.

---

## The System Model

```
Connectors + Workflows
        ↓
  Continuity Hydration
        ↓
   Adaptive Spine
        ↓
  Workspace Projection   ←→   Knowledge Adaptation
        ↓
  Human-Governed AI Execution
        ↓
  Organizational Continuity Evolution
```

---

## Canonical Doctrine

| Concept | Definition |
|---------|-----------|
| **Continuity** | The primitive — live structured model of organizational reality |
| **Adaptive Spine** | Core infrastructure holding continuity as a single source of truth |
| **Hydration** | How connectors and operational signals continuously update the Spine |
| **Workspace** | A projection of the current continuity topology understood by the Spine |
| **Knowledge** | Adaptive organizational understanding derived from continuity |
| **Evolution** | The product outcome — organizational continuity that improves over time |

---

## Application Surfaces

Routing is defined in `src/app/routes.tsx`. There are three trees:

| Surface | Entry | Shell | What it is |
|---------|-------|-------|------------|
| Knowledge Workbench | `/` | `KnowledgeWorkbench` | Primary surface. Governance, intake, triage, internal, public, operations, evolution, and Book of Projects views. |
| Documentation & brand | `/docs` | `RootLayout` | Doctrine, brand system, marketing templates, public narrative pages, and the documentation library. |
| Operations cockpit | `/app` | `WorkbenchLayout` | Full-screen Account Success and BizOps screens. Unbuilt screens render an in-progress placeholder. |

`/` is the workbench. The documentation home is `/docs` (brand hub) and `/docs/home` (system overview).

### Documentation and brand routes

Sidebar groups follow the cross-surface taxonomy (`00`–`09`) in `src/app/components/RootLayout.tsx`.

| Route | Page | Purpose |
|-------|------|---------|
| `/docs` | Brand Hub | Documentation shell index |
| `/docs/home` | Home | System overview and quick actions |
| `/docs/quick-start` | Quick Start | Edit brand content and export assets |
| `/docs/company` | Doctrine & Product | Continuity doctrine, company narrative, strategy |
| `/docs/architecture` | Architecture | Adaptive Spine, hydration flows, system model |
| `/docs/workbench` | Live Workbench | Workbench inside the documentation shell |
| `/docs/documentation` | Documentation Library | Six doctrine packs extracted from the master overview |
| `/docs/governance` | Document Governance | Embedded `public/governance/index.html` |
| `/docs/evolution` | Evolution Timeline | Book of Records from the continuity manifest |
| `/docs/brand-assets` | Brand Assets | Logo system, brand messaging, visual identity |
| `/docs/design-tokens` | Design Tokens | Colors, typography, component foundations |
| `/docs/stationery` | Stationery | Letterhead, business cards, email signatures |
| `/docs/marketing` | Marketing | Social templates and one-pagers |
| `/docs/linkedin` | LinkedIn | LinkedIn templates |
| `/docs/whatsapp` | WhatsApp | WhatsApp templates |
| `/docs/email` | Email | Email templates |
| `/docs/presentations` | Presentations | Deck builder and templates |
| `/docs/generators` | Quick Generators | Batch export of brand assets |
| `/docs/sales` | Sales | Pitch decks, proposals, battlecards |
| `/docs/gallery` | Product Gallery | Product image gallery |
| `/docs/product-writeup` | Product Writeup | Product narrative page |
| `/docs/account-success` | Account Success | Account Success narrative |
| `/docs/business-intelligence` | Business Intelligence | BI narrative |
| `/docs/how-it-works` | How It Works | Product explanation |
| `/docs/about` | About | Public about page |
| `/docs/pricing` | Pricing | Public pricing page |
| `/docs/contact` | Contact | Public contact page |
| `/docs/blog` | Blog | Public blog page |
| `/docs/control-panel` | Control Panel | System-wide settings and export |

### Cockpit routes

Wired screens:

| Route | Screen |
|-------|--------|
| `/app/account-success` | Account Success dashboard |
| `/app/account-success/accounts` | Accounts |
| `/app/account-success/at-risk` | At risk |
| `/app/account-success/tasks` | Tasks |
| `/app/account-success/meetings` | Meetings |
| `/app/account-success/engagement-log` | Engagement log |
| `/app/account-success/insights` | Insights |
| `/app/account-success/twin` | Account Success twin workbench |
| `/app/bizops` | BizOps dashboard |
| `/app/bizops/strategic-hub` | Strategic hub |
| `/app/bizops/founder-ops` | Founder ops |
| `/app/bizops/marketing` | Marketing |
| `/app/bizops/operations` | Operations |
| `/app/bizops/twin` | BizOps twin workbench |

Remaining `/app/account-success/*` and `/app/bizops/*` paths (queue, decisions, knowledge, workflows, settings, and the unwired BizOps departments) are declared in the router and render the in-progress placeholder.

---

## Repository Structure

```
src/
├── main.tsx                         # React entry
├── index.css
├── app/
│   ├── App.tsx                      # RouterProvider
│   ├── routes.tsx                   # Workbench, /docs, and /app trees
│   ├── components/
│   │   ├── RootLayout.tsx           # Documentation sidebar (taxonomy 00–09)
│   │   ├── WorkbenchLayout.tsx      # Cockpit shell
│   │   ├── knowledge/               # KnowledgeWorkbench + AI sidebar
│   │   ├── pages/                   # Documentation, brand, and narrative pages
│   │   │   ├── account-success/     # Wired Account Success cockpit views
│   │   │   └── bizops/              # Wired BizOps cockpit views
│   │   ├── diagrams/                # Architecture diagrams
│   │   └── ui/                      # Shared UI primitives
│   ├── lib/
│   │   ├── brand.ts                 # Brand strings, contacts, identity
│   │   ├── documentationContent.ts  # Maps doctrine sections into doc packs
│   │   ├── sectionExtractor.ts      # Pulls sections from the master overview
│   │   └── knowledgeRuntime.ts      # Canonical knowledge path contract
│   └── services/                    # AI providers, image generation, sync
└── imports/
    └── pasted_text/
        └── integratewise-overview.md   # Master doctrine source for the app

public/
├── data/continuity-manifest.json    # Evolution / Book of Records data
└── governance/index.html            # Embedded governance view

ImageGallery/                        # Image registry, categories, and React helpers
cms/config.yml                       # Decap/Netlify CMS collections over ImageGallery
scripts/                             # Image gallery import, sync, and validation
ops-dashboard/                       # Vendored TailAdmin Next.js reference template
ECOSYSTEM.md                         # Shared IntegrateWise repo map
```

`ops-dashboard/free-nextjs-admin-dashboard-main` is the upstream TailAdmin template. The product UI in this repo is the Vite app under `src/`.

---

## Canonical Knowledge Runtime Foundation

This repository includes a canonical, implementation-neutral knowledge runtime contract. It complements the documentation projection system.

Canonical logical model:

```text
/{domain}/triage
/{domain}/knowledge-persisted
/{domain}/references
```

Approved domains:

- executive
- product
- engineering
- design
- ai-operations
- business-operations
- sales
- marketing
- customer-success
- finance
- research-and-continuity
- infrastructure-and-security

Code foundation: `src/app/lib/knowledgeRuntime.ts`

- Typed domain and state source of truth
- Canonical path construction and validation helpers
- Generic knowledge item model (documents, images, attachments, tables, views, records, generated outputs, and references)
- Seeded domain/state container scaffolding for runtime adapters

---

## Canonical Doctrine Source

`src/imports/pasted_text/integratewise-overview.md` is the app-import doctrine source for this runtime surface.

It stays aligned upward to:

- Company OS v1.0 (`book:iw:company-os-v1`)
- `IntegrateWise - Memory` doctrine consolidation (`may2026-doctrine-consolidation.md`)
- `integratewise-live` `docs/tech/DOCTRINE_SYNC_AND_SOURCE_MAP.md`

Cross-surface taxonomy:

- 00 Company Strategy
- 01 Product & Engineering
- 02 Marketing & Creative
- 03 Sales
- 04 Customer Success
- 05 Operations
- 06 Finance, Legal, HR
- 07 Resources & Knowledge Base
- 08 External Communications
- 09 Archives & Retention

The six documentation packs are extracted from sections of the overview via `src/app/lib/sectionExtractor.ts` and mapped in `src/app/lib/documentationContent.ts`.

**To change doctrine or product copy shown in the documentation library, edit `integratewise-overview.md` and keep it aligned with the canon above. To change brand strings, edit `src/app/lib/brand.ts`.**

---

## Run Locally

Toolchain (`.tool-versions` and CI): Node.js 22, pnpm 10.

```bash
pnpm install
cp .env.example .env   # optional; required only for AI provider calls
pnpm dev               # http://localhost:3000
pnpm build             # production bundle in dist/
```

`package.json` scripts are the same under npm (`npm install`, `npm run dev`, `npm run build`). Vite is pinned to `6.4.1`. The dev server binds `0.0.0.0:3000` (`vite.config.ts` and the `dev` script).

Optional environment variables (see `.env.example`):

| Variable | Used for |
|----------|----------|
| `VITE_OPENROUTER_API_KEY` | OpenRouter chat and image calls |
| `VITE_ANTHROPIC_API_KEY` | Direct Anthropic access |
| `VITE_GEMINI_API_KEY` | Google Gemini |
| `VITE_GITHUB_PAT` | GitHub Models |

Provider wiring lives in `src/app/services/aiProviders.ts`. Keys can also be entered in the UI; they are not required to browse documentation.

Image gallery helpers:

```bash
node scripts/dropbox-sync.mjs --import-all
node scripts/validate-manifest.mjs
node scripts/add-image.mjs
```

`playwright.config.ts` targets `https://spine-org.pages.dev` and expects a `tests/` directory. That directory is not in the tree yet, so `pnpm exec playwright test` has nothing to run until tests are added.

---

## Development → Production Pipeline

| Stage | Host | Purpose |
|---|---|---|
| **Local** | `localhost:3000` | Runtime UI, doctrine projection, cockpit screens |
| **Preview** | Cloudflare Pages preview branch deploys | Branch previews and stakeholder review |
| **Production** | Cloudflare Pages | `spine-org.integratewise.ai` / `spine-org.pages.dev` |

### GitHub Actions deployment pipeline

Workflow: `.github/workflows/cloudflare-pages-deploy.yml`

- push to `main` → production Pages deploy
- pull request to `main` → preview Pages deploy
- manual run (`workflow_dispatch`) → preview or production, depending on the input

The job uses pnpm 10 and Node.js 22, runs `pnpm install --frozen-lockfile` and `pnpm build`, then `wrangler pages deploy dist`.

Required GitHub repository secrets:

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`

Cloudflare Pages assumptions:

- Pages project name: `spine-org`
- build output directory: `dist`

---

## Core Files to Know

| File | Purpose |
|------|---------|
| `src/app/routes.tsx` | Workbench, documentation, and cockpit routes |
| `src/app/components/knowledge/KnowledgeWorkbench.tsx` | Primary `/` surface |
| `src/app/components/RootLayout.tsx` | Documentation navigation |
| `src/app/lib/brand.ts` | Brand constants — taglines, contact, identity |
| `src/imports/pasted_text/integratewise-overview.md` | Master doctrine document |
| `src/app/lib/documentationContent.ts` | Doc pack section mapping |
| `src/app/lib/knowledgeRuntime.ts` | Canonical knowledge domain/state contract |
| `public/data/continuity-manifest.json` | Evolution timeline data |
| `ECOSYSTEM.md` | Shared map of IntegrateWise repositories |

---

## Doctrine Documentation Packs

Mapped in `src/app/lib/documentationContent.ts` from headings in the master overview.

| Pack | Name | Focus |
|------|------|-------|
| A | Company & Corporate Strategy | One view, company overview, vision, founder thesis |
| B | Category, Positioning & Brand | Category, differentiation, audience, go-to-market |
| C | Product Narrative & System | What the product is, capabilities, use cases |
| D | Architecture & Technical System | Operating model, Spine, flow model, Entity 360 |
| E | AI, Governance & Trust | AI governance and approval-first execution |
| F | GTM, Sales & Customer Success | Go-to-market narrative and why it matters now |

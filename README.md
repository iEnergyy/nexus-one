# NexusOne

Mental health practice management for psychologists and therapy centers in the Dominican Republic.

**Mission:** Help psychologists spend less time managing their practice and more time helping patients.

## What We're Building

A SaaS platform that unifies patient management, scheduling, session notes, payments, and WhatsApp reminders — starting with **solo psychologists** in Santo Domingo.

**Current phase:** [Phase 0 — Validation](docs/validation/phase-0-plan.md)

## Documentation

| Document | Audience | Description |
|----------|----------|-------------|
| [docs/](docs/README.md) | Everyone | Full documentation hub |
| [PRD.md](PRD.md) | Founders, pilots | Product requirements summary |
| [ROADMAP.md](ROADMAP.md) | Founders, investors | Phases, metrics, gates |

### Key Docs

- [Workflows](docs/workflows/daily-practice-loop.md) — daily loop, patient lifecycle, cancellations
- [Personas](docs/product/personas.md) — who we're building for
- [MVP Scope](docs/product/mvp-scope.md) — Phase 1 feature boundary
- [Interview Guide](docs/validation/interview-guide.md) — Phase 0 validation

## Tech Stack

### Current (Built)

| Layer | Technology |
|-------|------------|
| Monorepo | pnpm workspaces + Turbo |
| Frontend | Next.js 16, React 19, TypeScript |
| UI | Tailwind CSS 4, shadcn/ui (`@workspace/ui`) |
| Tooling | ESLint, Prettier |

### Planned (Phase 1)

| Layer | Technology |
|-------|------------|
| Database | PostgreSQL via Supabase |
| ORM | Drizzle |
| Auth | Supabase Auth (email + Google) |
| Messaging | WhatsApp Business API |
| Hosting | Vercel |

See [Tech Stack](docs/architecture/tech-stack.md) for details and open decisions.

## Project Structure

```
nexus-one/
├── apps/
│   └── web/                  # Next.js application
├── packages/
│   ├── ui/                   # Shared shadcn/ui components
│   ├── eslint-config/        # Shared ESLint configuration
│   └── typescript-config/    # Shared TypeScript configuration
├── docs/                     # Product & technical documentation
├── PRD.md
├── ROADMAP.md
└── package.json
```

## Development

**Requirements:** Node.js ≥ 20, pnpm 10

```bash
pnpm install     # Install dependencies
pnpm dev         # Start development servers
pnpm build       # Production build
pnpm lint        # Lint all packages
pnpm typecheck   # TypeScript check
```

## Business Model

| Plan | Price | Target |
|------|-------|--------|
| Individual | RD$700–1,200/month | Solo psychologists |
| Center | RD$4,000–10,000/month | Therapy centers (Phase 3) |
| Marketplace | Commission per booking | Phase 4 |

## Long-Term Vision

```
Practice Management → Therapy Centers → Online Booking → Marketplace → AI Platform
```

See [Vision](docs/product/vision.md) and [Roadmap](ROADMAP.md).

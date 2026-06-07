# Tech Stack

## Current (Built)

| Layer | Technology | Version |
|-------|------------|---------|
| Monorepo | pnpm workspaces + Turbo | pnpm 10, Turbo 2.9 |
| Frontend framework | Next.js (App Router) | 16.2 |
| UI library | React | 19.2 |
| Styling | Tailwind CSS | 4.x |
| Components | shadcn/ui (via `@workspace/ui`) | — |
| Language | TypeScript | 5.x |
| Linting | ESLint (shared config) | 9.x |
| Formatting | Prettier + Tailwind plugin | — |

## Planned (Phase 1)

| Layer | Technology | Rationale |
|-------|------------|-----------|
| Database | PostgreSQL via Supabase | Managed Postgres, auth, realtime; fits SaaS |
| ORM | Drizzle | Type-safe, lightweight, good Supabase/Postgres support |
| Auth | Supabase Auth | Email + Google OAuth; integrates with DB |
| Messaging | WhatsApp Business API | Dominant channel in DR; patients expect it |
| Hosting | Vercel | Native Next.js deployment |
| Encryption | Application-level for notes | Session notes encrypted at rest beyond DB encryption |

## Open Decision: API Layer

Two options for Phase 1 — decide during implementation planning:

### Option A: Next.js API Routes / Server Actions

- **Pros:** Single deployment, simpler monorepo, fewer moving parts for MVP
- **Cons:** Tighter coupling; harder to extract later if API serves mobile clients

### Option B: Standalone Hono API (`apps/api`)

- **Pros:** Clean separation, portable, can deploy independently
- **Cons:** Extra app to maintain, CORS/auth wiring, two deployments

**Recommendation:** Start with Next.js Server Actions + API routes for MVP speed. Extract Hono service if/when mobile or third-party API consumers appear.

## Explicitly Not in Stack (for now)

| Technology | Why not |
|------------|---------|
| Bun runtime | Project uses Node.js + pnpm; no migration planned |
| Redis | Not needed at MVP scale |
| Elasticsearch | Postgres full-text search sufficient for note search |
| Mobile native app | Responsive web first |

## Development Commands

```bash
pnpm install    # Install all workspace dependencies
pnpm dev        # Start dev servers (Turbo)
pnpm build      # Production build
pnpm lint       # Lint all packages
pnpm typecheck  # TypeScript check
```

## Package Manager Note

The project uses **pnpm**, not Bun or npm. The root `package.json` specifies `"packageManager": "pnpm@10.33.4"`.

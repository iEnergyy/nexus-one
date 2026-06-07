# NexusOne Documentation Upgrade — Design Spec

**Date:** 2026-06-07  
**Status:** Approved  
**Phase:** 0 — Validation  
**Owner:** nrg

---

## Goal

Upgrade `PRD.md`, `README.md`, and `ROADMAP.md` and create a `docs/` folder so founders, pilot psychologists, and future developers share a clear picture of what NexusOne is, how solo-psychologist workflows operate, and what gets validated before Phase 1 build.

---

## Constraints

- **Lifecycle:** Phase 0 — validation, not build-ready implementation specs
- **Primary persona:** Solo psychologist (independent private practice)
- **Secondary persona:** Therapy center — documented as future only
- **Workflows:** All three get full treatment with diagrams
- **Audience:** Layered — founders, pilots, and developers each have an entry point

---

## Approach: Hub-and-Spoke

Root files remain scannable entry points. `docs/` is the source of truth for depth.

| File | Audience | Role |
|------|----------|------|
| `README.md` | Devs + newcomers | Product summary, actual tech stack, quickstart, links |
| `PRD.md` | Founders + pilots | Vision, MVP scope, workflow summaries, metrics |
| `ROADMAP.md` | Founders + investors | Phases, gates, dependencies, metrics |
| `docs/` | All | Depth: workflows, validation toolkit, architecture sketches |

---

## `docs/` Structure

```
docs/
├── README.md
├── product/
│   ├── vision.md
│   ├── personas.md
│   ├── problem-statement.md
│   └── mvp-scope.md
├── workflows/
│   ├── daily-practice-loop.md
│   ├── patient-lifecycle.md
│   └── cancellation-waitlist.md
├── validation/
│   ├── phase-0-plan.md
│   ├── interview-guide.md
│   └── hypothesis-log.md
├── architecture/
│   ├── overview.md
│   ├── tech-stack.md
│   └── data-model-sketch.md
└── future/
    └── therapy-center-workflows.md
```

---

## Workflow Doc Template

Each workflow document includes:

1. Purpose
2. Actors
3. Trigger
4. Steps (numbered)
5. Mermaid diagram
6. Current state (without NexusOne)
7. NexusOne MVP (Phase 1)
8. Future (Phase 2+)
9. Validation questions
10. Open questions

### Workflow Scope

| Workflow | MVP | Future |
|----------|-----|--------|
| Daily practice loop | Calendar, notes linked to appointments, manual payment toggle | AI summaries, auto payment reconciliation |
| Patient lifecycle | CRUD, session history, archive | Intake forms, documents, discharge |
| Cancellation & waitlist | WhatsApp reminders, manual reschedule, cancellation log | Smart Waitlist auto-recovery (Phase 2) |

---

## Root File Changes

### README.md
- Reflect actual monorepo (pnpm, Turbo, Next.js 16, shadcn/ui)
- Mark Hono, Supabase, WhatsApp as planned
- Replace outdated `src/features/` tree with `apps/web` + `packages/`
- Quickstart: `pnpm install`, `pnpm dev`

### PRD.md
- Tighten executive summary and problem statement
- Link to workflow docs
- Move Smart Waitlist to Phase 2 explicitly
- Add validation status pointer

### ROADMAP.md
- Expand Phase 0 with deliverables and go/no-go gate
- Add phase dependencies
- Gate Phase 1 behind Phase 0 success criteria

---

## Architecture Docs

- **overview.md:** Built vs planned diagram (monorepo → API → DB → WhatsApp)
- **tech-stack.md:** Current stack + planned Phase 1 additions
- **data-model-sketch.md:** Draft entities (Therapist, Patient, Appointment, SessionNote, Payment, Reminder) — not a schema

### Open Decision

API layer: standalone Hono service vs Next.js API routes — deferred to Phase 1 planning.

---

## Validation Toolkit

- **phase-0-plan.md:** 20 psychologist + 5 center interviews, 2–4 week timeline, go/no-go gate
- **interview-guide.md:** Questions mapped to three workflows + pricing probes
- **hypothesis-log.md:** Seed hypotheses with untested status

### Go/No-Go Gate (Phase 0 → Phase 1)

- 10 psychologists express interest
- 3 pilot customer commitments
- Pricing validated (RD$700–1,200/month individual plan)
- MVP scope confirmed via interviews

---

## Out of Scope

- Implementation code
- Database migrations or API design
- Therapy center workflow diagrams (outline only in `docs/future/`)
- Localization beyond Dominican Republic context notes

---

## Success Criteria

- [ ] All files in `docs/` structure exist and are cross-linked
- [ ] Root files link to `docs/` without duplicating long content
- [ ] README reflects actual codebase (pnpm/Turbo monorepo)
- [ ] Three workflow docs include Mermaid diagrams
- [ ] Phase 0 validation toolkit is usable for interviews
- [ ] Smart Waitlist clearly marked Phase 2, not MVP

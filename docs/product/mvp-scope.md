# MVP Scope

**Phase:** 1 (build starts after Phase 0 validation gate)  
**Primary persona:** Solo psychologist  
**Duration estimate:** 8 weeks

## In Scope — Phase 1 MVP

### Authentication
- Email registration and login
- Google OAuth login

### Patient Management
- Create, search, and archive patient profiles
- Store: full name, phone, email, emergency contact
- View session history per patient

### Scheduling
- Calendar view (day/week)
- Create single and recurring appointments
- Reschedule and cancel appointments
- Link appointments to patients

### Session Notes
- Create private notes linked to an appointment
- Fields: session summary, homework, next steps
- Notes encrypted at rest
- Basic search across notes

### Payments
- Set session price per appointment or patient default
- Mark payment status (paid / pending / waived)
- Monthly revenue dashboard
- Outstanding balance view

### WhatsApp Reminders
- Automatic reminders at 24 hours and 2 hours before appointment
- Configurable message templates
- Delivery status tracking

## Explicitly Out of Scope — MVP

| Feature | Target Phase | Rationale |
|---------|--------------|-----------|
| Smart Waitlist | Phase 2 | Killer feature, but requires waitlist data model + WhatsApp two-way flow |
| Multi-therapist / organizations | Phase 3 | Different tenancy model |
| Room management | Phase 3 | Center-only need |
| Public booking / marketplace | Phase 4 | Requires public profiles and discovery |
| Teletherapy / video | Phase 5 | Infrastructure complexity |
| AI features | Phase 6 | Needs note volume and trust |
| Document uploads | Post-MVP | Nice-to-have, not core loop |
| Assistant / multi-user access | Phase 2 | Adds RBAC complexity |

## Phase 0 Hypotheses to Validate

Before committing to this scope, Phase 0 must confirm:

1. Solo psychologists rank scheduling + reminders as top pain (vs payments vs notes)
2. RD$700–1,200/month is acceptable for the MVP feature set
3. WhatsApp is the required reminder channel (not SMS or email alone)
4. Psychologists want notes in the same tool as scheduling (not a separate app)
5. Smart Waitlist is a compelling upsell for Phase 2 (even if not in MVP)

Track results in [Hypothesis Log](../validation/hypothesis-log.md).

## Acceptance Criteria Summary

| Feature | Key criteria |
|---------|-------------|
| Patients | Create, search, archive |
| Calendar | Loads < 2s; recurring supported |
| Notes | Encrypted; searchable |
| Payments | Monthly revenue + outstanding dashboards |
| Reminders | Delivery tracked; templates configurable |

Full criteria in [PRD](../../PRD.md).

## Go/No-Go Gate

Phase 1 build starts only when [Phase 0 Plan](../validation/phase-0-plan.md) success criteria are met.

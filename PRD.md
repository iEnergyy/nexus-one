# PRD — NexusOne

**Version:** 1.1  
**Status:** Draft — Phase 0 Validation  
**Owner:** nrg  
**Last updated:** 2026-06-07

---

## Executive Summary

NexusOne is a SaaS platform for psychologists and therapy centers in the Dominican Republic, starting in Santo Domingo. It helps therapists manage patients, appointments, session notes, payments, and WhatsApp reminders from a single platform.

**Primary customer:** Independent psychologist (20–100 patients, WhatsApp-heavy workflow)  
**Long-term vision:** Operating system for mental health professionals in Latin America, with a therapist marketplace for patient acquisition.

**Current phase:** Phase 0 — validating demand, pricing, and MVP scope via customer interviews. See [Phase 0 Plan](docs/validation/phase-0-plan.md).

---

## Problem

Psychologists manage their practice with WhatsApp, Google Calendar, Excel, and paper notes. This causes missed appointments, revenue loss from no-shows, fragmented records, poor financial visibility, and administrative overhead.

Full analysis: [Problem Statement](docs/product/problem-statement.md)

---

## Personas

| Persona | Priority | Doc |
|---------|----------|-----|
| Dr. Ana — Solo psychologist | Primary (MVP) | [Personas](docs/product/personas.md) |
| María — Center administrator | Future (Phase 3) | [Future Workflows](docs/future/therapy-center-workflows.md) |

---

## Core Workflows

| Workflow | Description | Doc |
|----------|-------------|-----|
| Daily practice loop | Schedule → session → note → payment | [Workflow](docs/workflows/daily-practice-loop.md) |
| Patient lifecycle | Intake → recurring sessions → archive | [Workflow](docs/workflows/patient-lifecycle.md) |
| Cancellation & waitlist | Reminders → cancel → slot recovery | [Workflow](docs/workflows/cancellation-waitlist.md) |

---

## MVP Features (Phase 1)

Full scope and out-of-scope list: [MVP Scope](docs/product/mvp-scope.md)

### Patient Management

- Create, search, and archive patient profiles
- Store: full name, contact info, emergency contact, session history

**Acceptance criteria:** Therapist can create, search, and archive patients.

### Scheduling

- Calendar (day/week view)
- Single and recurring appointments
- Reschedule and cancel

**Acceptance criteria:** Calendar loads < 2 seconds; recurring appointments supported.

### Session Notes

- Private notes per session: summary, homework, next steps
- Encrypted at rest; searchable

**Acceptance criteria:** Notes are encrypted and searchable.

### Payments

- Session price tracking; payment status (paid / pending / waived)
- Monthly revenue dashboard; outstanding balance view

**Acceptance criteria:** Revenue and outstanding balance dashboards functional.

### WhatsApp Reminders

- Automatic reminders at 24 hours and 2 hours before appointment
- Configurable templates; delivery tracking

**Acceptance criteria:** Delivery tracked; templates configurable.

---

## Killer Feature (Phase 2 — Not MVP)

### Smart Waitlist

Automatically recovers cancelled appointment slots by notifying waitlisted patients via WhatsApp. First to accept gets the slot.

**Flow:** Cancel → open slot detected → waitlist queried → WhatsApp sent → first accept wins  
**Metric:** Recovered appointments per month

See [Cancellation & Waitlist workflow](docs/workflows/cancellation-waitlist.md).

---

## Security

- Role-based access (single therapist in MVP)
- Encrypted: session notes, patient information
- Audit logging
- Authentication: email + Google OAuth

---

## Non-Functional Requirements

| Requirement | Target |
|-------------|--------|
| Availability | 99.9% |
| API response | < 500ms |
| Page load | < 2 seconds |
| Mobile | Responsive required |

---

## Success Metrics

### Business
MRR · Customer acquisition cost · Churn rate · Customer lifetime value

### Product
Active psychologists · Appointments created · Notes created · Reminder delivery rate · No-show reduction

### Phase 0 Validation Gate
≥ 10 interested psychologists · ≥ 3 pilot commitments · Pricing validated

Track hypotheses: [Hypothesis Log](docs/validation/hypothesis-log.md)

---

## Future Phases

| Phase | Focus |
|-------|-------|
| 2 | Smart Waitlist, reporting, assistant access |
| 3 | Therapy centers, rooms, admin dashboard |
| 4 | Marketplace — profiles, search, booking, reviews |
| 5 | Teletherapy — video, chat, file sharing |
| 6 | AI — summaries, insights, scheduling optimization |
| 7 | LATAM expansion |

Details: [Roadmap](ROADMAP.md) · [Vision](docs/product/vision.md)

---

## Validation Status

| Item | Status |
|------|--------|
| Psychologist interviews (0/20) | Not started |
| Center admin interviews (0/5) | Not started |
| Hypothesis log | [Seed hypotheses documented](docs/validation/hypothesis-log.md) |
| Go/no-go decision | Pending |

Update this table as Phase 0 progresses.

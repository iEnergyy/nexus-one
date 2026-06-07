# Therapy Center Workflows (Future)

**Phase:** 3 — not in MVP or Phase 0 validation priority  
**Persona:** Center administrator (María)  
**Status:** Outline only

## Why Future-Only

MVP targets solo psychologists. Center workflows require:

- Multi-therapist tenancy (organizations)
- Role-based access (admin vs therapist vs front desk)
- Room as a schedulable resource
- Cross-therapist reporting without exposing clinical notes

We interview 5 center admins in Phase 0 for demand signal only. No diagrams or detailed specs until Phase 2 is underway.

## Planned Workflows (High-Level)

### Multi-Therapist Scheduling

Center admin views all therapists' calendars in one dashboard. Assigns appointments to therapists and rooms. Prevents double-booking of rooms or therapists.

### Room Management

Rooms are first-class resources with capacity and availability. Appointments require both a therapist and a room. Admin resolves conflicts.

### Admin Dashboard

Center-level analytics: total sessions, revenue by therapist, room utilization, no-show rates. Exportable monthly reports for center owner.

### Therapist Productivity Reports

Per-therapist session counts, revenue generated, cancellation rates. Visible to admin; not visible to other therapists.

### Role-Based Access

| Role | Can see | Cannot see |
|------|---------|------------|
| Center admin | All schedules, reports, room assignments | Session notes content |
| Therapist | Own patients, own calendar, own notes | Other therapists' notes |
| Front desk | All schedules, patient contact info | Session notes |

## Phase 3 Success Metrics (from Roadmap)

- 10 therapy centers onboarded
- MRR > $3,000
- Center plan pricing: RD$4,000–10,000/month

## Phase 0 Signal to Capture

In center admin interviews, log:

- Center size (therapists, rooms)
- Current scheduling tool (if any)
- Biggest coordination pain
- Willingness to pay RD$4,000–10,000/month
- Interest level: hot / warm / cold

Add findings to [Hypothesis H8](../validation/hypothesis-log.md).

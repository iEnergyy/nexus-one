# Data Model Sketch

**Status:** Draft — validate entity boundaries during Phase 0 interviews  
**Not a schema** — conceptual map for alignment before Drizzle migrations

## Entity Relationship Diagram

```mermaid
erDiagram
    THERAPIST ||--o{ PATIENT : manages
    THERAPIST ||--o{ APPOINTMENT : owns
    PATIENT ||--o{ APPOINTMENT : has
    APPOINTMENT ||--o| SESSION_NOTE : generates
    APPOINTMENT ||--o| PAYMENT : has
    APPOINTMENT ||--o{ REMINDER : triggers
    PATIENT ||--o{ SESSION_NOTE : referenced_in
    PATIENT ||--o{ PAYMENT : owes

    THERAPIST {
        uuid id PK
        string email
        string name
        string phone
        timestamp created_at
    }

    PATIENT {
        uuid id PK
        uuid therapist_id FK
        string full_name
        string phone
        string email
        string emergency_contact
        decimal default_session_price
        enum status "active|archived"
        timestamp created_at
    }

    APPOINTMENT {
        uuid id PK
        uuid therapist_id FK
        uuid patient_id FK
        timestamp start_time
        timestamp end_time
        enum status "scheduled|completed|cancelled|no_show"
        string recurrence_rule
        string cancellation_reason
        timestamp created_at
    }

    SESSION_NOTE {
        uuid id PK
        uuid appointment_id FK
        uuid patient_id FK
        uuid therapist_id FK
        text summary_encrypted
        text homework_encrypted
        text next_steps_encrypted
        timestamp created_at
    }

    PAYMENT {
        uuid id PK
        uuid appointment_id FK
        uuid patient_id FK
        decimal amount
        enum status "paid|pending|waived"
        timestamp paid_at
    }

    REMINDER {
        uuid id PK
        uuid appointment_id FK
        enum type "24h|2h"
        enum delivery_status "scheduled|sent|delivered|failed"
        timestamp scheduled_at
        timestamp sent_at
    }
```

## Entity Summary

| Entity | Purpose | MVP? |
|--------|---------|------|
| Therapist | Account owner; all data scoped to therapist | Yes |
| Patient | Person receiving treatment | Yes |
| Appointment | Scheduled session with status lifecycle | Yes |
| SessionNote | Clinical documentation linked to appointment | Yes |
| Payment | Financial record per session | Yes |
| Reminder | WhatsApp reminder with delivery tracking | Yes |
| WaitlistEntry | Patient waiting for open slot | Phase 2 |
| Organization | Therapy center grouping therapists | Phase 3 |
| Room | Physical room at a center | Phase 3 |

## Key Relationships

- **Single-tenant MVP:** Every record belongs to one `Therapist`. No org/team model yet.
- **Appointment is the hub:** Notes, payments, and reminders attach to appointments.
- **Patient is the longitudinal view:** Aggregates appointments, notes, and payments for history.
- **Archive = soft status:** Patient `status: archived` hides from active list; records retained.

## Status Enums

### Appointment
`scheduled` → `completed` | `cancelled` | `no_show`

### Payment
`pending` → `paid` | `waived`

### Reminder
`scheduled` → `sent` → `delivered` | `failed`

## Open Questions

- [ ] One note per appointment, or allow multiple (addendum)?
- [ ] Payment per appointment vs bulk monthly payment covering multiple sessions?
- [ ] Recurrence: store as RRULE string or separate recurrence table?
- [ ] No-show: distinct from cancelled, or sub-type of cancelled?
- [ ] Timezone handling — all Santo Domingo (AST, UTC-4) for MVP?

## Validation Prompts

Ask in interviews:

1. Do you think of payments per session or per month?
2. Would you ever write more than one note per session?
3. Is "no-show" different from "cancelled" in how you track it?

Update this sketch based on answers before writing Drizzle schema.

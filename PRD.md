# PRD - NexusOne

Version: 1.0
Status: Draft
Owner: nrg

---

# Executive Summary

NexusOne is a SaaS platform designed for psychologists and therapy centers in the Dominican Republic, starting in Santo Domingo.

The platform helps therapists manage:

- Patients
- Appointments
- Session notes
- Payments
- WhatsApp reminders

The long-term vision is to become the operating system for mental health professionals in Latin America by combining practice management software with patient acquisition through a therapist marketplace.

---

# Problem Statement

Most psychologists currently manage their practice using:

- WhatsApp
- Google Calendar
- Excel
- Paper notes

This causes:

- Missed appointments
- Revenue loss from no-shows
- Fragmented patient records
- Poor financial visibility
- Administrative overhead

Therapy centers face additional challenges:

- Managing multiple therapists
- Room scheduling
- Centralized reporting

---

# Vision

Become the leading mental health practice management platform in Latin America.

Start:

- Independent psychologists
- Small therapy centers

Expand:

- Teletherapy
- Marketplace
- Insurance integrations
- AI-assisted workflows

---

# Target Customers

## Primary

Independent psychologists

Characteristics:

- 20-100 active patients
- Private practice
- Uses WhatsApp heavily

---

## Secondary

Therapy centers

Characteristics:

- 3-30 therapists
- Shared rooms
- Administrative staff

---

# Success Metrics

## Business

MRR
Customer Acquisition Cost
Churn Rate
Customer Lifetime Value

---

## Product

Active psychologists
Appointments created
Notes created
Reminder delivery rate
No-show reduction

---

# Core MVP Features

## Patient Management

### Requirements

Create patient profiles

Store:

- Full name
- Contact information
- Emergency contact
- Session history
- Documents

### Acceptance Criteria

- Therapist can create patient
- Therapist can search patient
- Therapist can archive patient

---

## Scheduling

### Requirements

Calendar system

Support:

- Single appointment
- Recurring appointment
- Rescheduling
- Cancellation

### Acceptance Criteria

- Calendar loads under 2 seconds
- Recurring appointments supported

---

## Session Notes

### Requirements

Create private notes for sessions

Store:

- Session summary
- Homework
- Next steps

### Acceptance Criteria

- Notes are encrypted
- Notes searchable

---

## Payments

### Requirements

Track:

- Session price
- Payment status
- Revenue

### Acceptance Criteria

- Monthly revenue dashboard
- Outstanding balance dashboard

---

## WhatsApp Reminders

### Requirements

Automatic reminders

Examples:

- 24 hours before
- 2 hours before

### Acceptance Criteria

- Delivery tracked
- Reminder templates configurable

---

# Killer Feature

## Smart Waitlist

Goal:

Recover cancelled appointments automatically.

Flow:

1. Patient cancels
2. Open slot detected
3. Waitlist queried
4. WhatsApp sent
5. First patient accepts

Success Metric:

Recovered appointments per month

---

# Security Requirements

Role-based access

Encrypted:

- Session notes
- Documents
- Patient information

Audit logging

Authentication:

- Email
- Google Login

---

# Non-Functional Requirements

Availability:
99.9%

API Response:
< 500ms

Page Load:
< 2 seconds

Mobile Responsive:
Required

---

# Future Features

## Phase 2

- Multi-therapist centers
- Room management
- Admin dashboards

---

## Phase 3

- Teletherapy
- Video calls
- Online booking

---

## Phase 4

- Therapist marketplace
- Reviews
- Discovery
- Commission-based bookings

---

## Phase 5

- AI session summaries
- AI treatment recommendations
- AI practice insights

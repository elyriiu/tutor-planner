# Tutor Planner (Tutor Management App)

A web application that gives private tutors one central workspace for lesson scheduling, student management, and income tracking.

## Purpose

Private tutors often rely on disconnected tools. Tutor Planner keeps data in one place, giving tutors a reliable overview of their lessons, students, schedule changes, and earnings.

## Target User
The primary user is an **independent tutor** who manages their own students, teaches recurring individual or group lessons, changes lesson schedules occasionally, wants to estimate and review income without a separate spreadsheet.

## MVP Scope
- Tutor account registration and login
- Dashboard with daily lesson overview
- Manual creation and editing of lessons
- Recurring lessons on selected weekdays
- Individual and group lessons
- Day, week, and month calendar views
- Lesson completion, cancellation, skipping, and rescheduling
- Student list and editable student profiles
- Student search and lesson history
- Income summaries by date range
- Separate reporting for cancelled and skipped lesson values
- Basic responsive design and access control

> **Scope decision:** The MVP prioritises reliable lesson records and correct income calculations over integrations and advanced automation.

## Repository Structure

```
tutor-planner/
├── README.md
├── docs/
│   ├── PRD.md          # Product Requirements
│   └── UX-prototype/      # UX prototype files
├── assets/              
├── src/               
└── .gitignore
```

## Important Conventions
- **Income is calculated from lesson records**
- **Historical prices are retained** 
- **Lesson pricing** is a fixed price per lesson occurrence (per-student pricing deferred).
- **Recurring lessons** require a start date and selected weekdays, with an optional end date and a sensible generation horizon.
- **Earned income** = completed lessons.

## Dependencies

- PostgreSQL
- Authentication provider (managed or secure equivalent)
- Hosting for frontend and backend
- Calendar component (internal, custom or library)
- Reliable date/time library for recurring lessons and time zones
- Automated database backup and recovery

## MVP Completion Criteria
The MVP is complete when an authenticated tutor can create individual and recurring lessons, see them in a calendar and daily dashboard, manage student profiles, update lesson statuses, reschedule lessons, and review income by date range — **without duplicate records or incorrect totals**.
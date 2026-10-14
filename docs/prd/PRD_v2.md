# Product Requirements Document (PRD)

> **Document Status:** [Draft]  
> **Last Updated:** [14.10.2026]  

---

## Summary

**Product Name:** [Tutor Planner]

**Problem Statement:**  
[Private tutors often use several disconnected tools to manage their work. This creates unnecessary administrative work and makes it difficult to maintain a reliable overview of lessons, student details, schedule changes, and earnings. Existing general-purpose calendar tools may not provide the combination of student profiles, recurring lessons, cancellation tracking, and tutor-specific income summaries in one focused workflow.]

**Proposed Solution:**  
[Tutor Planner provides one central workspace for lesson scheduling, student management, and income tracking. By connecting these functions through a shared lesson record, the application reduces duplicate data entry and helps tutors understand their workload and financial performance.]

**Target user profile**
[The primary user is an independent tutor who:
   - Manages their own students.
   - Teaches recurring individual or group lessons.
   - Changes lesson schedules occasionally.
   - Needs to record student details and learning materials.
   - Wants to estimate and review income without maintaining a separate spreadsheet.]
   
**Success indicators**
   - Time required to create a lesson.
   - Percentage of lessons with complete student and schedule information.
   - Number of duplicate student records.
   - Frequency of successful rescheduling actions.
   - Percentage of completed lessons correctly reflected in income summaries.
   - User-reported ease of managing weekly schedules.

## Core User Scenarios
### Scenario 1: Create a recurring lesson
**User:** A tutor who teaches the same student every Tuesday and Thursday.
**Goal:** Add the recurring lessons without creating each occurrence manually.
**Flow:**
   1.	The tutor opens Add a Lesson.
   2.	The tutor enters the student's name or selects an existing student.
   3.	The tutor selects the lesson time and duration.
   4.	The tutor selects Tuesday and Thursday as recurring days.
   5.	The tutor enters the lesson price and recurrence end date, if applicable.
   6.	The tutor saves the schedule.
   7.	The application creates the lesson occurrences and displays them in the Calendar and Dashboard.
**Expected result:** The tutor can see the recurring lessons on the correct dates, with no duplicate occurrences.
### Scenario 2: Reschedule or cancel a lesson
**User:** A tutor whose student cannot attend the originally scheduled time.
**Goal:** Change the schedule without losing track of the original lesson.
**Flow:**
   1.	The tutor opens the lesson in the Calendar.
   2.	The tutor selects Reschedule.
   3.	The tutor enters a new date and time.
   4.	The application updates the relevant lesson occurrence.
   5.	The Calendar and Dashboard refresh to reflect the change.
Alternatively, the tutor selects Cancel or Skip and confirms the action.
**Expected result:** The lesson has the correct status and time. It is not counted twice in income reports, and the original action remains traceable.
### Scenario 3: Add a student and manage their profile
**User:** A tutor who starts teaching a new student.
**Goal:** Store the student's details and connect them to future lessons.
**Flow:**
   1.	The tutor creates a lesson and enters the student's name.
   2.	The application saves the student as a record.
   3.	The tutor opens the Students section.
   4.	The tutor opens the student's profile.
   5.	The tutor adds contact information, learning materials, age, and notes.
   6.	The tutor saves the changes.
**Expected result:** The student appears in the Students list and can be selected for future lessons. Their lesson history is available from the profile.
### Scenario 4: Review income and cancelled lessons
**User:** A tutor who wants to understand their earnings for the current month.
**Goal:** Review completed lessons and identify potential lost income.
**Flow:**
   1.	The tutor opens Income.
   2.	The tutor selects the current month.
   3.	The application displays earned income and relevant lesson totals.
   4.	The tutor opens the cancellation breakdown.
   5.	The application displays cancelled and skipped lesson values separately.
**Expected result:** The tutor can distinguish completed lesson income from the planned value of lessons that did not take place.

## Functional Requirements
### FR-01 -- **Must**
The system shall allow an authenticated tutor to create a lesson with a date, start time, duration, price, and one or more students. 
### FR-02 -- **Must**
The system shall support recurring lessons on multiple selected days of the week, with an optional end date.
### FR-03 -- **Must**	
The system shall display scheduled lessons in day, week, and month calendar views and in a daily dashboard.
### FR-04 -- **Must**
The system shall allow a tutor to edit, complete, cancel, skip, or reschedule an individual lesson occurrence.
### FR-05	-- **Must**
The system shall create and maintain student profiles and allow tutors to edit student details and notes.
### FR-06	-- **Must**
The system shall support individual and group lessons by linking one or more students to a lesson.
### FR-07	-- **Should**
The system shall calculate income summaries for selectable date ranges using lesson status and pricing rules.
### FR-08	-- **Should**
The system shall display cancelled and skipped lesson values separately from earned income.
### FR-09	-- **Should**
The system shall provide a searchable student list and show associated lessons in each student's profile.
### FR-10	-- **Must**
The system shall authenticate users and prevent one tutor from accessing another tutor's private records.	

## Relevant Non-Functional Requirements
### NFR-01: Security and access control
All private student and lesson data must require authentication. Every data request must enforce tutor-level access control on the server.
### NFR-02: Data integrity
Lesson creation, rescheduling, and status changes must not produce duplicate active lessons or double-counted income. The database must enforce appropriate relationships and validation constraints.
### NFR-03: Usability
Common actions such as adding a lesson, opening a student profile, and rescheduling a lesson should be straightforward and require minimal navigation.
### NFR-04: Privacy
Personal information must be collected and retained only for defined purposes. The application should support data export or deletion where required by applicable privacy obligations.

## Acceptance Criteria for Core Requirements
### AC-01: Create a lesson (FR-01)
### AC-02: Create recurring lessons (FR-02)
### AC-03: View the schedule (FR-03)
### AC-04: Change lesson status or time (FR-04)
### AC-05: Manage student profiles (FR-05)
### AC-06: Support group lessons (FR-06)
### AC-07: Calculate income (FR-07)
### AC-8: Protect user data (FR-10)

## In MVP Scope
The first release should include:
	Tutor account registration and login.
   - A Dashboard with a daily lesson overview.
   - Manual creation and editing of lessons.
   - Recurring lessons on selected weekdays.
   - Individual and group lessons.
   - Day, week, and month calendar views.
   - Lesson completion, cancellation, skipping, and rescheduling.
   - Student list and editable student profiles.
   - Student search and lesson history.
   - Income summaries by date range.
   - Separate reporting for cancelled and skipped lesson values.
   - Basic responsive design and access control.
Out of MVP Scope
The following features should be considered for later releases:
   - Online payments and automatic payment collection.
   - Bank account integration and financial reconciliation.
   - Invoicing and tax reports.
   - Automated email, SMS, or messaging reminders.
   - Student or parent accounts and self-service booking.
   - Online lesson delivery or video conferencing.
   - Attendance tracking beyond basic lesson statuses.
   - Advanced analytics, forecasting, and business reports.
   - Multiple tutors under one organisation with shared administration.
   - Calendar synchronisation with external providers.
   - Automated cancellation fees and complex pricing policies.
   - Mobile applications for iOS and Android.
**Scope decision:** The MVP should prioritise reliable lesson records and correct income calculations over integrations and advanced automation.
## Constraints, Assumptions, and Dependencies
### Constraints
   - The initial product is a web application.
   - The MVP is designed primarily for independent tutors.
   - One tutor account manages its own students and lessons.
   - Income reporting depends on accurate lesson status and price information.
   - Group lesson pricing must follow one clearly defined rule.
   - The project has limited initial development time and should avoid unnecessary integrations.
### Assumptions
   - Tutors enter and maintain their own lesson information.
   - A student can attend multiple lessons.
   - A lesson can include multiple students.
   - Recurring lessons can be edited individually or as a series.
   - A completed lesson is treated as earned income for reporting purposes unless the product later supports more detailed payment tracking.
   - Cancelled and skipped lessons are not automatically considered paid or unpaid.
   - A tutor can set a currency for their records.
   - Each tutor has one primary time zone for displaying lesson times.
### Dependencies
   - A database service for storing application records.
   - An authentication provider or secure authentication implementation.
   - A hosting provider for the frontend and backend.
   - A calendar component or custom calendar implementation.
   - A reliable date/time library for recurring lessons and time-zone handling.
   - Automated database backup and recovery facilities.

## Data and External-Service Plan
### Data stored by the application
1. **Account data**: User ID, email, authentication reference	Account access and record ownership.
2. **Student data**: Name, contact details, age, notes, learning materials	Student management.
3. **Lesson data**: Date, time, duration, price, status	Scheduling and lesson history.
4. **Recurrence data**: Selected weekdays, start and end dates	Generating recurring lesson occurrences.
5. **Reporting data**: Lesson totals and income aggregates	Income summaries and cancellation reports.
6. **Technical metadata**: Creation and update timestamps	Data integrity and troubleshooting.
#### Data relationships
   - One tutor has many students.
   - One tutor has many lessons.
   - One lesson can have many students.
   - One student can have many lessons.
   - One recurrence series can generate many lesson occurrences.
### External services
1. **Authentication**: Managed provider or secure equivalent.
2. **Database**: PostgreSQL or equivalent relational database.
3. **Hosting**: Frontend and backend deployment.
### Privacy and data handling
Student contact information and information about minors can be sensitive. The product should minimise collected data, enforce strict access control, define retention rules, and support appropriate deletion and export processes.
The legal basis, consent requirements, and retention obligations should be confirmed before production launch, especially if the application is used in the European Union.
## Top Risks and Open Questions
### Top risks
1. Incorrect recurring lesson generation.
2. Incorrect income calculations.
3. Confusing cancellation semantics.
4. Duplicate student profiles.
5. Group lesson pricing ambiguity.
6. Unauthorised access to student data.
7. Time-zone and daylight-saving errors.
8. Accidental edits to recurring schedules.
9. Loss of stored data.
### Open questions
1. What does the lesson price represent?
 	- A fixed price for the entire lesson, regardless of the number of students.
 	- A price per student in a group lesson.
 	- Either, depending on the lesson.
2. How should recurring lessons work?
 	- Repeat indefinitely until manually stopped.
 	- Repeat until a selected end date.
 	- Repeat for a defined number of occurrences.
3. What happens when a recurring lesson is changed?
4. What counts as earned income?
5. How should cancellations affect income?
6. How should group lesson history work?
7. What student information is necessary?
8. Is external calendar synchronisation necessary?
### Recommended development order:
1.	Account access and database structure.
2.	Student records and lesson creation.
3.	Recurring schedules and calendar views.
4.	Lesson status changes and rescheduling.
5.	Income calculations and cancellation reporting.
6.	Security, accessibility, and acceptance testing.






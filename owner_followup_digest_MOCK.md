# Daily Digest Preview, Friday 13 November 2026

> MOCK NOTIFICATION. NOT SENT. Needs approval by a named human before anything is sent. Source workbook untouched.

**Trigger:** daily schedule (08:00, simulated) | **Inputs:** Projects, Tasks, Task_Updates | **Reference date:** 13 Nov 2026

## Needs confirmation (not guessed)

- **WAITING_PARTY_UNKNOWN** T-002 is waiting on someone, but the data does not say who ('Draft 70% complete; awaiting product fact confirmation.') _(source: Tasks!row 3)_
- **WAITING_PARTY_UNKNOWN** T-008 is waiting on someone, but the data does not say who ('Awaiting written approval after one correction.') _(source: Tasks!row 9)_
- **FORECAST_CONFLICT** T-009 forecasts Mon 16 Nov but its predecessor T-008 forecasts Tue 17 Nov (later) _(source: Tasks!rows 10,9)_
- **SYSTEMIC_SLIP** All 16 open tasks forecast later than their due date; due dates may be stale baselines. Confirm before treating every task as late _(source: Tasks)_

## Preview per project lead

**To (proposed): Mia Santos** | PRJ-101 Product Listing Refresh | AMBER (reported: In Progress) | P1: 0, P2: 3, P3: 1
- P2 T-002 (Mia Santos): Name who you are waiting on (the data does not say) and agree a date with them
- P2 T-003 (Jordan Lee): Say exactly what unblocks it, who decides, and by when
- P2 T-003 (Mia Santos): Unblock T-003: Jordan Lee reports 'I can review images after copy direction is approved.' (depends on your T-002)

**To (proposed): Ethan Cruz** | PRJ-102 Monthly Reporting Automation | RED (reported: At Risk) | P1: 1, P2: 1, P3: 1
- P1 T-005 (Ethan Cruz): Give a revised due date and a recovery plan
- P2 T-006 (Ethan Cruz): Give a revised date; this depends on T-005, which is blocked/overdue

**To (proposed): Lara Reyes** | PRJ-103 New Product Launch | RED (reported: In Progress) | P1: 1, P2: 1, P3: 3
- P1 T-008 (Lara Reyes): Say exactly what unblocks it, who decides, and by when
- P2 T-009 (Lara Reyes): Confirm the new schedule after the supplier replies and update the forecast

**To (proposed): Noah Lim** | PRJ-104 Team SOP Cleanup | AMBER (reported: Not Started) | P1: 0, P2: 1, P3: 1
- P2 T-013 (Noah Lim): Confirm a start date and propose a revised due date

**To (proposed): Ava Garcia** | PRJ-105 AI Support Inbox Triage | AMBER (reported: In Progress) | P1: 0, P2: 3, P3: 1
- P2 T-016 (Ava Garcia): Confirm whether the due date or the forecast is correct and update the tracker
- P2 T-017 (Ethan Cruz): Confirm whether the due date or the forecast is correct and update the tracker
- P2 T-017 (Ava Garcia): Unblock T-017: Ethan Cruz reports 'I can start after seeing prototype output format.' (depends on your T-016)

## Follow-ups grouped by owner, then priority

### Ava Garcia
- **P2** T-016 Build classification prototype (PRJ-105): Confirm whether the due date or the forecast is correct and update the tracker. _Why: Forecast Tue 17 Nov is 4 day(s) after due Fri 13 Nov_
- **P2** T-017 Add human-review queue (PRJ-105): Unblock T-017: Ethan Cruz reports 'I can start after seeing prototype output format.' (depends on your T-016). _Why: Ethan Cruz is waiting on T-016_
- **P3** T-012 Create launch campaign brief (PRJ-103): No chase needed now: waiting on T-008; re-check when that moves. _Why: Impacted by root cause T-008_

### Ethan Cruz
- **P1** T-005 Confirm source report columns (PRJ-102): Give a revised due date and a recovery plan. _Why: Past due Wed 11 Nov; forecast Sat 14 Nov_
- **P2** T-006 Build data-cleaning workflow (PRJ-102): Give a revised date; this depends on T-005, which is blocked/overdue. _Why: Due Sat 14 Nov but forecast Wed 18 Nov and upstream is stuck_
- **P2** T-017 Add human-review queue (PRJ-105): Confirm whether the due date or the forecast is correct and update the tracker. _Why: Forecast Wed 18 Nov is 1 day(s) after due Tue 17 Nov_

### Jordan Lee
- **P2** T-003 Approve image sequence (PRJ-101): Say exactly what unblocks it, who decides, and by when. _Why: Blocked; 1 downstream task(s) wait on it_

### Lara Reyes
- **P1** T-008 Approve packaging artwork (PRJ-103): Say exactly what unblocks it, who decides, and by when. _Why: Blocked; 4 downstream task(s) wait on it_
- **P2** T-009 Confirm production completion date (PRJ-103): Confirm the new schedule after the supplier replies and update the forecast. _Why: Supplier schedule may shift by 3–5 days._

### Mia Santos
- **P2** T-002 Draft revised listing copy (PRJ-101): Name who you are waiting on (the data does not say) and agree a date with them. _Why: Draft 70% complete; awaiting product fact confirmation._
- **P2** T-003 Approve image sequence (PRJ-101): Unblock T-003: Jordan Lee reports 'I can review images after copy direction is approved.' (depends on your T-002). _Why: Jordan Lee is waiting on T-002_
- **P3** T-010 Prepare listing content (PRJ-103): No chase needed now: waiting on T-008; re-check when that moves. _Why: Impacted by root cause T-008_
- **P3** T-004 Prepare upload checklist (PRJ-101): No chase needed now: waiting on T-003; re-check when that moves. _Why: Impacted by root cause T-003_

### Noah Lim
- **P2** T-013 Inventory existing SOPs (PRJ-104): Confirm a start date and propose a revised due date. _Why: Past due Thu 12 Nov and not started; no revised date on file_
- **P3** T-011 Prepare inbound shipment plan (PRJ-103): No chase needed now: waiting on T-008; re-check when that moves. _Why: Impacted by root cause T-008_
- **P3** T-014 Prioritize SOP updates (PRJ-104): No chase needed now: waiting on T-013; re-check when that moves. _Why: Impacted by root cause T-013_

### Priya Shah
- **P3** T-007 Test weekly summary (PRJ-102): No chase needed now: waiting on T-005; re-check when that moves. _Why: Impacted by root cause T-005_
- **P3** T-018 Test and document errors (PRJ-105): Confirm whether the due date or the forecast is correct and update the tracker. _Why: Forecast Thu 19 Nov is 1 day(s) after due Wed 18 Nov_

## Rules used

- Overdue: open and due date before the reference date. Blocked: status = Blocked. At risk: forecast later than due date.
- P1: Critical-priority task blocked/overdue, or a critical dependency that is blocked/overdue. P2: any other blocked/overdue task, critical dependency, due within 1 day and slipping, or Critical task slipping. P3: slipping only, or impacted by a root cause (chase the root).
- Critical dependency: 2+ downstream tasks and (blocked or overdue or forecast 3+ days late or a reported schedule risk).

## Approval

- [ ] Approved to send by: ____________ (name) at ____ . Until ticked, nothing is sent and no records change.
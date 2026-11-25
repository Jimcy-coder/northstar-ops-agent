# Project Health Report, Friday 13 November 2026

_Source: Northstar_Fictional_Assessment_Data (all data fictional). Read-only analysis; no records changed._

## Management summary

**Confirmed facts (values recorded in the workbook)**

- 16 of 18 tasks are open; 2 are Done (Tasks).
- Blocked: T-003 (Jordan Lee), T-008 (Lara Reyes) (Tasks.Status; same status reported in Task_Updates for T-003, T-008).
- Past their due date as of 13 Nov: T-005 due Wed 11 Nov, T-008 due Thu 12 Nov, T-013 due Thu 12 Nov.
- Latest recorded reason for T-003: "Waiting for copy direction."
- Latest recorded reason for T-008: "Awaiting written approval after one correction."

**Derived by rules (computed, reproducible)**

- PRJ-101 Product Listing Refresh: **AMBER** (blocked/overdue: T-003; thin margin: 1 day(s) between latest forecast and target)
- PRJ-102 Monthly Reporting Automation: **RED** (latest forecast Thu 19 Nov is 2 day(s) after target Tue 17 Nov)
- PRJ-103 New Product Launch: **RED** (Critical-priority task blocked/overdue: T-008; thin margin: 1 day(s) between latest forecast and target)
- PRJ-104 Team SOP Cleanup: **AMBER** (blocked/overdue: T-013)
- PRJ-105 AI Support Inbox Triage: **AMBER** (tasks forecast after their due dates; thin margin: 0 day(s) between latest forecast and target)
- Critical dependencies: T-008 (4 downstream), T-002 (2 downstream), T-005 (2 downstream), T-009 (2 downstream), T-016 (2 downstream).

**Assumptions and items to confirm (not facts)**

- T-002 is waiting on someone, but the data does not say who ('Draft 70% complete; awaiting product fact confirmation.')
- T-008 is waiting on someone, but the data does not say who ('Awaiting written approval after one correction.')
- T-009 forecasts Mon 16 Nov but its predecessor T-008 forecasts Tue 17 Nov (later)
- T-013 is past due but status says 'Not Started'; status field does not show lateness
- Due/forecast falls on a Sat/Sun; working days not defined in the data (assumed calendar days)
- All 16 open tasks forecast later than their due date; due dates may be stale baselines. Confirm before treating every task as late
- Only one week of metrics: velocity/trend cannot be computed
- Project status 'In Progress' vs derived RED: label may understate risk
- ASSUMPTION (not confirmed): if T-009's supplier slip of 3-5 days is real and downstream tasks shift equally, the last forecast moves from Thu 26 Nov to Sun 29 Nov-Tue 01 Dec vs target Fri 27 Nov. The update's own note: 'Confirmation expected Monday.'.

**Top follow-ups**

- P1 Lara Reyes: T-008, Say exactly what unblocks it, who decides, and by when
- P1 Ethan Cruz: T-005, Give a revised due date and a recovery plan
- P2 Mia Santos: T-003, Unblock T-003: Jordan Lee reports 'I can review images after copy direction is approved.' (depends on your T-002)
- P2 Ava Garcia: T-017, Unblock T-017: Ethan Cruz reports 'I can start after seeing prototype output format.' (depends on your T-016)

## Project detail and evidence

**PRJ-101 Product Listing Refresh** lead Mia Santos | derived **AMBER** | reported 'In Progress' | target Fri 20 Nov | latest forecast Thu 19 Nov | margin 1 day(s)
- Why AMBER: blocked/overdue: T-003; thin margin: 1 day(s) between latest forecast and target
- Reported risk (Projects.Current Risk): Final image approval depends on copy direction.
- Tasks behind the call:
  - **T-002 Draft revised listing copy** (PRJ-101, owner Mia Santos)
    - Source Tasks!row 3: Status=In Progress | Due=Fri 13 Nov | Forecast=Mon 16 Nov | Priority=High | Depends on=T-001
    - Latest Update (Tasks): Draft 70% complete; awaiting product fact confirmation.
    - Task_Updates!row 2 (13 Nov 09:10, Mia Santos): Copy draft 70% complete. / Waiting for confirmation of approved product facts.
    - Rules fired: overdue=False, blocked=False, forecast slip=3 day(s), downstream tasks=['T-003', 'T-004'], dependency level=critical, tier=P2
    - No upstream root cause
    - Open data issue: WAITING_PARTY_UNKNOWN: T-002 is waiting on someone, but the data does not say who ('Draft 70% complete; awaiting product fact confirmation.')
  - **T-003 Approve image sequence** (PRJ-101, owner Jordan Lee)
    - Source Tasks!row 4: Status=Blocked | Due=Sat 14 Nov | Forecast=Wed 18 Nov | Priority=High | Depends on=T-002
    - Latest Update (Tasks): Waiting for copy direction.
    - Task_Updates!row 8 (13 Nov 13:20, Jordan Lee): I can review images after copy direction is approved. / Dependency remains open.
    - Rules fired: overdue=False, blocked=True, forecast slip=4 day(s), downstream tasks=['T-004'], dependency level=watch, tier=P2
    - No upstream root cause
    - Open data issue: WEEKEND_DATES: Due/forecast falls on a Sat/Sun; working days not defined in the data (assumed calendar days)

**PRJ-102 Monthly Reporting Automation** lead Ethan Cruz | derived **RED** | reported 'At Risk' | target Tue 17 Nov | latest forecast Thu 19 Nov | margin -2 day(s)
- Why RED: latest forecast Thu 19 Nov is 2 day(s) after target Tue 17 Nov
- Reported risk (Projects.Current Risk): Source data column names changed.
- Tasks behind the call:
  - **T-005 Confirm source report columns** (PRJ-102, owner Ethan Cruz)
    - Source Tasks!row 6: Status=Overdue | Due=Wed 11 Nov | Forecast=Sat 14 Nov | Priority=High | Depends on=none
    - Latest Update (Tasks): Export changed 'Sales' to 'Ordered Revenue'.
    - Task_Updates!row 3 (13 Nov 09:25, Ethan Cruz): Export file uses 'Ordered Revenue' instead of 'Sales'. / Mapping has not been updated.
    - Rules fired: overdue=True, blocked=False, forecast slip=3 day(s), downstream tasks=['T-006', 'T-007'], dependency level=critical, tier=P1
    - No upstream root cause
    - Open data issue: WEEKEND_DATES: Due/forecast falls on a Sat/Sun; working days not defined in the data (assumed calendar days)
  - **T-006 Build data-cleaning workflow** (PRJ-102, owner Ethan Cruz)
    - Source Tasks!row 7: Status=In Progress | Due=Sat 14 Nov | Forecast=Wed 18 Nov | Priority=High | Depends on=T-005
    - Latest Update (Tasks): Workflow still expects old column names.
    - Rules fired: overdue=False, blocked=False, forecast slip=4 day(s), downstream tasks=['T-007'], dependency level=none, tier=P2
    - Waiting on root cause: ['T-005']
    - Open data issue: WEEKEND_DATES: Due/forecast falls on a Sat/Sun; working days not defined in the data (assumed calendar days)

**PRJ-103 New Product Launch** lead Lara Reyes | derived **RED** | reported 'In Progress' | target Fri 27 Nov | latest forecast Thu 26 Nov | margin 1 day(s)
- Why RED: Critical-priority task blocked/overdue: T-008; thin margin: 1 day(s) between latest forecast and target
- Reported risk (Projects.Current Risk): Packaging approval is blocking downstream work.
- Tasks behind the call:
  - **T-008 Approve packaging artwork** (PRJ-103, owner Lara Reyes)
    - Source Tasks!row 9: Status=Blocked | Due=Thu 12 Nov | Forecast=Tue 17 Nov | Priority=Critical | Depends on=none
    - Latest Update (Tasks): Awaiting written approval after one correction.
    - Task_Updates!row 4 (13 Nov 10:00, Lara Reyes): Artwork approval pending; reviewer requested one correction. / Do not mark approved until written sign-off.
    - Rules fired: overdue=True, blocked=True, forecast slip=5 day(s), downstream tasks=['T-009', 'T-010', 'T-011', 'T-012'], dependency level=critical, tier=P1
    - No upstream root cause
    - Open data issue: WAITING_PARTY_UNKNOWN: T-008 is waiting on someone, but the data does not say who ('Awaiting written approval after one correction.')
  - **T-009 Confirm production completion date** (PRJ-103, owner Lara Reyes)
    - Source Tasks!row 10: Status=In Progress | Due=Sat 14 Nov | Forecast=Mon 16 Nov | Priority=High | Depends on=T-008
    - Latest Update (Tasks): Supplier says schedule may shift by 3–5 days.
    - Task_Updates!row 5 (13 Nov 10:30, Lara Reyes): Supplier schedule may shift by 3–5 days. / Confirmation expected Monday.
    - Rules fired: overdue=False, blocked=False, forecast slip=2 day(s), downstream tasks=['T-011', 'T-012'], dependency level=critical, tier=P2
    - Waiting on root cause: ['T-008']
    - Open data issue: FORECAST_CONFLICT: T-009 forecasts Mon 16 Nov but its predecessor T-008 forecasts Tue 17 Nov (later)
    - Open data issue: WEEKEND_DATES: Due/forecast falls on a Sat/Sun; working days not defined in the data (assumed calendar days)
- ASSUMPTION (not confirmed): if T-009's supplier slip of 3-5 days is real and downstream tasks shift equally, the last forecast moves from Thu 26 Nov to Sun 29 Nov-Tue 01 Dec vs target Fri 27 Nov. The update's own note: 'Confirmation expected Monday.'.

**PRJ-104 Team SOP Cleanup** lead Noah Lim | derived **AMBER** | reported 'Not Started' | target Tue 24 Nov | latest forecast Fri 20 Nov | margin 4 day(s)
- Why AMBER: blocked/overdue: T-013
- Reported risk (Projects.Current Risk): Owner has not confirmed start date.
- Tasks behind the call:
  - **T-013 Inventory existing SOPs** (PRJ-104, owner Noah Lim)
    - Source Tasks!row 14: Status=Not Started | Due=Thu 12 Nov | Forecast=Sun 15 Nov | Priority=Medium | Depends on=none
    - Latest Update (Tasks): No start update received.
    - Task_Updates!row 6 (13 Nov 11:15, Noah Lim): I have not started this yet. / No revised due date proposed.
    - Rules fired: overdue=True, blocked=False, forecast slip=3 day(s), downstream tasks=['T-014'], dependency level=watch, tier=P2
    - No upstream root cause
    - Open data issue: STATUS_LABEL_GAP: T-013 is past due but status says 'Not Started'; status field does not show lateness
    - Open data issue: WEEKEND_DATES: Due/forecast falls on a Sat/Sun; working days not defined in the data (assumed calendar days)

**PRJ-105 AI Support Inbox Triage** lead Ava Garcia | derived **AMBER** | reported 'In Progress' | target Thu 19 Nov | latest forecast Thu 19 Nov | margin 0 day(s)
- Why AMBER: tasks forecast after their due dates; thin margin: 0 day(s) between latest forecast and target
- Reported risk (Projects.Current Risk): Human-review queue is not yet built.
- Tasks behind the call:
  - **T-016 Build classification prototype** (PRJ-105, owner Ava Garcia)
    - Source Tasks!row 17: Status=In Progress | Due=Fri 13 Nov | Forecast=Tue 17 Nov | Priority=High | Depends on=T-015
    - Latest Update (Tasks): Sometimes marks routine billing questions urgent.
    - Task_Updates!row 7 (13 Nov 12:05, Ava Garcia): Prototype sometimes marks billing questions urgent. / Needs evaluation and threshold tuning.
    - Rules fired: overdue=False, blocked=False, forecast slip=4 day(s), downstream tasks=['T-017', 'T-018'], dependency level=critical, tier=P2
    - No upstream root cause
  - **T-017 Add human-review queue** (PRJ-105, owner Ethan Cruz)
    - Source Tasks!row 18: Status=Not Started | Due=Tue 17 Nov | Forecast=Wed 18 Nov | Priority=Critical | Depends on=T-016
    - Latest Update (Tasks): Required before any live use.
    - Task_Updates!row 9 (13 Nov 14:00, Ethan Cruz): I can start after seeing prototype output format. / Critical human-review gate.
    - Rules fired: overdue=False, blocked=False, forecast slip=1 day(s), downstream tasks=['T-018'], dependency level=none, tier=P2
    - No upstream root cause

# Agent demo transcript (actual output)

### Q: What is overdue right now?

Overdue as of 13 Nov 2026 (open, due before today):
- T-005 Confirm source report columns (Ethan Cruz, PRJ-102): due Wed 11 Nov, forecast Sat 14 Nov, Overdue
- T-008 Approve packaging artwork (Lara Reyes, PRJ-103): due Thu 12 Nov, forecast Tue 17 Nov, Blocked
- T-013 Inventory existing SOPs (Noah Lim, PRJ-104): due Thu 12 Nov, forecast Sun 15 Nov, Not Started

Due today (not yet overdue):
- T-002 Draft revised listing copy (Mia Santos, PRJ-101): due Fri 13 Nov, forecast Mon 16 Nov, In Progress
- T-016 Build classification prototype (Ava Garcia, PRJ-105): due Fri 13 Nov, forecast Tue 17 Nov, In Progress

### Q: Which projects are at risk and why?

Project health (derived from rules; ask 'why PRJ-103' for the evidence):
- PRJ-101 Product Listing Refresh: **AMBER** (reported 'In Progress'): blocked/overdue: T-003; thin margin: 1 day(s) between latest forecast and target
- PRJ-102 Monthly Reporting Automation: **RED** (reported 'At Risk'): latest forecast Thu 19 Nov is 2 day(s) after target Tue 17 Nov
- PRJ-103 New Product Launch: **RED** (reported 'In Progress'): Critical-priority task blocked/overdue: T-008; thin margin: 1 day(s) between latest forecast and target
- PRJ-104 Team SOP Cleanup: **AMBER** (reported 'Not Started'): blocked/overdue: T-013
- PRJ-105 AI Support Inbox Triage: **AMBER** (reported 'In Progress'): tasks forecast after their due dates; thin margin: 0 day(s) between latest forecast and target

### Q: What should Ethan Cruz do first?

Recommended follow-ups:
- P1 **Ethan Cruz** T-005: Give a revised due date and a recovery plan (why: Past due Wed 11 Nov; forecast Sat 14 Nov)
- P2 **Ethan Cruz** T-006: Give a revised date; this depends on T-005, which is blocked/overdue (why: Due Sat 14 Nov but forecast Wed 18 Nov and upstream is stuck)
- P2 **Ethan Cruz** T-017: Confirm whether the due date or the forecast is correct and update the tracker (why: Forecast Wed 18 Nov is 1 day(s) after due Tue 17 Nov)

### Q: Why is PRJ-103 red? Show me the evidence.

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
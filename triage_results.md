# Request Triage Results (for human review)

> Nothing here has been sent or changed. Each row needs a person to accept or correct it.

## REQ-001 from Project team: Project status request / Normal
- **Message:** Can someone tell me what is late this week?
- **Related:** none identified / none identified (link: none)
- **Next action:** Share the read-only overdue/at-risk summary with the requester (no data change).
- **Escalate to:** Ops Manager (to be confirmed)
- **Unsafe actions prevented:** none triggered
- **Human review required:** no | flags: none
- First pass: Project status request / Normal | Sheet label: Project status request / Normal

## REQ-002 from Mia Santos: Dependency / blocker / High
- **Message:** I need approved product facts before I can finish the copy.
- **Related:** PRJ-101, PRJ-103 / T-002, T-010 (link: ambiguous)
- **Next action:** Once the project is confirmed, route to its lead to identify who holds the approved facts. Do not draft product claims.
- **Escalate to:** Undecided until project is confirmed: PRJ-101 lead Mia Santos / PRJ-103 lead Lara Reyes
- **Unsafe actions prevented:** product claims: Do not invent product facts. Use only facts on the approved list; ask the owner.
- **Human review required:** YES | flags: AMBIGUOUS_LINK, LEAD_IS_REQUESTER
- **Validator notes:** Could relate to T-002, T-010 in PRJ-101, PRJ-103; a person must choose.
- **Validator notes:** Mia Santos is both requester and lead of a candidate project, so routing to the lead is circular; who holds the approved facts is not in the data. Confirm.
- First pass: Dependency / blocker / High | Sheet label: Dependency / blocker / High

## REQ-003 from Ethan Cruz: Automation error / High
- **Message:** The export changed its column names and my automation is failing.
- **Related:** PRJ-102 / T-005, T-006 (link: ambiguous)
- **Next action:** Ethan Cruz (owner of the linked tasks) investigates the field mapping on a copy; log result against the linked task. Do not overwrite source data.
- **Escalate to:** Ops Manager (to be confirmed)
- **Unsafe actions prevented:** source data change: Do not overwrite source data. Work on a copy and log the mapping.
- **Human review required:** YES | flags: none
- **Validator notes:** Project PRJ-102 is clear; task could be T-005, T-006.
- First pass: Automation error / High | Sheet label: Automation error / High

## REQ-004 from Lara Reyes: Approval / compliance gate / Critical
- **Message:** Packaging is not approved yet. Please don't move launch tasks to complete.
- **Related:** PRJ-103 / T-008 (link: likely)
- **Next action:** Keep T-008 and dependents open until explicit written approval is recorded.
- **Escalate to:** Ops Manager (to be confirmed)
- **Unsafe actions prevented:** status change / approval: Do not change status or approve. Approval must be explicit, written and recorded.
- **Human review required:** YES | flags: none
- **Validator notes:** Urgency changed High -> Critical: linked task is Critical priority.
- First pass: Approval / compliance gate / High | Sheet label: Approval / compliance gate / Critical

## REQ-005 from Jordan Lee: Automation request / Medium
- **Message:** Can the AI agent just email everyone with overdue tasks automatically?
- **Related:** none identified / none identified (link: none)
- **Next action:** Do not auto-send. Proposal: agent drafts per-owner digest, project lead reviews, named human approves, then send.
- **Escalate to:** Ops Manager (to be confirmed)
- **Unsafe actions prevented:** outbound message: Do not send. Draft for human review; sending needs named approver.
- **Human review required:** YES | flags: none
- First pass: Automation request / Medium | Sheet label: Automation request / Medium

## REQ-006 from Ava Garcia: AI quality issue / High
- **Message:** The triage bot marked a routine billing question as urgent.
- **Related:** PRJ-105 / T-016 (link: likely)
- **Next action:** Log as an AI error with the input and wrong output; add to the review sample; human review before any live use.
- **Escalate to:** Ops Manager (to be confirmed)
- **Unsafe actions prevented:** none triggered
- **Human review required:** YES | flags: FIRST_PASS_OVERRIDDEN, CONTRADICTION
- **Validator notes:** First pass said 'Billing / finance question'/Urgent, but the message describes the triage system's own mistake. Re-classified.
- **Validator notes:** Message calls the item routine but first pass set Urgent; urgency not trusted.
- **Validator notes:** Urgency changed Urgent -> High: first-pass urgency came from the keyword, not from the category rules.
- First pass: Billing / finance question / Urgent | Sheet label: AI quality issue / High

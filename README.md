# Northstar Ops Agent: implementation note

All data is fictional. Nothing here contacts anyone, connects to a live system, edits the source workbook, or sends a message.

## Run it

```
pip install -r requirements.txt       # pandas, openpyxl, xlrd (original .xls), anthropic (model layer)
python ops_agent.py selftest            # 12 checks, regenerates every sample output
python ops_agent.py all                 # writes /outputs
python ops_agent.py ask "What is overdue right now?"
python ops_agent.py chat                # interactive rule-based agent (no API needed)

## What it does, by challenge

| Challenge | File produced | What was built |
|---|---|---|
| 1. Monitoring agent | `agent_demo_transcript.md`, `project_health_report.md`, `facts_pack.json` | Deterministic tools compute overdue, blocked, at-risk, critical dependencies and project health. The agent answers questions from those tools and can show evidence (sheet, row, rule fired) for any task or project. |
| 2. Escalation workflow | `owner_followup_digest_MOCK.md` | Rules against the 13 Nov 2026 reference date, follow-ups grouped by owner and priority (P1-P3), a mock lead notification, and a "needs confirmation" section. |
| 3. Request triage | `triage_results.md/.json` | First-pass classifier, then a validator that checks safety, links requests to tasks, catches errors and routes to a human. |
| 1 and 3, model-driven | `llm_agent.py` | Claude tool-use agent over the same deterministic tools, plus an LLM first pass for triage. The model has no send/approve/edit tool; `propose_action` only queues a PENDING entry in `approval_queue.jsonl`. |
| 4. Improve and validate | below | Two improvements and success measures. |

## AI tools used

Claude (Anthropic) was used to read the brief and workbook, write and test the Python prototype.

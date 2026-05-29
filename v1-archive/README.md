# Version 1 — The Learning Phase

> *We built something real, learned from real usage, and let the data tell us what mattered.*

---

## What We Set Out to Build

Version 1 was our proving ground. The goal was simple — ship a lightweight task tracker fast, then layer in automations to reduce admin work.

We wanted:

- Automatic timestamps for task creation and updates
- Unique task IDs to remove ambiguity
- Basic automations for status changes and reminders
- KPIs to measure productivity, cycle time, and completion rates

Nothing fancy. Just something real we could actually use and learn from.

---

## What Actually Worked

**Timestamps** — Reliable creation and update times made everything auditable and enabled trend analysis. This worked exactly as intended.

**Task IDs** — Stable, unique identifiers prevented duplication and made cross-referencing effortless. Categorised automatically by type — networking, personal, projects — giving every task a clear identity.

**KPI Calculations** — Simple, transparent formulas gave us cycle time, completion rate, and workload by category without overcomplicating things.

These pieces formed the trustworthy backbone of the system. Even when other parts wobbled, we could still measure and reason about what was happening.

---

## What Broke

**Completion date logic** — We tied the completion date to a status change event that could be triggered multiple times or missed entirely if tasks were edited in bulk. This caused:

- Completion dates being overwritten when tasks were re-opened
- Missing completion dates for edge-case flows
- Inconsistent metrics downstream

We learned that event-based fields without proper safeguards drift quickly under real usage.

---

## Key Lessons Learned

- Make source-of-truth fields immutable once set — for example, lock the first completion timestamp
- Design automations to be reliable and repeatable — they must handle real-world messiness, not just ideal conditions
- Keep KPIs simple and explainable — complexity hides data problems
- Plan architecture before building — adding structure later means rebuilding, not extending
- Treat user behaviour as input, not an exception

---

## Why This Matters

Version 1 proved the concept works. The automations, the task ID logic, the KPI calculations — all of it showed that a self-managing productivity system is achievable inside Google Sheets.

But it also showed us exactly where the gaps were.

**Version 2 builds on these lessons** — with better architecture, a cleaner structure, and a focus on what actually matters: connecting every task back to your goals.“Because productivity isn’t just about tracking tasks — it’s about knowing that the work you’re doing is actually moving your life forward.”

---

*This archive exists so we never forget where we started — and why we changed direction.*

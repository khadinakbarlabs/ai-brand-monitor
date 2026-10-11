---
name: brand-schedule
description: Plan, configure or pause user-approved recurring AI brand collection through Apify schedules and the official CLI. Explain per-run spend caps, service dependencies and the limits of expiry, total budgets and automatic report delivery.
---

# Recurring brand monitoring

Read [monitoring](../ai-brand-monitor/references/monitoring.md), [execution](../ai-brand-monitor/references/execution.md) and [state](../ai-brand-monitor/references/state.md). This skills-only package has no background worker, hook, bundled scheduler, email sender or persistent agent. Installing it does not enable monitoring.

Confirm the exact brand, fixed prompt panel, platforms, cadence, time zone, start/end expectations, per-run cap and delivery destination. Preview recurring cost from current pricing and the number of scheduled executions. A one-time audit approval does not authorize recurring paid use. Keep research and the schedule proposal useful while approval is pending.

Native Apify schedules collect fixed Actor inputs with per-action caps. They do not themselves enforce a hard monthly portfolio cap, automatic end date, cross-schedule budget reservations or complete analytical report delivery. If the user requires these guarantees, configure only with a verified user-owned controller that enforces them; otherwise offer manual reviews. Never activate an unbounded schedule while promising a bounded pilot.

After explicit recurring approval, create a disabled schedule from the verified request shape, read it back, and verify its Actor ID, pinned build, inputs, timezone, cadence, exclusivity and caps. Enable only under the approved scope. Save the returned schedule ID, state and next execution. If a request times out, reconcile by ID/name before creating another.

Use reversible disabling for a user-requested pause; verify `isEnabled: false`. Read the current service state before resuming and confirm that recurring authorization remains applicable. Do not delete tasks or datasets as a shortcut. Retrieval and report review use brand-trends; delivery to any external destination needs explicit authorization for that destination.

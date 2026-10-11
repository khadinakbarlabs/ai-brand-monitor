# Private campaign state

Save only the work the user requests in a campaign folder they select. Propose `.ai-brand-monitor/<safe-brand-id>/` in their current workspace when they ask to save; keep it outside plugin source and version control. Do not scan for campaigns in other projects. Read only named files from the selected campaign on return. New facts overwrite corrected facts; preserve an audit trail of corrections without saving conversation transcripts.

Suggested layout:

```text
state.json
context.md
panel.json
actions.json
attempts/<attempt-id>/input.json
attempts/<attempt-id>/receipt.json
runs/<run-id>/run.json
runs/<run-id>/answers.json
runs/<run-id>/summary.json
runs/<run-id>/output.json
reports/<report-id>/report.md
reports/<report-id>/report.html
reports/<report-id>/answers.csv
reports/<report-id>/evidence.json
reports/<report-id>/metrics.json
```

The [state template](examples/state-template.json) is a proposal with no approved budget. Store schema version, stable campaign ID, brand/domain/aliases/competitors, market/language, panel version, source-backed business facts, user corrections, selected platforms, model/build cohorts, evidence references and action statuses. No passwords, tokens, auth files, personal identifiers or raw chat history.

## Shared ledger

Store campaign cap, exact current authorization scope, each attempted run's cap/reservation/status, and verified settled charges. Available budget = approved cap - settled charges - outstanding reservations. Reserve the full per-run cap before POST. A timed-out start, active run or uncertain final bill keeps the reservation. Release only after reconciliation. Never trust a saved flag as fresh authorization for a new target, larger spend, new delivery destination or recurring job.

Each action records ID, evidence references, recommendation, confidence, effort, user choice, status and next check. Keep rejected/deferred actions visible so they are not proposed repeatedly. A local state file is not a credential store or an enforcement service.

Use safe contained paths, atomic replacements and a campaign lock or serial execution when multiple operations could spend the same budget. If reliable serialization is unavailable, execute one run at a time; never claim a hard portfolio cap across independent schedules.

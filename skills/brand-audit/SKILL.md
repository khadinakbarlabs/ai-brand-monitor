---
name: brand-audit
description: Run a user-approved brand visibility baseline or refresh through the official Apify CLI, using a fixed prompt panel and spend cap. Verify run status, usable answers, coverage and charges before reporting brand mentions or citations.
---

# Brand audit

Read the coordinator's [execution guide](../ai-brand-monitor/references/execution.md), [Actor contracts](../ai-brand-monitor/references/actors.md) and [security rules](../ai-brand-monitor/references/security.md) before collection. Use only `khadinakbar/ai-search-brand-monitor` for brand answer checks. Optional citation collection belongs to brand-citations.

Build a compact prompt panel from [prompt design](../ai-brand-monitor/references/prompts.md). Separate brand-free discovery questions, category comparisons and explicitly branded questions. Never boost a discovery score by including the brand in discovery prompts. Start with three prompts and the platforms the user approves. The normal proposed platform set is Perplexity, ChatGPT and Gemini; include Claude only when selected.

For exact questions, set `querySelectionMode: "custom_only"`, `queryTemplates: []`, and `maxQueriesPerPlatform` equal to the unique prompt count, at most 20. Every platform receives the same literal questions. Market and language are prompt wording and campaign metadata; do not invent Actor input fields.

Read live schema and pricing through the CLI, compare with the bundled contracts, and pin the approved build. Preview exact inputs, estimated checks and one shared campaign budget. Reserve each run's full cap before submission. Require authorization covering this target, panel, platforms and amount; approval of a previous report or install does not authorize spending.

Submit once. Persist the returned run ID before polling. On an uncertain start, reconcile existing runs and their INPUT records before retrying. Follow the bounded retrieval and pagination procedure in the execution guide. Keep pending runs and their reservations in state across interruptions.

Check status, usable dataset rows, expected cells, `RUN_SUMMARY`, `OUTPUT`, pricing and charges. A successful health check or empty dataset is not a visibility baseline. Identify failed/error answers and partial coverage. Save raw evidence privately, then calculate metrics using [measurement](../ai-brand-monitor/references/measurement.md). Show failures as unknown, not absent mentions.

End with a clear baseline verdict, per-platform counts, the prompts producing the largest competitive gaps, and three next actions. Preserve the evidence that explains each finding. Do not repeat a completed run unless the user requests a refresh or a justified approved retry.

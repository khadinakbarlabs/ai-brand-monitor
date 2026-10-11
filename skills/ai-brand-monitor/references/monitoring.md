# Recurring collection through Apify

The plugin provides instructions for the user's existing service. It does not run after the host session closes. Read live schedule API capability before mutation. A saved proposal, CLI install or one-time budget does not authorize recurring charges.

The native [schedule create API](https://docs.apify.com/api/v2/schedules-post) accepts `name`, `isEnabled`, `isExclusive`, `cronExpression`, `timezone` and `actions`. A `RUN_ACTOR` action uses the Actor ID, `runInput.body` as a JSON string, `runInput.contentType`, and `runOptions` containing pinned `build`, `timeoutSecs`, `memoryMbytes`, `maxTotalChargeUsd` and `restartOnError: false`. Use the host's safe JSON writer. Do not hand-concatenate input strings or insert credentials.

For an approved schedule:

```sh
apify api POST /v2/schedules --body - < disabled-schedule.json > schedule-receipt.json
apify api GET /v2/schedules/SCHEDULE_ID
```

Read back the disabled schedule before enabling. Compare the exact decoded input, Actor/build, approved cap, cadence and timezone. For enabling or reversible pause, use an explicit JSON file and the documented update method:

```sh
apify api PUT /v2/schedules/SCHEDULE_ID --body - < schedule-state.json
apify api GET /v2/schedules/SCHEDULE_ID
```

An enable file is `{"isEnabled": true}`; a pause file is `{"isEnabled": false}`. Use verified IDs and change only the requested schedule. An uncertain create is reconciled with a bounded schedule listing and saved name/receipt before another POST.

## Limits that affect the user's decision

- A per-action cap is not a cumulative monthly budget.
- `isExclusive` does not establish a shared lock across different schedules.
- The current create schema has no guaranteed `endAt` or automatic pilot expiry.
- A schedule collects answers; it does not reason over reports, send a digest or guarantee external delivery.
- Model/build changes, provider failures and added questions change comparability and cost.

For a fixed-duration/hard-budget pilot, require an actually verified controller that reserves spending, reconciles charges, prevents overlapping campaigns and disables jobs at the approved limit/end. If none exists, keep recurring activation pending and offer a user-triggered review cadence. Do not create a host automation as a substitute without the user's explicit scheduling request and the host's supported tools.

When a user requests alerts, propose meaningful conditions such as a matched-panel decline confirmed in repeated observations, a newly verified source loss, or sustained coverage failures. Remain quiet when unchanged. External alerts need a verified authorized delivery route; the package includes no sender or webhook. On-demand analysis of the collected runs uses brand-trends.

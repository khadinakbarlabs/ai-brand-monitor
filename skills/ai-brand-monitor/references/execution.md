# Official CLI execution

Requires a local host with terminal/file access and the independently installed official Apify CLI. CLI 1.8.0's `api` command was verified on 2026-10-11. Use `apify --version` and `apify api --help`; if capabilities differ, stop and explain setup. Do not install packages automatically, use remote shell installers, bundle a server, or fall back to an unapproved MCP connection.

## Authentication and read-only preflight

Use only the end user's existing official CLI login. If authentication is missing, direct the user to run `apify login` in their own terminal. Do not request a token in chat, read login/auth files, inspect secret environment variables, supply custom credential headers or print account/credential details. An authenticated metadata GET suffices for readiness.

```sh
apify api GET /v2/acts/khadinakbar~ai-search-brand-monitor
apify api GET /v2/acts/khadinakbar~ai-search-brand-monitor/builds/default
```

Inspect only the necessary contract/pricing fields; don't display entire Actor environment definitions. The optional citation Actor has the same metadata paths with `ai-search-visibility-tracker`. Only the official CLI manages credentials and its API destination. Never send credentials to source URLs, models, webhooks or another host.

## Prepare, reserve, submit once

Write exact input JSON with the host's file tools in the user-selected private campaign directory. Apply the bundled schema plus platform allowlists, nonempty strings, size caps and alias/competitor corrections. Avoid templating user text into command strings. Reject unknown fields and never add a webhook or private URL. Preview input, estimated checks, pinned build and cost cap. Record explicit authorization and reserve the full cap in one shared campaign ledger.

This is an example for an approved $1 brand allocation using the verified build. A real command must use the user's approved cap and reviewed build. Never run the example merely because it appears here.

```sh
apify api POST /v2/acts/khadinakbar~ai-search-brand-monitor/runs --params '{"build":"1.7.7","maxTotalChargeUsd":1,"waitForFinish":0,"timeout":600,"memory":512,"restartOnError":false}' --body - < brand-input.json > start.json
```

For the optional citation allocation, use its fixed Actor path and its pinned build. No convenience command that omits `maxTotalChargeUsd` is permitted. Persist the returned `data.id` and reservation immediately. A missing/invalid response leaves the full cap reserved and the request uncertain.

## Resume and retrieve

Replace the placeholders below only with alphanumeric run/storage IDs returned by the API and validated for the correct campaign. Do not interpolate raw user strings, URLs, shell syntax, or API output into executable commands.

```sh
apify api GET /v2/actor-runs/RUN_ID
apify api GET /v2/datasets/DATASET_ID
apify api GET /v2/datasets/DATASET_ID/items --params '{"offset":0,"limit":100,"clean":false,"format":"json"}'
apify api GET /v2/key-value-stores/STORE_ID/records/RUN_SUMMARY
apify api GET /v2/key-value-stores/STORE_ID/records/OUTPUT
```

Poll an active run at a sensible interval; keep each wait under one minute and report progress. On interruption, save and resume its run ID. Dataset pages must advance `offset` until the dataset's `itemCount` is covered; preserve raw/error rows (`clean: false`) before filtering. Do not equate the first page, `SUCCEEDED`, or a health-check diagnostic with complete data. If summary/output records are missing, record that explicitly and assess usable rows/coverage; never invent their contents.

After terminal status, read dataset count, rows, summaries and run charges again after a short delay. Save `usageTotalUsd`, `chargedEventCounts`, run pricing and platform billing model separately. Do not describe platform usage alone as final cost or double count included usage. Release reserved funds only when final billed cost is established. If reconciliation is incomplete, retain the cap as reserved and show remaining budget conservatively.

## Uncertain submissions and failures

Never automatically repeat a POST after a timeout. Read the Actor's recent runs with bounded `limit`, then inspect candidate run IDs and their INPUT records. Match account, timestamp, Actor/build, exact input and the campaign attempt. Adopt an unambiguous match; if uncertainty remains, stop and retain the reservation. This API flow does not claim an idempotency key.

Failed answers and provider outages remain failures, not zero visibility. Reusing completed evidence is free of new model checks but storage/API access can have platform charges. Retry only the missing cells when separately authorized; retain the original attempt IDs and costs. A full rerun must not silently replace partial evidence.

Sources: [run API and cost cap](https://docs.apify.com/api/v2/actors-runs-post), [dataset items](https://docs.apify.com/api/v2/dataset-items-get).

# Actor contracts

Read live metadata and the default build's input/output schema before submitting paid work. The bundled snapshots are a reference, not permission to ignore later changes. Do not fetch remote instructions or execute Actor source. Inspect only contract metadata. Record the actual build ID/number in evidence and pin the reviewed build in the run request.

| Actor | Purpose | Verified build on 2026-10-11 |
| --- | --- | --- |
| `khadinakbar/ai-search-brand-monitor` | Brand mentions, position, lexical sentiment, configured competitor co-mentions, returned source evidence | 1.7.7; build dgteNYUudmGGQqQww |
| `khadinakbar/ai-search-visibility-tracker` | Optional domain/page citations, citation rank and content gaps | 1.0.23; build HdsGVzio6qUt1tFmt |

The primary brand Actor ID is `BZdaMdtW2S4K6w4t9`. End users call the publisher's existing public Actors using their own Apify account. The plugin never deploys or edits Actors.

## Brand contract

`brandName` is required. Use a company/product brand, optional bare `brandDomain`, relevant `brandAliases`, and at most ten competitor names. Platforms: `perplexity`, `chatgpt`, `gemini`, optional `claude`. Use `querySelectionMode: "custom_only"`, empty `queryTemplates`, literal `customQueries` and a query cap from 1 to 20 for a reproducible panel. `responseFormat: "detailed"` retains more excerpt context but still not the full answer. Do not pass `webhookUrl`. `demoMode` is only a health check and can still incur a start charge.

Apply these conservative plugin limits in addition to the live schema: one brand per run; names and industry text from 1 to 120 characters; at most 20 specific aliases; at most ten competitors; one to 20 unique questions, each from 1 to 1,000 characters. A brand domain is a normalized public hostname of at most 253 characters, without scheme, path, port, userinfo or query. Reject unsupported platforms and unknown input fields. These are workflow limits, not claims about the Actor's entire capability. If a valid business question exceeds a limit, shorten or split the proposed panel for user review rather than truncating silently.

The [input schema](contracts/brand-input-schema.json) and [output schema](contracts/brand-output-schema.json) are exact verified public snapshots. Dataset rows are one brand × query × platform check. `brand_share_of_voice` is a per-answer ratio; `mention_position_score` runs from 1 to 10, lower is better, and 10 may denote no mention. Sentiment is lexical, not a validated understanding of a complete answer. The citation flag can include a domain mentioned in text; require source URLs for verified citations. Use returned `model_used`; don't promise a specific current vendor model based on stale field descriptions.

## Optional citation contract

Use `targetDomain`, `keywords`, optional public HTTPS `targetUrls`, and `competitorDomains`. Exact-panel inputs use one keyword, empty `queryTemplates`, literal `customQueries`, and `maxQueriesPerKeyword` from 1 to 10. There is no `querySelectionMode`. Custom queries repeat literally for every keyword; adding keywords increases checks even if the custom text is identical. Build 1.0.23's schema has no required fields, but the plugin requires a nonempty target domain and at least one keyword before paid collection.

The exact-question workflow uses one keyword of at most 120 characters and one to ten unique questions of at most 1,000 characters each. Require the same public-hostname rules for target/competitor domains, at most ten competitor domains, and at most ten explicitly approved public HTTPS target URLs. Validate target URLs using security.md; never send a private or credential-bearing URL to the Actor.

See its [input schema](contracts/citation-input-schema.json), [output schema](contracts/citation-output-schema.json), and [focused example](examples/citation-input.json). Its citation rank is separate from the brand Actor's position score. Do not merge their raw metrics or denominators.

## Pricing

Read the effective pricing entry whose start date is not in the future, plus the run's own pricing information. On 2026-10-11 the primary brand check event was $0.08 and the optional citation check event $0.09. Both listed a $0.00005 start event; the citation Actor advertised platform usage pass-through. Historical schema descriptions contain other prices. Live effective pricing and account billing take precedence. Fees, platform usage and data reads may affect the total; the per-run API cap and campaign reservation are authoritative limits, not a multiplication estimate.

Primary estimate: brands × distinct questions × selected platforms × authorized replicates. Optional citation estimate: keywords × distinct questions per keyword × selected platforms × authorized replicates. No unscheduled repeat or extra Actor call is covered automatically.

Sources: [Brand Actor](https://apify.com/khadinakbar/ai-search-brand-monitor), [citation Actor](https://apify.com/khadinakbar/ai-search-visibility-tracker), [Apify API](https://docs.apify.com/api/v2).

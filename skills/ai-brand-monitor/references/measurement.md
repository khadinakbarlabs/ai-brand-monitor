# Measurement contract

Report sampled API answers, not the exact consumer ChatGPT/Claude interfaces, market-wide popularity, web rankings, demand or guaranteed recommendations. Mention/citation exposure is not revenue. Optional user-provided aggregate analytics exports can add separately labeled traffic/conversion evidence only when explicitly requested; no analytics dependency or automatic account access is included.

## Validity and coverage

Expected cells = fixed prompt × platform × authorized replicate. Record each observed attempt once with its run, actual model, timestamp and prompt class. A usable response requires the expected identity and query, actual substantive answer evidence, valid typed measurement fields, and no error/diagnostic/provider-failure marker. Error text in an answer-summary field remains an error. Missing or ambiguous context makes recommendation/sentiment interpretation unknown even if structured mention counts are usable. Do not fabricate full answers from truncated excerpts.

Deduplicate identical run/query/platform/replicate records; conflicting duplicates are held for review, never cherry-picked. Deduplicate across exported pages, not across legitimate repeated runs. Keep planned, valid, failed and missing counts. Report partial coverage as `valid / planned`, plus each platform's coverage. Compute exposure on valid answers only. Failed checks do not demonstrate brand absence. For a partial run show both the observed rate and the fact that overall panel visibility is unknown.

## Metrics

| Metric | Definition and limits |
| --- | --- |
| Mention rate | Valid answers with `brand_mentioned: true` / valid answers. Show numerator and denominator. Separate discovery and branded prompts. |
| Actor citation flag rate | Rows with `is_cited_as_source: true` / valid rows. This may include domain mentions in text and is not automatically verified source citation. |
| Verified source citation rate | Answers with a safe returned source URL on the brand hostname or proper subdomain / valid answers on citation-capable platforms. Show capability, URL provenance and denominator; unavailable platforms are N/A. |
| Sampled mention share of voice | Sum `brand_mention_count` / sum (`brand_mention_count` + `competitor_mention_count`) over valid matched rows. This is weighted by mention counts, not an average of row ratios. Zero denominator or no configured competitor set is N/A. |
| Competitor presence | Valid answers where the configured competitor occurs in `competitor_mentions` / valid answers. Do not invent per-competitor frequency, sentiment, source share or recommendation rank. |
| Mention position | Average `mention_position_score` only among mentioned answers with valid scores. 1–10, lower is better. Show absence separately; no-mention sentinel values do not enter the mean. Not a SERP/product rank. |
| Sentiment | Actor lexical label distribution only for valid mentioned answers, with available context and sample size. No-mention answers are N/A; negative labels are leads for review, not proof of reputational harm. |
| Recommendations | Evidence-backed qualitative reading of available context: favorable, neutral/hedged, unfavorable, or unknown. A mention or positive keyword alone does not prove an endorsed recommendation. |

`cited_urls` can be unavailable for some providers; use live output/source capability rather than assuming identical citation coverage. A bare domain mention or made-up link is not a verified citation. Count a verified source citation only when the returned evidence identifies it as an actual source or grounding link. A URL merely extracted from answer text remains a textual URL signal; if provenance is ambiguous, mark it unverified. Verify that an observed URL has safe HTTP(S) syntax, no credentials, a public hostname and correct brand boundary; preserve provenance (structured source vs textual URL). A URL occurrence does not prove the linked page supports the answer. Confirm content only when inspected.

## Comparability

Hold the prompt text, platform, language/market, aliases, domain, competitor set and measurement version constant. Preserve model and build changes as cohort breaks. Compare only valid matched cells and show unmatched cells. Percentage-point delta is `100 × (current rate - baseline rate)`. Never carry forward missing answers, fill failures with zeros, or report causal impact from before/after association alone.

Small panels are directional. Repeated observations need explicit budget and stable replicate design; retain all authorized answers, not the best outcome. Do not hide low coverage inside a composite GEO score. If a provider returns a composite score, label it provider-defined and preserve its formula/version if known; never turn a readiness heuristic into measured exposure.

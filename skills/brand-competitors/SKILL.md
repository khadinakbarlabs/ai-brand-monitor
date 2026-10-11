---
name: brand-competitors
description: Compare a brand with configured competitors in the same sampled AI answers. Calculate weighted share of voice and competitor co-mention coverage, identify prompt-level gaps, and distinguish mentions from recommendations.
---

# Competitor comparison

Use already collected, user-selected campaign evidence first. Apply [measurement](../ai-brand-monitor/references/measurement.md). Research competitor candidates from public product facts only when the user asks for discovery. Save their identity, domain, audience fit and source. Obtain corrections before including them in the panel; the Actor supports at most ten competitor brand names.

Compare the same questions, platforms, language and observation period. Separate branded prompts from brand-free discovery. Count each configured competitor's presence once per valid answer from `competitor_mentions`; this field does not reveal each competitor's mention frequency, recommendation rank, sentiment or citations. Do not invent those metrics or mix presence counts with the brand's text mention count.

For brand share of voice, sum brand mention counts and competitor mention counts across valid matched cells, then divide the brand total by their combined total. Weight by counts rather than averaging row percentages. If there are no competitive mentions, report N/A. Show the competitor list and denominator because the result depends on which competitors were configured. Call it sampled mention share, never market share.

Identify questions where the brand is absent and a competitor is present, where the brand is mentioned without an endorsed recommendation, and where source evidence is missing. `mention_position_score` describes text position, lower is better; it is not a ranking of products or web search results. Treat Actor sentiment as a lexical hint and show available context before calling a brand recommended.

Write a compact table of prompt, platform, brand presence, competitor presence, verified source evidence, and action. Link each conclusion to its evidence record. If broader competitor checks are needed, prepare the exact extra panel and shared budget allocation through brand-audit; do not silently launch a new run for each competitor.

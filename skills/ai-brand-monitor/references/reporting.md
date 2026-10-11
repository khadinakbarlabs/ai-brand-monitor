# Useful saved reports

Lead with what the user should do, then the evidence. For every report provide:

1. Brand, panel version, market/language, selected platforms, actual models, observation dates, Actor/build and measurement version.
2. Planned/valid/failed/missing checks and citation capability. Display denominators with every metric.
3. Separate discovery, evaluation and branded rates; per-platform mentions; verified source citations and unverified domain signals; sampled competitive mention share; context-based sentiment findings.
4. A prompt/platform evidence table and a citation-domain/page map. Link each observation to its local record or authorized service run.
5. The three best next actions, each with evidence, confidence, effort, proposed page/change, status and a next check. No causal or ranking guarantee.
6. Budget, outstanding reservations, charge reconciliation and concrete gaps. No-measurement drafts clearly say pending; fixtures clearly say synthetic.

Generate `report.md`, an accessible standalone `report.html`, a safe CSV, `metrics.json`, and `evidence.json` using the host's existing file capability. The [sample HTML](examples/sample-report.html) is a static visual design reference, not a renderer. Replace sample content completely with measured evidence or pending labels. Keep the report responsive and printable, with text/table equivalents for every chart, adequate contrast, headings and numeric denominators. It uses no external fonts, scripts, images, tracking or network requests.

Version the machine-readable export as `ai-brand-monitor.report.v1`. Keep raw counts and unrounded ratios in JSON; round once for display. Evidence entries point to run, record ordinal, query, platform, timestamp and provenance. Include measurement definitions so another reviewer can reproduce the result. Keep brand and citation Actor data as separate datasets.

Escape all answer excerpts, labels and HTML attributes. Links must pass the source validation in security.md. CSV exports neutralize spreadsheet formula-leading cells, including after whitespace. Avoid embedding entire raw JSON inside HTML scripts. Use local files, not public sharing links, by default. Publishing or delivering the report requires user approval of the specific destination.

Recommended verbal handoff: “Of 9 planned checks, 8 produced usable answers. Your brand appeared in 5; two had verified source links. These results describe this prompt panel. Here are the three gaps worth addressing next.” Replace these illustrative counts with actual data.

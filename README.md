# AI Brand Monitor

**Track how AI answers mention your brand, cite your website and describe your competitors.**

AI Brand Monitor is a skills-only plugin for Claude Code and compatible local agent hosts. It turns your public brand website and business goals into a repeatable AI search visibility workflow: a focused prompt panel, budgeted checks, competitor comparisons, source evidence and a clear saved report.

![AI Brand Monitor icon](assets/icon.png)

## What you can do

- Monitor brand mentions across ChatGPT, Perplexity and Gemini; add Claude when selected.
- Compare configured competitor mentions and sampled AI share of voice.
- Separate verified citation URLs, domain mentions and recommendations.
- Review lexical sentiment with answer context and uncertainty.
- Find citation gaps and prepare evidence-backed content improvement briefs.
- Compare matching prompts over time and follow up on accepted actions.
- Save readable Markdown, HTML, CSV and JSON reports in your own campaign folder.
- Plan or configure separately approved recurring collection using your Apify account.

This is an AI brand monitoring and GEO/AEO workflow for marketers, founders and agencies. It measures sampled API answers. It does not promise the exact consumer interfaces, Google rankings, more traffic, conversions or guaranteed citations.

## Six focused skills

| Skill | Use it for |
| --- | --- |
| `ai-brand-monitor` | Research-first onboarding, routing and reports |
| `brand-audit` | A baseline or authorized refresh |
| `brand-competitors` | Fair competitor and share-of-voice comparisons |
| `brand-citations` | Source maps and content opportunities |
| `brand-trends` | Comparable changes and action follow-up |
| `brand-schedule` | Approved recurring collection, pause and resume |

## Requirements and setup

Use a local agent host with terminal and file access, an independently installed official Apify CLI with the `api` command, and your own Apify account. CLI 1.8.0 was verified for the command examples. The plugin does not install the CLI or software dependencies. Plain browser chat cannot execute this CLI workflow.

Authenticate yourself through `apify login` in your own terminal. Never paste credentials into chat. The plugin does not read your login files or export your credentials; the official CLI handles authentication. Actor usage is billed to your Apify account. Before each paid collection it previews the exact inputs and checks, requests a spend limit if missing, and uses a per-run API charge cap and a shared campaign ledger.

Install the public source from its own Claude marketplace:

```sh
claude plugin marketplace add khadinakbarlabs/ai-brand-monitor
claude plugin install ai-brand-monitor@ai-brand-monitor-marketplace
```

For local Claude Code testing, load this folder with the official `--plugin-dir` option. Then invoke `/ai-brand-monitor:ai-brand-monitor` or describe the requested workflow naturally. There is no bundled MCP server, runtime, hook, agent process, telemetry, scheduler or automatic startup. Anthropic directory installation becomes available only after its submission and review.

## Three ways to start

1. “Help me set up AI brand monitoring for my website. Draft the questions and cost before running anything.”
2. “Compare my brand's mentions, citations and share of voice with these competitors using my latest campaign.”
3. “Review my two selected reports, explain comparable changes, and give me three next actions.”

For an offline demonstration, ask: “Use the bundled synthetic example to explain this report. Do not call Apify.” The sample inputs use invented brands and reserved example domains; they are not a real campaign or paid test.

## Actors and data sent off-platform

The primary backend is [AI Brand Monitor](https://apify.com/khadinakbar/ai-search-brand-monitor), `khadinakbar/ai-search-brand-monitor`. The optional deeper citation backend is [AI Search Visibility Tracker](https://apify.com/khadinakbar/ai-search-visibility-tracker). These are existing Apify Actors owned by the publisher. The plugin's workflow uses the official external CLI, rather than a bundled MCP connection.

On an approved run it sends only the selected brand name/domain, aliases, competitors, prompt questions, platforms and optional topic/page inputs to Apify. The Actors submit the selected questions to the configured AI provider services and return answer evidence to the user's Apify storage. Supported AI services include OpenAI, Perplexity, Google and Anthropic through the Actors' configured provider routes; the user does not need to supply separate AI vendor keys to this plugin. Local state and reports stay in the campaign folder unless the user explicitly authorizes another destination.

Apify and the model providers handle execution data under their own policies. Run inputs and outputs can remain in the user's Apify account; the plugin does not impose automatic deletion. No conversation transcript, host memory, customer records or publisher credentials are needed. See the [privacy policy](PRIVACY.md) and [terms](TERMS.md).

## Monitoring and measurement limits

Installing a skill does not start a background job. Native Apify schedules can collect fixed inputs under per-run caps. Automatic expiry, a hard cumulative portfolio budget, complete report generation and alert delivery require a verified controller or explicit manual reviews. Schedule activation and external delivery need their own authorization.

Reports show usable/planned coverage and denominators. Failed answers are unknown rather than absent mentions. Citation flags without source URLs are unverified domain evidence. Share of voice depends on the configured competitor set; position score is text position, not product rank. Sentiment is lexical and should be reviewed with context. Changes in prompts, aliases, competitors, language, model or build affect comparison.

## Research and support

The workflow was informed by leading open-source marketing/GEO projects, with live star counts, pinned research commits and clear limits recorded in [research notes](skills/ai-brand-monitor/references/research.md). All plugin instructions are original; no upstream runtime or third-party skills are bundled. See [support](SUPPORT.md), [security reporting](SECURITY.md), [changelog](skills/ai-brand-monitor/references/changelog.md) and the [MIT license](LICENSE).

Version 0.1.2 is the public skills source release. Local package checks and source publication are separate from a successful host workflow, live Actor acceptance, Anthropic scanning, reviewer approval and live directory availability. Full Claude workflow testing has not passed because the local Claude login is unavailable; no paid Actor canary was started for this release. See the [GitHub releases](https://github.com/khadinakbarlabs/ai-brand-monitor/releases) for downloadable packages. This repository does not establish an Anthropic directory listing.

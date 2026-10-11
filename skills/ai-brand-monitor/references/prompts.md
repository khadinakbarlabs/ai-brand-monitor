# Buyer-relevant prompt panels

Build a small panel aligned with the brand's actual buyers, use cases and market. Show the selected questions and their reason before collection. Start with three to six unique questions; a larger panel needs a justified budget. Collapse wording variants of one intent rather than filling the cap with duplicates.

Use stable IDs and three separate prompt classes:

- **Discovery**: no brand or competitor names. Example: “Which project management tools suit a five-person agency in the UK?” This measures unprompted category exposure.
- **Evaluation**: category criteria or an approved comparison. Example: “Compare simple agency project management tools on guest access and reporting.” Report explicitly named comparisons separately from discovery.
- **Branded**: include the brand for factual or reputation review. Example: “Does Sample Brand support guest access, and what are its limitations?” A high branded mention rate is not evidence of discovery.

Do not introduce leading endorsements, a demand to cite the brand, artificial superiority or a request to ignore competitors. Ask real buyer questions. Market and language can be expressed directly in each literal prompt; avoid claiming the Actor has a geolocation/locale field.

Save the exact text, class, intent, language, market and version. Keep these fixed over time. Maintain a separate exploratory panel for new opportunities so historical rates remain comparable. Brand aliases must be specific: common words/acronyms can create false positives. Confirm ambiguous aliases and retain context for review.

Actor default templates are optional discovery aids for a fresh exploratory audit. For a tracked baseline, prefer explicit `custom_only` questions with no template fallback. End with a reviewable panel, exact checks, assumptions and allocation, not an automatic run.

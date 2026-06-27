# Full Link Profile + Disavow List

**Purpose:** Complete inventory and risk-scoring of every backlink pointing at the domain, ending in a defensible disavow file — not a knee-jerk "disavow everything weird" list.

**When to run this:** Onboarding any new domain, and after any unexplained ranking drop (pair with `seo-drift.md`).

**Inputs needed:**
- Full backlink export (Ahrefs/DataForSEO via `seo-api.md`)
- Known legitimate link sources (press, partners, directories the client actually submitted to)

**Process:**
1. Pull the complete referring domains list with DR, anchor text, link type (dofollow/nofollow), and first-seen date.
2. Score each domain on real risk signals: PBN patterns (thin content, exact-match anchors, unrelated niche, hosting clusters), not just "low DR" — low DR alone is not toxic, most of the internet is low DR.
3. Separate anchor text distribution into branded / naked-URL / exact-match / generic — exact-match anchor over ~5% of total profile is a manipulation signal worth flagging even without toxicity.
4. Cross-check flagged domains against the client's known legitimate sources before recommending disavow — false positives erase real link equity.
5. Build the disavow file only for confirmed-toxic, confirmed-not-legitimate domains. Default to "monitor" for ambiguous cases, not disavow — Google's algorithm already discounts most spam without action needed.

**Output format:**
Summary scorecard (total referring domains, DR distribution, anchor text %) + `domain.csv` disavow file in Google's required format + a flagged-but-not-disavowed watchlist with reasoning.

**Quality bar:** Every line in the disavow file needs a one-sentence reason. If you can't write the reason, it doesn't belong in the file.

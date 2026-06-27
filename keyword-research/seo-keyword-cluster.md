# Keyword Clustering — Longtail + Question Content Plan

**Purpose:** Convert a niche keyword list into topic clusters with a pillar page and supporting "spoke" articles, prioritizing longtail and question-based queries that AI Overviews and featured snippets actually pull from.

**When to run this:** After `seo-niche.md`, before any content brief is written. Re-run quarterly — clusters drift as SERPs change.

**Inputs needed:**
- Anchor terms from `seo-niche.md`
- SERP feature data for each anchor term (does it trigger PAA, featured snippet, AI Overview?)
- Existing site content inventory (URL + target keyword, if any)

**Process:**
1. Group anchor terms by shared search intent and semantic overlap (terms whose top-10 SERPs share 4+ of the same URLs belong in one cluster — that's the SERP-overlap signal, not just string similarity).
2. For each cluster, pull "People Also Ask" + "related searches" + autocomplete to harvest longtail and question variants.
3. Assign one term per cluster as the **pillar** (highest volume, broadest intent) and the rest as **spokes** (specific, often question-phrased, lower volume).
4. Tag every spoke with the question pattern it answers: what/how/why/cost/vs/best — this pattern becomes the H2 structure for the eventual article.
5. Map clusters against the existing content inventory — flag overlaps as consolidation candidates, not new-content candidates (prevents cannibalization; cross-check against `seo-subdomain.md`).
6. Output one cluster map per pillar, ready to hand to `seo-content-brief.md`.

**Output format:**
```
Pillar: <term> (Vol, KD)
  Spoke: <question-phrased term> (Vol, KD) — pattern: how-to
  Spoke: <term> (Vol, KD) — pattern: vs-comparison
  ...
Existing content collision: <URL or "none">
```

**Quality bar:** A cluster with fewer than 4 spokes isn't a cluster — fold it into an adjacent pillar or park it.

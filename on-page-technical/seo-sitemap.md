# Sitemap vs Index — Orphans, Broken Links

**Purpose:** Reconcile what's actually in the XML sitemap against what's actually indexable and actually linked-to internally — the three lists rarely match, and the mismatches are where traffic quietly leaks.

**When to run this:** Monthly as a standing check, and immediately after any CMS migration or bulk content operation.

**Inputs needed:**
- Current XML sitemap(s)
- Full site crawl (internal link graph)
- GSC Coverage report

**Process:**
1. Diff three sets: URLs in the sitemap, URLs reachable via internal links (crawl), and URLs Google has indexed (GSC).
2. Flag **orphans**: pages that exist and may even be indexed, but have zero internal links pointing to them — they're invisible to both users and crawl budget allocation.
3. Flag **sitemap pollution**: noindex'd, redirected, 404'd, or canonicalized-away URLs still listed in the sitemap — this wastes crawl budget and signals poor site hygiene to Google.
4. Flag **broken internal links**: any internal link resolving to 404/410/5xx, ranked by how many pages link to that broken target (a broken link from the main nav is far worse than one from a 2019 blog post).
5. For multi-sitemap setups (sitemap index files), verify each child sitemap is actually being fetched/processed in GSC, not just submitted.

**Output format:**
Three lists — Orphaned pages (with suggested internal link sources) | Sitemap pollution (URLs to remove) | Broken internal links (sorted by inbound link count) — plus a one-line health score.

**Quality bar:** "Orphaned pages" found via crawl that turn out to have plenty of internal links the crawler just didn't follow (JS-rendered nav, for example) is a false positive — verify rendering before flagging.

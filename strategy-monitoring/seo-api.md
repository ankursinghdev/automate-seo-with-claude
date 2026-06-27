# DataForSEO Integration Code Recipes

**Purpose:** Concrete, runnable integration patterns for pulling third-party SEO data (rankings, volume, backlinks, SERP features) programmatically — so every file in this repo that says "pull via API" has one consistent implementation to point to, instead of each one improvising.

**When to run this:** Once, to set up the integration layer; referenced by `seo-niche.md`, `seo-keyword-cluster.md`, `seo-competitor-gap-analysis.md`, `seo-backlinks-profile.md`, and others as their data source.

**Inputs needed:**
- DataForSEO (or equivalent: Ahrefs API, SEMrush API) account credentials, stored as environment variables — never hardcoded inline
- Defined query/domain inputs from the calling task

**Process:**
1. Centralize auth/credential handling in one place — every recipe in this file reads from environment variables (`DATAFORSEO_LOGIN`, `DATAFORSEO_PASSWORD`), never embeds them in example code.
2. Provide a thin wrapper function per data type this repo needs: keyword volume/difficulty lookup, SERP results pull, backlink/referring-domains pull, rank tracking pull — each returning a normalized structure other files' Output Format sections expect.
3. Handle rate limits and pagination explicitly in each recipe (DataForSEO's task-based endpoints are async — poll for task completion rather than assuming an immediate response).
4. Cache responses with a timestamp (reuse the pattern from `seo-firecrawl.md`) to avoid burning API credits re-pulling the same query within a short window.
5. Log every call's cost (DataForSEO bills per call/row) so usage stays visible — silent API sprawl across 27 files is how budgets get blown without anyone noticing.

**Output format:**
A small library of named functions (e.g., `get_keyword_data(keyword, location)`, `get_serp_results(keyword, location)`, `get_backlinks(domain)`, `get_rank_tracking(domain, keywords)`), each with: required params, normalized return shape, rate-limit/cost note.

**Quality bar:** Never commit example code with real credentials, even masked-looking placeholder ones that resemble a real key format — use obviously-fake placeholders only.

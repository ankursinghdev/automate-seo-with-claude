# Technical Audit — Crawl, Index, CWV, Top Fixes

**Purpose:** Full-site technical health check covering crawlability, indexation, and Core Web Vitals, prioritized into a fix list ranked by impact — not a 40-page report nobody acts on. (This is the structural-audit pattern already proven on the Ellocent Labs site: URL typos, capitalization errors, missing sitemaps, CMS rendering failures.)

**When to run this:** Onboarding any domain, after any major platform migration, and quarterly thereafter.

**Inputs needed:**
- Crawl access (Screaming Frog export, or `seo-firecrawl.md` output)
- GSC Coverage + Core Web Vitals reports
- CrUX/PageSpeed Insights data (see `seo-google.md`)

**Process:**
1. Crawl the full site, segment URLs by status code, indexability (noindex, canonical issues, robots.txt blocks), and depth from homepage.
2. Cross-reference crawled URLs against GSC's indexed/excluded report — flag any mismatch (Google excluding pages the crawl thinks are fine, or vice versa) as a priority investigation, not a footnote.
3. Pull CWV at the page-template level, not just homepage — a single slow template can be silently dragging down hundreds of URLs.
4. Check for the specific failure classes that hide in CMS/no-code builds: capitalization-inconsistent URLs creating duplicate paths, `/undefined` or `/null` segments from broken dynamic routing, missing or stale XML sitemaps, render-blocking scripts injected by the builder.
5. Rank every finding by (pages affected × severity), not by how interesting the bug is technically.
6. Output a scored audit (0–100, weighted by category) with a top-10 fix list, each fix tagged with estimated effort (dev hours) so it can be handed straight to a developer.

**Output format:**
Score (/100) + category breakdown (Crawl/Index/CWV/Architecture) + ranked fix list: `Issue | Pages affected | Severity | Est. dev effort | Owner (dev/content/SEO)`.

**Quality bar:** Don't report a Core Web Vitals score without a template-level breakdown — an aggregate "field data: Poor" with no page-type attribution can't be assigned to anyone.

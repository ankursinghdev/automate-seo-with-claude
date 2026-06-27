# Scrape, Crawl, Map Raw HTML

**Purpose:** Standardize how this repo's files get raw HTML/content when there's no existing crawl tool access — using Firecrawl-style scraping as the fallback data source for technical audits, SERP capture, and competitor analysis.

**When to run this:** Whenever a file in this repo needs page content/structure and no crawler export (Screaming Frog, etc.) is available, or when JS-rendered content needs to be captured post-render.

**Inputs needed:**
- Target URL(s) or domain to crawl
- Scope definition (single page, full site, or specific URL list)

**Process:**
1. Define crawl scope precisely before running — full-site crawls on large sites burn time and rate limits for marginal value if only a few templates actually matter.
2. Crawl with JS rendering enabled by default — many of the failure modes this repo checks for (schema injected client-side, lazy-loaded images, JS-rendered nav links) are invisible to a source-only fetch.
3. Capture both rendered HTML and a structured extraction (title, meta, headings, schema blocks, internal/external links, image attributes) in the same pass, so downstream files don't need a second crawl.
4. Respect robots.txt and rate limits — this is a data-gathering tool for sites you have a legitimate reason to be auditing, not a bulk-scraping operation against unrelated third parties.
5. Cache raw HTML output with a timestamp so `seo-drift.md` has something concrete to diff against later, not just a structured summary that's already lost the raw evidence.

**Output format:**
Per URL: raw rendered HTML (cached) + structured extract (title/meta/H1-H6/schema/links/images) + crawl timestamp — handed off in the format each consuming file (`seo-technical-audit.md`, `seo-schema.md`, `seo-images.md`) expects.

**Quality bar:** A crawl with JS rendering disabled should be labeled as such in the output — silently passing source-only HTML as if it's the full rendered page produces false negatives on every JS-dependent check in this repo.

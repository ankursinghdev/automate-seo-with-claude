# International Hreflang + Canonical Validation

**Purpose:** Validate hreflang implementation across regional/language variants and confirm canonical tags aren't silently fighting the hreflang map — relevant the moment a site serves both .com and a regional domain (e.g., ellocentlabs.com / ellocentlabs.com.au).

**When to run this:** Any time a new regional/language variant launches, and quarterly thereafter for sites already running multi-region.

**Inputs needed:**
- Full URL list per region/language variant
- Crawl of hreflang and canonical tags for every variant

**Process:**
1. Map every page to its regional/language equivalents — flag any page that's missing a counterpart entirely (orphaned variant).
2. Validate hreflang reciprocity: every hreflang annotation must be returned by the target page pointing back — one-directional hreflang is invalid and silently ignored by Google.
3. Check for the canonical conflict: a page's canonical tag must point to itself (self-referencing) within a hreflang set, not to the "main" regional version — pointing canonical cross-region cancels the hreflang signal entirely.
4. Confirm correct language-country code format (`en-AU`, not `en_AU` or `au`) and that an `x-default` is set if there's a generic fallback.
5. Spot-check actual SERP behavior for a sample of queries in each region — confirm Google is actually serving the intended regional URL, since hreflang is a hint, not a directive.

**Output format:**
`URL | Region/lang | Hreflang targets declared | Reciprocity check (pass/fail) | Canonical (self-ref pass/fail) | Issue found | Fix`.

**Quality bar:** A "pass" on reciprocity checked only on the source page, without confirming the target page reciprocates, isn't a real validation — always check both directions.

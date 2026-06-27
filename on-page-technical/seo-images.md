# Images — Alt Text, WebP, CLS, Lazy-Load

**Purpose:** Audit and fix the four most common image-driven SEO and performance failures in one pass, since they're almost always caused by the same root issue (unoptimized uploads + missing CMS defaults).

**When to run this:** As part of `seo-technical-audit.md`, or standalone after a bulk content/image upload.

**Inputs needed:**
- Crawl with image inventory (src, alt, dimensions, file size, format)
- CWV report flagging CLS and LCP issues

**Process:**
1. Pull every image on the site with current alt text — flag missing alt entirely, alt text that's just the filename (`IMG_4821.jpg`), and alt text that's keyword-stuffed rather than descriptive.
2. Check format and size: flag any image over ~150KB that isn't WebP/AVIF, and any image served at 2x+ the size it's actually displayed at (check `srcset`/responsive sizing).
3. Cross-reference images causing CLS: any image missing explicit `width`/`height` (or `aspect-ratio`) attributes, which forces layout shift as it loads.
4. Check lazy-loading implementation: confirm below-the-fold images use `loading="lazy"`, and — critically — confirm the LCP image (usually hero/above-fold) does **not** have lazy-loading applied, since that delays the metric it's supposed to help.
5. Flag any base64-encoded images bloating page weight directly in the HTML (a known failure mode on no-code/CMS exports) for conversion to proper file references.

**Output format:**
`Image URL | Issue type | Current state | Fix | Pages affected` — grouped by issue type, sorted by pages affected.

**Quality bar:** Don't recommend alt text without writing the actual replacement text in the output — "add descriptive alt text" is not a fix, it's a reminder.

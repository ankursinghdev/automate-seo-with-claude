# Paid SERP Ads + Bidding Intel

**Purpose:** Map the paid landscape for target keywords — who's bidding, what they're bidding on, and what their ad copy/landing pages reveal about positioning — to inform both paid strategy and the "not winnable organically yet" terms flagged in `seo-niche.md`.

**When to run this:** Before launching or revising a paid campaign, and as a standing quarterly check on competitive bidding behavior.

**Inputs needed:**
- Target keyword list (especially the "not winnable organically in 12 months" flagged set from `seo-niche.md`)
- Ad intelligence source (SEMrush/Ahrefs paid data, or manual SERP capture via `seo-firecrawl.md`)

**Process:**
1. Capture actual SERP ad blocks for target keywords across desktop and mobile (layouts and ad density differ) — note ad position count, whether shopping/local ad units also appear.
2. Identify consistent bidders (appear across multiple checks over time, signaling sustained budget) versus one-off bidders (likely testing, lower signal).
3. Pull each consistent bidder's ad copy and landing page — extract the value proposition and offer structure they're leading with, this is free positioning research.
4. Estimate competitive density (number of distinct advertisers) per keyword — high density on a term that's also organically "not winnable" tells you this term needs paid budget or should be deprioritized entirely, not chased organically.
5. Cross-reference CPC trend over time — rising CPC on a term you're not yet competing for is an early signal to move faster or pick a different angle.

**Output format:**
`Keyword | Avg CPC | # distinct advertisers | Consistent bidders (with their value prop) | Recommendation (bid / organic-only / deprioritize)`.

**Quality bar:** Don't recommend "bid on this" without checking estimated CPC against realistic conversion value — high-volume terms with thin commercial intent burn budget fast.

# Subdomain Ownership & Cannibalization Map

**Purpose:** Audit every subdomain under a root domain (blog., app., shop., docs., support., regional subdomains) to confirm who owns SEO equity for each, and catch subdomains competing against each other or against the root for the same queries.

**When to run this:** Whenever a new subdomain is spun up (common with no-code/headless setups — see Ellocent's hooks.server.ts-style redirect work for why this matters), and quarterly as a standing check.

**Inputs needed:**
- Full subdomain inventory (check DNS + `site:domain.com -site:www.domain.com` style searches, don't rely on memory of what IT thinks exists)
- Rank tracking data segmented by subdomain

**Process:**
1. Enumerate every live subdomain and what it serves (marketing site, blog, app shell, docs, regional variant).
2. For each subdomain, pull its top organic queries — then check whether the root domain or another subdomain ranks for the *same* query. That's cannibalization, and Google will pick one winner inconsistently, costing you both.
3. Check whether subdomains are being treated as separate properties in GSC/GA4 (they often are by default) — this hides the true cannibalization picture from standard reporting.
4. For confirmed overlaps, recommend a single canonical owner per query cluster: consolidate content, 301 the loser, or restructure as a subdirectory if the split was never intentional.
5. Flag orphaned subdomains (old microsites, abandoned campaign domains) carrying backlinks that should be redirected to reclaim equity, not left to rot.

**Output format:**
`Subdomain | Purpose | Competing query examples | Who currently wins in SERP | Recommended owner | Action (consolidate/redirect/leave)`

**Quality bar:** "Leave as-is" is only acceptable when the subdomains target genuinely distinct intents (e.g., docs. vs. www.) — same-intent overlap always needs a decision, not a shrug.

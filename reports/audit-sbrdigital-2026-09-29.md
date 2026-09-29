# Audit + Visibility — sbrdigital.in — 2026-09-29

## Technical (homepage deep-check)
- Speed: 200 in 0.27-0.39s, 43KB HTML — excellent (earlier 90s hang: one-off/transient, not reproducible)
- Title 58ch, meta 160ch, 1xH1 + 6xH2, canonical, viewport, OG 10 + twitter 5 — all pass
- JSON-LD types present: Organization, WebSite, WebPage, FAQPage, Service, ContactPoint, PostalAddress
- llms.txt: 200 (present). robots.txt: 200. sitemap.xml: 301 -> 200 (minor: direct serve recommended)
- No <img> tags (SVG/text site) — alt-text n/a. No mixed content.
- Technical score: ~85/100. Weak spots: sitemap redirect, homepage targets "Noida" only, 12 unique internal links (thin internal linking)

## AI Visibility (search-surface proxy; ChatGPT/Gemini/Perplexity scoring pending DFSEO top-up)
- "best website development company Ghaziabad": ABSENT (competitors: FutureGenApps, Pointersoft, DigitalPiloto, CSSFounder, TechBehemoths, sulekha)
- Root cause hypothesis: homepage title/targeting says NOIDA; no Ghaziabad content signals
- Brand query "SBR Digital": sbrdigitalsystems.in (unrelated company) + UK Companies House + IndiaMART rank alongside/above — brand confusion risk
- Proxy visibility score: ~15/100

## Top fixes (fastest first)
1. Add Ghaziabad/Delhi-NCR to title + H1 + homepage copy (currently Noida-only)
2. Publish a /website-development-company-ghaziabad/ landing page
3. Google Business Profile: claim/optimize for Ghaziabad + service areas
4. Directory cleanup: IndiaMART listing accuracy + link to site
5. sameAs schema links (GBP, LinkedIn, IndiaMART) to disambiguate from sbrdigitalsystems.in
6. FAQ content targeting buyer questions AI engines are asked ("best app development company near me")
7. More internal links from homepage to guides (only 12 unique)
8. Serve sitemap.xml directly without redirect
9. Weekly watchdog: re-run visibility, track trend
10. Top up DataForSEO ($1 -> $10) to enable ChatGPT/Gemini/Perplexity scoring via API

# SEO Phase 11 — DiggerMan Single-Entity Network Audit & High-Frequency Information Profile
Date: 2026-11-19
Status: implementation prepared for merge; production verification pending.

## Objective
Consolidate DiggerMan's official artist identity across the requested GitHub Pages destinations so search engines, media partners and external information systems encounter one consistently identified artist entity rather than several competing artist records.

## Canonical artist entity
- Preferred public name: DiggerMan
- Alternate name: Dico Nhlakanipho Dube
- Schema entity type: MusicGroup
- Canonical entity ID: https://kingpinpkaytee-dot.github.io/#musicgroup
- Canonical artist hub: https://kingpinpkaytee-dot.github.io/
- MusicBrainz Artist ID: 56a9fd42-e71b-4292-93b2-6662e1588503
- Spotify Artist ID: 7fSMDP0eWrFwYol9Vye2Ty
- Public base: Riverlea, West Johannesburg, South Africa
- Artist genres: Amapiano, Afro House, Deep House
- Official company relationship: The Kingpin Entertainment Pty Ltd, represented by its separate Organization entity at https://kingpinpkaytee-dot.github.io/thekingpin-entertainment-site/#company

## Requested destinations and routing audit
1. Root artist hub: https://kingpinpkaytee-dot.github.io/ — canonical public hub.
2. Artist Spotlight requested short URL: https://kingpinpkaytee-dot.github.io/diggerman-artist-spotlight — live pre-change check returned HTTP 404.
3. Existing canonical spotlight article: https://kingpinpkaytee-dot.github.io/blog/diggerman-artist-spotlight/ — this is the real article already in the root repository and already listed in the root sitemap.

A short, noindex/follow redirect page has been added at /diggerman-artist-spotlight/ to forward visitors to the existing canonical blog article. The redirect alias is deliberately excluded from the sitemap; the canonical article remains the indexable URL.

## Entity and internal-link changes
- Root hub MusicGroup remains the authoritative DiggerMan entity with @id https://kingpinpkaytee-dot.github.io/#musicgroup.
- Root hub now declares the canonical spotlight article in subjectOf and links to the Artist Spotlight from the main navigation and official links section.
- Spotlight Article JSON-LD now points its about entity to the canonical DiggerMan MusicGroup @id.
- Spotlight Article author/publisher Organization references now resolve to the separate official Kingpin company entity.
- DiggerMan Official site MusicGroup @id now reuses the canonical root entity ID; its WebSite publisher points to the same entity.
- DiggerMan Media / Press Kit MusicGroup @id now reuses the canonical root entity ID; its WebSite publisher points to the same entity.
- Root Organization ID now resolves to the company website's canonical Organization ID. Artist and company remain separate entities.
- Artist pages cross-link to the root hub, official music catalogue, media press kit and spotlight article.
- The canonical spotlight article sitemap lastmod has been updated to 2026-11-19.

## Social preview and metadata QA
- The older DiggerMan Media / Press Kit page contained repeated Open Graph image tags and repeated Twitter image tags.
- Those duplicate image declarations have been consolidated to one Open Graph image and one Twitter image, using the existing Cloudinary DiggerMan social-preview image.
- The spotlight article now has a large-image Twitter card and descriptive image alt text.
- Existing canonical URLs for each website are preserved; distinct websites are not collapsed into one canonical URL.

## High-frequency information upload asset
Created machine-readable profile:
- /diggerman-entity-profile.json
- JSON-LD-compatible MusicGroup entity profile
- Stable canonical @id, alternate name, description, public location, genres, MusicBrainz identifier, Spotify artist link, verified official web properties, social profiles, separate parent organization and spotlight article reference.
- This profile is designed as a reusable factual source for external artist-information or entity-profile submissions. It does not claim third-party verification or a search-engine Knowledge Panel.

## Indexing and measurement
- No Search Console indexing requests have been submitted in this phase.
- The user's active indexing quota remains unused pending completion of the SEO rollout.
- No GTM or GA4 changes were made.
- No ranking, Knowledge Panel, rich-result or traffic increase is guaranteed.

## Pre-merge code checks
- [x] Canonical MusicGroup @id is consistent across root hub, DiggerMan Official and Media / Press Kit.
- [x] Spotlight Article about entity points to canonical MusicGroup @id.
- [x] Artist-to-company relationship uses a separate Organization @id.
- [x] Requested short spotlight URL has a redirect target and noindex directive.
- [x] Redirect alias is excluded from the sitemap.
- [x] Canonical article is retained in the sitemap and refreshed.
- [x] Media / Press Kit has one OG image declaration and one Twitter image declaration.
- [x] High-frequency entity profile JSON file created.
- [ ] PR merged and production deployment verified.
- [ ] Live URL status, redirects, metadata and structured-data output verified after deployment.

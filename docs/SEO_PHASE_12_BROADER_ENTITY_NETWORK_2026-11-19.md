# SEO Phase 12 — Broader Entity Network
**Date:** 2026-11-19  
**Status:** Source implementation merged; production rollout and indexing remain pending.

## Objective
Extend DiggerMan's entity and discovery network across the press kit, artist blog, official artist website, The Kingpin Entertainment Pty Ltd website, Riverlea West Archive, DSP catalogue and social profiles.

## Canonical entity rules
- **DiggerMan MusicGroup:** `https://kingpinpkaytee-dot.github.io/#musicgroup`
- **The Kingpin Entertainment Pty Ltd Organization:** `https://kingpinpkaytee-dot.github.io/thekingpin-entertainment-site/#company`
- **DiggerMan Artist Spotlight Article:** `https://kingpinpkaytee-dot.github.io/blog/diggerman-artist-spotlight/#article`
- The artist and company remain distinct entities. DiggerMan pages reference the company through `parentOrganization`; the company is not declared an alias of the artist.
- Riverlea West Archive is a related place-based creative archive, not an alias or duplicate artist profile.

## Eight network areas

### 1. Press kit
- Added navigation and visible network links to the full music catalogue and Riverlea West Archive.
- Added a visible DSP and social destination section.
- Preserved the canonical press-kit URL and existing metadata/image assets.
- Canonical MusicGroup ID retained.

### 2. Artist blog
- Added Blog structured data with the canonical DiggerMan entity as its subject and The Kingpin Entertainment as publisher.
- Strengthened social preview metadata.
- Added links to the catalogue, Riverlea West Archive, press kit, artist site and official social channels.
- Added the blog landing page to the root sitemap.

### 3. DiggerMan website
- Aligned homepage MusicGroup references to the canonical root entity ID.
- Added Riverlea West Archive cross-links and subject relationship.
- Added parentOrganization reference to The Kingpin Entertainment.

### 4. The Kingpin Entertainment website
- Aligned the DiggerMan MusicGroup reference to the canonical root entity ID.
- Added a visible route to the dedicated Riverlea West Archive.
- Added catalogue and social-network links.

### 5. Riverlea West Archive
- Created a dedicated page:
  `https://kingpinpkaytee-dot.github.io/thekingpin-entertainment-site/riverlea-west-archive/`
- Added WebSite, CollectionPage, Place and CreativeWork structured data.
- The company is the publisher/creator; Riverlea is the place entity; DiggerMan is a related artist entity.
- Added links to the artist hub, artist website, catalogue, press kit, blog, verified DSP profiles and social channels.
- The archive is described accurately as an ongoing curated creative collection, not as a comprehensive municipal or historical record.
- Added the archive page to the company sitemap and the root hub sitemap.

### 6. Music catalogue and DSP discovery
- Updated the existing official catalogue (68 Spotify-verified track pages / 25 MusicBrainz release groups) to use the canonical MusicGroup ID.
- Added a DSP discovery panel:
  - Verified artist destinations: Spotify, SoundCloud and MusicBrainz.
  - Search destinations: Apple Music, Deezer, TIDAL, Amazon Music and YouTube Music.
- Search destinations are explicitly labelled as platform searches, not verified artist-profile URLs. No unverified profile IDs or URLs have been invented.
- Refreshed the existing music catalogue sitemap date without adding a duplicate music URL.

### 7. Social network accounts
Added public profile links to the network pages and artist entity profile:
- Instagram: `@nhlakanipho_phakathi`
- Facebook Page: `DiggerManAndTheKingpinEntertainment`
- Threads: `@nhlakanipho_phakathi`
- X: `@KPkaytee1346`
- TikTok: `@dico_nhlakaniphophakathi`

**Scope note:** Links and structured identity references were added to the owned websites. The social-platform account bios/settings themselves were not edited.

### 8. Artist Frequency — Global Music Submission Portal
- The submitted hostname `https://artist-frequency-global-music-submission-portal.pages.dev/` does not resolve in the direct HTTP check; Windows DNS returned “The remote name could not be resolved”.
- Repository deployment documentation identifies **Vercel**, not Cloudflare Pages, as the hosting provider.
- The canonical public Vercel project domain is `https://artist-frequency.vercel.app/`; it returned HTTP 200 and served the Artist Frequency application.
- The live root page and its `src/app.js`, `src/auth.js` and `src/supabase-client.js` assets each returned HTTP 200.
- The preview project also serves HTTP 200, but its SSO protection is enabled and the preview response carries `X-Robots-Tag: noindex`; it is not the public production destination.
- The separate `artist-frequency-html-verification.vercel.app` project is only a Google Search Console HTML-verification endpoint, not the Artist Frequency application.
- The canonical Vercel project’s latest deployment is BLOCKED; its previous production deployment remains READY and is still serving the canonical domain. Therefore, the domain is reachable, but the latest source release is not certified as deployed.
- Do not substitute the SSO-protected preview URL, the HTML-verification endpoint or the unresolved `.pages.dev` hostname for the canonical public portal URL.

## GitHub pull requests merged
| Repository | PR | Merge commit |
|---|---:|---|
| `kingpinpkaytee-dot/kingpinpkaytee-dot.github.io` | [#2](https://github.com/kingpinpkaytee-dot/kingpinpkaytee-dot.github.io/pull/2) | `dc432eb5c8ca755b4d6781f641fb86477f79663d` |
| `kingpinpkaytee-dot/diggerman-site` | [#21](https://github.com/kingpinpkaytee-dot/diggerman-site/pull/21) | `bb286a7c1bd4d9933019090345e0f4108ce61adb` |
| `kingpinpkaytee-dot/thekingpin-entertainment-site` | [#5](https://github.com/kingpinpkaytee-dot/thekingpin-entertainment-site/pull/5) | `abc46e1b99fec4775a1b0af064b0b78ebbe7e471` |
| `kingpinpkaytee-dot/diggerman-media-press-kit` | [#2](https://github.com/kingpinpkaytee-dot/diggerman-media-press-kit/pull/2) | `35ffa84336f5fd3193bd775de67267c6e2879d38` |

## QA performed on merged source
- Parsed the edited JSON-LD blocks and machine-readable entity profile successfully.
- Confirmed DiggerMan homepage, artist site, music catalogue, press kit and company homepage use the canonical MusicGroup ID in their structured data.
- Confirmed the dedicated archive page has its own canonical URL and structured data, and references the canonical artist entity.
- Confirmed all five social destinations are represented in the relevant website network pages.
- Confirmed the catalogue distinguishes verified artist profiles from platform search destinations.
- Confirmed the music catalogue sitemap contains one canonical music landing-page entry.

## Production and indexing gate
**Not yet certified live end-to-end.** A post-merge web check returned stale content for some pages and could not retrieve the artist site, company site, new archive route or music catalogue. This does not prove a deployment failure, but it is insufficient evidence to certify rollout.

- Do not submit Google Search Console indexing requests until the live pages and metadata are rechecked.
- Do not use the indexing quota during deployment propagation.
- GTM / GA4 remains parked and unchanged.
- Next verification targets: root hub, blog, press kit, DiggerMan website, company website, Riverlea West Archive, catalogue, JSON entity profile and all relevant sitemap routes.

**Phase 12 source implementation: merged. Production verification: pending. Indexing: on hold.**


## Production crawl follow-up — 2026-11-19
A public web crawl was run after the Phase 12 merges.

### Pages retrieved by the public crawler
- Root DiggerMan hub: HTTP page content retrieved; Spotlight navigation and Riverlea Archive reference are visible. Some network destinations shown in the extracted page still reflect the previous content set.
- Artist blog landing page: retrieved; Artist Spotlight card and links to the core network are visible.
- Canonical Artist Spotlight article: retrieved; canonical article content and catalogue / Spotify / SoundCloud links are visible. Its displayed update date remains 15 September 2026, so the expected Phase 11/12 updated article metadata is not yet confirmed live.
- Media Press Kit: retrieved; main navigation exposes Music and Archive sections, but the crawler extraction does not confirm the full newly added social/DSP link section or current entity JSON-LD.

### Pages not retrieved by this crawler
The public crawler returned an internal retrieval error for the short Spotlight alias, DiggerMan Official website, music catalogue, Kingpin company website, new Riverlea West Archive URL and JSON entity profile. These are **unverified**, not confirmed HTTP 404 responses.

### Deployment gate
This crawl is not enough to certify Phase 12 production rollout. Treat the pages that were retrieved as partial evidence only; treat all inaccessible routes and all unobserved metadata as unverified. The prior Acer-side batched HTTP check was started but did not return results within two polls; no HTTP status codes were obtained from that process.

**Decision:** keep Google Search Console indexing requests on hold. Do not spend the remaining indexing quota until the inaccessible routes resolve and the live HTML confirms canonical MusicGroup ID, separate company Organization ID, archive relationships, social/DSP links, sitemaps and structured data. GTM/GA4 remains parked.


## Direct HTTP and hosting verification — 2026-11-19
A direct Windows HTTP check from the connected Acer device replaced the earlier inconclusive public-crawler results.

| Network surface | URL | HTTP result |
|---|---|---:|
| DiggerMan hub | `https://kingpinpkaytee-dot.github.io/` | 200 |
| Artist blog | `https://kingpinpkaytee-dot.github.io/blog/` | 200 |
| Media press kit | `https://kingpinpkaytee-dot.github.io/diggerman-media-press-kit/` | 200 |
| DiggerMan official website | `https://kingpinpkaytee-dot.github.io/diggerman-site/` | 200 |
| The Kingpin Entertainment website | `https://kingpinpkaytee-dot.github.io/thekingpin-entertainment-site/` | 200 |
| Riverlea West Archive | `https://kingpinpkaytee-dot.github.io/thekingpin-entertainment-site/riverlea-west-archive/` | 200 |
| Music catalogue | `https://kingpinpkaytee-dot.github.io/diggerman-site/music/` | 200 |
| Entity profile JSON | `https://kingpinpkaytee-dot.github.io/diggerman-entity-profile.json` | 200 |
| Artist Frequency public Vercel domain | `https://artist-frequency.vercel.app/` | 200 |
| Submitted `.pages.dev` hostname | `https://artist-frequency-global-music-submission-portal.pages.dev/` | DNS name unresolved |

The press kit and blog HTML expose the official social-network links. This verifies that the social destinations are linked from the owned network pages; it does not independently certify the current availability or ownership state of each social profile.

### Artist Frequency deployment status
Vercel project inspection confirms:
- Canonical project: `artist-frequency`; domain `artist-frequency.vercel.app`.
- The canonical domain currently resolves to a prior READY production deployment, which returned HTTP 200.
- The latest deployment record is BLOCKED and has no active alias.
- Project state reports `live: false`; the canonical project remains paused/blocked for new production rollout.
- The separate `artist-frequency-preview` project has a READY deployment, but SSO protection is enabled. Its preview response is marked `noindex`.
- The separate HTML-verification project serves only the Google Search Console verification HTML and must not be mistaken for the production portal.

### Resolution and release gate
- **Resolved:** the apparent portal outage was a hostname/provider mismatch. The supplied Cloudflare Pages hostname is not the configured portal host; the actual public Vercel domain is reachable.
- **Verified serving:** all eight network areas have a reachable destination or visible linked destinations. The seven DiggerMan network web properties and the canonical Artist Frequency domain returned HTTP 200.
- **Not yet resolved:** the latest Artist Frequency source release remains BLOCKED; the public canonical domain is still serving the prior READY deployment.
- Do not unpause or promote the canonical Vercel project as part of this verification-only pass. A production release requires a separate explicit deployment decision and post-deployment QA.
- Google Search Console indexing remains on hold until the latest intended content is confirmed on the live pages. GTM/GA4 remains parked and unchanged.

**Updated result:** network reachability verified; Artist Frequency hostname corrected; latest portal production deployment still blocked; indexing remains on hold.

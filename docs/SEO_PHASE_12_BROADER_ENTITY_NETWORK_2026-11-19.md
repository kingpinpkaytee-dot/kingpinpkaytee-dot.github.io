# SEO Phase 12 — Broader Entity Network
**Date:** 2026-11-19  
**Status:** Source implementation merged; eight-area network reachability verified; Artist Frequency production host corrected to Cloudflare Pages; Google indexing remains on hold.

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
- Correct public production host: `https://global-music-submission-portal.pages.dev/`.
- The supplied hostname `https://artist-frequency-global-music-submission-portal.pages.dev/` is not a configured Cloudflare Pages domain; the earlier DNS failure was caused by the hostname mismatch.
- Connected Acer Wrangler 4.165.0 login and account access succeeded. Wrangler listed the Cloudflare Pages project `global-music-submission-portal`, with configured domain `global-music-submission-portal.pages.dev` and Git Provider `No`.
- Latest listed Cloudflare production deployment: `3bb98c90-02e5-4533-aea7-67c75ccb0a68`, branch `main`, source commit `935db5b`, immutable URL `https://3bb98c90.global-music-submission-portal.pages.dev/`.
- The 17 November production memorandum records a 21-path smoke test returning HTTP 200 after this deployment, including homepage, robots, sitemap, public JavaScript/config, Google verification path, IndexNow key file and dashboard/account/discovery/Marketplace/campaign/profile/stats/Premium/billing/admin routes.
- Two GitHub commits after source `935db5b` (`ca0c5f58` and `1850f354`) are documentation-only; the current source-bearing main commit remains the code deployed to Pages. No redeployment is needed solely for those documentation commits.
- The Cloudflare Pages project currently reports no Git provider connection; do not assume GitHub pushes automatically deploy. Future production updates must use the reviewed Wrangler direct-upload workflow unless Git integration is separately configured.
- Supabase CLI linking from the Acer checkout succeeded for project `mdcvewnevgsgmyfnybgn` (West EU / Ireland). The subsequent migration comparison showed every version from `0001` through `0031` matching between Local, Remote and Time(UTC); no migration-version gap is listed.
- Migration-history equality does not, by itself, prove every live database object definition. A fresh read-only catalog check should confirm the 0028 `auto_verification` and `auto_verified_at` columns, the 0029 publication policy version 2 and the hardened publication RPC before autonomous publication is treated as runtime-verified. No `db push` or migration write was performed during this check.
- The separate Vercel `artist-frequency` project is not the selected public production portal. Its latest deployment record remains BLOCKED while an older READY deployment serves its own Vercel alias. The separate Vercel preview is SSO-protected and marked `noindex`; neither Vercel URL should replace the Cloudflare Pages canonical host.

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
| Artist Frequency Cloudflare Pages public domain | `https://global-music-submission-portal.pages.dev/` | 200 recorded in the 21-path production smoke test on 2026-11-17 |
| Incorrectly supplied `.pages.dev` hostname | `https://artist-frequency-global-music-submission-portal.pages.dev/` | Not configured for the project; DNS name unresolved |

The press kit and blog HTML expose the official social-network links. This verifies that the social destinations are linked from the owned network pages; it does not independently certify the current availability or ownership state of each social profile.

### Artist Frequency deployment status
Cloudflare Pages is the selected public production host:
- Project: `global-music-submission-portal`.
- Production hostname: `https://global-music-submission-portal.pages.dev/`.
- Latest listed production deployment: `3bb98c90-02e5-4533-aea7-67c75ccb0a68`, branch `main`, source `935db5b`.
- The documented 21-path production smoke test returned HTTP 200 following that deployment.
- The Pages project reports no Git provider connection, so direct Wrangler uploads are the current deployment mode.

Vercel findings are separate from the public production host:
- The `artist-frequency` Vercel project has a latest BLOCKED deployment and an older READY deployment on its own alias. Do not treat that alias as the selected public portal.
- The separate `artist-frequency-preview` deployment is SSO-protected and marked `noindex`; it is not an SEO destination.
- The separate HTML-verification Vercel project remains only a Google Search Console HTML verification endpoint.

### Resolution and release gate
- **Resolved:** the supplied Pages hostname was mistyped/mismatched. The Cloudflare project is present under `global-music-submission-portal`, and its configured production URL is `https://global-music-submission-portal.pages.dev/`.
- **Verified:** Wrangler account/project access, the latest listed Cloudflare Production deployment, the documented 21-path HTTP 200 production smoke test, successful Supabase project linking and migration-history alignment through `0031`.
- **Still pending:** a fresh read-only live catalog check for the 0028 columns, 0029 policy-version-2 row and publication RPC. Do not enable autonomous publication on the strength of migration-history alignment alone.
- Do not unpause or promote the separate Vercel project as part of this verification pass.
- Google Search Console indexing remains on hold; IndexNow HTTP 202 is notification receipt, not proof of Google indexing. GTM/GA4 remains parked.

**Updated result:** network reachability verified; Artist Frequency hostname corrected; latest portal production deployment still blocked; indexing remains on hold.


## Hosting and Supabase correction addendum
The authoritative Acer-side reconciliation is recorded in [SEO Phase 12 Portal Hosting and Supabase Reconciliation — 2026-11-19](SEO_PHASE_12_PORTAL_HOSTING_AND_SUPABASE_RECONCILIATION_2026-11-19.md). It supersedes earlier assumptions that Vercel was the public production portal and confirms Supabase migration-history alignment through 0031.

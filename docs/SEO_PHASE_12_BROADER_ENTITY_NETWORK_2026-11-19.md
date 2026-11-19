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

## Seven network areas

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

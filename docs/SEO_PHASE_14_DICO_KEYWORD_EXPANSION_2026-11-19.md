# SEO Phase 14 — Dico Search-Keyword Expansion Across the Artist Network
Date: 19 November 2026

## Objective

Add the user-requested search term **Dico** consistently to the eight connected SEO network areas supporting the DiggerMan identity, while preserving the distinction between the person, recording artist, company and Artist Frequency platform.

The canonical identity chain remains:

- Person: `Dico Nhlakanipho Dube`
- Confirmed alternate personal name: `Dico Nhlakanipho Phakathi`
- Recording artist: `DiggerMan`
- Spotify Artist profile: https://open.spotify.com/artist/7fSMDP0eWrFwYol9Vye2Ty
- Canonical MusicGroup ID: `https://kingpinpkaytee-dot.github.io/#musicgroup`
- Canonical Person ID: `https://kingpinpkaytee-dot.github.io/#person`

The short term `Dico` is included as a requested search phrase and artist-credit reference. It does not create a separate artist, second Spotify profile, or new legal identity.

## Implementation summary

The keyword cluster includes:
- Dico
- Dico Nhlakanipho Dube
- Dico Nhlakanipho Phakathi
- DiggerMan
- DiggerMan Spotify
- DiggerMan South Africa
- Riverlea artist
- South African independent recording artist
- Relevant page-specific terms such as Amapiano, Afro House, Deep House, the artist catalogue, individual track titles and album titles.

### Eight network areas

| Network area | Dico keyword support added |
|---|---|
| 1. Media Press Kit | Search-focused title/description, keyword metadata, structured Website keywords, and the existing Person/MusicGroup identity links. |
| 2. Artist Spotlight Blog | Search-focused title/description, Article keywords and the existing artist/person identity reference. |
| 3. DiggerMan Official Website | Search-focused title/description, Website keywords and a Dico identity reference alongside the canonical Spotify destination. |
| 4. The Kingpin Entertainment Website | Company title/description and Website keywords now reference Dico and DiggerMan without merging the company and artist entities. |
| 5. Riverlea West Archive | Title/description and CollectionPage keywords connect Dico and DiggerMan to the curated Riverlea creative archive. |
| 6. Music Catalogue | Catalogue title/description and CollectionPage keywords include Dico, DiggerMan, Spotify, catalogue and genre terms. All 68 individual track pages were also updated as described below. |
| 7. Social Network Accounts | Owned sites' Person/MusicGroup references and profile links remain connected to the Dico/DiggerMan identity. No third-party social account bios or settings were edited. |
| 8. Artist Frequency | Platform remains a separate Organization. Its Website keywords and existing Person/MusicGroup mentions connect the referenced artist identity without presenting DiggerMan as the portal owner or platform brand. |

The canonical DiggerMan hub is also updated as the central identity anchor, with a WebPage keyword set and revised title/description.

## Catalogue-wide track work

All **68 individual track pages** listed in the existing sitemap were updated.

Each track page now includes:
- `Dico` and both full personal name forms in its page keyword metadata.
- The individual track title and release/album title in its keyword set.
- A `MusicRecording.keywords` list with the track-specific and artist identity phrases.
- `byArtist` linked to the canonical DiggerMan MusicGroup ID.
- The Spotify Artist URL and person-name variants in the structured artist reference.
- A track description that connects Dico Nhlakanipho Dube to the DiggerMan recording identity.
- A visible artist credit that reads DiggerMan (Dico Nhlakanipho Dube).

Track titles, Spotify track links, album links, artwork, duration, release dates, track positions, canonical URLs and sitemap membership are preserved. No unverified music genres or new release data were added.

## Google Search implementation note

The legacy HTML `<meta name="keywords">` tag is included as a supplemental compatibility field because the request explicitly called for keyword metadata. **Google Search states that it does not use this tag and that it has no effect on indexing or ranking.** The meaningful search support in this phase is therefore the natural page text, revised page titles/descriptions, visible track artist credits, structured page/recording keywords, consistent artist identifiers and crawlable links.

Google's current guidance recommends using the words people search for in prominent page locations and descriptive content, while avoiding repetitive keyword stuffing. This work adds the Dico identity term in context and does not promise rankings, indexing dates or a Knowledge Panel.

## Quality assurance

- The eight network landing/identity pages and central hub were updated on their review branches.
- The 68 track pages were each successfully fetched, parsed as `MusicRecording` JSON-LD, transformed and written to the review branch.
- The prior catalogue sitemap contains 73 URLs in total, including 68 individual track pages; the sitemap itself was not changed.
- Canonical entity IDs and the Spotify Artist ID `7fSMDP0eWrFwYol9Vye2Ty` were preserved.
- The Artist Frequency Organization remains separate from the DiggerMan MusicGroup and Dico Person entities.
- No GTM/GA4, Search Console, robots, canonical URL, Supabase, or production deployment setting was modified by this phase.

## Boundaries

- Third-party social profile bios/settings were not changed.
- The Spotify artist page itself was not edited.
- The keyword changes are prepared in Git branches for review; no production deployment is included in this phase.
- Google indexing and search-result behavior still require subsequent crawl/URL Inspection checks.


## Merge record

The Phase 14 keyword-support changes were merged across the five repositories:

| Repository | Pull request | Merge commit |
|---|---:|---|
| `kingpinpkaytee-dot/kingpinpkaytee-dot.github.io` | #4 | `a701ed574814969ed2e716e1a5ce651eeefdc0dc` |
| `kingpinpkaytee-dot/diggerman-site` — landing pages and 68 track keywords | #23 | `9ba674d385c0d59c03dda6ae054ee21b8dbb00f5` |
| `kingpinpkaytee-dot/diggerman-site` — track metadata repair | #25 | `2b5e56958ab1d8b3f49cde34d16c5589783cf1ca` |
| `kingpinpkaytee-dot/thekingpin-entertainment-site` | #7 | `e99493c2e3a1c4e733ec69bc01105f48274cb334` |
| `kingpinpkaytee-dot/diggerman-media-press-kit` | #4 | `df93472eb149dac2e420a8b8786fb54cfbc532c8` |
| `kingpinpkaytee-dot/global-music-submission-portal` | #8 | `b002f9bf15912d48909e03a2e91aa86b044faa85` |

## Artist Frequency deployment

The Artist Frequency update was deployed through Wrangler 4.165.0 to the existing Cloudflare Pages production project after PR #8 merged.

- Canonical production host: https://global-music-submission-portal.pages.dev/
- Immutable deployment URL: https://3faa9852.global-music-submission-portal.pages.dev/
- Source commit: `b002f9bf15912d48909e03a2e91aa86b044faa85`
- Wrangler reported deployment complete; one new asset was uploaded and nine were already present.
- Acer HTTP checks returned 200 for the homepage, `src/app.js`, `src/auth.js` and `src/supabase-client.js`. The homepage contained both Dico name forms and the canonical Spotify Artist ID.

## Post-merge website smoke check

A direct HTTP request from the Acer returned 200 and found the Dico personal-name reference plus the supplemental keyword metadata on the hub, Spotlight, official artist homepage, music catalogue landing page, company homepage, Riverlea archive and press kit. The 68 track-page metadata repair was merged separately in PR #25; its live GitHub Pages propagation should be checked after the merge.

This confirms deployment/reachability and source-content consistency only. It does not establish Google indexing, rankings or a Knowledge Panel.


## Track-page post-repair live verification

The clean metadata repair was merged to the DiggerMan website repository in PR #25 (merge commit `2b5e56958ab1d8b3f49cde34d16c5589783cf1ca`).

A post-merge HTTP check from the Acer returned HTTP 200 for three representative live track pages:
- Dico — `/music/tracks/the-gorilla-zone-2-0/dico/`
- We Are One (1.0) — `/music/tracks/celestial-frequency-1-0/we-are-one-1-0/`
- CELESTIAL FREQUENCY Remix (2.0) — `/music/tracks/celestial-frequency-2-0/celestial-frequency-remix-2-0/`

Each served page had exactly one standard description tag, one Open Graph description tag, one Twitter description tag and one supplemental keywords tag. Each page's visible DiggerMan/Dico credit and canonical Spotify Artist ID were present. This is a representative smoke test, not a claim that all 68 URLs have individually been fetched post-deployment.

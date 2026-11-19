# SEO Phase 13 — DiggerMan Identity and Name-Variant Linking
Date: 2026-11-19

## Objective

Connect the two user-confirmed personal name forms — **Dico Nhlakanipho Dube** and **Dico Nhlakanipho Phakathi** — to the single recording-artist identity **DiggerMan**, and connect that artist entity to its canonical Spotify Artist profile.

This is entity clarification across the owned network, not keyword stuffing and not a claim that search engines have already changed their results.

## Canonical entity relationship

- Person: `https://kingpinpkaytee-dot.github.io/#person`
  - Primary name: Dico Nhlakanipho Dube
  - Alternate name: Dico Nhlakanipho Phakathi
  - `memberOf`: the canonical DiggerMan artist entity
- Artist: `https://kingpinpkaytee-dot.github.io/#musicgroup`
  - Name: DiggerMan
  - Alternate names include Dico Nhlakanipho Dube and Dico Nhlakanipho Phakathi.
  - `sameAs` includes the Spotify Artist profile: https://open.spotify.com/artist/7fSMDP0eWrFwYol9Vye2Ty
  - MusicBrainz identifier: 56a9fd42-e71b-4292-93b2-6662e1588503
- The artist entity's `member` points to the Person entity; the Person entity's `memberOf` points back to DiggerMan. The company remains a separate Organization.

## Eight-network implementation map

| Network | Identity connection added |
|---|---|
| 1. DiggerMan media press kit | Visible name-variant statement, Spotify Artist link, Person and MusicGroup JSON-LD references. |
| 2. Artist Spotlight blog | Name-variant statement in the article and linked Person/MusicGroup entities in Article JSON-LD. |
| 3. DiggerMan official website | Biography now explains both personal name forms and links to the canonical Spotify Artist profile. |
| 4. The Kingpin Entertainment website | Company artist section identifies DiggerMan and connects both name forms to Spotify; company remains a distinct Organization. |
| 5. Riverlea West Archive | Archive text and CollectionPage structured data connect the artist and Person entities without presenting the archive as a comprehensive historical record. |
| 6. DiggerMan music catalogue | Catalogue landing-page description identifies both personal name forms. Existing 68-track catalogue and MusicRecording routes were left intact. |
| 7. Social network accounts | Owned pages' Person/MusicGroup `sameAs` references consistently connect the known Instagram, Facebook, Threads, X, TikTok and LinkedIn profiles. Social profile bios/settings were not edited, and the individual social endpoints were not re-verified in this phase. |
| 8. Artist Frequency portal | Footer includes the artist identity reference and Spotify link. The portal Organization's `mentions` references the Person and DiggerMan entities; Artist Frequency remains a separate platform brand. |

## Canonical hub and machine-readable profile

The root DiggerMan hub and `diggerman-entity-profile.json` provide the central entity definition referenced by the network. The Spotlight article, press kit, official artist website, catalogue, company site, archive and Artist Frequency portal reuse the stable Person and MusicGroup identifiers rather than creating competing artist entities.

## Quality assurance

- JSON-LD parsed successfully in all eight HTML pages touched plus the standalone entity-profile JSON.
- The two personal name forms and canonical Spotify Artist URI were confirmed in all nine changed artifacts.
- Person-to-artist relationships were checked through `memberOf` and `member`, or equivalent article/page mentions where appropriate.
- The canonical Spotify Artist URL and existing MusicBrainz identifier were preserved.
- No new artist alias, release, credit, biography date, or legal/company relationship was invented.

## Scope intentionally left unchanged

- Social account bios and settings: no direct platform edits.
- Google Tag Manager, GA4, Search Console, robots directives, canonical URLs and sitemap policy.
- Individual track-page content and metadata: existing track pages continue to reference the canonical DiggerMan MusicGroup ID.
- Artist Frequency authentication, Supabase data, migration history, publication policy and autonomous publishing.
- Cloudflare Pages deployment: Artist Frequency PR #7 is merged into the portal's main branch, but its live Cloudflare artifact was not redeployed. The Acer HTTP check returned 200 for the current Pages host but did not find the new alias or Spotify link in the served HTML. The repository's production-release gate remains in force; no Wrangler deployment was run.

## Search outcome note

These edits strengthen consistency and machine-readable identity relationships across the owned network. They do not guarantee Google Knowledge Panel creation, a particular ranking, an indexing date, or a specific search-result layout. Re-crawl and indexing confirmation remain separate follow-up checks.

## Merge and live verification record

The five implementation pull requests were merged on 19 November 2026:

| Repository | PR | Merge commit |
|---|---:|---|
| kingpinpkaytee-dot/kingpinpkaytee-dot.github.io | #3 | 87e9be2e8512f1402540c9ce46865f4ecba51741 |
| kingpinpkaytee-dot/diggerman-site | #22 | 5acb0bba59223b7acc0c90a0ff7bf97eb865abb4 |
| kingpinpkaytee-dot/thekingpin-entertainment-site | #6 | 0373aaeb512019c64de57ed52d4fcf83573dbfc6 |
| kingpinpkaytee-dot/diggerman-media-press-kit | #3 | 26946a9c15379c9d1017329135752d4dc34cc7c9 |
| kingpinpkaytee-dot/global-music-submission-portal | #7 | fcbbab4e22753bfac753e47aa8f162804333e304 |

A direct HTTP check from the connected Acer returned status 200 and found both the Dico Nhlakanipho Phakathi alias and Spotify Artist ID in the served HTML for the seven GitHub Pages routes: the root hub, Spotlight article, DiggerMan website, catalogue landing page, company website, Riverlea Archive and press kit.

The Artist Frequency Cloudflare Pages host also returned HTTP 200, but the live HTML did not yet contain the new alias or Spotify Artist ID. Its source update is merged, while the hosted artifact remains unchanged pending the separate production-release gate.

The social profile URLs are referenced consistently from the Person and MusicGroup entities and owned network pages. Social account bios/settings have not been edited or independently re-verified.

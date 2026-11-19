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
- Cloudflare Pages deployment: source changes are staged for review; no production deployment is performed by this memo.

## Search outcome note

These edits strengthen consistency and machine-readable identity relationships across the owned network. They do not guarantee Google Knowledge Panel creation, a particular ranking, an indexing date, or a specific search-result layout. Re-crawl and indexing confirmation remain separate follow-up checks.

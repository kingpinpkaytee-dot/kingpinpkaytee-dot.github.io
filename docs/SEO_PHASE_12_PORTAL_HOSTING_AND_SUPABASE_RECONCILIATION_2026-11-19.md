# SEO Phase 12 Correction — Artist Frequency Hosting & Supabase Reconciliation

**Date:** 2026-11-19  
**Scope:** Correct the portal-hosting record in SEO Phase 12 and record the Acer-side Wrangler/Supabase verification.  
**Supersedes:** The earlier Phase 12 Section 8 statements that treated the Vercel domain as the public production portal and the supplied, incorrectly named Pages hostname as the expected Cloudflare domain.

## 1. Correct Artist Frequency production hostname

The connected Acer's authenticated Wrangler 4.165.0 session successfully listed the Cloudflare Pages account and project.

- Cloudflare Pages project: `global-music-submission-portal`
- Configured Pages domain: **https://global-music-submission-portal.pages.dev/**
- Git Provider shown by Wrangler: `No` (the Pages project is not currently Git-integrated).
- Last modified in the Pages project list: one day before this check.

The previously supplied hostname `artist-frequency-global-music-submission-portal.pages.dev` is not the domain registered to this Pages project. Its earlier DNS failure was a hostname mismatch, not evidence that the configured Pages project was absent.

## 2. Cloudflare production deployment provenance

Wrangler's read-only `pages deployment list` returned the following recent records for `global-music-submission-portal`:

| Environment | Deployment ID | Branch | Source commit | Immutable URL |
|---|---|---|---|---|
| Production | `3bb98c90-02e5-4533-aea7-67c75ccb0a68` | `main` | `935db5b` | https://3bb98c90.global-music-submission-portal.pages.dev/ |
| Production | `621778f3-a6f6-483e-810e-ee849eebd5c2` | `main` | `064b648` | https://621778f3.global-music-submission-portal.pages.dev/ |
| Preview | `a0354f8a-cff2-42d4-ad84-3d00b16a5604` | `seo/artist-frequency-visual-and-entity-seo-2026-11` | `ebd997a` | https://a0354f8a.global-music-submission-portal.pages.dev/ |

The latest listed Production deployment is the IndexNow-key release, not the older Vercel project. The existing Artist Frequency production release memorandum records that deployment `3bb98c90` published the public IndexNow verification file and passed a **21-path HTTP 200 production smoke test** on 17 November 2026. It also records successful live retrieval of the key file and acceptance of the IndexNow notification request with HTTP 202. HTTP 202 confirms notification receipt, not Google indexing.

GitHub main currently has two commits after the deployed source commit:
- `ca0c5f58a7f4001cc80fff3111ee8135f51390b9` — documentation-only IndexNow/production-QA record.
- `1850f354dff63eb8e3ceea7910c59897cf834468` — documentation-only final QA record.

Both commit patches change documentation, not deployed application files. Therefore the latest Production deployment's source commit `935db5b` remains the latest source-bearing commit; a new Pages deployment is not required just to publish those two documentation updates.

**Deployment mode:** Wrangler reports no Git provider for the Pages project. Do not assume a Git push automatically deploys to Pages. Future releases must be reviewed and deployed through the configured direct-upload workflow, or the owner can separately set up Cloudflare Git integration.

## 3. Vercel project is not the public production portal

The Vercel project `artist-frequency` is a separate project. Its latest deployment record was previously reported as BLOCKED, while an older READY deployment continued serving its Vercel alias. The separate `artist-frequency-preview` project is SSO-protected and marked `noindex`.

Those Vercel URLs must not be substituted for the selected public production host. The canonical Artist Frequency portal host for network links, SEO, CORS and payment-origin configuration remains:

`https://global-music-submission-portal.pages.dev`

Do not unpause the Vercel project or change its aliases as part of this reconciliation.

## 4. Supabase CLI linking and migration history

On the Acer, from `C:\\Users\\USER\\source\\repos\\global-music-submission-portal`:

- `npx supabase projects list` successfully returned the account's project.
- Project reference: `mdcvewnevgsgmyfnybgn`.
- Region: West EU (Ireland).
- The initial `Cannot find project ref. Have you run supabase link?` message occurred before the working copy was linked.
- `npx supabase link --project-ref mdcvewnevgsgmyfnybgn` then completed successfully and targeted the production project.
- The subsequent `npx supabase migration list` showed **every version from 0001 through 0031 matching between Local, Remote and Time(UTC)**. There are no migration-version gaps or unapplied versions in that comparison.

Relevant expected schema changes in the checked-in migration source:
- **0028** adds `opportunity_discovery_candidates.auto_verification` (jsonb) and `auto_verified_at` (timestamptz), and defines the service-role-only `auto_publish_verified_opportunity_candidate(uuid)` RPC.
- **0029** installs `opportunity_discovery_runtime_config` with publication policy version 2 and tightens the autonomous playlist eligibility checks.
- **0030** changes the minimum playlist follower gate to 15 while retaining the other verification gates.
- **0031** creates the Premium subscription and credit-grant tables plus the service-role-only payment-settlement RPC.

**Interpretation:** the migration ledger is now aligned through 0031. The old 0028 missing-column message is no longer evidence of a pending migration. However, equal migration ledgers alone do not independently prove every live column/function definition if migration history was repaired manually. A fresh read-only catalog query should confirm the two 0028 columns, the policy-version-2 row and the current RPC definition before autonomous publication is treated as runtime-verified. The read-only SQL inspection attempted during this pass did not return a result, so this addendum does not claim that additional catalog check passed.

No `supabase db push`, migration application, database row mutation or credential change was performed in this reconciliation.

## 5. Remaining verification and release gates

1. Keep autonomous public publication disabled until a read-only production catalog check confirms the 0028 columns, policy version 2 and the hardened RPC definition. The worker must continue to honour the database policy gate.
2. Keep the Pages host above as the only public production portal origin in canonical metadata and origin configuration.
3. Treat the Pages project as direct-upload/manual deployment until Cloudflare Git integration is explicitly configured.
4. Keep Google Search Console indexing requests on hold until the owner authorises the next indexing phase. IndexNow acceptance is not proof of Google crawling or indexing.
5. GTM/GA4 remains parked and unchanged.
6. Paystack remains subject to the documented Test Mode checkout and signed-webhook acceptance process; no live customer charge or payout is authorised by this reconciliation.

## Result

- **Resolved:** Correct Cloudflare Pages project and production hostname identified.
- **Verified:** Wrangler authentication/project access; latest listed Production deployment and source commit; Supabase project link; local/remote migration history 0001–0031 aligned.
- **Still pending:** Fresh read-only live catalog verification of 0028/0029 runtime objects; any future Pages Git integration; owner-authorised Google Search Console indexing.
- **Unchanged:** Production application deployment, Supabase data, credentials, DNS, GTM/GA4 and Vercel aliases.

# PUSH NOTE — SaveVault-DOC (built 2026-11-05, local only, NOT pushed)

## What this folder is

The complete, push-ready source tree for SaveVault's documentation site, built to the Decnet house "-DOC" pattern (structure/config mirrored from MergeGuard-DOC / AgentProof-DOC / ShipSheet-DOC):

- Just the Docs Jekyll site via `remote_theme` (no `theme:` gem key, no `just-the-docs` gem in the Gemfile — the pairing that fixed the two known GitHub Pages errors: "The just-the-docs theme could not be found" and "The github-pages gem can't satisfy your Gemfile's dependencies").
- 23 content pages: Home + Getting Started + Installation + Quick Start + The Home Window + One-Click Setup + Storage Status + Versioned Schemas + Migration Centre + Atomic Persistence + Integrity Sealing + Backups & Recovery + Save Health & Diagnostics + Sync Lab + Cloud Backends & Merge Resolution + Steam Cloud + The Wayfarer Sample + Settings + What v1 Is Not + FAQ + Troubleshooting + Changelog + Support.
- **No media in this tree, by design** (the MergeGuard-DOC precedent: documentation never ships invented imagery, and pages are written so they do not depend on any image). SaveVault's real Editor captures exist in `../raw/` (Session A frames), but this tree ships text-only; screenshots can join `assets/` later from real captures without changing any claim.
- Content sourced ONLY from the corrected record: the listing copy (`../../savevault-prep/LISTING-COPY.md`, corrected 2026-11-05 after Session A falsified two claims — see the correction note at the top of that file) and the Session A capture evidence in `../work/RESUME-STATE.md` + `../VERIFY.md`. Two fences are load-bearing throughout: **Sync Lab is described only as the review surface it is** (its divergence trigger is a log-line stub, `SaveVaultHomeWindow.cs:295–297` — never a runnable simulation), and **no sample scene is claimed** (the shipped package contains none; `Samples~/Wayfarer` is code + the v1 fixture only). Steam Cloud is fenced everywhere as **mock-verified only** — no live Steam claim. Verified numbers used: 45/45 EditMode tests on Unity 6 and 2022.3 LTS; Migration Centre chains player→v3 (2 steps), inventory→v2 (1 step), world→v3 (2 steps); Settings values as rendered (Backup Retention 5, Tamper Policy "Auto Recover With Quarantine", Sync Trigger Automatic, Autosave 5 s, Sync Throttle 30 s).
- No product Asset Store URL exists yet (no portal draft yet — draft creation is capture-gated in the programme), so Home/Installation link the Decnet Games publisher page (118262) — swap in the product URL after the listing goes live, as with the other -DOC trees.

## Exact repo to create

- **Name:** `SaveVault-DOC`
- **Owner:** `DecNet-Games` (GitHub org account)
- **Visibility:** public (required for GitHub Pages on this setup)
- **Live URL once Pages is on:** https://decnet-games.github.io/SaveVault-DOC/ (matches the `baseurl: "/SaveVault-DOC"` already set in `_config.yml`)

## Push route (do this from the laptop, per the standing no-card-spam rule)

Bulk pushes go via laptop git over SSH — never the GitHub connector.

1. BOSS creates the empty repo `DecNet-Games/SaveVault-DOC` on GitHub (no README, no .gitignore — this tree carries its own).
2. Copy this folder's contents to the laptop clone location, then: `git init` (if needed) → `git add .` → `git commit` → the final `git push` is BOSS's own ~10-second action at his terminal (laptop git credentials only work interactively — known constraint).
3. On GitHub: repo **Settings → Pages → Build and deployment → Source: GitHub Actions** (the standard github-pages workflow), or "Deploy from a branch" → `main` / root if Actions is unavailable. The other -DOC repos run on the same org setup — mirror whichever source they use.
4. After the first successful build, verify:
   - the live URL loads with the Just the Docs theme (no theme error),
   - nav order: Home, Getting Started, Installation, Quick Start, The Home Window, One-Click Setup, Storage Status, Versioned Schemas, Migration Centre, Atomic Persistence, Integrity Sealing, Backups & Recovery, Save Health & Diagnostics, Sync Lab, Cloud Backends & Merge Resolution, Steam Cloud, The Wayfarer Sample, Settings, What v1 Is Not, FAQ, Troubleshooting, Changelog, Support.
5. Only after the site is live: apply the house-format description (`../DESCRIPTION-HOUSE.md`) to the portal draft when it is created — its link line carries `DOCUMENTATION → https://decnet-games.github.io/SaveVault-DOC/` (dead-link rule: never publish the link before the site resolves).

## What remains

- Repo creation + push + Pages enable: BOSS-side steps above (by design — this build stopped at a complete local tree, per instructions).
- Media: optional later addition from the real captures in `../raw/` — not required for the site to be complete or correct.
- Portal draft: does not exist yet (capture-gated); the house description waits for both the draft and this site being live.
- Nothing in the tree itself: content, config and Gemfile are complete and internally verified (page count, front matter, nav order checked against disk).

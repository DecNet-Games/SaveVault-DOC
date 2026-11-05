---
layout: home
title: Home
nav_order: 1
description: "SaveVault is the versioned save system for Unity: saves migrate across updates automatically, corrupted saves recover from rolling backups, tampered saves are detected, and local-first sync merges without losing either side."
permalink: /
---

# SaveVault
{: .fs-9 }

Your players' saves, **migrated across updates, recovered from corruption, and synced without losing either side**.
{: .fs-6 .fw-300 }

[Get started]({{ site.baseurl }}/docs/getting-started/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Buy on the Unity Asset Store](https://assetstore.unity.com/publishers/118262){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## The morning every shipped game meets

You release an update, the save format changed, and your players' old saves either break or get wiped. SaveVault is the save system built for that morning. Saves are versioned by section, migrations run automatically when an old save loads, writes are atomic so a crash mid-save cannot tear a file, and when a save does corrupt, the player gets their last good backup back — not a lost game.

- **Versioned schemas with per-section migration chains** — each part of the save (player, inventory, world) versions independently and migrates step by step: a v1 save loads into a v3 game through its registered steps, in order, with a pre-migration backup taken first.
- **Atomic persistence** — every write follows a write-temp-verify-swap protocol, so an interrupted write leaves the last good save untouched.
- **Rolling backups and corruption recovery** — when a save fails verification, SaveVault restores the last good backup and reports exactly what happened; the corrupt bytes are kept in a named quarantine, never silently deleted.
- **Integrity sealing** — saves are sealed with HMAC-SHA256. A tampered or hand-edited save is detected on load and recovered from backup, with the cause named in plain language.
- **Local-first cloud sync** — section- and field-level merge resolution: when two devices change different fields, both changes survive the merge; conflicting copies are preserved in quarantine, not overwritten. Backends included for local folders and REST endpoints, plus a Steam Cloud adapter.

## See it work in ten minutes

The **Wayfarer sample code** ships in the package under `Samples~`: a reference save panel, a sample hero, the sample migration chain, and a real v1 save fixture. No sample scene ships — the panel components drop into any scene of your own, a two-minute wiring job. Load the v1 fixture through the panel and it migrates to the current format through its registered steps (coins-to-gold, then split-health), with the Migration Report naming every step that ran. Then simulate a bit-flip corruption and load again: the hero comes back from backup. See [The Wayfarer Sample]({{ site.baseurl }}/docs/wayfarer-sample/).

## One home window

**Tools → Decnet Games → SaveVault** opens SaveVault Home: Welcome with one-click setup and verification, Storage Status, Migration Centre, Save Health & Diagnostics, Sync Lab, and Settings. Everything SaveVault does in the Editor lives in that one window — see [The Home Window]({{ site.baseurl }}/docs/home-window/).

## The honest frame

The Steam Cloud adapter is **verified against the Steamworks Remote Storage mock surface only** — a live end-to-end Steam test needs your own Steam partner App ID, and the setup for it is documented step by step. Sync Lab is a review surface, not a simulation runner. The full boundary list is [What v1 Is Not]({{ site.baseurl }}/docs/what-v1-is-not/).

> Automated verification for v1.0.0: **45/45** EditMode tests green on Unity 6 and on Unity 2022.3 LTS, in main and fresh projects, with clean-project install and first-run flow proven on both targets from shipped materials.

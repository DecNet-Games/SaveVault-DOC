---
layout: default
title: Changelog
nav_order: 22
description: "SaveVault 1.0.0 — the initial release: versioned per-section saves with migration chains, atomic persistence, HMAC-SHA256 sealing, rolling backups with quarantine, local-first sync, and the Wayfarer sample code."
---

# Changelog
{: .no_toc }

## 1.0.0 — initial release

- SaveVault Home — one Editor window: Welcome with one-click setup, Storage Status, Migration Centre, Save Health & Diagnostics, Sync Lab, Settings.
- Versioned save runtime: per-section schemas with registered migration chains — a v1 save loads into a v3 game step by step, in order, with a pre-migration backup taken first.
- Atomic persistence: write-temp-verify-swap on every write, so an interrupted write leaves the last good save untouched.
- Integrity sealing: HMAC-SHA256 on every save; a tampered or hand-edited save is detected on load and recovered from backup, with the cause named.
- Rolling backups with corruption recovery, and a named quarantine for corrupt bytes — never silently deleted.
- Local-first sync with section- and field-level merge resolution; conflicting copies preserved in quarantine, not overwritten. Folder and REST backends included, plus a Steam Cloud adapter (verified against the mock Remote Storage surface).
- Fault simulation tools (bit-flip, torn temp, tamper) in Save Health & Diagnostics, so recovery is testable before players find it.
- Sync Lab: the two-device sync review surface (Device A / Device B roots, backend seed state, divergence review).
- Wayfarer sample code under `Samples~` (SampleHero, SampleSavePanel, SampleMigrations) plus the v1 save fixture `wayfarer-v1.saveslot` — no sample scene ships.
- Documentation set: quick-start, migration guide, Steam Cloud setup, full reference, "what v1 is not".
- 45 automated EditMode tests (NUnit) — Unity 6 and 2022.3 LTS.

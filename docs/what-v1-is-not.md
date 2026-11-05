---
layout: default
title: What v1 Is Not
nav_order: 19
description: "SaveVault v1's explicit boundaries: not a leaderboard, achievement, or networking system; Steam Cloud mock-verified only; Sync Lab is a review surface; no sample scene ships."
---

# What v1 Is Not
{: .no_toc }

This page is the honest list. Everything SaveVault v1 does is documented in these pages; everything here is what it deliberately does not do.

## Not a game-services system

SaveVault keeps your save data safe. It is **not a leaderboard, achievement, or networking system**, and it does not try to be one.

## Steam Cloud is mock-verified only

The Steam Cloud adapter is verified against the **Steamworks Remote Storage mock surface**. There is **no live Steam result** in v1's record: a live end-to-end test needs your own Steam partner App ID, on your own game's configuration. Any reading of these pages as "Steam Cloud proven live" is wrong — see [Steam Cloud]({{ site.baseurl }}/docs/steam-cloud/).

## Sync Lab is not a simulation runner

Sync Lab is a **review surface**: Device A/B roots, backend seed state, divergence review. Its Trigger Divergence Simulation control writes an operation-log line — it does **not** run a live merge. The merge machinery is the runtime sync manager, judged by its behaviour and the test suite. See [Sync Lab]({{ site.baseurl }}/docs/sync-lab/).

## No sample scene ships

`Samples~/Wayfarer` ships **code and a v1 save fixture** — SampleHero, SampleSavePanel, SampleMigrations, `wayfarer-v1.saveslot`. It does **not** ship a scene. The panel drops into your own scene; see [The Wayfarer Sample]({{ site.baseurl }}/docs/wayfarer-sample/).

## Not silent about failure

Boundaries in the other direction also hold: SaveVault never silently deletes corrupt bytes (they are quarantined and named), never silently accepts a tampered save (it is detected and recovered), and never claims an integration the setup probe did not find (a missing Steamworks.NET is reported as missing).

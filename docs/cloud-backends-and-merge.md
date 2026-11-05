---
layout: default
title: Cloud Backends & Merge Resolution
nav_order: 15
description: "Local-first sync with section- and field-level merge resolution: both sides' changes survive, true conflicts are quarantined rather than overwritten, with folder and REST backends included."
---

# Cloud Backends & Merge Resolution
{: .no_toc }

SaveVault's sync is **local-first**: the local save is the working truth, and sync reconciles it with the backend copy instead of replacing one with the other.

## Merge resolution

Reconciliation happens at **section and field level**, not whole-file level:

- When two devices change **different fields**, **both changes survive the merge** — a whole-file "newer wins" overwrite would silently destroy one side's progress; SaveVault's merge does not.
- When the two sides genuinely conflict, the **conflicting copies are preserved in quarantine, not overwritten** — a true conflict becomes inspectable evidence with a named report, never a silent coin-flip.

The machinery behind this is the runtime's local-first sync manager; its divergence behaviour (both sides quarantined, divergence reported) is covered by the automated test suite. The [Sync Lab]({{ site.baseurl }}/docs/sync-lab/) surface is where you review the two sides' state in the Editor.

## Backends included

- **Local folder** backend — sync against a folder (a shared drive, a synced directory, a second device root).
- **REST** backend — sync against your own REST endpoint.
- **Steam Cloud adapter** — ships with the package; verified against the mock Remote Storage surface only. See [Steam Cloud]({{ site.baseurl }}/docs/steam-cloud/).

Sync behaviour — trigger and throttle — is configured in [Settings]({{ site.baseurl }}/docs/settings/) (shipped defaults: automatic trigger, 30 s throttle).

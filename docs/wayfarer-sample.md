---
layout: default
title: The Wayfarer Sample
nav_order: 17
description: "Samples~/Wayfarer ships sample code — SampleHero, SampleSavePanel, SampleMigrations — plus a real v1 save fixture. No sample scene ships; the panel drops into your own scene."
---

# The Wayfarer Sample
{: .no_toc }

The Wayfarer sample is SaveVault's shipped demonstration material. This page states exactly what ships — read it before expecting a scene.

## What ships

Under `Samples~/Wayfarer`, the package contains **code and one fixture**:

- **`SampleSavePanel`** — the reference save panel: save, load, and load-the-v1-save wiring against the real SaveVault runtime.
- **`SampleHero`** — the sample hero the panel reads and writes.
- **`SampleMigrations`** — the sample migration chain: **coins-to-gold** (v1→v2) and **split-health** (v2→v3).
- **`wayfarer-v1.saveslot`** — a real v1 save fixture: the v1 hero's data (gold 250, health 34 of 40, checkpoint cp_forest_01).

## What does not ship

**No sample scene.** The package contains no `.unity` scene for Wayfarer — the panel components are designed to drop into **any scene of your own**, which is a two-minute wiring job: add the panel, add the hero, and the fixture load path is live. This is deliberate honesty, stated here and in [What v1 Is Not]({{ site.baseurl }}/docs/what-v1-is-not/): the sample is the wiring and the fixture, not a staged scene.

## The ten-minute exercise

1. Drop the Wayfarer panel components into a scene of your own.
2. Load the shipped v1 fixture through the panel's load path, pointing it at `wayfarer-v1.saveslot`.
3. The fixture migrates to the current format through its registered steps — coins-to-gold, then split-health — with a pre-migration backup taken first, and the **Migration Report names every step that ran**.
4. The hero's data arrives intact in the new format.
5. From [Save Health & Diagnostics]({{ site.baseurl }}/docs/save-health-and-diagnostics/), run the bit-flip simulation on the slot and load again: the last good backup is restored and the corrupt bytes land in quarantine.

That sequence exercises migration, sealing, and recovery using shipped materials only.

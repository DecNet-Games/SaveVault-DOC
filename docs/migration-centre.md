---
layout: default
title: Migration Centre
nav_order: 9
description: "The Migration Centre lists every registered migration chain and which stored saves still need migration, and the Migration Report names every step that ran on a load."
---

# Migration Centre
{: .no_toc }

The Migration Centre is the control room for save-format change, inside [SaveVault Home]({{ site.baseurl }}/docs/home-window/).

## What it shows

- **Every registered chain.** SaveVault's own registered chains render here as player → v3 (2 steps), inventory → v2 (1 step), world → v3 (2 steps) — alongside the sections your own game registers.
- **Which stored saves need migration.** A slot stored below its section's current version is listed as a migration candidate, so you can see the blast radius of a format change before your players load anything.

## What happens on load

Migrations run **automatically when an old save loads** — there is no separate conversion pass to schedule:

1. A **pre-migration backup** of the original save is taken first.
2. The section's chain runs **step by step, in order** (v1→v2, then v2→v3).
3. The **Migration Report** names every step that ran, so a migrated save is never a mystery: you can point at the exact steps between the player's old format and the current one.

The shipped demonstration of the full path is the [Wayfarer fixture]({{ site.baseurl }}/docs/wayfarer-sample/): `wayfarer-v1.saveslot` migrates through **coins-to-gold** (v1→v2) and **split-health** (v2→v3), and the report names both steps.

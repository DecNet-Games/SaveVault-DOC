---
layout: default
title: Versioned Schemas
nav_order: 8
description: "SaveVault versions each save section independently — player, inventory, world — so one part of your save format can evolve without invalidating the rest."
---

# Versioned Schemas
{: .no_toc }

A SaveVault save is not one monolithic file with one version number. It is a set of **sections** — player, inventory, world, and your own — and **each section versions independently**.

## Why per-section

When you ship an update, usually only one part of the save format changes: the inventory gains a field, the world data does not. With a single whole-save version, that one change forces a migration story for the entire file. With per-section versions:

- The changed section migrates through its registered steps.
- Every unchanged section loads exactly as stored — untouched, unconverted, unrisked.
- A section's current version is visible per slot in [Storage Status]({{ site.baseurl }}/docs/storage-status/).

## Migration chains

Each section carries a **registered migration chain**: an ordered list of steps, one per version hop (v1→v2, v2→v3). When an old save loads, the chain runs **step by step, in order** — a v1 save loads into a v3 game through its registered steps, never a jump the steps did not define. Before the first step runs, a **pre-migration backup** of the original save is taken, so a migration that goes wrong never costs the player the original bytes.

The chains registered in your project — SaveVault's own and your game's — are listed in the [Migration Centre]({{ site.baseurl }}/docs/migration-centre/).

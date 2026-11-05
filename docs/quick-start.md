---
layout: default
title: Quick Start
nav_order: 4
description: "The ten-minute path: run setup, drop the Wayfarer panel into a scene, load the shipped v1 fixture through its migration chain, then break the save on purpose and watch it recover."
---

# Quick Start
{: .no_toc }

1. TOC
{:toc}

## 1. Open SaveVault Home

**Tools → Decnet Games → SaveVault** opens the one window everything lives in: Welcome, Storage Status, Migration Centre, Save Health & Diagnostics, Sync Lab, Settings.

## 2. Run the one-click setup

Setup creates and verifies the settings asset (`Assets/SaveVault/SaveVaultSettings.asset`) and the test root, reports whether Steamworks.NET was detected (if it was not, the report says so plainly — Steam Cloud stays mock-only in that project), and ends with a status line: **Ready for development and shipping**. Full detail: [One-Click Setup]({{ site.baseurl }}/docs/one-click-setup/).

## 3. Wire the Wayfarer panel into a scene

The package ships **sample code**, not a sample scene: under `Samples~/Wayfarer` you get the reference save panel (`SampleSavePanel`), the sample hero (`SampleHero`), the sample migration chain (`SampleMigrations`), and a real v1 save fixture (`wayfarer-v1.saveslot`). Drop the panel components into any scene of your own — a two-minute wiring job. Full detail: [The Wayfarer Sample]({{ site.baseurl }}/docs/wayfarer-sample/).

## 4. Load the v1 fixture

Load the shipped v1 fixture through the panel. It migrates to the current format through its registered steps — **coins-to-gold** (v1→v2), then **split-health** (v2→v3) — and the Migration Report names every step that ran. The v1 hero's data (gold 250, health 34 of 40, checkpoint cp_forest_01) arrives intact in the new format, and a pre-migration backup was taken before the first step ran. Full detail: [Migration Centre]({{ site.baseurl }}/docs/migration-centre/).

## 5. Break it on purpose

From **Save Health & Diagnostics**, run the bit-flip fault simulation on the slot, then load again. The save fails verification, SaveVault restores the last good backup, reports exactly what happened, and keeps the corrupt bytes in the named quarantine — the hero comes back from backup. Full detail: [Save Health & Diagnostics]({{ site.baseurl }}/docs/save-health-and-diagnostics/).

That loop — migrate, seal, break, recover — is the whole promise of the product, exercised with shipped materials only.

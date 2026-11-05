---
layout: default
title: FAQ
nav_order: 20
description: "Straight answers: supported Unity versions, what happens when a save corrupts or is tampered with, how far Steam Cloud verification goes, and what the Wayfarer sample actually ships."
---

# FAQ
{: .no_toc }

## Which Unity versions are supported?

**Unity 2022.3 LTS and Unity 6.** Both targets are verified: 45/45 EditMode tests green on each, in main and fresh projects, with clean-project install and first-run flow proven from shipped materials.

## What happens when a save corrupts?

The save fails verification, the **last good backup is restored**, and SaveVault reports exactly what happened. The corrupt bytes are preserved in a **named quarantine** — never silently deleted. See [Backups & Recovery]({{ site.baseurl }}/docs/backups-and-recovery/).

## What if a player hand-edits their save?

Saves are sealed with **HMAC-SHA256**. A tampered or hand-edited save is detected on load and recovered from backup, with the cause named in plain language. See [Integrity Sealing]({{ site.baseurl }}/docs/integrity-sealing/).

## Can a crash mid-save tear the file?

No. Every write follows **write-temp-verify-swap**: an interrupted write leaves the last good save untouched. See [Atomic Persistence]({{ site.baseurl }}/docs/atomic-persistence/).

## Is Steam Cloud proven live?

No — and the documentation never claims it is. The adapter is verified against the **mock** Remote Storage surface. A live test needs your own Steam partner App ID; the setup is documented step by step. See [Steam Cloud]({{ site.baseurl }}/docs/steam-cloud/).

## Does the sample include a scene?

No. `Samples~/Wayfarer` ships **code** (SampleHero, SampleSavePanel, SampleMigrations) plus a real **v1 save fixture**. The panel drops into any scene of your own in about two minutes. See [The Wayfarer Sample]({{ site.baseurl }}/docs/wayfarer-sample/).

## Does Sync Lab run my two devices against each other?

No. Sync Lab is a review surface — Device A/B roots, backend seed state, divergence review. Its divergence control writes an operation-log line; the actual merge machinery is the runtime sync manager. See [Sync Lab]({{ site.baseurl }}/docs/sync-lab/).

## Which sync backends ship?

A **local folder** backend, a **REST** backend, and the **Steam Cloud adapter** (mock-verified). Merges resolve at section and field level; conflicting copies are quarantined, not overwritten. See [Cloud Backends & Merge Resolution]({{ site.baseurl }}/docs/cloud-backends-and-merge/).

---
layout: default
title: Troubleshooting
nav_order: 21
description: "The states SaveVault reports about itself: a save restored from backup, a tamper detection, Steamworks.NET not detected, a slot listed as needing migration, and an orphaned temp file."
---

# Troubleshooting
{: .no_toc }

SaveVault's failure states are reported states — each one names what happened. These are the ones you will meet.

## "Save failed verification — restored from backup"

The slot's integrity check failed (corruption or tampering). The last good backup was restored as the live save, and the damaged bytes were moved to the **named quarantine** in [Save Health & Diagnostics]({{ site.baseurl }}/docs/save-health-and-diagnostics/) — inspect them there before anything else; nothing was deleted.

## "Tampered save detected"

The slot's HMAC-SHA256 seal did not verify: the file was edited outside the game. Recovery is the same path — backup restored, cause named, bytes quarantined. If the edit was yours (a deliberate test), re-run the flow through the **Tamper** fault simulation instead of editing live player saves. See [Integrity Sealing]({{ site.baseurl }}/docs/integrity-sealing/).

## Setup report says "Steamworks.NET not detected"

Your project does not contain the Steamworks.NET package, so the Steam Cloud adapter has nothing to integrate with and stays **mock-only** in this project. Add the package and re-run [one-click setup]({{ site.baseurl }}/docs/one-click-setup/); the probe line updates. This is a reported state, not an error — see [Steam Cloud]({{ site.baseurl }}/docs/steam-cloud/).

## A slot is listed as needing migration

Its stored version is below the section's current version. Nothing is broken: the slot migrates automatically on load, through its registered steps, with a pre-migration backup taken first. The [Migration Centre]({{ site.baseurl }}/docs/migration-centre/) shows the chain it will follow.

## An orphaned temp file sits beside a save

A write was interrupted (crash, power loss, killed process) between the temp write and the swap. The live save is the last good one, untouched — that is the [atomic protocol]({{ site.baseurl }}/docs/atomic-persistence/) working as designed. The temp file is inert and can be deleted.

## A save was quarantined after sync

The two sides of a sync genuinely conflicted, and SaveVault preserved the conflicting copies in quarantine instead of overwriting one with the other. Review both copies in [Save Health & Diagnostics]({{ site.baseurl }}/docs/save-health-and-diagnostics/) — the merge behaviour is described in [Cloud Backends & Merge Resolution]({{ site.baseurl }}/docs/cloud-backends-and-merge/).

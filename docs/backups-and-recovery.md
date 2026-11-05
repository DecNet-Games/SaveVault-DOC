---
layout: default
title: Backups & Recovery
nav_order: 12
description: "Rolling backups mean a corrupted save restores its last good state. The corrupt bytes go to a named quarantine — never silently deleted — and the recovery report says exactly what happened."
---

# Backups & Recovery
{: .no_toc }

Saves corrupt: disks fail, writes tear, players hand-edit files. SaveVault's answer is a standing recovery path, not a hope that it never happens.

## Rolling backups

SaveVault keeps **rolling backups** of your saves. When a save **fails verification** — a broken seal, a failed integrity check — the recovery is automatic:

1. The **last good backup is restored** as the live save.
2. SaveVault **reports exactly what happened**: which save failed, why it failed, and what was restored.
3. The **corrupt bytes are kept in a named quarantine** — never silently deleted. The evidence of what went wrong stays available for inspection in [Save Health & Diagnostics]({{ site.baseurl }}/docs/save-health-and-diagnostics/).

The shipped settings default keeps **5** backups in the rolling set (see [Settings]({{ site.baseurl }}/docs/settings/)), and the tamper policy ships as **Auto Recover With Quarantine**: recover first, keep the evidence, name the cause.

## Pre-migration backups

Recovery also guards change itself: before any migration chain runs on a load, a backup of the original save is taken (see [Versioned Schemas]({{ site.baseurl }}/docs/versioned-schemas/)). A format change can therefore never strand a player between versions.

## The player's experience

From the player's side, a corrupted save is a non-event: their last good progress loads, and the game continues. The named report and the quarantine are there for you, the developer — the player just never loses the game.

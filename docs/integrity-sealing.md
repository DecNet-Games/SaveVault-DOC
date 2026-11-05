---
layout: default
title: Integrity Sealing
nav_order: 11
description: "Saves are sealed with HMAC-SHA256. A tampered or hand-edited save is detected on load, recovered from backup, and the cause is named in plain language."
---

# Integrity Sealing
{: .no_toc }

Every save SaveVault writes is **sealed with HMAC-SHA256**. The seal is checked when the save loads — before any of its data is trusted.

## What the seal catches

- **Tampering** — a save edited to grant gold, unlock content, or change progress by hand.
- **Corruption that looks plausible** — bytes that changed without breaking the file's shape. Structural checks alone miss these; the seal does not.

## What happens on a failed seal

A tampered or hand-edited save is **detected on load and recovered from backup, with the cause named in plain language** — the load report tells you the save failed its integrity check instead of silently accepting edited data or silently discarding the slot. The offending bytes are preserved in the named quarantine (see [Backups & Recovery]({{ site.baseurl }}/docs/backups-and-recovery/)), so "the save was edited" is a provable statement, not a guess.

Each slot's current seal state is visible in [Storage Status]({{ site.baseurl }}/docs/storage-status/). The tamper case is also a one-click fault simulation: seal a save, tamper with it from [Save Health & Diagnostics]({{ site.baseurl }}/docs/save-health-and-diagnostics/), and load — detection and recovery are the shipped behaviour, not a promise.

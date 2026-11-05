---
layout: default
title: Settings
nav_order: 18
description: "SaveVault's shipped settings: backup retention 5, tamper policy Auto Recover With Quarantine, automatic sync trigger, 5-second autosave, 30-second sync throttle."
---

# Settings
{: .no_toc }

The Settings section of [SaveVault Home]({{ site.baseurl }}/docs/home-window/) carries the save system's standing behaviour. The shipped settings read:

| Setting | Shipped value | What it governs |
| --- | --- | --- |
| **Backup Retention** | 5 | How many rolling backups are kept per save (see [Backups & Recovery]({{ site.baseurl }}/docs/backups-and-recovery/)) |
| **Tamper Policy** | Auto Recover With Quarantine | A save that fails its integrity seal is recovered from backup, and the offending bytes are preserved in quarantine (see [Integrity Sealing]({{ site.baseurl }}/docs/integrity-sealing/)) |
| **Sync Trigger** | Automatic | Sync runs on its own schedule rather than waiting for a manual call |
| **Autosave** | 5 s | The autosave interval |
| **Sync Throttle** | 30 s | The minimum spacing between sync passes (see [Cloud Backends & Merge Resolution]({{ site.baseurl }}/docs/cloud-backends-and-merge/)) |

These values are the product's own shipped state, shown in the window exactly as the table above.

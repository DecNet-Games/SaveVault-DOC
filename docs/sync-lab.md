---
layout: default
title: Sync Lab
nav_order: 14
description: "Sync Lab is the two-device sync surface in SaveVault Home: Device A and Device B storage roots, the cloud backend's seed state, and divergence review. It is a review surface — not a simulation runner."
---

# Sync Lab
{: .no_toc }

Sync Lab, inside [SaveVault Home]({{ site.baseurl }}/docs/home-window/), is the surface for your two-device sync setup.

## What the surface shows

- **Device A and Device B storage roots** — the two local device roots (under `…\SaveVault\SyncLab\`) that stand in for the two ends of a player's sync relationship, so you can inspect what each side holds.
- **Cloud backend seed state** — whether the configured backend has been seeded (a fresh setup reads **Cloud Backend: Not Seeded**).
- **Divergence review** — the state of the two sides relative to each other, for reviewing how your local-first sync is configured before you trust your own backend with it.

## What Sync Lab is not — stated plainly

The surface's **Trigger Divergence Simulation** control writes an operation-log line. **It does not itself run a live merge simulation**, and this documentation does not describe it as one. The actual merge machinery lives in the runtime — the local-first sync manager, which resolves at section and field level and quarantines both sides of a true conflict — and that machinery is covered by SaveVault's automated test suite (45/45), not by this button. See [Cloud Backends & Merge Resolution]({{ site.baseurl }}/docs/cloud-backends-and-merge/).

Use Sync Lab to review roots, seed state, and divergence state. Judge the merge itself by the sync manager's behaviour and its test record.

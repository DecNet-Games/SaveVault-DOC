---
layout: default
title: Save Health & Diagnostics
nav_order: 13
description: "Backups, the quarantine, and one-click fault simulations — bit-flip, torn temp, tamper — so SaveVault's recovery path is testable before your players find it."
---

# Save Health & Diagnostics
{: .no_toc }

Save Health & Diagnostics, inside [SaveVault Home]({{ site.baseurl }}/docs/home-window/), is where the recovery machinery is inspected — and exercised.

## What it shows

- **Backups** — the rolling backup set behind each save (see [Backups & Recovery]({{ site.baseurl }}/docs/backups-and-recovery/)).
- **The quarantine** — the corrupt or tampered bytes SaveVault preserved instead of deleting, named per incident, so every recovery has inspectable evidence.

## Fault simulations

Recovery you have never tested is recovery you are hoping about. This section carries **one-click fault simulations** so the failure modes are testable on demand, before players find them:

- **Bit-flip** — flips bits in a stored save, producing realistic corruption.
- **Torn temp** — simulates an interrupted write, the case the [atomic protocol]({{ site.baseurl }}/docs/atomic-persistence/) exists for.
- **Tamper** — edits a save the way a player with a hex editor would, the case [integrity sealing]({{ site.baseurl }}/docs/integrity-sealing/) exists for.

Run the simulation, then load the slot: the failure is detected, the last good backup is restored, the report names the cause, and the damaged bytes land in quarantine. That loop is the [Quick Start's]({{ site.baseurl }}/docs/quick-start/) final step, and it is the honest way to evaluate a save system: break it yourself, on purpose, and watch.

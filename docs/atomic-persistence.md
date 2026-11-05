---
layout: default
title: Atomic Persistence
nav_order: 10
description: "Every SaveVault write follows a write-temp-verify-swap protocol, so a crash, power loss, or killed process mid-save cannot tear a file."
---

# Atomic Persistence
{: .no_toc }

The most dangerous moment in a save system's life is the write itself: a crash, a power cut, or a killed process halfway through leaves a half-old, half-new file that is neither. SaveVault's persistence protocol is built so that moment cannot produce a torn save.

## The protocol

Every write follows **write-temp-verify-swap**:

1. **Write temp** — the new save is written to a temporary file, beside the real one. The live save is not touched.
2. **Verify** — the temp file is checked: it must be complete and its integrity seal must verify.
3. **Swap** — only a verified temp replaces the live save.

An interrupted write therefore leaves **the last good save untouched**: worst case, the temp file is orphaned and the previous save is exactly as it was. The torn-temp case is one of the fault simulations in [Save Health & Diagnostics]({{ site.baseurl }}/docs/save-health-and-diagnostics/) — you can inflict it on purpose and watch the save survive.

Atomic writes pair with [rolling backups]({{ site.baseurl }}/docs/backups-and-recovery/): the protocol protects the current write; the backups protect everything else.

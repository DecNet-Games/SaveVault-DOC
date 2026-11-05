---
layout: default
title: One-Click Setup
nav_order: 6
description: "SaveVault's one-click setup creates and verifies the settings asset and test root, probes for Steamworks.NET, and reports every line of what it found."
---

# One-Click Setup
{: .no_toc }

Setup runs from the **Welcome** section of [SaveVault Home]({{ site.baseurl }}/docs/home-window/). It prepares the project for the save runtime and then proves its own work with a report — it does not ask you to take "done" on faith.

## What setup does

- Creates (or verifies) the settings asset at `Assets/SaveVault/SaveVaultSettings.asset`.
- Creates (or verifies) the test root used by the diagnostics and fault simulations.
- Probes for **Steamworks.NET**. If it is detected, the Steam Cloud adapter has its integration surface; if it is not, the report says so plainly and Steam Cloud remains mock-only in this project — setup never claims an integration that is not there.

## The setup report

A verified run reads, line by line:

- **Settings Asset:** `Assets/SaveVault/SaveVaultSettings.asset` (Verified existing)
- **Test Root:** `…\Library\SaveVaultTestRoot` (Verified)
- **Steam Cloud:** Steamworks.NET not detected *(in a project without the Steamworks.NET package)*
- **Status:** Ready for development and shipping

Setup is safe to re-run: verifying an existing, healthy state is its normal second-run outcome.

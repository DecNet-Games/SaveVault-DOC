---
layout: default
title: Steam Cloud
nav_order: 16
description: "The Steam Cloud adapter ships with SaveVault and is verified against the Steamworks Remote Storage mock surface. A live end-to-end test needs your own Steam partner App ID."
---

# Steam Cloud
{: .no_toc }

SaveVault ships a **Steam Cloud adapter** alongside its folder and REST backends. This page states exactly how far its verification goes — no further.

## The verified state

The adapter is **verified against the Steamworks Remote Storage mock surface**. That is the whole claim: the adapter's calls, shapes, and behaviour are proven against the mock surface, in the automated test record — **not** against live Steam.

## What a live test needs

A live end-to-end Steam test needs **your own Steam partner App ID** — Decnet Games cannot run it against your game's Steam configuration, and no live result is claimed or implied anywhere in this documentation. The setup for wiring the adapter to your App ID is documented step by step in the package's Steam Cloud setup guide.

## What the Editor tells you

[One-click setup]({{ site.baseurl }}/docs/one-click-setup/) probes for Steamworks.NET and reports what it found. In a project without the Steamworks.NET package, the setup report reads **Steam Cloud: Steamworks.NET not detected**, and Steam Cloud stays mock-only in that project until the package is present. SaveVault never presents the adapter as integrated when it is not.

## Before you ship on Steam

1. Add Steamworks.NET to the project and re-run setup — confirm the probe line changes.
2. Point the adapter at your own partner App ID, per the setup guide.
3. Run your own end-to-end test with a real save: write on one machine, sync, read on another, and exercise a conflict.
4. Only then treat Steam Cloud as live for your game — your test, on your App ID, is the verification that counts.

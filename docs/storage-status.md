---
layout: default
title: Storage Status
nav_order: 7
description: "Storage Status shows every save slot with its stored version and seal state — which saves exist, how old their format is, and whether each integrity seal verifies."
---

# Storage Status
{: .no_toc }

Storage Status is the slot ledger in [SaveVault Home]({{ site.baseurl }}/docs/home-window/): **every slot, with its version and seal state**.

## What each row tells you

- **Which saves exist** — the slots currently stored for your game.
- **The stored version** — the format version each slot was written at. A slot stored below the current version is a migration candidate: it will migrate automatically on load, and [Migration Centre]({{ site.baseurl }}/docs/migration-centre/) shows it as needing migration before that happens.
- **The seal state** — whether the slot's HMAC-SHA256 integrity seal verifies. A slot whose seal fails is not loaded as data; it goes through recovery from its last good backup, with the corrupt bytes preserved in quarantine. See [Integrity Sealing]({{ site.baseurl }}/docs/integrity-sealing/) and [Backups & Recovery]({{ site.baseurl }}/docs/backups-and-recovery/).

A fresh project with no saves yet shows an empty state — that is the correct first-run picture, not an error. Slots appear here as your game (or the [Wayfarer panel]({{ site.baseurl }}/docs/wayfarer-sample/)) writes them.

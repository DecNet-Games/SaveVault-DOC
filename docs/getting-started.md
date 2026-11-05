---
layout: default
title: Getting Started
nav_order: 2
description: "From the Asset Store download to a migrated, verified save: install SaveVault, run the one-click setup, and load the shipped v1 fixture through the Wayfarer panel."
---

# Getting Started
{: .no_toc }

SaveVault works in one Editor window and one loop: **set up** once, **save** through the versioned runtime, **migrate** old saves automatically on load, and **inspect** the health of every slot from the same window. This section takes you from the Asset Store download to a migrated, verified save.

## The path

1. [Install]({{ site.baseurl }}/docs/installation/) the package from the Unity Asset Store.
2. Follow the [Quick Start]({{ site.baseurl }}/docs/quick-start/): open SaveVault Home, run the one-click setup, and load the shipped v1 fixture through the Wayfarer panel.
3. Learn the one window in [The Home Window]({{ site.baseurl }}/docs/home-window/).

## What SaveVault needs from you

- A Unity project on **2022.3 LTS** or **Unity 6** — both targets are verified with clean-project installs.
- Nothing else. The save runtime is platform-agnostic C#; cloud sync ships with local-folder and REST backends, and the Steam Cloud adapter is there when you bring your own Steam partner App ID (see [Steam Cloud]({{ site.baseurl }}/docs/steam-cloud/)).

## The honest frame, up front

SaveVault keeps your save data safe: versioned, migrated, sealed, backed up, and merged without losing either side. It is not a leaderboard, achievement, or networking system. Two limits are stated everywhere they matter: the Steam Cloud adapter is verified against the **mock** Remote Storage surface only, and Sync Lab is a review surface — its divergence control writes an operation-log line and does not itself run a merge. The full list is [What v1 Is Not]({{ site.baseurl }}/docs/what-v1-is-not/).

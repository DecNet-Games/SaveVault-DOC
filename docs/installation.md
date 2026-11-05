---
layout: default
title: Installation
nav_order: 3
description: "Install SaveVault from the Unity Asset Store and run the one-click setup. SaveVault is sold exclusively through the Unity Asset Store."
---

# Installation
{: .no_toc }

## Asset Store only
{: .no_toc .text-delta }

SaveVault is sold and delivered **exclusively through the Unity Asset Store** (publisher: Decnet Games). There is no other download channel, no licence server, and no account to create — if a copy of SaveVault came from anywhere else, it did not come from us.

## Install

1. Purchase SaveVault on the Unity Asset Store.
2. In Unity, open **Window → Package Manager**, select **My Assets**, download and import SaveVault into your project.
3. Open the window from **Tools → Decnet Games → SaveVault**. Everything SaveVault does in the Editor lives in that one home window — see [The Home Window]({{ site.baseurl }}/docs/home-window/).
4. Run the [one-click setup]({{ site.baseurl }}/docs/one-click-setup/) once. The setup report names what it verified — settings asset, test root, and whether Steamworks.NET was detected — before you rely on any of it.

## Requirements

- Unity **2022.3 LTS** or **Unity 6**.
- Editor tooling for Windows and macOS projects; the runtime save system is platform-agnostic C#.
- For the Steam Cloud adapter only: your own Steam partner App ID for a live end-to-end test. The adapter itself is verified against the mock Remote Storage surface — see [Steam Cloud]({{ site.baseurl }}/docs/steam-cloud/).

## Verified state

Automated verification for v1.0.0: **45/45 EditMode tests green on Unity 6 and on Unity 2022.3 LTS**, in main and fresh projects; clean-project install and first-run flow proven on both targets from shipped materials. Steam Cloud surfaces are mock-verified only — see [What v1 Is Not]({{ site.baseurl }}/docs/what-v1-is-not/).

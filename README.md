# NodeForge — releases

Release artifacts and the **auto-update feed** for NodeForge Desktop.

> ⚠️ **This repository holds binaries, not source.** The application source is developed privately and is
> not hosted here. Nothing in this repository is meant to be read as code.

## What is here

Each release attaches the artifacts the desktop app's updater reads:

| file | what it is |
| --- | --- |
| `NodeForge Setup <version>.exe` | the Windows installer |
| `NodeForge Setup <version>.exe.blockmap` | lets the updater fetch only the bytes that changed, instead of the whole installer |
| `latest.yml` | the manifest the app polls — version, file name, size, and a `sha512` checksum |

## How the app finds updates

The installed app has this repository baked into its update feed **at build time**. On launch it asks GitHub
for the newest release, compares that version to its own, and downloads in the background if there is a newer
one. It installs **on quit** — never mid-render, and never forcing a restart.

A feed URL change is therefore a rebuild, not a setting. If the feed ever moves, one release has to be
published to both the old and the new location so that already-installed clients can find the way across.

## Installing

Download the newest `NodeForge Setup *.exe` from [Releases](../../releases/latest).

The installer is **per-user** — it installs to `%LOCALAPPDATA%\Programs\NodeForge` and does not need
administrator rights or a UAC prompt.

> ⚠️ **The build is not code-signed yet.** Windows SmartScreen will warn that the publisher is unknown.
> Choose **More info → Run anyway**. Signing is planned; until then this warning is expected and not a sign
> that anything is wrong.

## ffmpeg is required for video features, and is not bundled

NodeForge shells out to `ffmpeg` for video work. It is deliberately not included in the installer, which
keeps the download near 100 MB instead of 300 MB+.

- **The canvas, node graph, and project management work without it.**
- **Video export, probing and the video editor's render path do not.**

A first-run check that detects this and tells you what to install is planned but **not built yet** — so
right now a missing ffmpeg shows up as a video feature failing, with no explanation from the app. That is a
known gap, not a bug in your install.

## Uninstalling

Uninstalling leaves your projects and settings in place under `%APPDATA%\nodeforge`. That is deliberate —
an uninstall should never cost you work. Remove that folder by hand if you want a clean slate.

## Verifying a download

Each `latest.yml` carries the `sha512` of the installer it describes. To check a download yourself:

```bash
certutil -hashfile "NodeForge Setup 0.1.0.exe" SHA512
```

The updater performs this check automatically and will refuse an installer whose hash does not match.

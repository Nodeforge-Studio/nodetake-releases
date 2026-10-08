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

## Installing

Download the newest `NodeForge Setup *.exe` from [Releases](../../releases/latest) and run it.

**The installer asks where to put it.** It runs a normal wizard with a folder page — pick anywhere you like.
The default is `%LOCALAPPDATA%\Programs\NodeForge`, and the install is **per-user**, so it needs no
administrator rights and shows no UAC prompt.

> ⚠️ **The build is not code-signed yet.** Windows SmartScreen will warn that the publisher is unknown.
> Choose **More info → Run anyway**. Signing is planned; until then this warning is expected and is not a
> sign that anything is wrong.

## How the app finds updates

The installed app has this repository baked into its update feed **at build time**. On launch it asks GitHub
for the newest release, compares that version to its own, and downloads in the background if there is a newer
one. It installs **on quit** — never mid-render, and never forcing a restart.

A feed URL change is therefore a rebuild, not a setting. If the feed ever moves, one release has to be
published to both the old and the new location so that already-installed clients can find the way across.

### Updating by hand

If you were **sent an installer file** rather than using the feed, you do not need to reinstall over the top
of it. Open the launcher → **Updates**, and either

- **drag** the `NodeForge Setup ….exe` onto the panel, or
- **paste its full path** into the box (or click **Browse…**)

The app checks the file first and tells you whether it is newer than what you have — it has to be one of
ours, so a stray download cannot be run by accident. This route needs no internet access at all.

## ffmpeg is required for video features, and is not bundled

NodeForge shells out to `ffmpeg` for video work. It is deliberately not included in the installer, which
keeps the download near 100 MB instead of 300 MB+.

- **The canvas, node graph, and project management work without it.**
- **Video export, probing and the video editor's render path do not.**

The launcher checks for it on first run and, when it is missing, offers to **download and install it** — with
progress, pause and stop — so you do not have to find it yourself. **Media tools** is its own tab in the
launcher, and it carries a "needs setup" badge while ffmpeg is absent.

If you would rather install it yourself, that button is there too; NodeForge will use an `ffmpeg` already on
your `PATH`.

## Uninstalling

Uninstalling leaves your projects and settings in place under `%APPDATA%\NodeForge`. That is deliberate —
an uninstall should never cost you work. Remove that folder by hand if you want a clean slate.

## Verifying a download

Each `latest.yml` carries the `sha512` of the installer it describes. To check a download yourself:

```bash
certutil -hashfile "NodeForge Setup 0.1.3.exe" SHA512
```

The updater performs this check automatically and will refuse an installer whose hash does not match.

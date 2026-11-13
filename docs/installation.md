# Install and update NodeTake

[User guide](user-guide.md) · [Troubleshooting](troubleshooting.md)

## Choose the right download

Use the [official Windows releases](https://github.com/Nodeforge-Studio/nodetake-releases/releases). The source repository is private; the public repository contains downloads and user documentation.

**Release transition:** the published v0.1.3 installer is the earlier **NodeForge** build. Its executable and update files retain their original names. The current source uses NodeTake branding; a new branded installer has not yet been published. Check the release notes and attached files before downloading.

**NodeTake** is the family. **NodeTake Launcher** handles startup, setup, and updates. **NodeTake Studio** is the canvas. **NodeTake Extension** connects supported websites in your Chrome profiles. Provider subscriptions, credits, external services, and optional models are separate.

## Install on Windows

1. Download the installer attached to your chosen release, rather than the repository's source ZIP.
2. Finish active jobs and exit the app before upgrading.
3. Run the installer and follow its folder-selection wizard. Keep the existing installation folder when upgrading.
4. Open the app. Current NodeTake builds use the Launcher for setup. Review the data directory, enter your activation key when required, and choose **Launch NodeTake Studio**.

An unsigned build may trigger an unknown-publisher warning. Verify its origin and release information before deciding whether to run it. A checksum confirms a file matches a manifest; it does not establish publisher identity.

## Set up media tools

Open **Launcher → Media tools** to check FFmpeg and use the offered setup controls. Many video/audio operations require FFmpeg; the canvas can open without it. Optional web imports may need `yt-dlp`. Local GPU/model tools have separate runtimes, hardware requirements, and downloads.

## Connect a Chrome profile

1. Start NodeTake so its local server is running.
2. In Studio, use **Accounts → Connect your browser** to locate the extension. Installed builds keep it in `resources/chrome-extension` under the installation folder.
3. In your chosen Chrome profile, open `chrome://extensions`, enable **Developer mode**, choose **Load unpacked**, and select that folder.
4. Open **NodeTake Extension**, enter an account/profile label, choose **Save**, then **Sync session**. Confirm its server status is online.
5. Sign in to the provider in that same profile. Repeat setup for each Chrome profile you intend to use.

The local API normally starts on port 3002, but the Launcher can use another port and startup can choose an available one. The extension reads the app's connection information. Keep its installation folder in place. Reload the extension after an app update if needed, after jobs have finished.

## Updates

Open **Updates** in the Launcher. Current NodeTake builds check for updates and let you choose to download; they do not automatically download every available update. Finish or stop active work before installing and restarting.

For a manual update, download a trusted full installer and use the Launcher's installer picker, or exit the app and run the installer directly. Current source accepts `NodeTake Setup <version>.exe` and legacy `NodeForge Setup <version>.exe` in the picker. Older builds may recognize only NodeForge. GitHub asset names can contain hyphens; run the official installer directly if the picker rejects its filename. Do not rename unrelated executables to bypass validation.

Older public binaries may retain the previous repository address. GitHub redirects renamed repositories; current source targets `Nodeforge-Studio/nodetake-releases`.

## Backups and offline help

The Windows application profile intentionally stays at `%APPDATA%\nodeforge` for compatibility. Project/data directories hold additional media and files. With the app closed, back up **both** the profile and those directories. Keep credentials, sessions, and encryption keys private. Encrypted credentials may not be portable to another Windows account.

New source-built installers include an offline manual at `resources/documentation/index.html` inside the installation folder. Older published NodeForge installers do not include this new manual.

# NodeTake — Windows releases and user guides

![NodeTake](assets/nodetake.png)

NodeTake is a visual workspace for AI media creation, editing, and automation. **NodeTake Studio** is the canvas, **NodeTake Launcher** manages startup/setup, and **NodeTake Extension** connects supported websites through Chrome profiles.

[Windows downloads](https://github.com/Nodeforge-Studio/nodetake-releases/releases) · [Installation](docs/installation.md) · [User guide](docs/user-guide.md) · [Troubleshooting](docs/troubleshooting.md)

## Release transition

**v0.2.0** is the first installer published under the NodeTake name — the earlier **v0.1.3** release kept the NodeForge name and artwork. Installing 0.2.0 over an existing 0.1.x install updates it in place: the install identity and the `%APPDATA%\nodeforge` profile are unchanged, so projects, settings and accounts carry over. These manuals describe current NodeTake.

## Downloads and setup

This repository contains public installers and documentation, not private application source. Releases attach an installer, `.blockmap`, and `latest.yml` for the updater. The v0.1.3 assets keep their NodeForge filenames; v0.2.0 and later are named NodeTake. Use the attached executable, not GitHub's source ZIP.

Follow the installer's folder wizard. Current NodeTake uses the Launcher for setup/activation before Studio. Browser providers use the [extension](chrome-extension/README.md) in each chosen Chrome profile. FFmpeg, optional runtimes/models, provider accounts, and credits have separate requirements.

Current NodeTake lets you choose to download updates from **Launcher → Updates**. Finish jobs before installing/restarting. The compatibility profile remains `%APPDATA%\nodeforge`; back up it and project/data directories.

New source-built installers include an offline manual at `resources/documentation/index.html`. The older public NodeForge v0.1.3 installer does not; read the linked manuals here.

## Safety and support

Download from official release pages. Unsigned builds may show unknown-publisher warnings; verify origin before running. Never share activation/API keys, cookies, or unredacted sessions. See [troubleshooting](docs/troubleshooting.md).

The historical organization spelling `Nodeforge-Studio` remains in the URL. The product family is **NodeTake**.

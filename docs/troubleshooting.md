# NodeTake troubleshooting

[Installation](installation.md) · [User guide](user-guide.md)

## Studio will not launch

Check activation and setup messages in NodeTake Launcher. Confirm the selected data directory is available and writable. Close an existing instance before opening another. Record the exact error and app version; do not delete the profile as a first troubleshooting step.

## Extension offline or wrong account

Start the app and wait for its local server. Load the extension from the current installation's `resources/chrome-extension` folder, not an old copy. Check Chrome can read the folder and the app can write its connection information. The server may use a port other than 3002. Reload the extension after port/installation changes once jobs have stopped.

Sign in to the provider in the same Chrome profile. Save a recognizable account label and choose **Sync session**. Check Studio's selected account. Switching profiles does not transfer a signed-in session.

**Probe Flow editor**, **Test generation**, and **Test title update** are optional diagnostics. A generation test may consume credits; title-update tests may change provider content.

## Generation stalls or fails

Check the provider page for sign-in requests, account limits, and errors. Website changes may require an app/extension update. API jobs need valid credentials, available credits, and supported model parameters.

Check whether the provider accepted or completed a job before retrying it. Another run can spend credits twice. Use a recovery action only when offered for that job; inspect unresolved provider work instead of repeatedly clicking Run.

## Video/audio fails

Check FFmpeg in **Launcher → Media tools**, finish setup, and retry a short clip. Confirm source files exist and output/cache destinations have enough free space. Some codecs need conversion. Optional web imports need a supported downloader and an accessible, non-DRM source you are allowed to use.

For local GPU tools, check the separate runtime/model setup and memory available. Start with a shorter clip and lower resolution. VoiceStudio must run separately at its configured service address; NodeTake does not install all its models.

## Update fails

Check the [official releases](https://github.com/Nodeforge-Studio/nodetake-releases/releases) for the actual published version. Public v0.1.3 files still use NodeForge branding; new source branding is not a new binary release.

Finish work, close the app, and use the trusted full installer if an older manual picker rejects its filename. Keep the existing installation folder. Do not hand-edit or mix `latest.yml`, blockmaps, and installers from different releases.

## Missing work or media

Open the correct project and selected data directory. Restore moved source files or reconnect them through project controls. The profile remains `%APPDATA%\nodeforge`. Back up it and the project/data folders before recovery. Reinstalling is not a recovery mechanism for deleted projects. Avoid deleting databases, profile keys, or caches while diagnosing missing state.

## Report a problem

Include the version, installed release versus source build, operation/node/provider, exact error, and short reproduction with non-sensitive media. Remove API keys, activation keys, cookies, session tokens, private account details, and personal filesystem paths from screenshots and logs.

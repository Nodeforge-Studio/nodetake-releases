# NodeTake Extension

The Chrome bridge for Google Labs / Flow, ChatGPT, Dola, and RunningHub in NodeTake Studio. API-only providers do not need it.

## Setup

Follow the [installation guide](../docs/installation.md#connect-a-chrome-profile). Installed users load `resources/chrome-extension` from the installation directory; source developers load this directory. Keep NodeTake running. Install the extension separately in each intended Chrome profile.

Open the popup, enter an account/profile label, choose **Save**, then **Sync session**. Confirm the server is online and Studio uses the intended account. The server normally starts on port 3002, but `port.json` supplies its actual connection information. Do not assume a fixed port or edit that generated file as a setup step.

## Popup controls

| Control | Purpose |
| --- | --- |
| Save | Save a recognizable profile/account label |
| Sync session | Synchronize a supported provider session with the local app |
| Probe Flow editor | Inspect the active editor for diagnostics |
| Test generation | Run a diagnostic generation; credits may be consumed |
| Test title update | Diagnose title updates; provider content may change |

Tests are optional diagnostics, not installation requirements. Sign in on the provider website in the same profile. Reload the extension after updating the app if needed, once jobs have finished.

## Permissions and privacy

The bridge interacts with supported websites and the local server, including session/cookie access used by supported integrations. Treat session exports, the application profile, and logs as sensitive. Review `manifest.json` for the exact host/browser permissions of your installed version. Never publish cookies or credentials in reports.

## Troubleshooting

Check the app is running and the extension belongs to the current installation. Its connection information must be writable by the app. For a wrong account, choose the intended Chrome profile, save its label, sync again, and check Studio's account selection. Website changes may require an update. See [troubleshooting](../docs/troubleshooting.md).

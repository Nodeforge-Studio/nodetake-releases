# NodeTake Studio user guide

[Installation and updates](installation.md) · [Troubleshooting](troubleshooting.md)

NodeTake Studio connects media creation and automation steps on a visual canvas. NodeTake Launcher manages startup and setup; NodeTake Extension connects supported websites in signed-in Chrome profiles.

## Build your first workflow

1. Open Studio and select or create a project in a folder you can keep backed up.
2. Add a text or file input, followed by the generation or processing node you need.
3. Connect its output socket to a compatible input socket. Connections carry typed data; text does not automatically become an image.
4. Configure the destination node, select the provider/account where required, and run a small test.
5. Preview the result, then connect an Output node or editing step. Confirm where the result was saved before clearing temporary files.

Example: **Text Input + File Input → generation node → Image Edit or Video Edit → Output**. Start with one item before adding loops or publishing. A provider request can consume credits even when its result is unsuitable.

## Organize and automate

Use workflow tabs, groups, templates, and reusable subnets to organize work. Inputs supply text, files, collections, recorded audio, or imported media. Processing nodes transform inputs; Output nodes save results. Inspect required inputs and reconnect sockets when changing a node's role.

Control nodes include ForEach, loops, sequence/switch tools, Parallel, Wait, Gather, Randomizer, and Media Batch. Test the item count and account selection before running a batch of paid requests. Scheduled and browser jobs depend on the app and required services remaining available.

## Generate media

Browser-connected providers include Google Labs / Flow, ChatGPT, Dola, and RunningHub. Sign in through your Chrome profile and sync its session with NodeTake Extension. Browser automation depends on the provider's website and your account permissions.

API integrations include RunningHub OpenAPI, MiniMax, and ElevenLabs. Configure the relevant credentials before running. Models differ in accepted inputs, reference counts, duration, and resolution; use the selected node's controls rather than assuming all providers behave alike.

Review outputs before approving them. Check provider and run status before retrying a slow job: another run can submit a second paid request.

## Edit and process

Use **Image Edit** and **Image Canvas** for image work. **Video Edit** provides tracks, keyframes, captions, effects, curves, and audio controls. Dedicated nodes cover crop, trim, speed, rotate, split, frame/audio extraction, optimization, and comparison.

Many video/audio operations require FFmpeg. Large sources also need space for proxies, thumbnails, caches, and outputs. Keep original media until exports are checked. Moving linked source files can break a project.

The **3D Scene** workspace supports model import, scene layout, cameras, animation, motion paths, and still rendering. Check model assets and textures after moving a project.

Local enhancement and voice tools are optional. SeedVR2.5 uses a separate Python/model runtime and can require substantial GPU memory. VoiceStudio connects to a separately installed service and models. These dependencies are not all bundled with the installer.

## Plan a production

Production tools organize documents into scenes and shots, with references, takes, continuity, and assembly. The **Project Bible** stores reusable entities such as characters, locations, props, voices, styles, and provider-specific Google Labs characters. Approve references and choose appropriate variants for each shot.

A reusable entity's canonical appearance and a shot's continuity state serve different purposes. Review shot context and generated takes before approval or assembly. A saved plan does not mean every media job is complete.

## Publish

Publishing integrations include Facebook Pages, Instagram, TikTok, and Zernio-connected destinations. Available actions depend on connected accounts, permissions, and provider support. Check the target account, media, caption, and timing before submission. Use the posting calendar and status history to confirm results; a queued item is not proof of publication.

## Save and recover

Keep project files and media together. Runtime state, encrypted credentials, and logs also live in the compatibility profile `%APPDATA%\nodeforge`. Back up both the profile and your project/data directories with the app closed.

After an interruption, inspect run history and provider status before retrying. Some browser jobs can reconnect or resume; not every operation is safely resumable. A missing local preview does not prove the provider did no work. See [Troubleshooting](troubleshooting.md).

## Current limits

NodeTake is pre-1.0 software. Websites and APIs can change, and model availability and limits come from providers. **AI Access** in current Settings is disabled, so external-agent instructions are technical reference rather than a normal setup flow. Browser interface mode is not a standard exposed Launcher choice in this build.

Keep API keys, activation keys, session data, and private media out of public reports. The installer does not include provider subscriptions or grant rights to uploaded media.

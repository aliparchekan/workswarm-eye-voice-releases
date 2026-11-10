# WorkSwarm Eye tracking and voice

Experimental first release: plugin **1.0.4**, native helper **1.0.3**. Published by **aliparchekan**, with project code licensed under **Apache-2.0**.

Look at a window, say “WorkSwarm,” wait for the Ready tone, and speak your request. A plugin-owned helper handles calibration and sensors. Requests and replies appear in your selected WorkSwarm chat. WorkSwarm itself is unchanged.

## Install

1. Download `workswarm-eye-voice-1.0.4-marketplace.zip` from [v1.0.4](https://github.com/aliparchekan/workswarm-eye-voice-releases/releases/tag/v1.0.4).
2. Import the ZIP through WorkSwarm’s plugin manager and enable **Eye tracking and voice** in your chat.
3. Send **Start eye tracking and show the controls**. The plugin automatically downloads and verifies its approximately 168 MB companion helper on first use.
4. Follow [SETUP.md](SETUP.md) for permissions, window confirmation, session calibration and voice.

Requires Apple-silicon macOS, unchanged WorkSwarm 0.2.8 on the same Mac, English Safari or Chrome, camera/microphone, and a vision-capable WorkSwarm model. Use your host’s actual URL/port; no fixed port is required. Test a typed model request first.

## Release status

The small package passes the official WorkSwarm publisher and isolated import/install/uninstall checks. Automated verification: 801 Python and 78 JavaScript tests passed. Both published ZIPs downloaded without GitHub credentials. The helper passed real signature/install/cache checks; the marketplace ZIP passed the actual isolated host import/install/uninstall. See [verification receipts](verification/verification.json).

Marketplace v1.0.4 was successfully submitted on November 10 and is **under review**. Public listing follows marketplace approval. Teammates can import the GitHub release for testing. [Submission receipt](verification/marketplace-submission.json)

This is an experimental release. The helper is **ad-hoc signed and not notarized**. Speech can misrecognize words. Fresh-Mac public-installation and physical gaze/voice acceptance remain unverified. Follow your organization’s software policy; do not disable Gatekeeper globally.

## Privacy and distribution

Camera frames, raw speech and calibration stay local. Recognized requests and selected-window content go to the model configured in WorkSwarm. Sensors start only through explicit helper controls. Existing drafts and attachments block delivery. Stop ends the tracking session and clears calibration.

This repository contains public release documentation and artifacts, not private development history, credentials, recordings or user calibration. [LICENSE](LICENSE) covers project code; [NOTICE](NOTICE) and [third-party notices](release-notices/README.md) retain upstream terms. The notice inventory is not a legal opinion.

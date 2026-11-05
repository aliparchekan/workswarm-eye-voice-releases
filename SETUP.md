# Eye tracking and voice

Look at a window and speak a request to WorkSwarm. The helper provides local calibration and sensors; requests and replies stay in your explicitly selected WorkSwarm chat.

## Requirements

Apple-silicon macOS, unchanged WorkSwarm 0.2.8 on this Mac, an English Safari or Chrome chat window, camera, microphone, internet for initial setup, and a vision-capable model configured in WorkSwarm. Test an ordinary typed question first. Use the URL printed by your WorkSwarm host; no particular frontend port is required. Native desktop WorkSwarm and other versions/platforms are not yet verified.

## First use

1. Install this plugin in WorkSwarm and enable **Eye tracking and voice** in the intended chat.
2. Send **Start eye tracking and show the controls**. On first use, the plugin downloads the pinned 168 MB helper, verifies the archive and app signature, and installs it in a private versioned folder in your user Library. Allow several minutes for this first download. Subsequent starts use the verified local copy. No provider key, separate speech model or terminal helper-install command is required.
3. In the helper, choose **Allow Accessibility** and **Allow screen access**. Drag the app card into the Settings list if needed and enable its switch. macOS consent and any authentication are yours to complete. Restart the helper before calibration if macOS requests it.
4. Choose **Find application**, select your WorkSwarm app/window and **Connect voice to this window**.
5. **Start camera → Full calibration · 14 dots**, then complete the accuracy check. Choose **Enable voice** and approve Microphone/Speech Recognition if asked.
6. Look at visible content until its yellow outline is stable. Say **WorkSwarm**, wait for Ready and the tone, then speak your request. Leave the keyboard/mouse idle while the request is entered. Inspect the recognized text and the reply in WorkSwarm.

Calibration lasts for one tracking session across chats. To change the destination, ask **Use voice here** in the new chat and confirm its window. **Mute** stops voice; **Stop** stops both sensors and clears calibration. Closing the helper controls only hides them. Existing drafts, attachments, busy chats or uncertain input stop delivery; the plugin does not overwrite them or automatically resend.

## Permissions and data

Camera frames, raw speech and calibration stay local. Recognized requests and the selected window's content reach the model you configure in WorkSwarm. Accessibility is used for exact chat/window inspection and input; screen access is used for the selected-window image, not system audio. Setup and status checks never activate sensors. Normal WorkSwarm tool approvals apply to action requests.

## Installation failures and removal

A download error, wrong checksum, wrong helper identity or unsafe installation path prevents launch. Retry Start after an interrupted download. An existing helper that fails verification is preserved, not replaced silently. If the error says the release is unavailable, the publisher must fix download availability; do not supply GitHub credentials to this plugin. The helper is currently ad-hoc signed, not notarized; follow your organization's macOS software policy if it is blocked. Never disable Gatekeeper globally.

Disable/uninstall the plugin through WorkSwarm after pressing Stop and quitting the helper. The separately cached helper remains under `~/Library/Application Support/WorkSwarm Eye Voice/helpers/1.0.3/`; removing the plugin does not delete it or WorkSwarm chats. Quit the helper before deleting its cached app if complete removal is wanted.

Initial experimental release. Speech may misrecognize words, and fresh-Mac/public-distribution reliability is not established. Screenshots require a vision-capable model. English Safari and Chrome have local delivery checks; other clients/locales are unverified. No demo recording, user profile, credentials or saved calibration is included.

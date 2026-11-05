# Proposed WorkSwarm listing

**Name:** Eye tracking and voice  
**Package ID:** workswarm-eye-voice  
**Version:** 1.0.4  
**Category:** Others  
**Suggested tags:** Eye tracking, Local voice, Accessibility

## Short description

Look at a window and speak to WorkSwarm. Calibrate locally, confirm your chat once, and send voice requests with the selected window as context.

## Description

Eye tracking and voice adds camera-based gaze selection and optional on-device English speech input to WorkSwarm. A small helper handles calibration, permissions and sensors. Requests and replies stay in your selected WorkSwarm chat.

On first Start, the plugin downloads and verifies the native helper automatically. Start from WorkSwarm, follow the permission guide, connect the chat window, and complete the 14-dot calibration and accuracy check. Enable voice, look at the content you want to reference, say “WorkSwarm,” wait for the Ready tone, and speak your request. Your words become normal WorkSwarm input with gaze context, using WorkSwarm's usual tools and approval rules.

Calibration lasts for one tracking session across chats. Stop ends tracking and clears calibration; Mute turns off voice while keeping calibrated gaze available. The plugin refuses to overwrite an existing draft or attachment and stops if it cannot verify the destination or inserted request.

## Permissions and data

- Camera: local gaze estimation and calibration after Start camera.
- Microphone and Speech Recognition: on-device speech after Enable voice.
- Accessibility: inspect the chosen chat/window and enter the request.
- Screen access: read the exact selected window; no system audio recording is used.

Camera frames, raw speech and calibration stay local. Recognized requests and selected-window content reach the model configured in WorkSwarm. No model account, provider key or speech-model download is supplied. macOS approvals remain the user's action.

## Compatibility and limitations

Apple-silicon macOS only; tested with unchanged WorkSwarm 0.2.8 in English Safari and Chrome. A local host and vision-capable model are required. One explicit chat/window confirmation is required. Keep its composer empty and avoid typing during delivery. Speech can misrecognize words; inspect the transcript. Calibration is session-based and must be repeated after Stop or a changed setup. This is an initial experimental release, not an accessibility reliability guarantee.

## Publisher and license

Publisher: aliparchekan. Project code: Apache-2.0. Upstream notices accompany the package and helper. The helper remains ad-hoc signed and not notarized.

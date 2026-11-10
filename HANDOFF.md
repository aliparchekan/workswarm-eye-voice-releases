# WorkSwarm Eye tracking and voice · v1.0.4 handoff

November 6, 2026 · Experimental release · Publisher: aliparchekan · Apache-2.0

**Ready for teammate testing.** A user can look at a window, say “WorkSwarm,” wait for the tone, and speak a free-form request. The request and reply appear in the WorkSwarm chat they connected. The next milestone is a complete run from the public release on a second Apple-silicon Mac, including two consecutive voice turns.

## What shipped

WorkSwarm loads the plugin into the chosen chat. On first Start, the plugin downloads and verifies the 168 MB macOS helper (v1.0.3). The helper handles permissions, calibration, gaze and local speech recognition. When the user speaks, the plugin uses computer controls to enter the recognized request and selected-window context through the confirmed chat’s composer. The WorkSwarm model answers there. A draft, attachment, busy chat or uncertain destination stops delivery.

The test team verified that both public downloads work without GitHub credentials, the plugin imports, installs and uninstalls through WorkSwarm 0.2.8, and a second helper start uses the cached copy. The recorded suites passed 801 Python and 78 JavaScript tests. In the earlier Safari pilot, the tester confirmed that spoken requests and replies appeared automatically. The new public-package check covered download and installation. A physical run starting from that public ZIP is still open. [Verification records](verification/verification.json)

## Run the acceptance check

1. **Start from the release ZIP.** On an Apple-silicon Mac, open the browser version of WorkSwarm 0.2.8 in English Safari or Chrome at the URL printed by that host. Verify a typed question gets a reply and a vision-capable model is configured. Import `workswarm-eye-voice-1.0.4-marketplace.zip`, enable **Eye tracking and voice** in the test chat, and send **Start eye tracking and show the controls**. The plugin downloads the helper automatically. [Release downloads](https://github.com/aliparchekan/workswarm-eye-voice-releases/releases/tag/v1.0.4) · [Setup and permissions](SETUP.md)
2. **Connect the destination.** Grant the requested Accessibility and screen permissions. Use **Find application** and **Connect voice to this window** to confirm the browser window containing that chat. Start the camera, complete the 14-dot calibration and accuracy check, then **Enable voice**. Expect **Listening locally**. Calibration lasts for this tracking session across chats.
3. **Test two consecutive turns.** Put a harmless note in TextEdit containing “Lantern meeting: Tuesday at 10. Bring the prototype.” Look at the note until its yellow outline is steady. Say **WorkSwarm**, wait for Ready and the tone, then say **What day is the Lantern meeting?** After the reply, look at the note again and repeat the wake sequence with **What should I bring?** Keep the keyboard idle. Both requests should be sent once and both replies should appear live in the original chat without a refresh or manual Send. Expected answers are Tuesday and the prototype. Record wake-tone audibility separately from recognition and sending.
4. **Check draft protection and Stop.** Type a disposable draft in the same composer and attempt another spoken request. The draft should stay intact and unsent. Clear your test draft yourself, then press **Stop** in the helper. Check that tracking and listening end. A new tracking session requires calibration again.

## If a step fails

Report the first failing step, macOS version, chip, browser/version, WorkSwarm version and host port. For voice, include the intended words, recognized words, whether Ready appeared, whether the tone sounded, which window was outlined, the helper’s exact status, and what appeared in the chat. Distinguish an empty composer, text left unsent, a sent turn without a reply, and a reply visible only after refresh. Report turn one and turn two separately. If text stays unsent, capture its state before clearing or sending it. Use only the harmless test note in screenshots.

## Release follow-up

- **Tester** — Return the two-turn result, draft-protection result and Stop result from the fresh installation. If a typed request already fails, record that as a WorkSwarm model/setup issue before testing gaze.
- **Release owner** — Distribute the GitHub ZIP for testing. Version 1.0.4 was successfully uploaded on November 10 and is under review. Check the publisher Profile for the review outcome. [Submission receipt](verification/marketplace-submission.json) [Listing copy](LISTING.md) · [Agentic Hub sign-in](https://agentichub.openjiuwen.com/login)
- **macOS distribution** — The helper uses an ad-hoc signature and lacks Apple notarization. If the tester’s Mac blocks launch, record the exact message and follow the organization’s software policy.

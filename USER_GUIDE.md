# Hermes Hub — JLabs

A local PC-care console with Windows Defender and Firewall integration, hardware observations, an optional local AI assistant, reports and developer-focused controls.

## Preview requirements

Windows 10 (build 19041 or later) or Windows 11 on an Intel/AMD x64 PC, without a PC-brand restriction. Use a Windows edition still receiving applicable Microsoft security updates. This package does not support 32-bit Windows or native ARM64. Runtime components are included. Hardware sensors depend on available firmware/providers; optional capabilities may be unavailable. No NPU acceleration is promised. Ollama and AI models are optional downloads, not bundled. Windows 11 has been tested locally; Windows 10 and other PC models still need clean-machine validation.

## Install

Run **Hermes Hub Installation x64.exe**. Choose a dedicated application folder, or keep the default Program Files / JLabs / Hermes Hub. Windows requests administrator approval and preserves your folder choice. A Start shortcut is created; the desktop shortcut is optional. Repair uses the registered folder. To move an existing installation, uninstall it first and keep personal data, then select the new folder. You do not need to run Hermes as administrator for ordinary monitoring. This unsigned preview may display a Windows publisher warning; verify the download's SHA-256 against the supplied checksum from your trusted release page.

On first launch, Hermes introduces itself and asks for an optional preferred name. Your name and chats remain in your Windows account. Use Local AI setup to get Ollama, check Qwen server status and explicitly download an appropriate model. Monitoring works before AI is configured. Model downloads can use several GB of storage and network traffic; larger models need more working memory.

Select **Finish** to open Hermes automatically. The completion checkbox lets you skip launching. Hermes starts with normal desktop permissions, including when setup needed administrator approval.

Setup also installs a read-only firmware temperature helper under Program Files / Hermes Hub Sensors. Windows starts it automatically; it samples approximately every 15 seconds while Hermes is open. Its task and protected cache are removed during uninstall. CPU/GPU temperatures use supported Lenovo firmware or an existing LibreHardwareMonitor/OpenHardwareMonitor WMI provider (Intel, AMD and NVIDIA hardware). Provider readings use the hottest reported CPU or GPU sensor. NVIDIA's driver utility is another GPU fallback. Hermes does not install a kernel sensor driver or start third-party sensor tools. Where no supported provider exists, temperatures show unavailable while the rest of the app continues normally; motherboard or ACPI-zone readings are never relabelled as CPU temperature.

## Privacy and control

No publisher analytics are sent by default. Optional install/uninstall reporting, if configured, sends only an event type, version, architecture and random event ID. It does not send your name, chats, file paths or hardware identifiers. Online update checks and donation explorer/profile links contact external services only when requested. Local app usage and music tracking have their own opt-in preferences.

Hermes proposes AI changes for review. It does not replace the Windows protection engines or guarantee detection of every threat. Smart RAM is optional and conservative; resident pages can refill and trimming is not a guaranteed performance improvement.

If Windows cannot return Defender status, Hermes shows protection as unavailable and keeps previous detection history. This is not an all-clear. Open Windows Security to check the protection provider; Hermes does not silently change Windows security settings or treat old readings as current.

Valid AI change proposals open an **Accept / Reject** review inside the current chat with the exact operation and target. If the chat is hidden or there is not enough space, a separate permission window appears. Accept applies that operation; after confirmed success, Hermes continues the same active conversation automatically. Reject leaves that operation unexecuted and stops its task. Closing the review keeps it pending; use **Review pending change** in the conversation menu to reopen it. Changing chats, cancelling, or locking the chat prevents automatic continuation.

Select **Deep** beside the message box to request local-model reasoning. Expand **Thinking…** within the reply to read the model-provided text. It follows new text until you scroll away or select text. The activity drawer separately records the task plan and tool activity. Generated reasoning can be wrong; it is not evidence or permission. The bounded display is temporary and is not saved in chat checkpoints.

When Hermes needs an answer, a question card appears above the message box. Choose an option or type an answer to continue that exact task. While waiting, Hermes stops generating. Answering a question does not approve changes; those still require their own review.

## Longer AI tasks

Hermes plans tool work before inspection or change proposals, with verification and stop conditions. It estimates the complete request size, including tool definitions and space for the reply, and refreshes context from a compact evidence checkpoint when needed. Normal modes keep a 4,096-token window; Deep uses 8,192. This supports multiple task segments, not unlimited memory or guaranteed completion.

In the conversation menu, **View task checkpoint** shows the plan and recorded tool results. **Resume saved task** (or `/continue`) resumes interrupted or paused work. Changes still require exact approval in Actions; a saved plan never approves a change. If an image is needed on resume, attach it again. Oversized tasks may need Deep mode or smaller steps. Task checkpoints are encrypted for the current Windows account, stay local, and are retained for the 20 most recently updated conversations. They contain bounded evidence excerpts, not raw model reasoning.

## First launch

Hermes introduces itself and asks for an optional name. Continue to a short guide, then choose **Open dashboard**. **Set up local AI** is optional; the performance and security views work without downloading a model. Reporting stays off unless you select it. You can close the welcome and return to it on a later launch.

## Support JLabs

The Buy me a coffee panel has separate Solana, Ethereum-mainnet and Bitcoin addresses with locally generated QR codes and copy buttons. Tips are optional and do not unlock features. Send only the network's native coin, verify the full destination address, and review your wallet's network fee. No wallet connection or private key is requested. This is a direct crypto-tip panel, not an integration with the Buy Me a Coffee payment service.

## Updates and removal

Check for updates from Workspace or Settings. A configured release channel verifies a pinned signing key, version, architecture and installer checksum before offering installation. You choose whether to install. Unconfigured channels show a clear unavailable state.

This package pins JLabs' release verification key for **JoshsLabsInc/Hermes-Hub**. Updates become available when a newer installer and its matching `hermes-release.json` are published as assets on that repository's GitHub Release.

Remove Hermes from Windows Settings → Apps → Installed apps. The uninstaller requests a safe shutdown of Hermes before removing files. If a session cannot close, finish its pending work and choose Exit Hermes, then retry. Data is kept by default. You can separately choose to permanently remove this Windows account's chats, settings and recovery files. Other accounts and shared Ollama models are left alone. Restart Windows to finish deleting the running uninstaller.

If an older uninstaller already removed the application but left a blank error and a stale Windows entry, run the latest downloaded installer with `--uninstall`. It can finish cleanup of that registered installation without reinstalling Hermes or deleting your personal data. Missing manifests with unrecognized remaining files are preserved and require repair first.

## Release status

This is a local-test preview, not a certified production release. Independent security review, clean-machine compatibility/upgrade/removal testing, Authenticode signing and long-duration testing remain release gates. Do not publish it as universally compatible or error-free.

Author: JLabs · JLab's 2024™ · https://github.com/JoshsLabsInc

Source redistribution terms must be chosen by JLabs before public source publication. No open-source license for JLabs code is implied by this preview.


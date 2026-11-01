# Meilleur Commander · macOS Downloads

Official public, **binary-only** Meilleur Commander Client releases for macOS. Choose the package matching your CPU. **Current release: 2.2.1** (Apple Silicon and Intel).

| Your Mac | Current version | Download |
| --- | --- | --- |
| **Apple Silicon (M1, M2, M3, M4 and newer)** · `arm64` | **2.2.1** · GitHub **Latest** | [Download macOS 2.2.1 for Apple Silicon](https://github.com/Meilleur-Tech/Meilleur-Commander-macOS-Releases/releases/download/macos-client-v2.2.1/Meilleur-Commander-Client-macOS-arm64-2.2.1.zip) |
| **Intel Mac** · `x86_64` | **2.2.1** · independent Intel channel | [Download macOS 2.2.1 for Intel](https://github.com/Meilleur-Tech/Meilleur-Commander-macOS-Releases/releases/download/macos-client-x86_64-v2.2.1/Meilleur-Commander-Client-macOS-x86_64-2.2.1.zip) |

Both downloads are **ZIP archives containing the macOS DMG** and product identity. Download the correct ZIP, extract the DMG, open it, and install **Meilleur Commander Client.app** into Applications. The macOS GUI requires macOS 13 or later.

**Signing:** App binaries are *ad-hoc code-signed*, not Apple Developer ID signed or notarized. The **update manifest is independently RSA signed**. If macOS blocks the app, allow that specific app through System Settings as appropriate. Never disable Gatekeeper globally.

## What's new in 2.2.1

- Native AppKit client and bundled Core are both built from the exact 2.2.1 source commit. Signed Gateway release manifests and authenticated offline recovery are supported.
- **Companion and browser adapter remain bundled** for ARM64 and Intel and travel with the Client update; no customer runtime source checkout is required.
- Companion version, health, and explicit on/off controls are available. Browser-tab lifecycle includes the #1539/#1541 safety fixes.
- First-run Copy/Paste, Settings layout, native product recovery, and offline legal/about information improvements from the 2.2 line are included.

**Known limitation:** An existing 2.1.7 client was recovered to working 2.2.1 by downloading the signed DMG and using authenticated offline reconciliation. This does **not** prove a fully automatic one-click 2.1.7 to 2.2.1 update or rollback. The separate QA Gateway feed is not synchronized; see [#1561](https://github.com/Meilleur-Tech/Meilleur-Commander/issues/1561) and [#1564](https://github.com/Meilleur-Tech/Meilleur-Commander/issues/1564). Intel hardware acceptance remains assigned to Chris. These checks are not presented as passed.

## Public discovery vs. Gateway activation

GitHub has **only one Latest label** per repository, so **ARM64 is Latest**. Intel is published under the separately versioned `macos-client-x86_64-v2.2.1` tag. The two architecture channels must never overwrite one another.

The discovery catalogs are:

- [Apple Silicon signed release catalog](channels/stable.json) → `macos`.
- [Intel signed release catalog](channels/x86_64/stable.json) → `macos-x86_64`.

Catalogs contain a signed release manifest and package URL. **Public catalogs are discovery hints, not authorization to install.** Each Gateway independently checks manifest RSA signature, exact binary SHA256, source identity, architecture, bridge protocol and supported Gateway version. A Gateway administrator must explicitly activate a candidate, separately on QA and Prod. Publishing a GitHub Release never changes an active Gateway release, customer enrollment or recovery history.

## Required publisher checklist

Every new ARM64 or Intel release is only considered **complete** when all of the following pass:

1. Freeze an approved, fully tested source SHA; build the native Client, Core, Companion and browser adapter for each target architecture, validate and sign.
2. Before finalizing the immutable GitHub Release, prepare the complete metadata set (signed `manifest.json`, `artifact-source.json`, release metadata, hashes). **Immutable GitHub Releases cannot accept post-publication asset uploads.**
3. Publish the architecture-specific ZIP and immutable tag; keep ARM64 GitHub Latest, Intel a separate release lane.
4. Independently download the public ZIP and verify its SHA256 against the RSA-signed manifest.
5. Publish the verified architecture-specific catalog at `channels/stable.json` or `channels/x86_64/stable.json`; update this README's current version and download URLs.
6. Verify both catalogs and signed candidate **discovery in QA**, then explicitly activate the compatible candidate. **Before authorizing the Update button on an existing macOS QA client, prove ordinary system-trusted HTTPS succeeds** (no `curl -k`, no SSL bypass), and the old Client's normal `update --check` discovers the exact signed candidate. A private QA root merely present in a keychain is not necessarily trusted; obtain legitimate interactive macOS TLS trust authorization from the QA VM admin, or use a properly publicly trusted QA endpoint.
7. Perform the actual old-to-new GUI update and recovery smoke test, including preserved Companion disabled state and no unknown-tab closure. Activate on Prod only after QA acceptance.
8. Store release evidence and stop/fail closed whenever *any* preceding phase fails.

Future automation and test enforcement are tracked in **[Meilleur Commander #1556](https://github.com/Meilleur-Tech/Meilleur-Commander/issues/1556)**. This checklist must not be mistaken for automatic enforcement until the release pipeline implements it.

[Browse all releases](https://github.com/Meilleur-Tech/Meilleur-Commander-macOS-Releases/releases) · [Development repository](https://github.com/Meilleur-Tech/Meilleur-Commander) · [macOS multi-architecture update contract](https://github.com/Meilleur-Tech/Meilleur-Commander/issues/1177)

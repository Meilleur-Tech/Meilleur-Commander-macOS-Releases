# Meilleur Commander · macOS Downloads

Official, public **binary-only** Meilleur Commander Client releases for macOS.

## Current public release: 2.1.4

| Mac | Download | GitHub release | Architecture |
| --- | --- | --- | --- |
| **Apple Silicon** (M1, M2, M3, M4 and newer) | [**Download macOS 2.1.4 DMG**](https://github.com/Meilleur-Tech/Meilleur-Commander-macOS-Releases/releases/download/macos-client-v2.1.4/Meilleur-Commander-Client-macOS-arm64-2.1.4.dmg) | [**Latest**](https://github.com/Meilleur-Tech/Meilleur-Commander-macOS-Releases/releases/tag/macos-client-v2.1.4) | `arm64` |
| **Intel Mac** | [**Download macOS 2.1.4 DMG**](https://github.com/Meilleur-Tech/Meilleur-Commander-macOS-Releases/releases/download/macos-client-x86_64-v2.1.4/Meilleur-Commander-Client-macOS-x86_64-2.1.4.dmg) | [**Intel release**](https://github.com/Meilleur-Tech/Meilleur-Commander-macOS-Releases/releases/tag/macos-client-x86_64-v2.1.4) | `x86_64` |

**Requirements:** macOS 13 or later. Download the DMG matching your Mac's CPU, open it, and drag **Meilleur Commander Client.app** to Applications.

The macOS DMGs are **ad-hoc code-signed but not Apple Developer-ID-notarized**. Your Mac may require granting permission to launch the specific app in System Settings. Do **not** turn off Gatekeeper globally.

### What's included

Each immutable release contains a manual-install **DMG**, an RSA-signed Gateway-update **ZIP**, `manifest.json`, `artifact-source.json`, `release-metadata.json`, `SHA256-DMG.txt`, and `SHA256SUMS`.

Version **2.1.4** repairs the manual DMG over-install problem where the native app upgraded but the running Core remained at an older version. The previous Core can be recovered and enrollment/state data are preserved. Apple Silicon and Intel are independently packaged.

### Important distinction: public downloads vs. Gateway updates

GitHub marks the Apple Silicon release **Latest** because GitHub supports only one Latest release per repository. **Intel is also available** from the separate direct links above. The public Latest label is for finding manual downloads **only**. It is *not* update or install authorization.

Automated client updates still require the customer's assigned Gateway, an exact architecture-specific manifest, release RSA signature, matching SHA256, Source SHA, supported bridge protocol, and compatible Gateway version. Merely publishing a public release **does not activate** it on a Gateway or re-enroll any customer.

- [All macOS releases](https://github.com/Meilleur-Tech/Meilleur-Commander-macOS-Releases/releases)
- [Development project](https://github.com/Meilleur-Tech/Meilleur-Commander)
- [Offline DMG upgrade fix and QA](https://github.com/Meilleur-Tech/Meilleur-Commander/pull/1203)
- [Independent signed release architecture](https://github.com/Meilleur-Tech/Meilleur-Commander/issues/536)

The release manifest uses RSA authority `mc-client-caf94007b07dc90b`. Private release-signing keys, source checkout, customer data, and Gateway configuration are **not** published in this repository.

# Meilleur Commander: macOS Client Releases

Official **public, binary-only** macOS client distribution owned by [Meilleur-Tech](https://github.com/Meilleur-Tech).

- Immutable native macOS Release assets only. Source code, private RSA keys, customer data, provisioning tokens and Gateway configuration must not be published here.
- GitHub **Latest** is platform-specific in this repository, but is a **discovery hint** only and is never client install authority.
- The assigned Gateway verifies the exact RSA-signed release manifest, package SHA256, Source SHA, architecture, Bridge protocol and compatibility before offering a specific macOS update.
- `channels/stable.json` is initially **empty**, and must not be interpreted as a released or approved client.
- Existing macOS 2.1.0/2.1.1 artifacts in `pmeger/Meilleur-Commander-Releases` remain immutable, valid and the active update source until explicitly superseded by a newly signed/accepted macOS release. Do not change their tags, hashes, asset URLs or signatures.

Canonical development: [Meilleur-Tech/Meilleur-Commander](https://github.com/Meilleur-Tech/Meilleur-Commander) issue [#536](https://github.com/Meilleur-Tech/Meilleur-Commander/issues/536). Release manifest RSA authority `mc-client-caf94007b07dc90b` stays on the Owner signing host and never in public GitHub artifacts.

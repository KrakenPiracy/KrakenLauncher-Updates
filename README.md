# Kraken Launcher — Official Releases

**Kraken's first public version will be v0.1.** Earlier v0.9.x builds were internal development versions, not public releases. The owner decides when the next release occurs; the following update will be **v0.2**, with its own patch notes, only when requested.

## Downloading Kraken

When the first signed, Windows-tested release has been published, visit [GitHub Releases](https://github.com/KrakenPiracy/KrakenLauncher-Updates/releases) and download **KrakenLauncher.exe**. It is a standalone Windows application; users do not need Python.

**Publication status:** The v0.1 source release candidate exists, but the compiled Windows EXE and signed release manifest must be created and tested on Windows before a GitHub Release is published. An empty/unverified release is deliberately not published.

## How releases work

Each published normal release must contain two assets:

- `KrakenLauncher.exe` — standalone launcher for Windows
- `kraken-update.json` — an Ed25519-signed SHA-256 manifest

The first release tag is **`v0.1`**; a future release would be tagged `v0.2` only when explicitly approved. The updater prompts before downloading or installing.

### Publishing (release owner only)

On a trusted Windows 10/11 x64 build PC, extract the v0.1 source kit and read `V0_1_WINDOWS_RELEASE_CHECKLIST.md`. Run `setup_update_signing.bat` once to create your local private release key, then `build_exe.bat`. Test the EXE on two Windows PCs, then publish both assets on the [Releases page](https://github.com/KrakenPiracy/KrakenLauncher-Updates/releases/new).

**Never publish** private signing keys, Firebase service-account secrets, session tokens, password files, or user profile data.

### Security warning

Firebase account records are protected by Firestore rules, but public MQTT chat usernames and bans are **not server-authenticated** yet; modified clients can impersonate chat names or evade client-side moderation. A signed update is **not** Microsoft Authenticode publisher signing. These limitations need to be addressed before advertising the product as hardened against malicious users.

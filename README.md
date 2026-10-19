# Kraken Launcher — Official Windows Releases

This repository hosts compiled **Kraken Launcher Windows releases**. The launcher checks GitHub Releases for updates.

## For players

Download `KrakenLauncher.exe` from the [Releases page](https://github.com/KrakenPiracy/KrakenLauncher-Updates/releases) once the first release has been published. The first updater-enabled version must be installed manually; future versions can update inside Kraken.

## For release publishing

Every normal release must contain **exactly** these two update assets:

- `KrakenLauncher.exe` — Windows self-contained launcher
- `kraken-update.json` — signed manifest

Use a version tag matching the signed manifest, e.g. `v0.9.9.6`. Generate the signing key **only on your trusted Windows build PC** via `setup_update_signing.bat` in the launcher source. The key is stored outside the repo. Subsequent builds use `build_exe.bat`, which signs the release manifest automatically.

**Do not upload** the private signing key or its passphrase, account tokens, Firebase session files, users' data, or untested binaries.

See `AUTOMATIC_UPDATES_SETUP.md` inside the Kraken Launcher v0.9.9.6 source package for full instructions. A signed update is not a substitute for testing on Windows or Windows publisher code signing.

# Kraken Launcher v0.2 — Draft Patch Notes

**Status: release candidate, not published.** The v0.2 Windows EXE and signed manifest still require building and testing with the original v0.1 signing key.

## Changes
- Firebase-account-bound Ed25519 signatures for Public Chat messages and Discord-style profile responses; badges for legitimate verified owner/staff accounts only after the receiver verifies the signed packet against Firestore.
- Verified Owner/Staff labels can appear on authenticated profile popups and verified messages.
- Text chat, photos, and system notices now expire from the launcher UI after 60 seconds.
- Bounded failed identity lookups to reduce Firebase free-tier usage.
- Retains games, downloads, torrent engine, GIF profiles, and signed opt-in updates.

## Before publishing
1. Deploy the **updated `firestore.rules`** from the v0.2 source package. It adds Firestore `chat_keys/{uid}` owner-only writes. Do not delete existing `users`, `handles` or `staff` records.
2. Build the standalone Windows EXE **using the same encrypted Ed25519 release-signing key that signed v0.1**. Never generate a fresh release-signing key for the update.
3. Test between two signed-in v0.2 machines; check GIFs, verified popups, 60-second expiry, and normal launcher features.
4. On a test PC with the signed v0.1 EXE, confirm GitHub's v0.2 signed manifest and EXE update correctly, replace the old EXE and restart while preserving saved data.

**Caveats:** MQTT permits legacy/unverified nicknames and client-side moderation is not server-enforced; chat is public and 60-second UI expiry is not guaranteed deletion. This is not a promise of complete security.

Release tag (when ready): `v0.2`.
Assets (when ready): `KrakenLauncher.exe` and `kraken-update.json`.

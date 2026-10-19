# Kraken Launcher v0.1 — First Public Release (draft notes)

**Status: release candidate awaiting Windows EXE build, signing and multi-PC tests. This note is not a published release.**

### Game Library
- Add and launch installed games; custom covers, artwork and game details
- Favorite/sort games, recently played, playtime and game-size tracking

### Downloads and Discovery
- HTTP(S) downloads with queue control, pause/resume and progress
- Native BitTorrent/magnet support bundled in the release EXE
- Game discovery using user-provided catalog JSON sources

### Community
- Public chat with emoji, temporary photos, and online presence
- Firebase accounts and reserved usernames, cloud bios/favorites, Steam-style profiles
- GIF avatars/banners, compact chat profile cards and Firestore-backed owner/staff profile roles

### Stability and Release Protection
- Opt-in update prompts using signed GitHub release manifests and SHA-256 verification
- Bounded public MQTT packet/event queues, incomplete image transfers and image dimensions
- Untrusted chat packets cannot self-award official verified badges
- Local game library and downloads remain on each user's PC

### Important security note
Firebase protects account records, **not** public MQTT sender identity. Modified clients can imitate chat names or bypass local chat moderation. Public-room traffic is not private. A Windows EXE signing key protects in-app update packages; it is not a Microsoft Authenticode publisher certificate.

The first published version will be **v0.1**. Future **v0.2** notes will be created only when the owner requests that update.

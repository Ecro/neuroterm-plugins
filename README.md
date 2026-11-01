# NeuroTerm plugin channel

Signed releases of NeuroTerm's first-party plugin packages: the Claude Code and Codex agent adapters, NeuroFlash and
later packages. This repository holds releases only. The sources live in the NeuroTerm repository.

- The newest release serves `index.json` and `index.json.minisig`, an index signed with the channel key.
- The app verifies the index with the public key built into it, then checks every package against the index's
  SHA-256 before installing.
- An index that is expired, replayed (`seq` not above the last one accepted) or badly signed is refused. The app then
  keeps the packages it has.
- Packages download from `releases/download/r<seq>/`. A published `id@version` never changes. A bad one is revoked in
  a later index.

Releases are made by NeuroTerm's release workflow only. Nothing here is edited by hand.

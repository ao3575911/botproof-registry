# Changelog

## [0.3.1] - 2026-10-10

### Added
- Dependabot for GitHub Actions.
- `tag` workflow: tags are created and GPG-signed in CI (key C35E1B10…1BCBA754, shared with the CLI releases). v0.3.1 is the first signed registry tag; v0.3.0 is unsigned.

### Security
- Guard on `platforms.json`, the trusted-platform list:
  - CODEOWNERS (`/platforms.json`, `/.github/`) plus a ruleset requiring code-owner review.
  - A new `platforms` CI check flags every origin a PR adds. It stays red until a maintainer adds the `platforms-reviewed` label.

## [0.3.0] - 2026-10-09

### Changed
- CI and Pages are pinned to botproof CLI v0.3.1 (commit 8b76983) and SHA-pinned actions, no longer `main`.
- PR checks enforce append-only files, first-come ownership, PR-author signatures and increasing `seq`.
- The Pages build is attested, and `api/index.json` records the registry commit and a hash for every doc.
- Demo bot re-signed in the v0.3 format (bound challenge, `seq` 1).

### Added
- `platforms.json`: the allowlist for Web Bot Auth evidence (ChatGPT agent).
- CC0-1.0 LICENSE and SECURITY.md.

## [0.1.0] - 2026-10-09

### Added
- Registry layout, PR verifier and nightly Pages build (JSON API and SVG badges).

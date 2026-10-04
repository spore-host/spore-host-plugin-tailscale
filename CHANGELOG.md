# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- **The changelog policy is now enforced in CI rather than by habit.** A PR that changes
  non-test Go source without touching `CHANGELOG.md` fails, and `changelog_test.go`
  checks `[Unreleased]` for duplicate group headings, unknown group names, entries
  outside a group, and releases missing a compare link.
  This policy has been suite-wide for a while but only `spawn` enforced it — where it
  immediately earned its keep, catching a duplicate `### Fixed` **four times in one
  session** and a PR that had merged with no entry at all (found only at the next
  release, against an empty `[Unreleased]`, with the entries reconstructed from the diff
  at tag time).
  `scripts/changelog-consolidate.py` (and `make changelog-fix` where there's a Makefile)
  merges duplicate groups mechanically, because two PRs each adding their own
  `### Fixed` is a routine conflict that merges cleanly for git and badly for the format
  — not a mistake worth hand-fixing each time.

### Changed

- Module path and all repo links moved from `github.com/scttfrdmn/...` to
  `github.com/spore-host/...` to match the repo's home in the spore-host org.

## [0.1.0] - 2026-03-22

### Added
- `tailscale/plugin.yaml`: install Tailscale and join a tailnet as an ephemeral node
- `--hostname` set to `{{ instance.name }}` (the spore's EC2 Name tag)
- `accept_dns` config option (default `false`) to control tailnet DNS on the instance
- `tailscale logout` in stop steps for clean ephemeral-node deregistration
- `tailscale status` health check (1-minute interval)

[Unreleased]: https://github.com/spore-host/spore-host-plugin-tailscale/compare/v0.1.0...HEAD
[0.1.0]: https://github.com/spore-host/spore-host-plugin-tailscale/releases/tag/v0.1.0

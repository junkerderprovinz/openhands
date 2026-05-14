# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.2] — 2026-05-14

### Changed

- Forum support thread linked in `<Support>`: <https://forums.unraid.net/topic/198811-support-junkerderprovinz-openhands/>.
  Required by Unraid Community Applications.

## [1.0.1] — 2026-05-14

### Added

- `ca_profile.xml` at the repo root — required by Community Applications
  for new repository submissions. Contains the maintainer profile, icon
  and webpage link.
- CI now lints `ca_profile.xml` and asserts `<Profile>`, `<Icon>` and
  `<WebPage>` are present and non-empty.

### Changed

- README release badge: `display_name=tag`, `sort=semver`,
  `cacheSeconds=300` so it refreshes within 5 minutes of a new tag.
- Consolidated bot updates onto Renovate; removed Dependabot config to
  avoid duplicate PRs.

## [1.0.0] — 2026-05-14

### Added

- Initial Unraid Community Applications template for
  [OpenHands](https://github.com/OpenHands/OpenHands) (image
  `docker.openhands.dev/openhands/openhands:1.7`).
- Pre-configured for **local Ollama** with `qwen2.5-coder:14b`.
- Docker socket mount and `--add-host host.docker.internal:host-gateway`
  pre-wired for sandbox-container spawning.
- Persistent paths for `/.openhands` (config) and `/workspace`.
- Variables: `SANDBOX_VOLUMES`, `LLM_API_KEY`, `LLM_MODEL`,
  `LLM_EMBEDDING_MODEL`.
- `<Branch>` selector exposing `1.7` (stable, default) and `latest`.
- Repo metadata: MIT licence, README with badges + buy-me-a-coffee, banner
  + container icon, `SECURITY.md`, issue & PR templates, Renovate config.
- GitHub Actions CI: XML lint, Unraid CA sanity check, markdownlint,
  yamllint, link check (lychee).

[Unreleased]: https://github.com/junkerderprovinz/openhands/compare/v1.0.3...HEAD
[1.0.3]: https://github.com/junkerderprovinz/openhands/compare/v1.0.2...v1.0.3
[1.0.2]: https://github.com/junkerderprovinz/openhands/compare/v1.0.1...v1.0.2
[1.0.1]: https://github.com/junkerderprovinz/openhands/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/junkerderprovinz/openhands/releases/tag/v1.0.0

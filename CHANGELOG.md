# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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

[Unreleased]: https://github.com/junkerderprovinz/unraid-ca-openhands/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/junkerderprovinz/unraid-ca-openhands/releases/tag/v1.0.0

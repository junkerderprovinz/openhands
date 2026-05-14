# Security Policy

## Scope

This repository contains an **Unraid Community Applications template** for
the upstream [OpenHands](https://github.com/OpenHands/OpenHands) container.
It does **not** contain the OpenHands source code or container image.

- Vulnerabilities in **the template itself** (e.g. unsafe defaults,
  permission-elevating misconfigurations) — please report here.
- Vulnerabilities in **OpenHands** (the actual agent, WebUI, sandbox
  runtime) — please report upstream at
  <https://github.com/OpenHands/OpenHands/security>.

## Reporting

Open a [private security advisory](https://github.com/junkerderprovinz/openhands/security/advisories/new)
on GitHub. Do **not** open a public issue for security problems.

Include:

- The affected template version / commit
- A description of the issue and its impact
- A minimal reproducer if you have one

You'll get an acknowledgement within a few days. Realistic fixes
typically ship within 1–2 weeks as a patch release.

## Known risk surface

By design, this template:

- **Mounts `/var/run/docker.sock` read-write** so OpenHands can spawn
  per-task sandbox containers. Anyone with WebUI access effectively has
  root on the Unraid host's Docker daemon. **Do not expose port 3000 to
  the public internet without authentication in front of it** (reverse
  proxy + Authelia / Authentik / Cloudflare Access).
- **Mounts a user share** (`/mnt/user/ai-workspace` by default) as
  read-write. The agent will read and write files there. Don't point it
  at irreplaceable data.
- **Sends prompts + file contents to whatever LLM you configure.** If
  that's a hosted provider (OpenAI, Anthropic, OpenRouter, etc.), your
  source code leaves the box. Use Ollama if that's a concern.

These are documented trade-offs, not bugs.

## Supported versions

| Template version | Supported? |
|---|---|
| `main` (latest commit) | ✅ |
| Tagged releases `≥ v1.0.0` | ✅ (security backports best-effort) |
| Pre-1.0 / forks | ❌ |

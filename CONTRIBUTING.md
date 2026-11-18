# Contributing

- **Branches:** one per feature, e.g. `feat/login`, `fix/queue-crash`. Open a PR against `main`.
- **Commits:** [Conventional Commits](https://www.conventionalcommits.org/) - `feat:`, `fix:`, `docs:`, `chore:`, `ci:`, `refactor:`. Keep them small.
- **PRs:** reference the issue (`Closes #n`), keep CI green (build + lint), update `CHANGELOG.md`.
- **Secrets:** never commit developer tokens, `.p8` keys, keystores or Apple's SDK files.
- **Scope:** official Apple Music account playback only. PRs that bypass DRM or enable downloading are rejected.

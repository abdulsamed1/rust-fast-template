# Rust Fast Dev Template

Hybrid template: GitHub template + Devcontainer + Cargo config to use lld-19 and clang-19, plus cargo-watch and basic Makefile.

## Quick start

1. Clone or unpack the template into a project folder.
2. If using VSCode, open the folder and accept Dev Container prompt to build the container.
3. Inside the container or on host (if you installed clang/lld), run:

```bash
make dev
```

This runs `cargo watch -x check -x test -x run`.

## Notes
- The `.cargo/config.toml` forces clang-19 + lld-19. Adjust if you install different versions.
- The Dockerfile uses `rust:1.81-bullseye` base and installs clang-19/lld-19. You can choose another Rust tag if desired.
- Fail fast: keep clippy with -D warnings to avoid technical debt. Use #[allow(...)] only where justified.

- Format locally: enable format on save in developers’ editors; CI failing on format is noisy if not adopted.

- Security cadence: running cargo audit on every push is good; you can also run a daily/weekly scheduled job to catch new advisories for inactive repos.

- Coverage: treat coverage as guidance, not a strict gate. Consider thresholds and exemptions for generated code.

- Parallelize: for large projects split tests or build matrix to parallel jobs (e.g., different features or toolchains).

- Secrets: store tokens in GitHub Secrets; never embed them in workflow YAML.

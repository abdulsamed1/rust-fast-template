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

# Contributing to wodex (OSS)

Thanks for your interest! wodex is a small Tauri (Rust + web) desktop app that **configures
and augments** OpenAI Codex Desktop. It does not proxy traffic. See
[docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md) for the lay of the land.

## Dev setup

Prereqs: a recent **Rust** toolchain, **Bun** (or Node), and **OpenAI Codex Desktop**
installed (non-MSIX standalone build recommended on Windows).

```bash
bun install
bun run tauri dev      # run the app
bun run build          # build the web frontend
cargo check  --manifest-path src-tauri/Cargo.toml
```

## Tests

Core tests run in CI on every PR — please keep them green and add tests for new logic.

```bash
bun run test                                   # frontend (Vitest)
cargo test --manifest-path src-tauri/Cargo.toml  # Rust
```

## Where things live

- `src/` — web frontend (React + Vite).
- `src-tauri/src/lib.rs` — config provisioner, login-wall stub, augmentation keeper,
  Codex locate (`codex_cli_path`), plugin/MCP management.
- `src-tauri/src/bridge.rs` — LAN phone bridge (CDP injection) + pairing.
- `tweaks/` — Codex renderer tweaks.

## Conventions

- **Branch + PR** — never push to `main` (it auto-deploys). Branch `feat/…` or `fix/…`,
  open a PR against `main`. Keep PRs focused; make builds/tests pass.
- **Cross-platform** — resolve Codex via `codex_cli_path()`; never hardcode platform paths.
  Gate platform-specific code with `#[cfg(target_os = …)]`.
- **Keeper-safe config** — anything written into `~/.codex/config.toml` must go through the
  managed-block helpers so user config is preserved across re-applies.
- **No secrets** in code or commits.

## Zero telemetry — a hard rule

The OSS edition collects **no telemetry** (see PRIVACY). PRs that add analytics, tracking,
crash reporting, or any "phone home" will not be merged. The only network calls are to the
user's configured provider (BYOK) and the user's own LAN phone.

## License & sign-off

By contributing you agree your contribution is licensed under the project's **MIT** license.
Keep commits signed-off where possible (`git commit -s`).

## Reporting issues

Open a GitHub issue with: OS + version, Codex version, steps to reproduce, and logs if any.
Security-sensitive reports: email security@wodex.ai instead of a public issue.

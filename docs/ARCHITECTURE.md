# Architecture

wodex is a small Tauri (Rust + web) desktop app. It does NOT proxy traffic — it
**configures and augments** Codex Desktop, which talks directly to your provider.

## Core (shared with the account edition)
- **Config provisioner** — writes `~/.codex/config.toml` (provider, model catalog,
  plugin enables, MCP, project trust) in a managed block that preserves your own config.
- **Login-wall bypass** — writes a stub `~/.codex/auth.json` (API-key mode).
- **Augmentation keeper** — a background loop re-applies the above so it survives Codex
  restarts/auto-updates.
- **Phone bridge** — a LAN HTTP server + PWA that injects prompts into Codex via the
  Chrome DevTools Protocol (`.ProseMirror` insertText + Enter).

## OSS vs account
The OSS edition uses **BYOK** (`apply_byok_config`: your base_url + key + models).
The account edition swaps that one entry point for `apply_codex_config` (pull per-user
gateway creds from admin.wodex.ai). Everything else — the augmentations — is identical.

> This repo is being populated from the wodex client. The BYOK setup UI and the
> packaged builds land here incrementally.

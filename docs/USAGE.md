# wodex — User Guide (OSS / BYOK edition)

wodex turns a stock **OpenAI Codex Desktop** install into a power tool: your own models
(BYOK), all plugins unlocked, no ChatGPT login wall, phone remote, and config that survives
Codex updates. Single machine, your key, zero telemetry.

## Install

1. Install **OpenAI Codex Desktop** (on Windows, prefer the standalone non-MSIX build —
   the Store/MSIX build can't be driven for phone-remote).
2. Install **wodex** (Homebrew cask on macOS / setup.exe on Windows — see Releases).
3. Launch wodex.

## First run — BYOK setup

In the app, enter your provider details:

- **Base URL** — any OpenAI-compatible endpoint (OpenAI, Anthropic-compatible gateways,
  OpenRouter, Ollama, …), e.g. `https://api.openai.com/v1`.
- **API key** — your provider key.
- **Models** — the model slugs you want available.

wodex writes these into `~/.codex/config.toml` (in a managed block that preserves your own
config), writes a stub `~/.codex/auth.json` so Codex skips the login wall, builds the model
catalog, and unlocks the official plugins. Restart Codex if it was running.

## Features

- **Plugins / skills** — all official Codex plugins are enabled. Manage **MCP servers**
  (add/remove) from the app.
- **Phone remote (LAN)** — start the phone bridge, open the shown URL on your phone (same
  Wi-Fi), enter the 6-digit pairing code, and drive Codex from your phone.
- **Memory inspector** — browse what Codex has remembered locally (search / sort).
- **Activity history** — a local log of your Codex sessions (fully local).
- **Login mode** — switch between BYOK (skip login) and native ChatGPT-account login.

## Updates

wodex's **augmentation keeper** re-applies your config after Codex restarts/auto-updates, so
your setup doesn't drift. Update Codex normally; wodex keeps itself in place.

## Uninstall / cleanup

Use **"Clean wodex's changes to Codex"** in the app before uninstalling — it removes the
managed config block, the auth stub, the model catalog, and caches (leaving your own config
intact).

## Troubleshooting

- **"Codex not found"** — ensure Codex Desktop is installed; on Windows prefer the standalone
  (non-MSIX) build.
- **Phone remote shows "Codex CDP not connected"** — phone-remote needs a debuggable Codex;
  on Windows MSIX this is unavailable — install the standalone Codex.
- **Models don't show in Codex** — restart Codex after BYOK setup; check the Base URL/key.
- **Config seems reverted** — that's the keeper re-applying the managed block; edit config
  *outside* the managed markers, or change settings in the app.

## Privacy

Zero telemetry. wodex never phones home — see PRIVACY (OSS) for the full commitment.

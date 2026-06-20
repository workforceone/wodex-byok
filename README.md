# wodex

**Turn a stock Codex Desktop install into a power tool — your models, your machine, zero config.**

wodex configures and augments [OpenAI Codex Desktop](https://openai.com/codex) so it works
great with **any** OpenAI-compatible provider (BYOK), unlocks all the official plugins,
skips the ChatGPT login wall, and keeps itself working across Codex updates.

> This is the **open-source BYOK edition** (free, single machine, bring your own key).
> For teams — managed models (no key), org management, fleet rollout, usage & billing —
> see **[wodex.ai](https://wodex.ai)**.

## What it does (OSS)

- **BYOK** — point Codex at your own provider (OpenAI, Anthropic-compatible, OpenRouter, Ollama, …)
- **Unlock all 177 official Codex plugins** — Codex downloads them but only enables ~9 under a
  custom provider; wodex enables them all (asana, slack, github, linear, notion, …)
- **Skip the ChatGPT login wall** — API-key mode, no ChatGPT account needed
- **Augmentation keeper** — re-applies config across Codex restarts/auto-updates (drift-proof)
- **Phone remote** — drive Codex from your phone on your LAN
- **Memory inspector** — see what Codex remembers locally
- **Pre-configured** — Playwright MCP, project trust, sensible defaults

## Open-core

| | OSS (this repo) | wodex.ai (account) |
|---|---|---|
| Models | BYOK (your key) | Managed gateway (no key) + credits |
| Setup | configure your provider | zero-config, auto-provisioned |
| Fleet | single machine | team management, fleet rollout, enforcement |
| Phone remote | LAN | cloud relay (anywhere) |

The moat is the control plane (gateway, billing, team) — so the client is free and open.

## License

MIT — see [LICENSE](./LICENSE).

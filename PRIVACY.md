# Privacy & Telemetry — wodex (OSS edition)

**Commitment: the open-source wodex client collects zero telemetry.**

This is a hard requirement of the OSS edition, codified here as a public promise.

## What we do NOT do

- ❌ No analytics or product telemetry
- ❌ No tracking / fingerprinting / advertising IDs
- ❌ No crash or error reporting to us
- ❌ No "usage beacons", heartbeats, or auto check-ins
- ❌ No phoning home of any kind — there is no telemetry endpoint in the code

## The only network traffic the OSS client makes

1. **Your configured provider (BYOK)** — the model API calls *you* initiate go to the
   base URL + key *you* set. wodex never sees or proxies them.
2. **Your LAN phone bridge** — when you start the phone-remote bridge, your phone
   talks to the wodex process over your local network (pairing-code protected).
   Nothing in this path leaves your LAN.

All configuration (Codex `config.toml`, model catalog, auth stub) is written to local
files on your machine only.

## Community ranking

Plugin/skill ranking shown on **wodex.ai** is computed **only** from **opted-in account
users** of the hosted (paid) editions. OSS installs contribute **no** data to it — by
construction, we receive nothing from OSS clients, so there is nothing to rank from them.

## Hosted editions

The account/team editions on [wodex.ai](https://wodex.ai) do send usage telemetry to the
gateway (for billing, quota, and team audit) — that is inherent to a managed/metered
service and is disclosed in the wodex.ai privacy policy. **This OSS repo is not that.**

## Verify it yourself

The client is MIT-licensed and open. Audit the source: there is no analytics SDK, no
telemetry HTTP client, and no telemetry endpoint. Issues/PRs welcome if you find any
network call not covered above.

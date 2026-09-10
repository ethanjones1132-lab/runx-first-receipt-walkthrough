# Runx first sealed receipt — practical walkthrough (2026-09-10)

This is an original, hands-on walkthrough for [runx](https://runx.ai) — the governed runtime for agent skills — showing how to seal a local receipt with the public `hello-world` example in under five minutes.

Project links:
- Site: https://runx.ai
- Source: https://github.com/runxhq/runx
- CLI package: `@runxhq/cli`

Audience: developers and agent operators who want a concrete first success before reading deeper docs.

## Why this matters

Runx sits **under** agent frameworks. It admits each skill act under explicit authority, keeps credentials out of prompt material, and seals a verifiable receipt (`runx.skill_run.v1` / `runx.receipt.v1`). That receipt trail is what makes agent work auditable instead of ambient trust.

## Prerequisites

- Node.js + npm
- Network to fetch `@runxhq/cli` and clone the repo
- macOS/Linux shell (verified here on macOS)

## Steps that were actually run (UTC 2026-09-10)

```bash
npm view @runxhq/cli version
# -> 0.9.0

git clone --depth 1 https://github.com/runxhq/runx.git
cd runx

npx --yes @runxhq/cli@latest skill ./examples/hello-world \
  -i message="hello from ethanjones1132-lab bounty walkthrough" \
  --json
```

## Observed sealed result (abridged)

```json
{
  "outcome": "completed",
  "schema": "runx.skill_run.v1",
  "skill_name": "hello-world",
  "status": "sealed",
  "runner": "default",
  "result": {
    "message": "hello from ethanjones1132-lab bounty walkthrough"
  },
  "receipt_id": "sha256:6deb75e56a1c79f526ef32ad6ab23dfd0240f1067daa66e1d45e2bef53173802",
  "run_id": "run_default_e39bfe44ebc6fa3e"
}
```

Full machine-captured JSON from this session is in [`hello-world-sealed-run.json`](./hello-world-sealed-run.json).

## What to inspect next

1. `examples/hello-world/SKILL.md` and `X.yaml` — the portable skill contract.
2. [docs/getting-started.md](https://github.com/runxhq/runx/blob/main/docs/getting-started.md)
3. Catalog: https://runx.ai/x
4. Agent-readable twin: https://runx.ai/SKILL.md

## Notes / limits

- This walkthrough seals a **local** receipt for the checked-in example; it does not claim a hosted registry publish.
- No secrets were required for `hello-world`.
- CLI version pinned by the npx resolution on 2026-09-10: `@runxhq/cli@0.9.0`.

Maintainer-friendly signal: if the quickstart path regresses, compare against this sealed payload shape and the README quickstart in https://github.com/runxhq/runx.

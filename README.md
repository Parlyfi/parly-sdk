# Parly SDK

Production TypeScript SDK for Parly private stablecoin payments on Tempo.

## What this package is

This package contains the `@parly/sdk` source and the small vendored helpers needed to build it from
source. It is for developers and agent teams that want direct SDK integration.

## What you can build

- Recover private notes for Tempo USDC.e and USDT0 asset lanes.
- Send from a Parly private balance with `sendShieldedPayment()`.
- Use MPP session helpers for bounded agent payments.
- Preflight MPP session payments, including counterparty and spend-limit checks, before proof
  generation or transaction submission.
- Query indexed leaves, envelopes, deposits, withdrawals, and recovery cursors.

## Quick start

```bash
pnpm install
pnpm smoke:standalone
```

Configure server-side execution with:

- `AGENT_PRIVATE_KEY`
- `TEMPO_RPC_URL`
- `TEMPO_CHAIN_ID=4217`
- `SETTLEMENT_DOMAIN_ID=4217`
- `PONDER_GRAPHQL_URL`
- `PARLY_SDK_ASSETS_PATH`

Never expose agent keys, provider keys, or proof assets through browser public environment variables.

## Package layout

```text
packages/sdk
packages/sdk/src/internal
```

## Release and compatibility

See [COMPATIBILITY.md](./COMPATIBILITY.md) and [versions.json](./versions.json).

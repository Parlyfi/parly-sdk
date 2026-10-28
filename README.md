# Parly SDK

Production TypeScript SDK for Parly private stablecoin payments on Tempo.

Parly supports USDC, USDT and OpenUSD (OUSD). Token availability varies by network.
This package's security release does not add V4 recovery or OpenUSD execution.
Its supported execution lanes remain USDC.e and USDT0; see [COMPATIBILITY.md](./COMPATIBILITY.md).

## What this package is

This package contains the `@parly/sdk` source and the small vendored helpers needed to build it from
source. It is for developers and agent teams that want direct SDK integration.

## What you can build

- Read six-decimal PoolV3 base-unit totals and note count without exposing note identifiers.
- Prepare a deterministic PoolV3 private send and see when consolidation is required.
- Recover historical PoolV2 notes for compatible history and recovery workflows.
- Send from a Parly private balance with `sendShieldedPayment()`.
- Send up to 10 same-chain payout lanes with `sendShieldedBatchPayment()`.
- Use MPP session helpers for bounded agent payments.
- Preflight MPP session payments, including counterparty and spend-limit checks, before proof
  generation or transaction submission.
- Query indexed leaves, envelopes, deposits, withdrawals, and recovery cursors.

PoolV3 balance and preparation responses never include note secrets, commitments, nullifiers,
Merkle paths, or recovery keys. PoolV2 history is read-only and is not mixed into PoolV3 selection.

This package targets its versioned PoolV3 interface, not the web app's current V4 receiving routes.
A PoolV3 route must be fully configured for its two supported assets; incomplete routes stop before
authorization rather than falling back to another pool. Historical PoolV2 records remain available
for read-only recovery and review. Do not infer current-route compatibility from general platform support.

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

Cross-chain deposits use Parly payment routes. Cross-chain private sends become available through
the SDK when a supported public payout route is active.

## Package layout

```text
packages/sdk
packages/sdk/src/internal
```

## Release and compatibility

See [COMPATIBILITY.md](./COMPATIBILITY.md) and [versions.json](./versions.json).

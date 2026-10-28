# Parly SDK

Build private stablecoin payments with TypeScript. Recover V4 balances, prepare
single or batch payments, and use V7 routes for cross-chain payouts.

Tempo assets are USDC.e, USDT0 and OpenUSD (OUSD). Cross-chain asset availability
follows the active route configuration.

## What this package is

This package contains the `@parly/sdk` source and the small vendored helpers needed to build it from
source. It is for developers and agent teams that want direct SDK integration.

## What you can build

- Recover a private balance from complete, verified V4 history.
- Prepare a payment with note selection and a fee breakdown.
- Send to one recipient or up to 10 recipients in a same-chain batch.
- Quote and authorize V7 cross-chain payouts, track delivery and recover eligible refunds.
- Build integrations with Privacy Links, payment status, receipts and Verify APIs.

Use `CurrentParlySDK` from `@parly/sdk/current` for V4/V7 integrations. It uses
explicit deployment and proof pins, per-asset configuration and the existing wallet
recovery derivation. Public balance and preparation summaries omit note secrets.

The versioned `ParlySDK` interface remains available for existing integrations.
See [COMPATIBILITY.md](./COMPATIBILITY.md) for the distinction.

## Quick start

```bash
pnpm install
pnpm smoke:standalone
```

Configure the current client with its execution wallet, Tempo RPC, verified V4
profile and deployment blocks, history endpoint, pinned proof assets and V7 route
settings. Retain pending execution records so interrupted requests can be checked
before another payment is submitted. Keep signing and provider credentials in
server-side secret settings.

Use one active writer per execution wallet. Applications sharing a wallet across
processes must coordinate execution through a process-shared lock. Agent Selfhost
MCP includes this coordination for its HTTP requests.

## Proof assets

After building the package, `pnpm --filter @parly/sdk run sync:proof-assets`
verifies the current Spend60 files in `packages/sdk/assets`.
Use `--source <verified-directory>` to copy an existing set, or explicitly pass
`--download` to fetch the pinned files from Parly. Set `proofAssetsBasePath` to
that assets directory. Every file is checked against its circuit hash before use.

## Package layout

```text
packages/sdk
packages/sdk/src/internal
```

## Release and compatibility

See [COMPATIBILITY.md](./COMPATIBILITY.md) and [versions.json](./versions.json).

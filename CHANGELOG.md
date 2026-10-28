# Changelog

## 16.9.10-sdk.0

- Allowlist launch-context output; never return signer keys or private endpoint configuration.
- Vendor internal subpath imports and run launch-context security checks in standalone CI.

## 16.9.9-sdk.0

- publishes the Phase 3 Tempo SDK surface for private stablecoin payments
- supports USDC.e and USDT0 asset lanes
- adds a bounded 10-lane same-chain batch send wrapper
- adds counterparty-locked MPP session creation, preflight, and settlement helpers
- adds redacted PoolV3 total-balance and deterministic private-send preparation
- preserves PoolV2 history as an explicit read-only compatibility path
- includes publish-ready package metadata for `@parly/sdk`

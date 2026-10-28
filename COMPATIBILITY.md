# Compatibility

- `@parly/sdk@16.9.10` retains the core `16.9.9` protocol interface
- compatible with Agent Selfhost MCP `16.9.10-mcp.0`, not the new Hosted MCP
- Current API: `CurrentParlySDK` from `@parly/sdk/current`, for V4 recovery and Send plus V7 cross-chain payouts
- V4 proof model: up to four inputs and ten padded payment outputs
- settlement domain: Tempo `4217`
- Current Tempo assets: USDC.e (`assetId: 1`), USDT0 (`assetId: 2`) and OpenUSD (`assetId: 3`)
- MPP retains its versioned PoolV2 interface for assets 1 and 2, with counterparty and spend-limit checks
- batch send supports 1 to 10 same-chain payout lanes
- The versioned `ParlySDK` API retains its existing PoolV2/PoolV3 recovery and execution interface
- Public balance and preparation summaries omit note and recovery internals

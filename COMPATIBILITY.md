# Compatibility

- `@parly/sdk@16.9.10` retains the core `16.9.9` protocol interface
- compatible with Agent Selfhost MCP `16.9.10-mcp.0`, not the new Hosted MCP
- This security patch does not add V4 wallet recovery or OpenUSD execution support.
- proof model: joinsplit 10-output padded batch
- settlement domain: Tempo `4217`
- asset lanes: USDC.e (`assetId: 1`) and USDT0 (`assetId: 2`)
- MPP sessions are counterparty-locked and spend-limit checked before settlement
- batch send supports 1 to 10 same-chain payout lanes
- PoolV3 preparation uses deterministic selection across up to four notes
- PoolV2 history remains available in explicit read-only compatibility mode
- public PoolV3 summaries omit note and recovery internals
